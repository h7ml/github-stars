---
project: exile
stars: 154
description: Alternative to ports for running external programs. It provides back-pressure, non-blocking io, and solves port related issues
url: https://github.com/akash-akya/exile
---

Exile
=====

Exile is an alternative to ports for running external programs. It let you stream input and output to external program with back-pressure, non-blocking IO. Also, it fixes other port related issues such as selectively closing stdin.

### Port IO Issue

With Port if you run external program which generates lot of output to stdout. Something like streaming video using `ffmpeg` to serve a web request. If you try this with port then quickly going to run out of memory. Because port IO is not not demand driven. It consumes output from stdout as soon as it is available and `send` it to process mailbox. And as you know beam process mailbox is unbounded, so output sits there waiting to be `receive`d.

#### Lets take an example.

Memory consumption with Port

Port.open({:spawn\_executable, "/bin/cat"}, \[{:args, \["/dev/random"\]}, {:line, 10}, :binary, :use\_stdio\])

#### Memory consumption with Exile

Exile.stream!(~w(cat /dev/random))
|> Enum.each(fn data \->
  IO.puts(IO.iodata\_length(data))
end)

Exile achieves this by implementing demand-driven, asynchronous IO mechanism with external process using NIF. See Rationale for details. For example, getting audio out of a stream is as simple as

Exile.stream!(~w(ffmpeg -i pipe:0 -f mp3 pipe:1), input: File.stream!("music\_video.mkv", \[\], 65\_535))
|> Stream.into(File.stream!("music.mp3"))
|> Stream.run()

See `Exile.stream!/2` module doc for more details about handling stderr and other options.

`Exile.stream!/2` is a convenience wrapper around `Exile.Process`. Prefer using `Exile.stream!` over using `Exile.Process` directly.

Exile requires OTP v22.1 and above.

Exile is based on NIF, please know consequence of that before using Exile. For basic use cases use ExCmd instead.

Installation
------------

def deps do
  \[
    {:exile, "~> x.x.x"}
  \]
end

Quick Start
-----------

Run a command and read from stdout

iex\> Exile.stream!(~w(echo Hello))
...\> |> Enum.into("") \# collect as string
"Hello\\n"

Run a command with list of strings as input

iex\> Exile.stream!(~w(cat), input: \["Hello", " ", "World"\])
...\> |> Enum.into("") \# collect as string
"Hello World"

Run a command with input as Stream

iex\> input\_stream \= Stream.map(1..10, fn num \-> "#{num} " end)
iex\> Exile.stream!(~w(cat), input: input\_stream)
...\> |> Enum.into("")
"1 2 3 4 5 6 7 8 9 10 "

Run a command with input as infinite stream

\# create infinite stream
iex\> input\_stream \= Stream.repeatedly(fn \-> "A" end)
iex\> binary \=
...\>   Exile.stream!(~w(cat), input: input\_stream, ignore\_epipe: true) \# we need to ignore epipe since we are terminating the program before the input completes
...\>   |> Stream.take(2) \# we must limit since the input stream is infinite
...\>   |> Enum.into("")
iex\> is\_binary(binary)
true
iex\> "AAAAA" <> \_ \= binary

Run a command with input Collectable

\# Exile calls the callback with a sink where the process can push the data
iex\> Exile.stream!(~w(cat), input: fn sink \->
...\>   Stream.map(1..10, fn num \-> "#{num} " end)
...\>   |> Stream.into(sink) \# push to the external process
...\>   |> Stream.run()
...\> end)
...\> |> Stream.take(100) \# we must limit since the input stream is infinite
...\> |> Enum.into("")
"1 2 3 4 5 6 7 8 9 10 "

When the command wait for the input stream to close

\# base64 command wait for the input to close and writes data to stdout at once
iex\> Exile.stream!(~w(base64), input: \["abcdef"\])
...\> |> Enum.into("")
"YWJjZGVm\\n"

`stream!/2` raises non-zero exit as error

```
iex> Exile.stream!(["sh", "-c", "echo 'foo' && exit 10"])
...> |> Enum.to_list()
** (Exile.Stream.AbnormalExit) program exited with exit status: 10
```

`stream/2` variant returns exit status as last element

```
iex> Exile.stream(["sh", "-c", "echo 'foo' && exit 10"])
...> |> Enum.to_list()
[
  "foo\n",
  {:exit, {:status, 10}} # returns exit status of the program as last element
]
```

