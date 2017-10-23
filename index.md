C-SKY Linux Arch 介绍:
===

* C-SKY CPU体系结构由杭州中天微系统有限公司开发。Linux Arch 支持的 C-SKY CPU有: CK807和CK810，使用C-SKY V2指令集。

* 为了方便大家体验 C-SKY Linux 我们准备了 [buildroot](https://buildroot.org) ，buildroot 使用方便，功能强大．用它可以方便地构建 linux 嵌入式系统开发环境．我们已將 C-SKY 体系结构提交至 buildroot-master，但还是初版，所以请大家从 [github.com/c-sky/buildroot](https://github.com/c-sky/buildroot) 下载最新C-SKY buildroot 代码．
github.com/c-sky/buildroot 的 master 分支是通过 [gitlab.com/c-sky](https://gitlab.com/c-sky) CI 自动化测试后才同步上去的，所以我们推荐您直接使用 master 最新代码．同时我们也会持续更新 buildroot 官网的主干代码，感谢 buildroot 的 gitlab 自动化集成方案．

* [uClibc-ng](https://uclibc-ng.org) 是我们重点推荐的C库，它的特点是小巧，精悍．非常契合 C-SKY Linux Iot 的小目标．

基于 C-SKY CPU 的开发板:
---

| **[诛仙剑开发板介绍](docs/gx6605s.md)**<br>**[点此购买](https://item.taobao.com/item.htm?spm=a1z10.1-c.w4004-13250088290.6.4b1f9628jKW8o8&id=556322544984)** | <img src="images/gx6605s_0.gif" alt="gx6605s" /> | <img src="http://www.nationalchip.com/static/web/img/logo.png" alt="NationalChip" /> |

/* | **[CK-Eragon开发套件](docs/eragon.md)** | <img src="images/eragon_0.gif" alt="eragon" /> | <img src="images/eragon_logo.png" alt="Eragon" /> | */

