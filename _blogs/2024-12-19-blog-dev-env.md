---
title: 'Ubuntu Development Environment'
date: 2024-12-18
permalink: /blogs/dev-env/
tags:
  - development
---

This blog details the steps to configure and install my usual development environment on Ubuntu 20.04.  

### System Update
```
sudo apt-get update
sudo apt-get upgrade -y
```  

### Build Essential
```
sudo apt-get install build-essential -y
sudo apt-get install git -y
```

### Terminal Tools
#### Terminator
`sudo apt-get install terminator -y`

#### Zsh
`sudo apt-get install zsh -y`  
Set zsh as default:
`chsh -s /bin/zsh`

#### Oh my zsh  
* Auto installation:  
```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```  
* Manual installation:  
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```
* Modify preference in `~/.zshrc`
```
ZSH_THEME="ys"
```

### zsh-syntax-highlighting  
* Clone the repository  
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
* Modify preference in `~/.zshrc`  
```
plugins=(... zsh-syntax-highlighting)
```
* Validate it by reopening a terminator or `source ~/.zshrc`

### zsh-autosuggestions  
* Clone the repository  
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
* Modify preference in `~/.zshrc`  
```
plugins=(... zsh-autosuggestions)
```
* Validate it by reopening a terminator or `source ~/.zshrc`

### Install IDE: VS Code
Official download link: https://code.visualstudio.com/download
##### IntelliSense and Autocompletion
In the console (press F1), search for C/C++: Edit Configurations, and configure the Include path in IntelliSense Configurations to enable autocompletion for std, OpenCV, etc.
```
${workspaceFolder}/**
/usr/include/**
/usr/local/include/**
```

### git difftool
* **meld**
```
sudo apt-get install meld
git config --global diff.tool meld
```

