# Linux内核 arch/csky 项目介绍

项目目标：<br>
在Linux 内核里支持 C-SKY 指令集 （www.c-sky.com） CPU <br>
就像linux内核arch目录下的其他CPU体系结构: x86, arc, arm, mips ...<br>
为了让大家更容易的体验 csky-linux，我们准备了buildroot。<br>

# C-SKY buildroot 介绍

目的：以最少的时间， 构建完整的 C-SKY linux开发环境。 <br>
包括： 内核， 根文件系统， 各种调试工具， 软件包。 <br>
并遵循 https://buildroot.org 规范。

## 以gx6605s开发板为例， 在ubuntu 16.04 64位上，编译只需4步：
$ git clone git@github.com:c-sky/buildroot.git<br>
$ cd buildroot<br>
$ make csky_gx6605s_defconfig<br>
$ make<br>

## README： board/nationalchip/gx66xx/readme.txt

## 编译问题汇总
请使用64位ubuntu系统<br>
对于中国大陆用户，如果遇到不能下载的软件包，可以到 ［github.com/c-sky/tools/dl］（https://github.com/c-sky/tools/tree/master/dl） 下找找，拷贝到buildroot/dl目录下。

# gx6605s开发板，　快速体验
## 准备启动U盘，（它包含了内核根文件系统）
你可以在gitlab上下载最新编译好的bin，例如： https://gitlab.com/c-sky/buildroot/-/jobs/22301421/artifacts/file/output/images/usb.img<br>
dd if=usb.img of=/dev/sdb bs=8192 (usb.img包含２个分区，一定要烧写整个U盘)

## 连接HDMI，插上U盘和USB鼠标键盘，插上一根micro-USB 5V电源线

