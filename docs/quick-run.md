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

* 使用 Startup Disk Creator 烧录U盘，选择 usb.img 作为 Source disc image，在 Disk to use 中选择U盘，然后点击右下角 Make Startup Disk，开始烧录．

<img src="/images/prepare_usb_drive.png" alt="uart" />

* 高阶linux用户，可以使用 dd 命令暴力烧录U盘，在 bash 执行:

```bash
sudo dd if=usb.img of=/dev/sdb bs=8192;
sync;
sync执行结束立即拔掉盘，别犹豫！！
```

注意 sdb 是整个U盘，而不是分区 (也可能是sdc或sdd等等)。执行这个命令要特别小心，不要操作到你的系统盘。

运行
---

* **csky_gx6605s_defconfig** 配置文件，使用串口作为默认终端，將U盘插在板子上，將micro-usb线连接在COM口，如下图所示:

<img src="/images/gx6605s_2.jpg" alt="uart" />

  板上集成了usb转串口芯片，ubuntu 16.04 自带驱动，可以直接使用 minicom:

```bash
sudo minicom -D /dev/ttyUSB0
```
  minicom设置为115200-8N1 关闭流控制 (ctrl+A 键再按 O 键，选择第三行 Serial port setup 进行设置)


* **csky_gx6605s_fbcon_defconfig** 配置文件，使用 HDMI framebuffer Console，插上 micro-usb 电源 USB键盘 HDMI，就可以用了，请参考 [诛仙剑开发板介绍](gx6605s.md)

有线网络
---

* 默认开启了rtl8152 usb有线网卡的支持，直接插上，用ifconfig -a 命令就可以看到 eth0．

```bash
/* 获取 DHCP */
$udhcpc -i eth0
```

无线网络
---
* 内置了mt7601u WIFI linux 内核开源驱动，稳定性欠佳．在我的ubuntu x86 上测试，连接wifi一整个晚上，第二天会内核崩溃．
* 改善办法是，使用mtk商用驱动．
* 目前我们也在寻找，便宜好用的 usb-wifi 解决方案，也希望随着新内核的升级，能够解决此问题．

```bash
/* 加载驱动 */
$modprobe mt7601u
/* 设置连接 AP 密码 */
$wpa_passphrase qa_test3_d300 12345678 >> /etc/wpa_supplicant.conf
/* 启动wifi连接 */
$wpa_supplicant -Dnl80211 -iwlan0 -c /etc/wpa_supplicant.conf -B
/* 获取 DHCP */
$udhcpc -i wlan0
```

[返回gx6605s.md](gx6605s.md)
