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

sudo apt install zsh -y

sudo apt install curl

sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

nao coloque o zsh como padrao
nerd fonts e baixar a font meslogl nerd font
extrair clica botao direito install

troque a fonte do terminal apertando botao direito e properties

Enabling Plugins (zsh-autosuggestions & zsh-syntax-highlighting)
Download zsh-autosuggestions by
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions

Download zsh-syntax-highlighting by
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting

nano ~/.zshrc find plugins=(git)

Append zsh-autosuggestions & zsh-syntax-highlighting to plugins() like this

plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

Reopen terminal

para deixar o zsh com terminal padrao

chsh -s $(which zsh)

https://github.com/junegunn/fzf instale o fzf utilizando o clone do github (mais fácil)

instale o ripgrep

https://github.com/BurntSushi/ripgrep

sudo apt-get install ripgrep

instale o bat

https://github.com/sharkdp/bat

sudo apt install bat

abra o ~./zshrc e ~./bashrc

coloque no final 
alias bat="batcat"

sudo ln -s /usr/bin/batcat /usr/bin/bat



===================================
Powershell

$PROFILE

Invoke-Expression (&starship init powershell)
Clear-Host
Set-PSReadLineOption -PredictionSource History
Set-PSReadLineOption -PredictionViewStyle ListView
Set-PSReadLineOption -EditMode Windows

instalar starship

instalar PSReadline

Set-PSRepository -Name "PSGallery" -InstallationPolicy Trusted
 Install-Module -Name PSColors -AllowClobber -force






