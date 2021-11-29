# CMPE283 Assignment 3

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
- For CPUID leaf node %eax=0x4FFFFFFD:
- ◦Return the number of exits for the exit number provided (on input) in %ecx
- ▪This value should be returned in %eax 
- •For CPUID leaf node %eax=0x4FFFFFFC:
- ◦Return the time spent processing the exit number provided (on input) in %ecx
- ▪Return the high 32 bits of the total time spent for that exit in %ebx
- ▪Return the low 32 bits of the total time spent for that exit in %ecx

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

## TROUBLESHOOTING 
- Error: make: ** No rule to make target 'modules'. Stop
- git clone https://github.com/govis99/linux.git
- cd linux
- make -j 4 modules
- make -j 4
- sudo make INSTAL_MOD_STRIP=1
- sudo make install
- sudo reboot 
- git checkout Assignment-2 

## EXTRA QUESTIONS
- For whichever assignment you chose to complete CPUID 0x4FFFFFFD and 0x4FFFFFFC:
- 3. Comment on the frequency of exits – does the number of exits increase at a stable rate? Or are there 
- more exits performed during certain VM operations? Approximately how many exits does a full VM 
- boot entail?
- The number of exits do not increase at a stable rate. A full vm boot entails about 1421145 exits. 
- 4. Of the exit types defined in the SDM, which are the most frequent? Least?
- The ones that are most frequent are CPUID instructions, I/O exits, and HLT instructions. The ones that are least frequent are RDMSR, the VM instructions, MWAIT, and monitor instructions. 


## OUTPUT NESTED VM
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffff
- CPU 0:
-   0x4fffffff 0x00: eax=0x00146087 ebx=0xffffaa04 ecx=0x00000000 edx=0x00000000
- CPU 1:
-   0x4fffffff 0x00: eax=0x00146091 ebx=0xffffaa04 ecx=0x00000000 edx=0x00000000
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4ffffffd -s 33
- CPU 0:
-   0x4ffffffd 0x21: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- CPU 1:
-   0x4ffffffd 0x21: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4ffffffd -s 1
- CPU 0:
-   0x4ffffffd 0x01: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- CPU 1:
-   0x4ffffffd 0x01: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffc -s 0
- CPU 0:
-   0x04fffffc 0x00: eax=0x000002e7 ebx=0x00000a88 ecx=0x00000a88 edx=0x00000000
- CPU 1:
-   0x04fffffc 0x00: eax=0x000002e7 ebx=0x00000a88 ecx=0x00000a88 edx=0x00000000
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffc -s 56
- CPU 0:
-   0x04fffffc 0x38: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- CPU 1:
-   0x04fffffc 0x38: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4ffffffd -s 3
- CPU 0:
-   0x4ffffffd 0x03: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- CPU 1:
-   0x4ffffffd 0x03: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffc -s 3
- CPU 0:
-   0x04fffffc 0x03: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- CPU 1:
-   0x04fffffc 0x03: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4ffffffd -s 64
- CPU 0:
-   0x4ffffffd 0x40: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- CPU 1:
-   0x4ffffffd 0x40: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x0fffffff
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ cpuid -l 0x4fffffc -s 35
- CPU 0:
-   0x04fffffc 0x23: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- CPU 1:
-   0x04fffffc 0x23: eax=0x00000000 ebx=0x00000000 ecx=0x00000000 edx=0x00000000
- govi@govi-Standard-PC-Q35-ICH9-2009:~$ 



