# Zhaoxin-KaiXian-KX-7000-model-for-QEMU
Zhaoxin KaiXian KX-7000 model and Shanghai vendor id support for QEMU, including SM2, SM3, SM4, zxpause

# 使用方法
下载本代码，将ShiJiDaDaoEmulation文件夹的zhaoxin shijidadao.c源码复制到qemu主线的/target/i386/cpu.c中Skylake-Client model之前，Broadwell的model之后。

zhaoxin shijidadao.h源码分批复制，其中

/* SHA512 Instruction */

#define CPUID_7_1_EAX_SHA512            (1U << 0)

/* Zhaoxin Guo Mi SM3 Instruction */

#define CPUID_7_1_EAX_SM3               (1U << 1)

/* Zhaoxin Guo Mi SM4 Instruction */

#define CPUID_7_1_EAX_SM4               (1U << 2)

/* Zhaoxin Guo Mi SM2 Instruction */

//#define CPUID_7_1_EAX_SM2               (1U << 15)

/* Zhaoxin ZXPAUSE Instruction */

//#define CPUID_C000_0006_EAX_ZXPAUSE     (1U << 0)

复制到/target/i386/cpu.h中，/* AVX VNNI Instruction */之前并排序，

#define CPUID_VENDOR_ZHAOXIN   "  Shanghai  "复制到#define CPUID_VENDOR_HYGON    "HygonGenuine"之后

如嫌麻烦，可以直接使用我已经改好的cpu.c与cpu.h，配合qemu 9.2使用。

# Usage
Download this code, and copy the source code of zhaoxin shijidadao.c from the ShiJiDaDaoEmulation folder to the qemu mainline's /target/i386/cpu.c, before the Skylake-Client model and after the Broadwell model.

The source code of zhaoxin shijidadao.h is copied in batches, where

/* SHA512 Instruction */

#define CPUID_7_1_EAX_SHA512            (1U << 0)

/* Zhaoxin Guo Mi SM3 Instruction */

#define CPUID_7_1_EAX_SM3               (1U << 1)

/* Zhaoxin Guo Mi SM4 Instruction */

#define CPUID_7_1_EAX_SM4               (1U << 2)

/* Zhaoxin Guo Mi SM2 Instruction */

//#define CPUID_7_1_EAX_SM2               (1U << 15)

/* Zhaoxin ZXPAUSE Instruction */

//#define CPUID_C000_0006_EAX_ZXPAUSE     (1U << 0)

Copy it into /target/i386/cpu.h, before /* AVX VNNI Instruction */ and sort it.

Copy #define CPUID_VENDOR_ZHAOXIN   "  Shanghai  " after #define CPUID_VENDOR_HYGON    "HygonGenuine"

If you find it troublesome, you can directly use the modified cpu.c and cpu.h that I have already prepared, which can be used in conjunction with qemu 9.2.
