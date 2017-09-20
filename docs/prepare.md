开发环境准备
===

64位 ubuntu 16.04
---
我们以64位 ubuntu为例，请安装以下软件包

```bash
sudo apt-get install  build-essential git lzip ncurses-dev minicom
```

buildroot在编译过程中，如果遇到缺少的系统软件包，它会停止编译，并给出提示．

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

[返回gx6605s.md](gx6605s.md)

