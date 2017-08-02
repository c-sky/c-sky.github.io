运行
===

编译完成后，在 output/images 目录下会生成:

boot.vfat | vfat分区镜像，含有linux内核(uImage)和设备树 gx6605s.dtb 文件
uImage | linux内核镜像
gx6605s.dtb | 设备树编译后的二进制文件
rootfs.ext2/ext4 | 跟文件系统分区的镜像
usb.img | 由 boot.vfat 和 rootfs.ext2/ext4 共同组成的U盘完整镜像，包含了分区表信息

制作U盘镜像
---
在ubuntu 16.04下有两种方法

* 使用 Startup Disk Creator 图形化软件，选择 usb.img 作为 Source disc image，在 Disk to use 中选择U盘，然后点击右下角 Make Startup Disk，开始烧录．

<img src="/images/prepare_usb_drive.png" alt="uart" />

* 使用 dd 命令，在 bash 执行:

```bash
sudo umount /dev/sdb;
sudo dd if=usb.img of=/dev/sdb bs=8192;
sync;
```

注意 sdb (也可能是sdc或sdd等等)，这是整个U盘，而不是一个分区，所以执行这个命令千万小心，不要操作到你的系统盘．显然使用图形化的专用烧录工具更安全．

运行
---

* csky_gx6605s_defconfig 配置文件，使用串口作为默认终端，將U盘插在板子上，將micro-usb线连接在COM口，如下图所示:

<img src="/images/gx6605s_2.jpg" alt="uart" height="480" />

  板上集成了usb转串口芯片，ubuntu 16.04 自带驱动，可以直接使用 minicom:

```bash
sudo minicom -D /dev/ttyUSB0
```
  minicom设置为115200-8N1 关闭流控制 (ctrl+A 键再按 O 键，选择第三行 Serial port setup 进行设置)


* 如果你是 csky_gx6605s_fbcon_defconfig 配置文件，插上电源 USB键盘 HDMI，就可以用了，参考 [诛仙剑开发板介绍](gx6605s.md)
