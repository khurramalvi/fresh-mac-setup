# Zsh Configuration

Let&#39;s create a .zshrc file to optimise our setup to house our aliases, exports, and path modifications. By centralising these components in the .zshrc file, we can maintain a cleaner and more organised configuration. If you want a pre-made .zshrc dotfile, download the one available in this directory.

Now, let&#39;s create a .zshrc file in the home directory.

```
cd ~
```
```
touch .zshrc
```
```
open .zshrc
```

The following is the configuration that will go into the .zshrc file.

```
# Zsh path
# ------------------------------------------------------------------------------
export PATH="/usr/local/sbin:$PATH"


# Starship
# ------------------------------------------------------------------------------
eval "$(starship init zsh)"


# Eza for ls command
# ------------------------------------------------------------------------------
alias l="eza --icons"
alias ls="eza --icons"
alias ll="eza -lg --icons"
alias la="eza -lag --icons"
alias lt="eza -lTg --icons"
alias lt1="eza -lTg --level=1 --icons"
alias lt2="eza -lTg --level=2 --icons"
alias lt3="eza -lTg --level=3 --icons"
alias lta="eza -lTag --icons"
alias lta1="eza -lTag --level=1 --icons"
alias lta2="eza -lTag --level=2 --icons"
alias lta3="eza -lTag --level=3 --icons"


# # Specify default editor. Possible values: vim, neovim, nano, ed etc.
# ------------------------------------------------------------------------------
export EDITOR=vim


# Custom functions
# ------------------------------------------------------------------------------
# file search functions
function f() { find . -iname "*$1*" ${@:2} }
function r() { grep "$1" ${@:2} -R . }

# create a folder and move into it in one command
function mkcd() { mkdir -p "$@" && cd "$_"; }

# refresh shell
function reload(){
  source ~/.zshrc
}


# Git
# ------------------------------------------------------------------------------
# update feature branch with latest master
function update(){
  git checkout main && git fetch && git pull && git checkout - && git rebase main
}

GIT_MERGE_AUTOEDIT=no
export GIT_MERGE_AUTOEDIT


# Aliases
# ------------------------------------------------------------------------------
alias cppcompile='c++ -std=c++11 -stdlib=libc++'

# folder
alias desk="cd ~/Desktop"
alias home="cd ~"
alias ..="cd .."
alias ...="cd ../.."
alias p="cd $HOME/Sites"
alias ka="cd $HOME/Sites/khurramalvi.com"
alias tb="cd $HOME/Sites/thinkbiginteractive.com"
alias web="cd $HOME/Sites/webhostingmix.com"


# command
alias c="clear"
alias l="ls -lh"
alias h=history
alias t="rm -rf ~/.Trash/*"
alias f="open -a Finder ./"
alias z="code ~/.zshrc"
alias r="exec $SHELL -l"
alias gk="sudo spctl --master-disable"
alias ds="find . -name ".DS_Store" -print -delete"
alias chrome="open -a \"Google Chrome\""
alias server="open http://localhost:8000 && python -m SimpleHTTPServer"

# show/hide hidden files in Finder
alias show="defaults write com.apple.finder AppleShowAllFiles -bool true && killall Finder"
alias hide="defaults write com.apple.finder AppleShowAllFiles -bool false && killall Finder"

# networking
alias myip="curl ip.appspot.com"
alias localip="ipconfig getifaddr en0"

# make executable
alias ax="chmod a+x"
```

