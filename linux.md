Linux Kernel
============

## Kernel Build
### Cross Compile Command with optimised thread
> $ make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- -j\`nproc\`

### Decompile DTB in kernel tree
> $ ./scripts/dtc/dtc -I dtb -O dts -o devicetree.dts devicetree.dtb

### Install Compiled Modules
> $ make ARCH=ARM modules_install INSTALL_PATH=/home/work/nfs

## User Space
### df output, sorted by Use% and correctly maintaining header row
> $ df -h | grep -v ^none | ( read header ; echo "$header" ; sort -rn -k 5)


