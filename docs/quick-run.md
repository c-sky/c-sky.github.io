运行
===


* 编译完成后，在 output/images 目录下会生成:

boot.vfat | vfat分区镜像，含有linux内核(uImage)和设备树 gx6605s.dtb 文件
uImage | linux内核镜像
gx6605s.dtb | 设备树编译后的二进制文件
rootfs.ext2/ext4 | 跟文件系统分区的镜像
usb.img | 由 boot.vfat 和 rootfs.ext2/ext4 共同组成的U盘完整镜像，包含了分区表信息
