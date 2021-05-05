---
title: CentOS7使用手记
date: 2021-05-05 22:59:56
tags:
  - CentOS
  - Linux
  - Learn
---

## RPM使用

```bash
# 检查安装了关键词“code”的软件
rpm -qa | grep code

# 卸载软件
sudo rpm -e code-insiders-1.56.0-1619504838.el8.x86_64
```

## YUM使用

```bash
# 查询code相关软件
yum list | grep code

# 查询版本信息
yum --showduplicates list code | expand

# 安装指定版本
sudo yum install code-1.49.3-1601661990.el7

您需要给出命令
Usage: yum [options] COMMAND

List of Commands:

check          检查 RPM 数据库问题
check-update   检查是否有可用的软件包更新
clean          删除缓存数据
deplist        列出软件包的依赖关系
distribution-synchronization 已同步软件包到最新可用版本
downgrade      降级软件包
erase          从系统中移除一个或多个软件包
fs             Acts on the filesystem data of the host, mainly for removing docs/lanuages for minimal hosts.
fssnapshot     Creates filesystem snapshots, or lists/deletes current snapshots.
groups         显示或使用、组信息
help           显示用法提示
history        显示或使用事务历史
info           显示关于软件包或组的详细信息
install        向系统中安装一个或多个软件包
langavailable  Check available languages
langinfo       List languages information
langinstall    Install appropriate language packs for a language
langlist       List installed languages
langremove     Remove installed language packs for a language
list           列出一个或一组软件包
load-transaction 从文件名中加载一个已存事务
makecache      创建元数据缓存
provides       查找提供指定内容的软件包
reinstall      覆盖安装软件包
repo-pkgs      将一个源当作一个软件包组，这样我们就可以一次性安装/移除全部软件包。
repolist       显示已配置的源
search         在软件包详细信息中搜索指定字符串
shell          运行交互式的 yum shell
swap           Simple way to swap packages, instead of using shell
update         更新系统中的一个或多个软件包
update-minimal Works like upgrade, but goes to the 'newest' package match which fixes a problem that affects your system
updateinfo     Acts on repository update information
upgrade        更新软件包同时考虑软件包取代关系
version        显示机器和/或可用的源版本。
remove         删除相关软件
```

## 开启图形界面

- https://www.jianshu.com/p/20268756611e

```bash
yum groupinstall "X Window System"
yum groupinstall "GNOME Desktop"

## dos界面与图形化界面切换快捷键
## - 图形到dos：ctrl+alt+f2
## - dos到图形：输入startx
```

## 安装开发环境

### 安装基础工具

```bash
# TODO: oh my zsh安装

# nodejs相关
yum install nvm
```

## CentOS安装Chrome

```bash
vim  /etc/yum.repos.d/google-chrome.repo

# 内容如下

[google-chrome]
name=google-chrome - \$basearch  
baseurl=http://dl.google.com/linux/chrome/rpm/stable/\$basearch  
enabled=1  
gpgcheck=0  

# 然后运行
yum install google-chrome-stable
```

## 安装WPS

```bash
# 访问： https://linux.wps.cn/
sudo yum install mesa-libGLU
sudo yum install libXss* -y
sudo rpm -ivh wps-office-11.1.0.10161-1.x86_64.rpm
```

## 按照VMware

```bash
下载地址： https://www.vmware.com/products/workstation-pro/workstation-pro-evaluation.html

ZF3R0-FHED2-M80TY-8QYGC-NPKYF
YF390-0HF8P-M81RQ-2DXQE-M2UT6
ZF71R-DMX85-08DQY-8YMNC-PPHV8
```
