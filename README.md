# dotfiles setup

Custom configuration files managed using a git bare repository.


## Quick Start 

**Initialize a bare repository**

`git init --bare $HOME/.cfg`

**Create an alias so in the future we can just type `config status` or `config push` etc instead of `git`**

`alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'`

**Don't show me untracked files (you don't care about them and you don't want them to show up)**

`config config --local status.showUntrackedFiles no`

**Add the line from above to your .bashrc, .bash_profile, .zshrc, zprofile file**

`echo "alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> $HOME/.bashrc`

## Usages

`config add .vimrc # where .vimrc can be any config file you want tracked`

`config commit -m "added vimrc"`

`config push`

## Pull your custom configs to a remote machine (or any machine

Note these are basically the same commands as above but this time we threw them in a script.

```bash
echo "alias config='/usr/bin/git --git-dir=$HOME/.cfg/ --work-tree=$HOME'" >> ~/.zshrc
source ~/.zshrc
echo ".cfg" >> .gitignore
git clone --bare git@github.com:nancynobody/dotfiles.git .cfg/
config checkout
config config --local status.showUntrackedFiles no
git clone https://github.com/VundleVim/Vundle.vim.git ~/.vim/bundle/Vundle.vim
```
# github_tutorial_repo_1
# github_tutorial_repo_2
