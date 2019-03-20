* 编译真的很简单:

```bash
git clone https://github.com/c-sky/buildroot.git
cd buildroot
make csky_gx6605s_br_defconfig
make
```
* 一共有两个配置可供选择:

csky_gx6605s_br_defconfig | 使用串口作为终端
csky_gx6605s_fbcon_br_defconfig | 使用HDMI作为终端

[运行](quick-run.md)

[返回gx6605s.md](gx6605s.md)
