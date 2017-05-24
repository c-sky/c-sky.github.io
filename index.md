# C-SKY buildroot 介绍

C-SKY使用buildroot向用户发布linux

目的：以最少的时间， 构建完整的 C-SKY linux开发环境。
包括： 内核， 根文件系统， 各种调试工具， 软件包。 并且完全遵循 https://buildroot.org 规范。

## 在ubuntu下，只需以下几步：
$ git clone git@github.com:c-sky/buildroot.git<br>
$ cd buildroot<br>
$ make csky_gx6605s_defconfig<br>
$ make<br>

## README
按照buildroot的规范，我们准备了readme.txt, 例如：<br>
board/csky/gx6605s/readme.txt<br>
board/csky/sc8925/readme.txt<br>
