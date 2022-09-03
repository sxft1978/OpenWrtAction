
[![Lean](https://img.shields.io/badge/SourceCode-Lean-green?style=flat&logo=GitHub)](https://github.com/coolsnowwolf/lede) [![releases](https://img.shields.io/badge/UpdateCheck-blueviolet?style=flat&logo=Checkmarx)](https://github.com/smallprogram/OpenWrtAction/releases) [![LICENSE](https://img.shields.io/badge/LICENSE-MIT-important?style=flat)](https://github.com/smallprogram/OpenWrtAction/blob/main/LICENSE)


## WorkFlows
|ActionStatus|
|-|
|[![Build-OpenWrt_X64](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_X64.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_X64.yml)|
|[![Build-OpenWrt_R2C](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R2C.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R2C.yml)|
|[![Build-OpenWrt_R2S](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R2S.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R2S.yml)|
|[![Build-OpenWrt_R4S](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R4S.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R4S.yml)|
|[![Build-OpenWrt_R5S](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R5S.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_R5S.yml)|
|[![Build-OpenWrt_Pi4_Model_B](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_Pi4_Model_B.yml/badge.svg)](https://github.com/smallprogram/OpenWrtAction/actions/workflows/build-openwrt_Pi4_Model_B.yml)|




# [English Readme](README_EN.md)

# [最新固件列表，点击自取](https://github.com/smallprogram/OpenWrtAction/tags)

# 感觉不错的话，给个Star吧

# 目录<!-- omit in toc --> 
- [新增TG跟Wechat推送说明](source/bot.md)
- [Lean Openwrt GitHubAction](#lean-openwrt-githubaction)
    - [目前包含x86与ARM固件,根据源码更新自动编译](#目前包含x86与ARM固件根据源码更新自动编译)
  - [包含内容](#包含内容)
      - [包含各种常用插件，特殊的内容如下：](#包含各种常用插件特殊的内容如下)
  - [config列表](#config列表)
  - [argon主题的背景资源](https://github.com/smallprogram/OpenWrtAction/tree/main/source)
  - [具体功能组件相关截图：](#具体功能组件相关截图)
  - [wsl2op.sh本地自动编译shell脚本说明](#wsl2opsh本地自动编译shell脚本说明)
    - [执行方式](#执行方式)
      - [首次执行](#首次执行)
      - [二次执行](#二次执行)
    - [执行过程详解](#执行过程详解)

# Lean Openwrt GitHubAction

![image](source/login.gif)

![image](source/login2.jpg)
### 根据源码更新自动编译


## 包含内容

#### 包含各种常用插件，特殊的内容如下：

> 移除一系列下载工具

|名称|类型|简介|源码地址
-|-|-|-
|SSRP(Xray内核)|插件|Lean源码的亲儿子，评测说效率最高|https://github.com/fw876/helloworld|
|PassWall|插件|一款功能强大的科学工具|https://github.com/xiaorouji/openwrt-passwall|
|PassWall2|插件|一款功能强大的科学工具|https://github.com/xiaorouji/openwrt-passwall2|
|DockerMan|插件|OP上玩Docker的必备插件|https://github.com/lisaac/luci-app-dockerman|
|新版argon主题|主题|十分漂亮的OP主题|https://github.com/jerrykuku/luci-theme-argon|
|Argon Config|插件|新版argon主题的设置插件|https://github.com/jerrykuku/luci-app-argon-config|
|AdguardHome|插件|屏蔽广告插件|https://github.com/rufengsuixing/luci-app-adguardhome.git|
|广告屏蔽大师Plus+|插件|屏蔽广告插件|lean code source|
|京东签到|插件|白嫖京豆插件|lean code source|
|PushPlus全能推送|插件|钉钉、企业微信推送、Bark、PushPlus各种推送|https://github.com/zzsj0928/luci-app-pushbot|
|网易云音乐Unlock|插件|周杰伦出现在网易云音乐|lean code source|
|UU加速器|插件|土豪玩家必备插件，加速PS5 Switch等|lean code source|
|FRP|插件|内网穿透|lean code source|
|MWAN3|插件|多线的负载均衡|lean code source|
|OpenVPN Server|服务|OpenVPN服务端|lean code source|
|PPTP VPN Server|服务|PPTP VPN服务端|lean code source|
|IPSec VPN Server|服务|IPSec VPN服务端|lean code source|
|ZeroTier|插件|内网穿透工具|lean code source|
|多线多播|插件|多线多播工具|lean code source|
|Turbo ACC|插件|网络加速器|lean code source|
|vim|工具|Linux 系统上一款文本编辑器，它是操作Linux 的一款利器|lean code source|
|nano|工具|比vi/vim要简单得多，比较适合Linux初学者使用|lean code source|
|Openssh-sftp-server|服务|sshd内置的SFTP服务器|lean code source|

## config列表
|适用平台|KERNEL大小|ROOTFS大小|地址|
-|-|-|-
X86平台|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/x64.config|
Pi4_Model_B|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/Pi4_Model_B.config
R5S软路由|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/R5S.config
R4S软路由|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/R4S.config
R2S软路由|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/R2S.config
R2C软路由|128Mb|1024Mb|https://github.com/smallprogram/OpenWrtAction/blob/main/config/R2C.config



## 具体功能组件相关截图：
![image](source/function.png)


## wsl2op.sh本地自动编译shell脚本说明

运行前请确保你的编译环境已经安装Lean源码中要求的编译环境，并且使用非root用户执行。如果未满足Lean源码编译环境要求，请执行如下命令:
```shell
sudo apt update -y
sudo apt full-upgrade -y
sudo apt install -y ack antlr3 asciidoc autoconf automake autopoint binutils bison build-essential \
bzip2 ccache cmake cpio curl device-tree-compiler fastjar flex gawk gettext gcc-multilib g++-multilib \
git gperf haveged help2man intltool libc6-dev-i386 libelf-dev libglib2.0-dev libgmp3-dev libltdl-dev \
libmpc-dev libmpfr-dev libncurses5-dev libncursesw5-dev libreadline-dev libssl-dev libtool lrzsz \
mkisofs msmtp nano ninja-build p7zip p7zip-full patch pkgconf python2.7 python3 python3-pip libpython3-dev qemu-utils \
rsync scons squashfs-tools subversion swig texinfo uglifyjs upx-ucl unzip vim wget xmlto xxd zlib1g-dev
```

### 执行编译方式(非Root用户)

```shell
cd /home/$USER && (if [ ! -d "/home/$USER/OpenWrtAction" ]; then git clone https://github.com/smallprogram/OpenWrtAction.git; else cd /home/$USER/OpenWrtAction; git stash; git stash drop; git pull; fi;) && cd /home/$USER/OpenWrtAction && bash wsl2op.sh
```



