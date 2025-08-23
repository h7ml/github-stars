---
project: ChessCoach
stars: 500
description: Neural network-based chess engine capable of natural language commentary
url: https://github.com/chrisbutner/ChessCoach
---

ChessCoach
==========

@PlayChessCoach on Lichess: Watch | Stats | Challenge (1+0 or 0+1 up to 15+10)

Overview
--------

ChessCoach is a neural network-based chess engine capable of natural-language commentary. It plays chess with a rating of approximately 3450 Elo, which means it should usually beat even the strongest human players at 2850 Elo, and many other engines, but will often lose to the strongest, such as Stockfish 14 at 3550 Elo.

As with all engines, ChessCoach relies on examining millions of chess positions to decide on the best move to play. It uses a large, slow neural network just like AlphaZero or Leela Chess Zero (Lc0) to evaluate each position, unlike classical engines which aim for speed with a much simpler evaluation, or more recent NNUE engines, which are a stronger hybrid of both styles.

The neural network at the core of the engine is trained by playing against itself, using a feedback cycle to start from almost zero knowledge – just the rules of chess – and learn new ways to beat itself as it grows stronger. Stronger neural network evaluations let it search better, and stronger search results let it train its neural network evaluation more effectively.

ChessCoach can also feed its chess knowledge into an additional neural network to comment on moves and positions in English. It is not very insightful and often wrong but shows some promise for the limited data it has been able to train on.

Contents
--------

-   Overview
-   Motivation
-   Comparisons
-   Results
-   Measurements
-   Documentation
-   Programs
-   Files
-   Installation
    -   Pre-installation
    -   Linux (Debian/Ubuntu), GPU
    -   Linux (Debian/Ubuntu), older-style TPU
    -   Linux (Debian/Ubuntu), newer-style Cloud TPU VM
    -   Windows, GPU
    -   Post-installation
    -   Linux, post-installation for Google Cloud Storage support
    -   Linux, post-installation for cluster support
-   Usage
-   Running tests
    -   Linux
    -   Windows
-   Acknowledgements
-   License
-   Contact

Motivation
----------

I started developing ChessCoach as a two to three-month project to see whether I liked machine learning and ended up taking things further than I expected. The original plan had three overly ambitious goals: replicating a small AlphaZero-like engine, adding natural-language commentary to the training feedback cycle, and making some degree of training possible on a single-GPU workstation.

After a little over a year of development, I can claim almost no progress on training methods. However, I am happy with the commentary that ChessCoach produces, all things considered, and surprised at the eventual strength of the engine.

I was lucky to have so many public resources available, including free cloud compute and freely available papers, discussions and data. I am also very grateful to a number of folks who have helped with important clarifications, discussions and debugging.

Comparisons
-----------

The chess engine at the core of ChessCoach is very similar to that of AlphaZero (Silver et al., 2018) or Lc0 (Linscott & Pascutto, 2018), in the structure of the neural network, training schedule and search algorithm, but with a practical, engineering approach by necessity, lacking the breadth and depth of research talent of a larger team. However, I hope that there are a few new ideas that can be useful elsewhere.

The natural-language commentary piece is most like the work of Learning to Generate Move-by-Move Commentary for Chess Games from Large-Scale Social Forum Data (Jhamtani, Gangal, Hovy, Neubig & Berg-Kirkpatrick, 2018) and Automated Chess Commentator Powered by Neural Chess Engine (Zang, Yu & Wan, 2019), but relies on a more heavily trained chess engine and larger training corpus, albeit with more simplistic architecture.

Results
-------

ChessCoach is designed to be somewhat minimal and portable. It runs on Linux and Windows and supports single-GPU, multi-GPU and Tensor Processing Units (TPUs). Performance-oriented code is in C++ (10.5k lines) and neural network code is in Python (3.7k lines), relying on TensorFlow 2. Stockfish code is used for position management, move generation and endgame tablebase probing, but not for search or evaluation. Self-play training data has been completely generated within the ChessCoach project, following the AlphaZero schedule of 44 million games and 700,000 training batches of 4,096 positions each.

Some ideas beyond AlphaZero but existing in literature and projects such as KataGo (Wu, 2020) and Lc0 have been integrated (often I thought I was trying something new, but it turns out smart folks at Lc0 have tried almost everything). These include mate-proving, endgame tablebase probing, endgame minimax, stochastic weight averaging (SWA), exponentially weighted moving averages (EWMA), various exploration incentives, prediction caching, auxiliary training targets, and knowledge distillation.

I believe that some ideas are new. The first is a search method that aims to avoid tactical traps and minimize simple regret via Linear Exploration and Selective Backpropagation, applied via elimination – SBLE-PUCT. The second is a simple neural architecture for natural-language commentary on positions and moves in conjunction with a tweaked application of nucleus sampling (top-p) focused on correctness-with-variety – COVET sampling.

