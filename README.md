# kvm-and-qemu

install qemu in arch:
pacaman -S qemu

create image file in qcow2 format so that all space is not allocated at once.
qemu-img create -f qcow2 image_file_windows10 15G

start the vm.
qemu-system-x86_64 -enable-kvm -cpu host -m 4096 -smp 1 -boot menu=on -soundhw all -drive file=image_file_windows10,format=qcow2 -cdrom windows10.iso
-cpu host option to make QEMU emulate the host's exact CPU. If you do not do this, it may be trying to emulate a more generic CPU.
-smp 1 says number of cpu's is 1
