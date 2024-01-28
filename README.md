# Chookpen OS

A minimal OS compiled from source, in very early beta.

## Install

Don't install it yet, there's better versions coming!

If you want to install it in a virtual machine, we don't have an installer yet lol.

This is a very early build, dont use this in production!!!!!!

## Build it yourself

(From my internal documents, config files will be provided in the "config" directory)

1. Make Linux kernel and Busybox (make sure to apply the configs!!!).
2. Access the bzImage at linux/arch/x86/boot/bzImage and copy it to boot-files/bzImage
3. In the BusyBox folder, run make CONFIG_PREFIX=/boot-files/initramfs install
4. Make a file called init in the /boot-files/initramfs and make it start the shell using the shell, and make it executable.
5. Remove linuxrc
6. Run find . | cpio -o -H newc > ../init.cpio in initramfs
7. cd ..
8. Run dd if=/dev/zero of=boot bs=1M count=50
9. Make a fat filesystem with mkfs -t fat boot
10. Install syslinux with syslinux boot
11. Mount boot at a directory
12. Copy bzImage and init.cpio to where boot is mounted.
13. Add config file for syslinux to root directory.
14. Unmount boot.
15. Test in QEMU with qemu-system-x86_64 boot
16. Run /bzImage -initrd=/init.cpio 
Should be working now!