The outcome is a suite of tools to play chess, train the neural networks, optimize parameters, test strength, process training data, view and debug training data, organize training data, unit-test, and coordinate clusters. To wrap up the project, a bot is set up at https://lichess.org/@/PlayChessCoach to play games against challengers and other bots, and provide commentary to spectators.

Measurements
------------

On a newer-style v3-8 Cloud TPU VM:

-   Approximate tournament Elo ratings of 3535 at 40/15 time, 3486 at 300+3 time, 3445 at 60+0.6 time, vs. Stockfish 14 with 8 threads, 8192 hash, 3-4-5 Syzygy, pinned to 3550 Elo (details)
-   125,000 nodes per second (NPS) (varying 68,000 - 141,000 with position) (details)
-   2,360 self-play games per hour (lots of room for improvement) (details)
-   3317 STS Elo estimation (commonly varying 3260 - 3350 with parameters) (details)
-   117/199 Arasan21 score (commonly varying 118 - 126 with parameters) (details)

Documentation
-------------

-   High-level explanation
-   Technical explanation
-   Development process
-   Data

Programs
--------

-   ChessCoachUci is the chess engine itself, implementing the Universal Chess Interface (UCI) protocol.
-   ChessCoachTrain is the core of the project, generating self-play game data and training the neural networks.
-   ChessCoachOptimizeParameters is used to find a global optimum for a collection of parameters that affect chess-playing strength, using Bayesian optimization via Scikit-Optimize (skopt).
-   ChessCoachStrengthTest runs positional and tactical test suites in Extended Position Description (EPD) format and gives a score and sometimes a rating estimate.
-   ChessCoachPgnToGames processes existing collections of games in Portable Game Notation (PGN) format and generates either supervised training data for the primary neural network, or commentary training data.
-   ChessCoachGui (Windows-only) launches a web user interface to analyze training data over a chess board. The same interface can instead be used to live-analyze engine searches by running ChessCoachUci rather than ChessCoachGui and entering the `gui` command before searching.
-   ChessCoachTest runs a suite of 36 tests in the Config, Game, MCTS, Network, PGN, PoolAllocator, PredictionCache and Stockfish categories.
-   ChessCoachBot runs a bot on the Lichess platform, playing games and providing commentary, based on https://github.com/ShailChoksi/lichess-bot.
-   cluster-up/down/run/kill.sh are scripts that manage a Kubernetes cluster of older-style TPUs and compute VMs on Google Cloud, coordinating via Google Storage, to generate larger volumes of self-play data and train on that data.
-   alpha.py is a script that manages a cluster of newer-style Cloud TPU VMs, currently available via preview but termed _alpha TPU VMs_ in code. These are faster and architecturally simpler to use, but currently lack Kubernetes support and require SSH wrangling instead.
-   gsclean.py is a simple script for cleaning up neural network training checkpoints and Docker images in Google Cloud Storage using predicates like **delete version <= 29**.
-   scrape.py is a script that uses the ScrapingBee service to download publicly available chess games with commentary.
-   uci\_proxy\_client.py, uci\_proxy\_server.py are scripts that allow running a chess engine on a remote machine as if it were on the local machine. This is useful for running tournaments using TPUs, since each accelerator chip can only be held by one process, and it also allow speeding up parameter optimization using a cluster. These are really just standard input/output proxies and do not do anything specific to UCI.
-   docker-build-upload.sh is a script that builds Docker images for training/self-play clusters and distributed parameter optimization clusters. The images are uploaded to the Google Container Registry (GCR) and referenced by the older-style cluster-\*.sh (via cluster-\*.yaml) and newer-style alpha.py scripts for cluster management.

Files
-----

Some key files are located at the root, including config.toml which drives most tools and is read from C++ and Python code. Meson.build defines the Linux build, and cpp/ChessCoach.sln and cpp/\*\*/\*.vcxproj define the Windows build. The setup.sh/.cmd and build.sh/.cmd scripts automate setup and building, although additional steps can be required. Dockerfiles at the root define images for each cluster worker role, and docker-\*.sh scripts assist with building and uploading these images.

In the cluster directory the .sh/.yaml files manage Kubernetes clusters on older-style TPUs, whereas py/alpha.py manages clusters on newer-style Cloud TPU VMs.

The cpp directory contains C++ code, mostly in cpp/ChessCoach. ChessCoach C++ code is mainly performance oriented. Third-party libraries include cpp/crc32c, cpp/hunspell, cpp/numpy, cpp/protobuf-3.13.0, cpp/Stockfish, cpp/tclap, cpp/toml11 and cpp/zlib. Third-party data includes cpp/Dictionaries and cpp/StrengthTests. Additional third-party C++ libraries are installed using the Advanced Package Tool (APT) and discovered by the Meson build system on Linux, and installed and discovered using NuGet on Windows. The cpp/protobuf library is code-generated using the protoc tool and cpp/protobuf/ChessCoach.proto.

