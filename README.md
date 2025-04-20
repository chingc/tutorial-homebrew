# Homebrew

Homebrew is a popular command-line package manager for macOS (and Linux). It can install CLI tools, libraries, and prebuilt binaries. It can also install native macOS applications typically distributed as `.dmg`, `.pkg`, or `.app`. These two categories of software are known as formulae and casks in homebrew, respectively.

Installing software can be a complicated multi-step process. Knowing how to use homebrew means you'll be able to save time by installing software with a single command. More importantly, it enables automated installation of many applications with very simple scripts.

## Install

1. Open the macOS Terminal (or Linux shell prompt).
1. Run the following code as a normal user. Do not use `sudo` or administrative privileges. The script explains what it will do and asks if you want to proceed. Accept to continue.
   ```
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
   ```
1. Edit your shell profile as directed by the script to ensure homebrew loads when a terminal is started.
1. Quit and restart your terminal.

To verify the installation, run `brew` and you should see example usage and help.

## Managing Software

Here are some commands I think you'll be using frequently.

### search, info

- search: Searches for available formulae or casks in homebrew by name.
    - `brew search ghostty`

- info: Displays detailed information about a specific formula or cask. This includes version, dependencies, whether it auto-updates, and more.
    - `brew info ghostty`

### install, uninstall, reinstall, list, deps, services

- install: Downloads and installs a specified formula or cask to your system. In some rare cases you will find a formula and cask sharing the same name. To specifically install the cask add `--cask`.
    - `brew install neovim`

- uninstall: Removes a specified formula or cask from your system.
    - `brew uninstall neovim`

- reinstall: Uninstalls and then reinstalls a formula or cask to fix issues or refresh it. A shortcut for uninstall then install.
    - `brew reinstall neovim`

- list: Shows all installed formulae and casks on your system. The output also includes dependences required by formulae you've installed. If you include the name of a formula or cask it will show you where it's installed.
    - `brew list`
    - `brew list neovim`

- deps: Lists the dependencies required by a specific formula.
    - `brew deps neovim`

- services: Some programs come with background services which homebrew can manage for you.
    - `brew services`
    - `brew services info redis`
    - `brew services start redis`
    - `brew services stop redis`

### update, outdated, upgrade

- update: Gets the latest homebrew formulae and cask definitions. Run this before checking for outdated versions.
    - `brew update`

- outdated: Lists installed formulae or casks that have newer versions available.
    - `brew outdated`

- upgrade: Upgrade all outdated formulae and casks. Specify a name to only upgrade a specific one.
    - `brew upgrade`
    - `brew upgrade starship`

### autoremove, cleanup

- autoremove: Removes unused dependencies that were installed as dependencies of other formulae.
    - `brew autoremove`

- cleanup: Deletes old versions and cached downloads to free up disk space.
    - `brew cleanup`

### pin, unpin

- pin: Prevents a formula from being upgraded to keep it at the current version.
    - `brew pin redis`

- unpin: Allows a pinned formula to be upgraded again.
    - `brew unpin redis`

### link, unlink

- link: Symlink all of formula's installed files into homebrew's prefix. This is done
automatically, but in some cases you may have to do it manually.
    - `brew link python@3.13`

- unlink: Removes symlinks for a formula, temporarily disabling access to its executables.
    - `brew unlink python@3.13`

### --prefix, --cellar, --caskroom

- --prefix: Displays the installation path where homebrew or a formula stores its files.
    - `brew --prefix`
    - `brew --prefix uv`

- --cellar: Shows the directory where homebrew stores installed formulae.
    - `brew --cellar uv`

- --caskroom: Displays the directory where homebrew stores installed casks.
    - `brew --caskroom zed`

## Uninstall

Directions can be found [here](https://github.com/homebrew/install#uninstall-homebrew) if you want to uninstall homebrew.

## GitHub Actions

The official [setup-homebrew](https://github.com/Homebrew/actions/tree/master/setup-homebrew) action will let you use homebrew on GitHub Actions.

```
- uses: Homebrew/actions/setup-homebrew@master
```

Check out this sample workflow: [homebrew.yml](https://github.com/chingc/tutorial-github-actions/blob/main/.github/workflows/homebrew.yml)

## Reference

The commands above should be enough for most users, but homebrew can do a lot more.

Type `brew commands` to see all commands. Use `brew help [COMMAND]` for help with any of them.

- [Homebrew](https://brew.sh)
- [Homebrew terminology](https://docs.brew.sh/Formula-Cookbook#homebrew-terminology)
