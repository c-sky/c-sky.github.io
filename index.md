C-SKY Linux Arch 介绍:
===

>C-SKY CPU 体系结构是由杭州中天微开发的，其中 Linux Arch 支持的 C-SKY CPU 有 CK610 CK807 CK810, CK610是C-SKY V1指令集是在mcore处理器改进而来，CK807/810 是C-SKY V2指令集，自主研发的16/32位混编指令集架构．

>C-SKY Linux Arch 项目的目标是在 linux 内核里支持 C-SKY 体系结构，现在 linux/arch/csky 目录仍然单独维护在 [github](https://github.com/c-sky/csky-linux) 仓库里，计划在2017年底提交至 linux 主线．以 arch/csky 这个目录单独建立仓库维护，而不是整个内核源码树，目的是使自己仓库轻量话，方便跟踪 linux-master ．使用的时候將它拷贝到 linux 内核官方源码 arch 目录下即可，这也是得益于Linux内核良好的组织结构．

>为了方便大家体验 C-SKY Linux 我们准备了 [buildroot](https://buildroot.org) ，buildroot使用方便，功能强大．用它可以方便的构建 linux 嵌入式系统开发环境．虽然我们初步將 C-SKY 体系结构提交至buildroot-master，但想体验最新 gx6605s 开发板，还是要从 [github.com/c-sky/buildroot](https://github.com/c-sky/buildroot) 下载．github/buildroot 的 master 代码是经过 gitlab.com/c-sky CI 测试通过再同步上去的，是有保障的，所以我们推荐您直接使用 github/buildroot 上的 master 最新代码．后续我们也会更新buildroot官网master的代码．

基于 C-SKY CPU 的开发板:
===

<img src="images/gx6605s_0.png" width=150>

* [gx6605s 开发板介绍](boards/gx6605s.md)