The py directory contains Python code, primary accessed through network.py from C++, but also some standalone script tools. ChessCoach Python code is mainly concerned with the neural network and cloud storage. Additional third-party Python libraries are installed using pip.

The js directory contains the debug GUI used in ChessCoachGui and ChessCoachUci, relying on chessboardjs.

The tools directory contains cutechess-cli and bayeselo for running tournaments and calculating Elo ratings of participants, as well as the Stockfish 13 engine binary to act as an opponent.

The scripts directory contains various situational scripts and conveniences.

The docs directory contains documentation and supporting assets.

After installation, ChessCoach locates static data at /usr/local/share/ChessCoach on Linux and alongside the binary in Windows. It locates dynamic data at ${XDG\_DATA\_HOME}/ChessCoach, or failing that, at ~/.local/share/ChessCoach on Linux, and at %LOCALAPPDATA%/ChessCoach on Windows. Dynamic data can also be located in Google Cloud Storage; for example, gs://chesscoach-eu/ChessCoach.

Installation
------------

### Pre-installation

1.  Install git and clone this repository.
2.  Customize parameters in config.toml according to GPU/TPU, following commented guidelines (alternatively, if only using ChessCoachUci, the **search\_threads** option can be set at runtime).

### Linux (Debian/Ubuntu), GPU

If running on Google Cloud, it can simplify GPU setup to use a pre-built Deep Learning disk image with CUDA 11.

1.  Follow TensorFlow GPU Linux setup instructions if not using a pre-built Deep Learning disk image on Google Cloud.
2.  Run `./setup.sh` (it may take 30 minutes to build Protobuf from source).
3.  To add commentary support:
    -   Run `pip3 install -r requirements-all.txt`.
4.  Run `sudo ./build.sh release install`.

### Linux (Debian/Ubuntu), older-style TPU

1.  Enable **Cloud TPU API**.
2.  Create a compute VM and TPU with matching name, zone and TensorFlow version.
3.  Run `./setup.sh` (it may take 30 minutes to build Protobuf from source).
4.  To add commentary support:
    -   Run `pip3 install -r requirements-all.txt`.
5.  Run `sudo ./build.sh release install`.

### Linux (Debian/Ubuntu), newer-style Cloud TPU VM

1.  Enable **Cloud TPU API**.
2.  Create a Cloud TPU VM.
3.  Run `./setup.sh` (it may take 30 minutes to build Protobuf from source).
4.  To add commentary support:
    1.  Obtain private binaries for tf-nightly and tf-text-nightly that are non-monolithic and support custom ops.
    2.  Run `pip3 install tf-models-official==2.5.0` (this clobbers the pre-installed tf-nightly).
    3.  Run `pip3 uninstall tensorflow tf-slim tf-nightly`.
    4.  Install the private tf-nightly package with `--force-reinstall`.
    5.  Install the private tf-text-nightly package.
5.  Run `sudo ./build.sh release install`.

### Windows, GPU

1.  Install Visual Studio (for example, Visual Studio Community).
    -   Install the **Desktop development with C++** component.
2.  Install Python and add it to the PATH.
    -   It can simplify GPU setup to install Python using Anaconda and install the Anaconda tensorflow-gpu package.
    -   Update activate\_virtual\_env.cmd if using Anaconda or another virtual environment. The default is to attempt `conda activate chesscoach`, but it is okay if this fails when not using a virtual environment.
3.  Follow TensorFlow GPU Windows setup instructions if not using the Anaconda tensorflow-gpu package.
4.  Run `setup.cmd` (this sets CHESSCOACH\_PYTHONHOME after running activate\_virtual\_env.cmd).
5.  Run `build.cmd`.

### Post-installation

ChessCoach relies on data installed to ${XDG\_DATA\_HOME}/ChessCoach, or failing that, at ~/.local/share/ChessCoach on Linux, and at %LOCALAPPDATA%/ChessCoach on Windows.

Install neural network weights. This requires a 372 MiB download and 406 MiB disk space.

-   **Linux:** Run `scripts/download_install_data.sh`.
-   **Windows:** Run `scripts/download_install_data.cmd`.
-   After running, …/ChessCoach/Networks/chesscoach1\_005600000 and …/ChessCoach/Commentary/tokenizer.model should exist.
-   Neural network weights accessed by these scripts are located at https://github.com/chrisbutner/ChessCoachData/releases/download/v1.0.0/Data.zip.

Optionally, install Syzygy endgame tablebases. Files for 3-4-5 pieces take approximately 1 GiB, and files for 3-4-5 + 6 pieces take approximately 150 GiB. The installation process is somewhat technical.

