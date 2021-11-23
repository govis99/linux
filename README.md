# CMPE283 Assignment 2

1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member 
implemented / researched. (You may skip this question if you are doing the lab by yourself).
- COMPLETED BY MYSELF

2. Describe in detail the steps you used to complete the assignment. Consider your reader to be someone 
skilled in software development but otherwise unfamiliar with the assignment. Good answers to this 
question will be recipes that someone can follow to reproduce your development steps.

FUNCTIONS COMPLETED IN THIS ASSIGNMENT 

- For CPUID leaf node %eax=0x4FFFFFFF:
- ◦Return the total number of exits (all types) in %eax
- For CPUID leaf node %eax=0x4FFFFFFE:
- ◦Return the high 32 bits of the total time spent processing all exits in %ebx
- ◦Return the low 32 bits of the total time spent processing all exits in %ecx
- ▪%ebx and %ecx return values are measured in processor cycles, across all VCPUs

I completed this assignment on VMWARE WORKSTATION 16 Player and install ubuntu 20.04.3
Go to machine and click "Edit virtual machine settings" from here we have 16GB of memory with 4 processors
In setup for nested virtualization:
Click "Processors"
Make sure "Virtualize Intel VT-x/EPT or AMD-V/RVI has a check mark next to it

Verify by typing: cat /proc/cpuinfo
Make sure you see VMX flags and if so you have done it correctly

- Open the terminal
- Make sure you have a working kernel
- git remote -v
- ls
- cd arch/x86
- cd kvm/
- ls
- cd vmx/
- vi vmx.c
- grep -R kvm_emulate_cpuid*
- make modules
- make -j 4 modules
- sudo bash
- make INSTALL_MOD_STRIP = 1 modules_install && make install
- lsmod | grep kvm
- rmmod kvm
- rmmod kvm_intel
- modprobe kvm
- lsmod | grep kvm
- modprobe kvm_intel
- lsmod | grep kvm

## Installing nested virtual machine 
- sudo apt install cpu-checker
- sudo apt install -y qemu qemu-kvm libvirt-daemon libvirt-clients bridge-utils virt-manager
- sudo systemctl status libvirtd
- sudo systemctl enable --now libvirtd
- lsmod | grep -i kvm
- virt-manager 
(Set up vm to own personal preferences)
- virt-manager
(then click on run to run nested virtual machine)
- sudo apt-get update
- sudo apt-get install cpuid






## OUTPUT NESTED VM
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffff
- CPU 0:
- 0x4fffffff 0x00: eax=0x022de514 ebx=0xffffad45 ecx=0x00000000 edx=0x00000000
- CPU 1:
- 0x4fffffff 0x00: eax=0x022de51f ebx=0xffffad45 ecx=0x00000000 edx=0x00000000


- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4ffffffe
- CPU 0:
- 0x4ffffffe 0x00: eax=0x4ffffffe ebx=0x0000002a ecx=0x13401db0 edx=0xffffb71f
- CPU 1:
- 0x4ffffffe 0x00: eax=0x4ffffffe ebx=0x0000002a ecx=0x134578a1 edx=0xffffb71f



## OUTPUT DMESG
- [ 1575.918326] CPUID(Ox4FFFFFFF), exits=36562196
- [ 1575.918545] CPUID(Ox4FFFFFFF), exits=36562207

- [ 1616.645254] CPUID(Ox4FFFFFFE), total time in vmm:180711595440
- [ 1616.646092] CPUID(Ox4FFFFFFE), total time in vmm:180711946401

