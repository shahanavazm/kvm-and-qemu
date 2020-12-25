# kvm-and-qemu

## Install qemu in arch
pacman -S qemu

## Create image file in qcow2 format so that all space is not allocated at once, with 30G space
qemu-img create -f qcow2 image_file_windows10 30G

## start the vm
qemu-system-x86_64 -enable-kvm -cpu host -smp 2 -m 4096 -boot menu=on -soundhw all -drive file=image_file_windows10,format=qcow2

-cpu host, Use this option to make QEMU emulate the host's exact CPU. If you do not do this, it may be trying to emulate a more generic CPU.

-smp 2, For dual core machine set it to use 2 cpu units.

-soundhw all, This option makes audio work well.

## keyboard shortcuts
alt ctrl g to capture mouse pointer.

alt ctrl f to enable/disable full screen.

## references
arch qemu wiki: https://wiki.archlinux.org/index.php/QEMU

enable audio: https://techpiezo.com/linux/enable-audio-in-qemu-virtual-machine/