1.  Download WDL and DTZ files for the chosen piece counts from https://syzygy-tables.info/, using either a recursive web download, or BitTorrent download.
2.  Validate file integrity using the provided checksums.
3.  Install the files to …/ChessCoach/Syzygy (or set the **syzygy** UCI option).

In cloud storage mode, Syzygy tables are automatically replicated to local storage on launch.

The script scripts/ramdisk\_syzygy6.sh sets up a RAM disk on machines like newer-style Cloud TPU VMs to host 3-4-5 + 6-piece tables, when memory is high but disk space is low. When using a disk, it is best to place these tables on SSDs to maintain search speed. The script scripts/ramdisk\_syzygy6.sh uses the path …/ChessCoach/Syzygy6, relying on a configuration change in config.toml, but …/ChessCoach/Syzygy could be used instead.

### Linux, post-installation for Google Cloud Storage support

1.  Create a storage bucket, update **cloud\_data\_root** in config.toml, and reinstall.
2.  Copy necessary networks, commentary tokenizer, Syzygy tablebases, validation data, etc. to the bucket.

### Linux, post-installation for cluster support

1.  Enable **Container Registry API**.
2.  Run `export PROJECT_ID=<your Google Cloud project ID>`.
3.  Update **distributed\_zone** in config.toml with your compute zone, and reinstall.

If using alpha.py (this part is especially messy):

1.  Run `cluster/cluster-prep-creds.sh` to create a service account and a corresponding key.json file.
2.  Update **IMAGE\_PREFIX** in alpha.py with your preferred Google Container Registry domain and Google Cloud project ID.
3.  Update **KEY\_PATH** in alpha.py with your storage bucket.
4.  Copy key.json to **KEY\_PATH** using `gsutil cp`.

The Distributed training and self-play section in the Technical explanation has more information on managing older-style and newer-style clusters.

Usage
-----

Most ChessCoach programs depend on the built and installed config.toml. It is particularly important to set the **search\_threads** parameter when running ChessCoachUci, either via config.toml at build time or UCI option at runtime, to avoid thread starvation from unfair prediction scheduling.

The ChessCoachUci binary can be loaded as a UCI engine in various chess GUIs.

However, when using a virtual environment for Python, it may be necessary to either:

-   a) Activate the virtual environment before launching the chess GUI, or
-   b) Load the engine using a wrapper script that first activates the virtual environment before launching ChessCoachUci (scripts/uci.cmd script is a development-time example on Windows).

ChessCoachUci offers custom commands in addition to those of the UCI protocol:

-   `comment` generates natural-language commentary for the current position and last move played. It is best to provide full move history with a `position startpos moves …` command.
-   `gui` flags the debug GUI to launch when starting a search (as shown in Figure 9 in the High-level explanation).
-   `~ puct [moves …] [csv]` displays debug GUI data in text form.
-   `~ fen` displays the current position in Forsyth–Edwards Notation (FEN).

For self-play and training, see Self-play and training process in the Data document.

For other utilities listed in Programs, look for comments in config.toml for configuration guidance. Many utilities support the `--help` argument. The contents of scripts in the scripts directory can show examples. When using a virtual environment for Python, it may need to be activated before running utilities, although some do not depend on Python.

Running tests
-------------

### Linux

Run `build/gcc/debug/ChessCoachTest` or `build/gcc/release/ChessCoachTest`.

### Windows

Run `activate_virtual_env.cmd` then `cpp/x64/Debug/ChessCoachTest.exe` or `cpp/x64/Release/ChessCoachTest.exe`.

You can also run/debug the ChessCoachTest project within Visual Studio, or use the Test Explorer interface within Visual Studio.

Acknowledgements
----------------

Google's TPU Research Cloud (TRC) program has been exceptionally generous with computing resources that made this project possible, and I thank Jonathan Caton in particular for making things happen.

I'm very appreciative of Google's Cloud TPU team for the use of Cloud TPU VMs, and especially Michael Banfield for engineering assistance throughout the alpha of the new technology.

I sincerely thank Karlson Pfannschmidt (Paderborn University), whose Chess Tuning Tools and Bayes-skopt implementation, and advice on Bayesian optimization were invaluable in strengthening the ChessCoach engine.

I'm very grateful to Matthew Lai (DeepMind) for providing in an independent capacity, important clarifications on the AlphaZero paper.

I extend thanks to Pierre de Wulf for providing research credits for ScrapingBee to enable natural-language commentary training in ChessCoach.

Thank you to Ted Li for valuable ideas and discussions at the commencement of the project.

Thank you to Freya Wilcox for assistance with diagram prototyping.

And special thanks to Gary Butner and Lynelle Rafton for editing, proofreading and support.

License
-------

ChessCoach is released under the GPLv3 or later license.

Contact
-------

Chris Butner, chris.butner@outlook.com
