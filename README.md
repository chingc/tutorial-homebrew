# Homebrew

Homebrew is a popular command-line package manager for macOS (and Linux).  It can install CLI tools, libraries, and prebuilt binaries.  It can also install native macOS applications typically distributed as `.dmg`, `.pkg`, or `.app`.  These two categories of software are known as formulae and casks in homebrew, respectively.

Installing software can sometimes be a complicated multi-step process.  Knowing how to use homebrew means you'll be able to install software with a single command.

## Install

1. Open the macOS Terminal (or Linux shell prompt)
1. Paste the following
    ```
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
    ```
    - This should be run as a normal user.  Do not use `sudo` or administrative privileges.
    - The script explains what it will do and then pauses before it does it.  Accept to continue.
1. Edit your shell profile as directed by the script to ensure homebrew loads when a terminal is started
1. Quit and restart your terminal

To verify the installation, type `brew` and you should see some sample usage.

## Uninstall

Directions can be found [here](https://github.com/homebrew/install#uninstall-homebrew) if you wish to uninstall homebrew.

## Reference

- [Homebrew](https://brew.sh)
- [Homebrew terminology](https://docs.brew.sh/Formula-Cookbook#homebrew-terminology)
