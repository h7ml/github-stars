---
project: commitlive
stars: 6
description: Write Conventional Commits Livly
url: https://github.com/yaonyan/commitlive
---

### commitlive: livly cli to make conventional commit

Probably the most elegant way to make a `conventional commit` on the **command line**

### Features

-   `tab completion`, `placeholders` and `livly prompt`: this gives the user enough hints to make a better commit, with the help of repll
    
-   `find issues for you`: when you start typing `#` with a number, we will search for issues on github, it's based on gh cli, make sure it's installed and configured
    
-   `conventional commit lint`: while you are typing, we lint it for you using the great commitlint(!NOTE: When linting, we won't prompt <body> & <footer> as an input, this avoids overwhelming output message)
    
-   `focus more on typing rather than choosing`: some other commit tools pop up prompts for the user to select, whereas in `commitlive` you just type something and press tab to complete, which I think is closer to the way we interact with command line
    
-   `very close to git commit command`: under the hood, `commitlive` just run `git commit` command for you with the flag and commit you provided, and `flag` is always same as `git commit`
    

### Usage

**NOTE! You must have NodeJS v13.5.0+(v12.16.0+) installed in order to get `commitlive` up and running**

Install it globally or run it directly using `npx`

npm i -g commitlive

npx commitlive

Run commitlive to commit your staged changes:

commitlive -m

Or make them staged while committing:

commitlive -am

You may have noticed, it's same as `git commit`, quite easy to grasp its usage

Finally, be a good commitzen

### Related projects

-   commitzen-cli
-   commitlint
