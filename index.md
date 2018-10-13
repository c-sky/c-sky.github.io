# Linux C-SKY Introduction:

There are abiv1 & abiv2 supported in linux/arch/csky:

abiv1: 610 (no sale)
abiv2: 807 810 860

  * 807 => A7 (ck610 is replaced by ck807 on sales)
  * 810 => A9
  * 860 => A12/A17/A15
  * "f" means FPU Instruction set
  * "v" means VDSP Instruction set
  * "t" means Trust Execute Environment
  * SMP supported

Now, we are in linux-next:
https://git.kernel.org/pub/scm/linux/kernel/git/next/linux-next.git/tree/arch/csky

Result of the build
-------------------

    output/images/
    ├── csky_buildroot_version.txt (Contain version details)
    ├── qemu_csky_ck860_4.18_glibc_defconfig_330c911e41b0f638583e101b639966b20b4e6acd.tar.xz
    ├── linux-4.18.4.patch.xz
    ├── qemu.dtb
    ├── rootfs.cpio.xz
    └── vmlinux.xz

How to Run
==========

Download all files above.

```bash
  $ xz -d vmlinux.xz
  $ mkdir toolchain
  $ cd toolchain
  $ tar -Jxf ../qemu_csky_ck860_4.18_glibc_defconfig_330c911e41b0f638583e101b639966b20b4e6acd.tar.xz
  $ cd ..
  $ toolchain/csky-qemu/bin/qemu-system-csky2 -kernel vmlinux -dtb qemu_smp.dtb -nographic -M mp860 -smp 4
```

The development repo of "gcc, binutils, glibc, uclibc-ng, qemu" is here: [github.com/c-sky](https://github.com/c-sky)

### Development Boards:
---

| **[诛仙剑 Development Board](docs/gx6605s.md)**<br>**[Only 39RMB](https://item.taobao.com/item.htm?spm=a1z10.1-c.w4004-13250088290.6.4b1f9628jKW8o8&id=556322544984)** | <img src="images/gx6605s_0.gif" alt="gx6605s" /> | 

