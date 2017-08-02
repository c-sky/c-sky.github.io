编译真的很简单: 下载源码，选择配置，make!

```bash
git clone git@github.com:c-sky/buildroot.git
cd buildroot
make csky_gx6605s_defconfig
make
```

csky_gx6605s_defconfig | 使用串口作为默认终端
csky_gx6605s_fbcon_defconfig | 使用 framebuffer console 作为默认终端，就像照片里那样.

请按自己的需要进行选择

[运行](quick-run.md)
