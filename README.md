# Dotfile Configurations for Linux

Source: [Atlassian Blog](https://www.atlassian.com/git/tutorials/dotfiles), [Hacker News Thread](https://news.ycombinator.com/item?id=11070797)

*Note: This README will live in your `$HOME` directory.*

## Getting Started

```bash
# Target config directory
config_dir=$HOME/.cfg

# Setup the repo on local
git clone --bare https://github.com/justinmklam/dotfiles.git $config_dir
alias config='/usr/bin/git --git-dir=$config_dir --work-tree=$HOME'
config checkout
config config status.showUntrackedFiles no

# Add config command to bashrc
echo "alias config='/usr/bin/git --git-dir=$config_dir --work-tree=$HOME'" >> $HOME/.bashrc
```

Adding new files from anywhere in your `$HOME` directory:

```bash
config add .bash_aliases
config commit -m "Add bash_aliases"
config push
```
