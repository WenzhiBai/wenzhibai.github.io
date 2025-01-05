---
title: 'Ubuntu Development Environment'
date: 2024-12-19
permalink: /blogs/dev-env/
tags:
  - development
---

This blog details the steps to configure and install my usual development environment on Ubuntu 20.04.

## 1. System Update
```
sudo apt update
sudo apt upgrade -y
```  

## 2. Build Essential
```
sudo apt install build-essential -y
sudo apt install git -y
```

## 3. Terminal Tools
### 3.1. Terminator
```
sudo apt install terminator -y
```

### 3.2. Zsh
```
sudo apt install zsh -y  
```
Set zsh as default:
```
chsh -s /bin/zsh  
```

### 3.3. Oh my zsh  
* Auto installation:  
```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```  
* Manual installation:  
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```
* Modify preferences in `~/.zshrc`, for example:
  * Change the theme:
    ```
    ZSH_THEME="ys"
    ```
  * Add plugins:
    ```
    plugins=(git zsh-syntax-highlighting zsh-autosuggestions)
    ```
  * Set aliases:
    ```
    alias ll='ls -la'
    alias gs='git status'
    ```

### 3.4. zsh-syntax-highlighting  
* Clone the repository  
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
* Modify preference in `~/.zshrc`  
```
plugins=(... zsh-syntax-highlighting)
```
* Validate it by reopening a terminator or `source ~/.zshrc`

### 3.5. zsh-autosuggestions  
* Clone the repository  
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
* Modify preference in `~/.zshrc`  
```
plugins=(... zsh-autosuggestions)
```
* Validate it by reopening a terminator or `source ~/.zshrc`

## 4. IDE: VS Code
[Official download link](https://code.visualstudio.com/download)
### 4.1. Login to load settings, like extensions
### 4.2. IntelliSense and Autocompletion
In the console (press F1), search for C/C++: Edit Configurations, and configure the Include path in IntelliSense Configurations to enable autocompletion for std, OpenCV, etc.
```
${workspaceFolder}/**
/usr/include/**
/usr/local/include/**
```

## 5. git difftool: meld
```
sudo apt install meld -y
git config --global diff.tool meld
git config --global difftool.prompt false
```
To use `meld` as a git difftool, you can run `meld` in everywhere and `git difftool` in your repository to compare changes.  

You can also use `meld` to compare specific commits or branches in your repository:  
```
git difftool <commit1> <commit2>
git difftool <branch1> <branch2>
```

## 6. ROS: Noetic
ROS Noetic Ninjemys is a distribution of ROS 1, available for Ubuntu Focal Fossa (20.04).  
[Installation Instructions](https://wiki.ros.org/noetic/Installation/Ubuntu)
