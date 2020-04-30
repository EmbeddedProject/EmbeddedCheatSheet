Linux Kernel
============

## Kernel Build
### Cross Compile Command with optimised thread
> $ make ARCH=arm CROSS_COMPILE=arm-linux-gnueabihf- -j\`nproc\`

### Decompile DTB in kernel tree
> $ ./scripts/dtc/dtc -I dtb -O dts -o devicetree.dts devicetree.dtb

### Install Compiled Modules
> $ make ARCH=ARM modules_install INSTALL_MOD_PATH=/home/work/nfs

Linux User Space
================

### df output, sorted by Use% and correctly maintaining header row
> $ df -h | grep -v ^none | ( read header ; echo "$header" ; sort -rn -k 5)

### redo last command but as root
> $ sudo !!

### open an editor to run a command
> $ctrl+x+e

### create a super fast ram disk
> $ mkdir -p /mnt/ram
> $ mount -t tmpfs tmpfs /mnt/ram -o size=8192M

### don't add command to history (note the leading space)
> $  ls -l

### fix a really long command that you messed up
> $ fc

### tunnel with ssh (local port 3337 -> remote host's 127.0.0.1 on port 6379)
> $ ssh -L 3337:127.0.0.1:6379 root@emkc.org -N

### quickly create folders
> $ mkdir -p folder/{sub1,sub2}/{sub1,sub2,sub3}

### intercept stdout and log to file
> $ cat file | tee -a log | cat > /dev/null

### exit terminal but leave all processes running
> $ disown -a && exit
