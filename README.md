# Dotfile Configurations for Linux

Source: [Atlassian Blog](https://www.atlassian.com/git/tutorials/dotfiles), [Hacker News Thread](https://news.ycombinator.com/item?id=11070797)

*Note: This README will live in your `$HOME` directory.*

## Getting Started

Run the following commands to clone this repository and setup the config git alias.

```bash
# Target config directory
config_dir=$HOME/.cfg

# Setup the repo on local
git clone --bare https://github.com/justinmklam/dotfiles.git $config_dir
alias config='/usr/bin/git --git-dir=$config_dir --work-tree=$HOME'
config config status.showUntrackedFiles no

# This may fail if existing files have changes (ie. in .bashrc). Make a backup of the conflicting file and try this command again
config checkout
```

Optional (this should be in `.bashrc` already):

```bash
# Add config command to bashrc
echo "alias config='/usr/bin/git --git-dir=$config_dir --work-tree=$HOME'" >> $HOME/.bashrc
```

## Usage

Adding new files from anywhere in your `$HOME` directory:

```bash
# Add a specific file
config add .bash_aliases
# Alternatively, to add the recently changed (tracked) file(s)
config add -u

config commit -m "Add bash_aliases"
config push
```
