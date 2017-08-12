内核编译
---
* buildroot封装了对内核编译和配置，也符合buildroot的包管理的规则。
* 例如: 在 buildroot目录下，您可以执行 make linux-menuconfig 进行内核配置，前提是你已经编译过buildroot了。执行 make linux-rebuild 对内核重新编译。

* 更详细的内容，请参考 [The Buildroot user manual](https://buildroot.org/downloads/manual/manual.html) 的 [Chapter 7. Configuration of other components](https://buildroot.org/downloads/manual/manual.html#_configuration_of_other_components)

内核调试
---
> gx6605s 的 buildroot 已经集成了 Jtag-Derver 软件包。

* 启动 Jtag-DebugServer
```bash
$ cd output/host/csky-debug
$ sudo ./DebugServerConsole.elf -ddc -rstwait 1000 -prereset -port 1025
 (运行后终端里会显示: target jtag jtag://127.0.0.1:1025)
```

* 用 gdb 连接 Jtag-DebugServer
```bash
$ cd output/images
$ ../host/usr/bin/csky-linux-gdb -x ../../board/nationalchip/gx66xx/gdbinit ../build/<Linux内核目录>/vmlinux
```

注意 gdbinit 的 IP 和 Port 要和DebugServer里的一致.

[返回gx6605s.md](gx6605s.md)
