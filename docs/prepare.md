开发环境准备
===

ubuntu 16.04
---
buildroot编译需要在Linux环境下，我们以ubuntu 16.04为例，安装完成后，请先安装 build-essential，git，等软件包．buildroot在编译过程中，如果遇到缺少的系统软件包，它会停止编译，并且给出提示．

buildroot的编译过程，会从各个第三方网站下载软件包到 dl 目录下，所以编译 buildroot 时要保证 Internet 连接．对于大陆用户，由于众所周知的原因，可能会遇到个别软件包不能下载，这时您可以选择翻墙，或者到 [github.com/c-sky/tools/dl](https://github.com/c-sky/tools/tree/master/dl) 找一下，我將部分软件包放在这里供大家下载，请把它们拷贝到你 buildroot 目录下的 dl 目录里即可．

docker
---
buildroot 原生支持 docker-debian，它的自动化测试框架就是建立在 gitlab docker 环境上的．

```bash
image: debian:stable
before_script:
    - dpkg --add-architecture i386
    # The container has no package lists, so need to update first
    - apt-get update -qq
    - apt-get install -y -qq --no-install-recommends
        build-essential locales bc ca-certificates file rsync gcc-multilib
        git bzr cvs mercurial subversion libc6:i386 unzip wget cpio
    # To be able to generate a toolchain with locales, enable one UTF-8 locale
    - sed -i 's/# \(en_US.UTF-8\)/\1/' /etc/locale.gen
    - /usr/sbin/locale-gen
```

以上就是 docker-debian 中安装的软件包，docker 用户可以参考它完成对 docker 的配置．

对gitlab docker 完整的配置是 buildroot 源码根目录下的 [.gitlab-ci.yml](https://github.com/c-sky/buildroot/blob/master/.gitlab-ci.yml) 文件
