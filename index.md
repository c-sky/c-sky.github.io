# C-SKY buildroot 介绍

C-SKY使用buildroot向用户发布linux

目的：以最少的时间， 构建完整的 C-SKY linux开发环境。 <br>
包括： 内核， 根文件系统， 各种调试工具， 软件包。 <br>
并遵循 https://buildroot.org 规范。

## 在ubuntu 16.04 64位上，只需4步：
$ git clone git@github.com:c-sky/buildroot.git<br>
$ cd buildroot<br>
$ make csky_gx6605s_defconfig<br>
$ make<br>

## 编译问题汇总
请使用64位ubuntu系统<br>
对于中国大陆用户，如果遇到不能下载的软件包，可以到 https://github.com/c-sky/tools/tree/master/dl 下找找，拷贝到buildroot/dl目录下。

## README
按照buildroot的规范，我们准备了readme.txt, 例如：<br>
board/csky/gx6605s/readme.txt<br>


## C-SKY buildroot 开发板

