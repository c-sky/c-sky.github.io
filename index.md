C-SKY Linux Arch 介绍:
===

* C-SKY CPU体系结构由杭州中天微系统有限公司开发。Linux Arch 支持三款C-SKY CPU: CK610、CK807和CK810。其中CK610使用C-SKY V1指令集，16位指令编码，32位数据总线; CK807/810使用C-SKY V2指令集，为自主研发的16/32位混编指令集架构。

* C-SKY Linux Arch 项目的目标，是在Linux内核里加入对 C-SKY 体系结构的支持，现在 linux/arch/csky 目录仍然单独维护在 [github](https://github.com/c-sky/csky-linux) 仓库里，计划在2017年底提交至 linux 主线．目前 arch/csky 以单独目录仓库维护，目的是使代码仓库轻量话，方便跟踪 linux-master．使用时请將 csky 拷贝到 linux 内核源码 arch 目录下，能这样管理也是得益于 Linux 内核良好的目录结构．

* 为了方便大家体验 C-SKY Linux 我们准备了 [buildroot](https://buildroot.org) ，buildroot 使用方便，功能强大．用它可以方便地构建 linux 嵌入式系统开发环境．我们已將 C-SKY 体系结构提交至 buildroot-master，但还是初版，所以请大家从 [github.com/c-sky/buildroot](https://github.com/c-sky/buildroot) 下载最新C-SKY buildroot 代码．
github.com/c-sky/buildroot 的 master 分支是通过 [gitlab.com/c-sky](https://gitlab.com/c-sky) CI 自动化测试后才同步上去的，所以我们推荐您直接使用 master 最新代码．同时我们也会持续更新 buildroot 官网的主干代码，感谢 buildroot 的 gitlab 自动化集成方案．

* [uClibc-ng](https://uclibc-ng.org) 是我们重点推荐的C库，它的特点是小巧，精悍．非常契合 C-SKY Linux Iot 的小目标．

基于 C-SKY CPU 的开发板:
---

**[诛仙剑开发板介绍](docs/gx6605s.md)** | <img src="images/gx6605s_0.gif" alt="gx6605s" /> | <img src="http://www.nationalchip.com/static/web/img/logo.png" alt="NationalChip" />

上手指南：
---

* 快速开始
  - [开发环境准备](docs/prepare.md)
  - [编译](docs/quick-compile.md)
  - [运行](docs/quick-run.md)
* 基础
  - [buildroot功能介绍](docs/buildroot.md)
  - [启动&设备树介绍](docs/boot-dts.md)
  - [内核的调试](docs/kernel-debug.md)
  - [应用程序调试](docs/app-debug.md)
* 进阶
  - [使用-O0编译和调试内核](docs/kernel-O0.md)

