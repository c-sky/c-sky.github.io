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

### Quick start with qemu
https://gitlab.com/c-sky/buildroot/-/jobs/107754332/artifacts/browse/output/images/
```sh
    $ git clone https://gitlab.com/c-sky/buildroot.git
    $ cd buildroot
    $ make qemu_csky_ck810_uclibc_bt_defconfig
    $ make
```
The development repo of "gcc, binutils, glibc, uclibc-ng, qemu" is here: [github.com/c-sky](https://github.com/c-sky)

### Development Boards:
---

| **[诛仙剑 Development Board](docs/gx6605s.md)**<br>**[Only 39RMB](https://item.taobao.com/item.htm?spm=a1z10.1-c.w4004-13250088290.6.4b1f9628jKW8o8&id=556322544984)** | <img src="images/gx6605s_0.gif" alt="gx6605s" /> | 

