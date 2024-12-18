---
title: 'Useful Ubuntu Tools'
date: 2024-12-18
permalink: /blogs/ubuntu-tools/
tags:
  - development
---

### 工具一：输入法
#### 谷歌拼音输入法
1. 在Ubuntu Software Center中搜索googlepinyin安装  
或者  
`sudo apt-get install fcitx-googlepinyin -y`  
2. 安装完成后进入右上角->System Settings->Language Support进行更新，更新完成后将keyboard input method system设置为fcitx。  
3. 注销后重新登录。  
4. 右上角->System Settings -> Keyboard，左下角Text Entry，点“+”，搜索google，添加google输入法。  
5. 使用鼠标控制右上角的键盘或者Ctrl + Space触发google输入法。  

### 工具二：有道词典
官网下载地址：http://cidian.youdao.com/index-linux.html  
有道词典多平台下载地址：http://cidian.youdao.com/multi.html  
***

### 工具三：Kazam（录屏、截屏）
在Ubuntu Software Center中搜索Kazam安装即可。
***

### 工具五：XMind
官网下载地址：http://www.xmind.net/download/linux/  
如果是压缩包则下载完毕后解压，进行安装  
`sudo sh setup.sh`  
如果是deb安装包，直接双击安装即可。
***

### 工具六：google chrome（浏览器）
官网下载地址：https://www.google.com/intl/en/chrome/browser/desktop/  
或者使用终端：  
`wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb`  
可下载得到deb安装包，点击安装即可。
***

### 工具七：VS Code
官网下载地址：https://code.visualstudio.com/download
##### 智能提示及补全
控制台（按F1）搜索C/C++:Edit Configurations，进入IntelliSense Configurations对Include path进行配置，从而实现对std、OpenCV等的智能提示及补全。
```
${workspaceFolder}/**
/usr/include/**
/usr/local/include/**
```
***

### 工具八：Terminator
`sudo apt-get install terminator`
***

### 工具九：Zsh
`sudo apt-get install zsh`  
修改zsh为默认:
`chsh -s /bin/zsh`
***

### 工具十：Oh my zsh  
* 自动安装：  
```
wget https://github.com/robbyrussell/oh-my-zsh/raw/master/tools/install.sh -O - | sh
```  
* 手动安装：
```
git clone git://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```
* 偏好参数
```
ZSH_THEME="ys"
```
***

### 工具十一：zsh-syntax-highlighting  
**克隆项目**  
```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting
```
**配置**  
```
plugins=(其他的插件 zsh-syntax-highlighting)
```
**生效**  
```
source ~/.zshrc
```
***

### 工具十二：zsh-autosuggestions  
**克隆项目**
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
**配置**
```
plugins=(其他的插件 zsh-autosuggestions)
```
**生效**
```
source ~/.zshrc
```
***

### 工具十三：常用包管理命令
```
# 提供C/C++的编译环境
sudo apt-get install build-essential

# 删除已安装包，不保留配置文件
apt-get –purge remove

# 删除为了满足依赖而安装的，但现在不再需要的软件包（包括已安装包）
apt-get autoremove

# 删除已安装的软件包，保留配置文件
apt-get remove

# 只会删除 /var/cache/apt/archives/ 已经过期的deb
# APT的底层包是dpkg, 而dpkg安装Package时, 会将 *.deb 放在 /var/cache/apt/archives/中
apt-get autoclean .

#将 /var/cache/apt/archives/ 的 所有 deb 删掉
apt-get clean

# 如果是彻底卸载软件，推荐使用apt-get –purge remove,不推荐使用autoremove，因为你删除该依赖软件包，也可能被其他软件包所依赖，从而导致其他软件不可用。
# 如果是清理硬盘，推荐使用apt-get autoclean，deb安装后基本上就没多大用了，完全可以删除掉。
```
***

### 工具十四：WPS
* *(optional)* 清除自带LibreOffice
```
sudo apt-get remove --purge libreoffice*
```
* 安装WPS
官网下载地址：https://www.wps.cn/product/wpslinux
***

### 工具十五：git difftool
* **meld**
```
sudo apt-get install meld
git config --global diff.tool meld
```
***

### 工具十六：Typora
```
# or run:
# sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE
wget -qO - https://typoraio.cn/linux/public-key.asc | sudo apt-key add -
# add Typora's repository
sudo add-apt-repository 'deb https://typoraio.cn/linux ./'
sudo apt-get update
# install typora
sudo apt-get install typora
```
* 官网下载地址：https://typoraio.cn/#linux
***
