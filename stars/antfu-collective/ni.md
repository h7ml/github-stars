---
project: ni
stars: 7136
description: 💡 Use the right package manager
url: https://github.com/antfu-collective/ni
---

ni
==

_`npm i` in a yarn project, again? F\*\*k!_

**ni** - use the right package manager

  

```
npm i -g @antfu/ni
```

npm · yarn · pnpm · bun · deno

  

### `ni` - install

ni

# npm install
# yarn install
# pnpm install
# bun install
# deno install

ni vite

# npm i vite
# yarn add vite
# pnpm add vite
# bun add vite
# deno add vite

ni @types/node -D

# npm i @types/node -D
# yarn add @types/node -D
# pnpm add -D @types/node
# bun add -d @types/node
# deno add -D @types/node

ni -P

# npm i --omit=dev
# yarn install --production
# pnpm i --production
# bun install --production
# (deno not supported)

ni --frozen

# npm ci
# yarn install --frozen-lockfile (Yarn 1)
# yarn install --immutable (Yarn Berry)
# pnpm install --frozen-lockfile
# bun install --frozen-lockfile
# deno install --frozen

ni -g eslint

# npm i -g eslint
# yarn global add eslint (Yarn 1)
# pnpm add -g eslint
# bun add -g eslint
# deno install eslint

# this uses default agent, regardless your current working directory

ni -i

# interactively select the dependency to install
# search for packages by name

  

### `nr` - run

nr dev --port=3000

# npm run dev -- --port=3000
# yarn run dev --port=3000
# pnpm run dev --port=3000
# bun run dev --port=3000
# deno task dev --port=3000

nr

# interactively select the script to run
# supports https://www.npmjs.com/package/npm-scripts-info convention

nr -

# rerun the last command

# Add completion script for bash
nr --completion-bash \>> ~/.bashrc

# Add completion script for zsh
# For zim:fw
mkdir -p ~/.zim/custom/ni-completions
nr --completion-zsh \> ~/.zim/custom/ni-completions/\_ni
echo "zmodule $HOME/.zim/custom/ni-completions --fpath ." \>> ~/.zimrc
zimfw install

  

### `nlx` - download & execute

nlx vitest

# npx vitest
# yarn dlx vitest
# pnpm dlx vitest
# bunx vitest
# deno run npm:vitest

  

### `nup` - upgrade

nup

# npm upgrade
# yarn upgrade (Yarn 1)
# yarn up (Yarn Berry)
# pnpm update
# bun update
# deno upgrade

nup -i

# (not available for npm & bun & deno)
# yarn upgrade-interactive (Yarn 1)
# yarn up -i (Yarn Berry)
# pnpm update -i

  

### `nun` - uninstall

nun webpack

# npm uninstall webpack
# yarn remove webpack
# pnpm remove webpack
# bun remove webpack
# deno remove webpack

nun

# interactively select
# the dependency to remove

nun -m

# interactive select,
# but with multiple dependencies

nun -g silent

# npm uninstall -g silent
# yarn global remove silent
# pnpm remove -g silent
# bun remove -g silent
# deno uninstall -g silent

  

### `nci` - clean install

nci

# npm ci
# yarn install --frozen-lockfile
# pnpm install --frozen-lockfile
# bun install --frozen-lockfile
# deno cache --reload

if the corresponding node manager is not present, this command will install it globally along the way.

  

### `na` - agent alias

na

# npm
# yarn
# pnpm
# bun
# deno

na run foo

# npm run foo
# yarn run foo
# pnpm run foo
# bun run foo
# deno task foo

  

### Global Flags

# ?               | Print the command execution depends on the agent
ni vite ?

# -C              | Change directory before running the command
ni -C packages/foo vite
nr -C playground dev

# -v, --version   | Show version number
ni -v

# -h, --help      | Show help
ni -h

  

### Config

; ~/.nirc

; fallback when no lock found
defaultAgent\=npm # default "prompt"

; for global installs
globalAgent\=npm

# ~/.bashrc

# custom configuration file path
export NI\_CONFIG\_FILE="$HOME/.config/ni/nirc"

# environment variables have higher priority than config file if presented
export NI\_DEFAULT\_AGENT="npm" # default "prompt"
export NI\_GLOBAL\_AGENT="npm"

# for Windows

# custom configuration file path in PowerShell accessible within the \`$profile\` path
$Env:NI\_CONFIG\_FILE \= 'C:\\to\\your\\config\\location'

  

### Integrations

#### asdf

You can also install ni via the 3rd-party asdf-plugin maintained by CanRau

# first add the plugin
asdf plugin add ni https://github.com/CanRau/asdf-ni.git

# then install the latest version
asdf install ni latest

# and make it globally available
asdf global ni latest

### How?

**ni** assumes that you work with lock-files (and you should).

Before `ni` runs the command, it detects your `yarn.lock` / `pnpm-lock.yaml` / `package-lock.json` / `bun.lock` / `bun.lockb` / `deno.json` / `deno.jsonc` to know the current package manager (or `packageManager` field in your packages.json if specified) using the package-manager-detector package and then runs the corresponding package-manager-detector command.

### Trouble shooting

#### Conflicts with PowerShell

PowerShell comes with a built-in alias `ni` for the `New-Item` cmdlet. To remove the alias in your current PowerShell session in favor of this package, use the following command:

'Remove-Item Alias:ni -Force -ErrorAction Ignore'

If you want to persist the changes, you can add them to your PowerShell profile. The profile path is accessible within the `$profile` variable. The ps1 profile file can normally be found at

-   PowerShell 5 (Windows PowerShell): `C:\Users\USERNAME\Documents\WindowsPowerShell\Microsoft.PowerShell_profile.ps1`
-   PowerShell 7: `C:\Users\USERNAME\Documents\PowerShell\Microsoft.PowerShell_profile.ps1`
-   VSCode: `C:\Users\USERNAME\Documents\PowerShell\Microsoft.VSCode_profile.ps1`

You can use the following script to remove the alias at shell start by adding the above command to your profile:

if (\-not (Test-Path $profile)) {
  New-Item \-ItemType File \-Path (Split-Path $profile) \-Force \-Name (Split-Path $profile \-Leaf)
}

$profileEntry \= 'Remove-Item Alias:ni -Force -ErrorAction Ignore'
$profileContent \= Get-Content $profile
if ($profileContent \-notcontains $profileEntry) {
  ("\`n" + $profileEntry) | Out-File $profile \-Append \-Force \-Encoding UTF8
}

#### `nx`, `nix` and `nu` are no longer available

We renamed `nx`/`nix` and `nu` to `nlx` and `nup` to avoid conflicts with the other existing tools - nx, nix and nushell. You can always alias them back on your shell configuration file (`.zshrc`, `.bashrc`, etc).

alias nx="nlx"
# or
alias nix="nlx"
# or
alias nu="nup"