You can fetch exit\_status from the error for `stream!/2`

```
iex> try do
...>   Exile.stream!(["sh", "-c", "exit 10"])
...>   |> Enum.to_list()
...> rescue
...>   e in Exile.Stream.AbnormalExit ->
...>     e.exit_status
...> end
10
```

With `max_chunk_size` set

iex\> data \=
...\>   Exile.stream!(~w(cat /dev/urandom), max\_chunk\_size: 100, ignore\_epipe: true)
...\>   |> Stream.take(5)
...\>   |> Enum.into("")
iex\> byte\_size(data)
500

When input and output run at different rate

iex\> input\_stream \= Stream.map(1..1000, fn num \-> "X #{num} X\\n" end)
iex\> Exile.stream!(~w(grep 250), input: input\_stream)
...\> |> Enum.into("")
"X 250 X\\n"

With stderr set to `:consume`

iex\> Exile.stream!(\["sh", "-c", "echo foo\\necho bar >> /dev/stderr"\], stderr: :consume)
...\> |> Enum.to\_list()
\[{:stdout, "foo\\n"}, {:stderr, "bar\\n"}\]

With stderr set to `:disable`

iex\> Exile.stream!(\["sh", "-c", "echo foo\\necho bar >> /dev/stderr"\], stderr: :disable)
...\> |> Enum.to\_list()
\["foo\\n"\]

For more details about stream API, see `Exile.stream!/2` and `Exile.stream/2`.

For more details about inner working, please check `Exile.Process` documentation.

Rationale
---------

Existing approaches

#### Port

Port is the default way of executing external commands. This is okay when you have control over the external program's implementation and the interaction is minimal. Port has several important issues.

-   it can end up creating zombie process
-   cannot selectively close stdin. This is required when the external programs act on EOF from stdin
-   it sends command output as a message to the beam process. This does not put back pressure on the external program and leads exhausting VM memory

#### Middleware based solutions

Libraries such as Porcelain, Erlexec, Rambo, etc. solves the first two issues associated with ports - zombie process and selectively closing STDIN. But not the third issue - having back-pressure. At a high level, these libraries solve port issues by spawning an external middleware program which in turn spawns the program we want to run. Internally uses port for reading the output and writing input. Note that these libraries are solving a different subset of issues and have different functionality, please check the relevant project page for details.

-   no back-pressure
-   additional os process (middleware) for every execution of your program
-   in few cases such as porcelain user has to install this external program explicitly
-   might not be suitable when the program requires constant communication between beam process and external program

On the plus side, unlike Exile, bugs in the implementation does not bring down whole beam VM.

#### ExCmd

This is my other stab at solving back pressure on the external program issue. It implements a demand-driven protocol using odu to solve this. Since ExCmd is also a port based solution, concerns previously mentioned applies to ExCmd too.

Exile
-----

Internally Exile uses non-blocking asynchronous system calls to interact with the external process. It does not use port's message based communication instead does raw stdio using NIF. Uses asynchronous system calls for IO. Most of the system calls are non-blocking, so it should not block the beam schedulers. Makes use of dirty-schedulers for IO.

**Highlights**

-   Back pressure
-   no middleware program
    -   no additional os process. No performance/resource cost
    -   no need to install any external command
-   tries to handle zombie process by attempting to clean up external process. _But_ as there is no middleware involved with exile, so it is still possible to endup with zombie process if program misbehave.
-   stream abstraction
-   selectively consume stdout and stderr streams

If you are running executing huge number of external programs **concurrently** (more than few hundred) you might have to increase open file descriptors limit (`ulimit -n`)

Non-blocking io can be used for other interesting things. Such as reading named pipe (FIFO) files. `Exile.stream!(~w(cat data.pipe))` does not block schedulers, so you can open hundreds of fifo files unlike default `file` based io.

#### TODO

-   add benchmarks results

### 🚨 Obligatory NIF warning

As with any NIF based solution, bugs or issues in Exile implementation **can bring down the beam VM**. But NIF implementation is comparatively small and mostly uses POSIX system calls. Also, spawned external processes are still completely isolated at OS level.

If all you want is to run a command with no communication, then just sticking with `System.cmd` is a better.

### License

Copyright (c) 2020 Akash Hiremath.

Exile source code is released under Apache License 2.0. Check LICENSE for more information.
