编译真的很简单: 下载源码，选择配置，make!

```bash
git clone git@github.com:c-sky/buildroot.git
cd buildroot
make csky_gx6605s_defconfig
make
```

**csky_gx6605s_defconfig** 配置文件是使用串口的，如果想像照片里那样使用 framebuffer 终端，请使用 **csky_gx6605s_fbcon_defconfig** 配置文件.

[运行](quick-run.md)
