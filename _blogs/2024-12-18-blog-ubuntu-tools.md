---
title: 'Useful Ubuntu Tools'
date: 2024-12-18
permalink: /blogs/ubuntu-tools/
tags:
  - development
---

This blog collects some useful Ubuntu tools for me.  

## 1. 输入法-谷歌拼音输入法
1. 在Ubuntu Software Center中搜索googlepinyin安装  
或者  
`sudo apt install fcitx-googlepinyin -y`  
1. 安装完成后进入右上角->System Settings->Language Support进行更新，更新完成后将keyboard input method system设置为fcitx。  
2. 注销后重新登录。  
3. “右上角->System Settings->Keyboard，左下角Text Entry”或者“在系统中查找fcitx configuration”，进入配置后点“+”，搜索google（若查找不到注意取消“仅查找当前语言”选项），添加google输入法。  
4. 使用鼠标控制右上角的键盘或者Ctrl + Space触发google输入法。  

## 2. 有道词典
官网下载地址：http://cidian.youdao.com/index-linux.html  
有道词典多平台下载地址：http://cidian.youdao.com/multi.html  

## 3. Kazam（录屏、截屏）
在Ubuntu Software Center中搜索Kazam安装即可。

## 4. XMind
官网下载地址：http://www.xmind.net/download/linux/  
如果是压缩包则下载完毕后解压，进行安装  
`sudo sh setup.sh`  
如果是deb安装包，直接双击安装即可。

## 5. google chrome（浏览器）
官网下载地址：https://www.google.com/intl/en/chrome/browser/desktop/  
或者使用终端：  
`wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb`  
可下载得到deb安装包，点击安装即可。

## 6. VS Code
### 6.1. 官网下载
地址：https://code.visualstudio.com/download
### 6.2. 智能提示及补全
控制台（按F1）搜索C/C++:Edit Configurations，进入IntelliSense Configurations对Include path进行配置，从而实现对std、OpenCV等的智能提示及补全。
```
${workspaceFolder}/**
/usr/include/**
/usr/local/include/**
```

## 7. Clang-format for VS Code
### 7.1. Install
```
sudo apt install clang-format
```
The executable will be located in `/usr/bin/clang-format`.
### 7.2. Configuration
* Install `Clang-Format` from `VS Code Extensions Marketplace`.  

* Create a `.clang-format` file in your project root directory (or the home directory to apply it globally). Use the following configuration for Google Style:
```
BasedOnStyle: Google
IndentWidth: 2
ColumnLimit: 80
```

* Open VS Code settings (Ctrl+,):
Enable the option `Editor: Format On Save` to automatically format your code whenever you save it.  
Choose the option `Editor:Default Formatter` to `Clang-Format`.  

## 8. Terminator
`sudo apt install terminator`

## 9. Zsh
`sudo apt install zsh`  
修改zsh为默认:
`chsh -s /bin/zsh`

## 10. Oh my zsh  
### 10.1. 自动安装  
```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```  
### 10.2. 手动安装
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```
### 10.3. 偏好参数
```
ZSH_THEME="ys"
```

## 11. zsh-syntax-highlighting  
### 11.1. 克隆项目  
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
### 11.2. 配置  
```
plugins=(其他的插件 zsh-syntax-highlighting)
```
### 11.3. 生效  
```
source ~/.zshrc
```

## 12. zsh-autosuggestions  
### 12.1. 克隆项目
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
### 12.2. 配置
```
plugins=(其他的插件 zsh-autosuggestions)
```
### 12.3. 生效
```
source ~/.zshrc
```

## 13. 常用包管理命令
### 13.1. 提供C/C++的编译环境
```
sudo apt install build-essential
```

### 13.2. 删除已安装包，不保留配置文件
```
apt –purge remove
```

### 13.3. 删除为了满足依赖而安装的，但现在不再需要的软件包（包括已安装包）
```
apt autoremove
```

### 13.4. 删除已安装的软件包，保留配置文件
```
apt remove
```

### 13.5. 只会删除 /var/cache/apt/archives/ 已经过期的deb
apt的底层包是dpkg, 而dpkg安装package时, 会将 *.deb 放在 /var/cache/apt/archives/中**
```
apt autoclean
```

### 13.6. 将 /var/cache/apt/archives/ 的 所有 deb 删掉
```
apt clean
```

如果是彻底卸载软件，推荐使用`apt –purge remove`,不推荐使用`autoremove`，因为你删除该依赖软件包，也可能被其他软件包所依赖，从而导致其他软件不可用。
如果是清理硬盘，推荐使用`apt autoclean`，deb安装后基本上就没多大用了，完全可以删除掉。

## 14. WPS
### 14.1. *(optional)* 清除自带LibreOffice
```
sudo apt remove --purge libreoffice*
```
### 14.2. 安装WPS
官网下载地址：https://www.wps.cn/product/wpslinux

## 15. git difftool-meld
```
sudo apt install meld
git config --global diff.tool meld
```

## 16. Typora
### 16.1. wget
```
# download
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
wget -qO - https://typoraio.cn/linux/public-key.asc | sudo apt-key add -
# add Typora's repository
sudo add-apt-repository 'deb https://typoraio.cn/linux ./'
sudo apt update
# install typora
sudo apt install typora
```
### 16.2. 官网下载地址：https://typoraio.cn/#linux
