# kvm-and-qemu

install qemu in arch:

pacman -S qemu

create image file in qcow2 format so that all space is not allocated at once:

qemu-img create -f qcow2 image_file_windows10 30G

start the vm:

qemu-system-x86_64 -enable-kvm -cpu host -m 4096 -boot menu=on -soundhw all -smp 2 -drive file=image_file_windows10,format=qcow2

-cpu host option to make QEMU emulate the host's exact CPU. If you do not do this, it may be trying to emulate a more generic CPU.

-smp 2 for dual core machine set it to use 2 cpu units

another example command:

qemu-system-x86_64   -drive file=image_file,format=qcow2   -m 4096 -enable-kvm -M q35   -cpu host -smp 4,sockets=1,cores=4,threads=1   -bios /usr/share/qemu/bios.bin -boot menu=on   -cdrom iso_image_lm.iso -soundhw all

keyboard shortcut:

alt ctrl g to capture mouse pointer.

alt ctrl f to enable/disable full screen.

references:

arch qemu wiki: https://wiki.archlinux.org/index.php/QEMU

enable audio: https://techpiezo.com/linux/enable-audio-in-qemu-virtual-machine/

sample commands: https://www.reddit.com/r/archlinux/comments/68jvew/installing_archlinux_in_a_qemu_kvm_vm/dgz9srt/?utm_source=reddit&utm_medium=web2x&context=3

