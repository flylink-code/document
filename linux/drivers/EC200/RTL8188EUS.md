# RTL8188的使用

## 交叉编译
**下载驱动**  
**解压驱动**  
**修改编译文件:Makefile**
```
CONFIG_PLATFORM_I386_PC= n
CONFIG_PLATFORM_TI_AM335x = y

ifeq ($(CONFIG_PLATFORM_TI_AM335x), y)
EXTRA_CFLAGS += -DCONFIG_LITTLE_ENDIAN
CROSS_COMPILE := arm-linux-gnueabihf-
KSRC := /work2/sdk06/board-support/linux-3.2.0-psp04.06.00.11
ARCH := arm
KVER := 3.2.0
endif
```