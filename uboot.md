UBOOT 
=====

### NFS boot
setenv nfsroot '/home/hico/work/nfsroot/'  
setenv serverip 192.168.1.1  
setenv ethaddr 00:11:22:33:44:55  
setenv bootfileimage 'zImage'  
setenv fdtfile 'devicetree.dtb'  
setenv netboot 'echo Booting from network ...; setenv autoload no; dhcp; run netloadimage; run netloadfdt; run netargs; bootz ${loadaddr} - ${fdtaddr}'  
setenv netloadimage 'nfs ${loadaddr} ${nfsroot}/boot/${bootfileimage}'  
setenv netloadfdt 'nfs ${fdtaddr} ${nfsroot}/boot/${fdtfile}'  
setenv netargs 'setenv bootargs console=${console} ${optargs} root=/dev/nfs nfsroot=${serverip}:${nfsroot},nolock rw ip=dhcp'  

run netboot
