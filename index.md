# C-SKY buildroot 介绍

C-SKY的linux输出目前利用 [https://buildroot.org](https://buildroot.org) ， 这样用户可以用最少的时间， 构建完整的 C-SKY linux开发环境。

包括： 内核， 根文件系统， 各种调试工具， 软件包。 并且完全遵循buildroot规范。

# 快速上手

我们以ubuntu16.04为例，请确认已安装build-essential等基础开发包，如果缺少组件，buildroot会有提示。网上资料较多，这里不再赘述

## 获取源码
$ git clone git@github.com:c-sky/buildroot.git

## 编译
$ cd buildroot<br>
$ make csky_gx6605s_defconfig<br>
$ make<br>

按照buildroot的规范，我们准备了readme.txt, 例如：<br>
board/csky/gx6605s/readme.txt<br>
board/csky/sc8925/readme.txt<br>
