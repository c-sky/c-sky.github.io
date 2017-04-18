# buildroot 介绍

buildroot官网 [https://buildroot.org](https://buildroot.org)

Buildroot 是一个简单，高效，易于使用的嵌入式系统交叉编译工具，它可以替用户编译 交叉工具链，根文件系统镜像，内核镜像， bootloader， 从而使用户可以快速搭建自己的嵌入式开发环境

# 快速上手

我们以ubuntu16.04为例，请确认已安装build-essential等基础开发包，如果缺少组件，buildroot会有提示。网上资料较多，这里不再赘述

## 获取源码
在　[https://github.com/c-sky/buildroot](https://github.com/c-sky/buildroot)　里下载最新发布源码包

## 编译
进入buildroot目录后，以gx6605s开发板为例，执行以下2条命令：<br>
$ make csky_gx6605s_defconfig<br>
$ make<br>
然后等待完成，buildroot会自动构建编译环境，编译内核和应用程序，建立根文件系统，生成最终镜像．<br>

按照buildroot的规范，我们为每块板子准备readme.txt,具体操作步骤请参考：<br>
board/csky/gx6605s/readme.txt<br>
board/csky/sc8925/readme.txt<br>
