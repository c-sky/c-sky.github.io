* buildroot封装了对内核编译和配置，也符合buildroot的包管理的规则。
* 例如: 在 buildroot目录下，您可以执行 make linux-menuconfig 进行内核配置，当然前提是你已经编译过buildroot了。执行 make linux-rebuild 对内核重新编译。

* 更详细的内容，请参考 [The Buildroot user manual](https://buildroot.org/downloads/manual/manual.html) 的 [Chapter 7. Configuration of other components](https://buildroot.org/downloads/manual/manual.html#_configuration_of_other_components)

