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

===============================================

# ============================================
# MCP (Model Context Protocol) Configuration
# ============================================
# Paths to Windows applications (accessible via WSL2)

# Chrome - used by MCP Chrome DevTools server
export MCP_CHROME_PATH="/mnt/c/Program Files/Google/Chrome/Application/chrome.exe"

# Figma - used by MCP Figma server
export MCP_FIGMA_PATH="/mnt/c/Users/lucasfigueiredo.bhs/AppData/Local/Figma/Figma.exe"

# Alternative: if using Chrome from other location, update the path
# export MCP_CHROME_PATH="/mnt/c/Program Files (x86)/Google/Chrome/Application/chrome.exe"

# Helper function to launch Chrome with remote debugging from WSL2
launch-chrome-debug() {
  local port=${1:-9222}
  "$MCP_CHROME_PATH" --remote-debugging-port=$port --user-data-dir=/tmp/chrome-debug &
  echo "Chrome launched with remote debugging on port $port"
}

# Helper function to launch Figma from WSL2
launch-figma() {
  "$MCP_FIGMA_PATH" &
  echo "Figma launched"
}

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion


===============================================================

 "figma/mcp-server-guide": {
      "type": "http",
      "url": "http://127.0.0.1:3845/mcp",
      "gallery": "https://api.mcp.github.com/2025-09-15/v0/servers/26cb5bb7-a100-4f25-9a92-086ba4037345",
      "version": "1.0.0",
      "env": {
        "FIGMA_DESKTOP_PATH": "/mnt/c/Users/lucasfigueiredo.bhs/AppData/Local/Figma/Figma.exe"
      }
    },

    "chromedevtools/chrome-devtools-mcp": {
      "type": "stdio",
      "command": "npx",
      "args": [
        "-y",
        "chrome-devtools-mcp@latest",
        "--headless",
        "false",
        "--isolated",
        "true",
        "--channel",
        "stable"
        // Do NOT include --browserUrl unless you actually set one
      ],
      "env": {
        "CHROME_PATH": "C:/Program Files/Google/Chrome/Application/chrome.exe"
      },
      "gallery": "https://api.mcp.github.com/2025-09-15/v0/servers/13749964-2447-4c31-bcab-32731cced504",
      "version": "0.0.1-seed"
    }


