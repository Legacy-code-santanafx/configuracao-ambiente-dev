# configuracao-ambiente-dev

instalar windows terminal

entrar no site da microsoft e ver como instalar o wsl

sudo apt update && sudo apt upgrade

sudo apt install git

nano ~/.bashrc

==========================================

PROCURE POR 

if [ "$color_prompt" = yes ]; then
    PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
else
    PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w\$ '
fi

SUBSTITUA POR 

# Add git branch to prompt
parse_git_branch() {
    git rev-parse --is-inside-work-tree >/dev/null 2>&1 || return
    git branch 2> /dev/null | sed -e '/^[^*]/d' -e 's/* \(.*\)/(\1)/' | sed 's/^/ /'
}
if [ "$color_prompt" = yes ]; then
 PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[01;31m\]$(parse_git_branch)\[\033[00m\]\$ '
else
 PS1='${debian_chroot:+($debian_chroot)}\u@\h:\w$(parse_git_branch)\$ '
fi

=========================================

git config --global user.name "lucas"
git config --global user.email "santanafx@hotmail.com"

instalar node

entra no site do node e olha como

instalar docker

vai no site do docker e olha como

sudo apt install zsh

========================
instalacao opcional

entrar no site do zim

instalar zim

chsh -s $(which zsh)

code ~/.zimrc

zmodule completion
zmodule prompt-pwd
zmodule eriner

zimfw install

======================










