WHAT IS THIS?
=============

Linux Kernel source code for the devices:
* bq aquaris E5 4G


BUILD INSTRUCTIONS?
===================

Specific sources are separated by branches and each version is tagged with it's corresponding number. First, you should
clone the project:

        $ git clone https://github.com/bq/aquaris-e5-4g.git

After it, choose the version you would like to build:

*Aquaris E5 4G*

        $ cd aquaris-e5-4g/
        $ git checkout aquaris-E5-4G

Download a prebuilt gcc

        $ git clone https://android.googlesource.com/platform/prebuilts/gcc/linux-x86/arm/arm-eabi-4.7

Create KERNEL_OUT dir:

        $ mkdir KERNEL_OUT   
Your directory tree should look like this:
* kernel
* arm-eabi-4.7
* KERNEL_OUT

Finally, build the kernel according the next table of product names:

| device                                                                                | product                                                               |
| --------------------------|-------------------------|
| bq aquaris E5 4G                                      | vegetalte                                      |


        $ make -C kernel  O=../KERNEL_OUT  ARCH=arm CROSS_COMPILE=../arm-eabi-4.7/bin/arm-eabi- {product}_defconfig
        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm  CROSS_COMPILE=../arm-eabi-4.7/bin/arm-eabi-                       
    
You can specify "-j CORES" argument to speed-up your compilation, example:

        $ make O=../KERNEL_OUT/ -C kernel ARCH=arm  CROSS_COMPILE=../arm-eabi-4.7/bin/arm-eabi- -j 8
