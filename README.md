# CMPE283 Assignment 1

1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member 
implemented / researched. (You may skip this question if you are doing the lab by yourself).
COMPLETED BY MYSELF

2. Describe in detail the steps you used to complete the assignment. Consider your reader to be someone 
skilled in software development but otherwise unfamiliar with the assignment. Good answers to this 
question will be recipes that someone can follow to reproduce your development steps.

We completed this assignment on VMWARE WORKSTATION 16 Player and install ubuntu 20.04.3
Go to machine and click "Edit virtual machine settings" from here we have 16GB of memory with 4 processors
In setup for nested virtualization:
Click "Prcoessors"
Make sure "Virtualize Intel VT-x/EPT or AMD-V/RVI has a check mark next to it

Verify by typing: cat /proc/cpuinfo
Make sure you see VMX flags and if so you have done it correctly

- Open the terminal
- sudo apt update
- sudo apt install htop
- sudo apt install gcc
- sudo apt install build-essential
- htop
- git clone https://github.com/govis99/linux.git
- cd linux/
- git status
- git remote -v
- cd ..
- vi cmpe283-1.c
- cat Mkefile
- make
- cd linux
- uname -a
- make menuconfig
- cp /boot/config-5.11.0-40-generic .config
- vi .config
- make oldconfig (Press Enter for all of them)
- make prepare
- cd ../
- make
- make clean
- cd linux/
- make -j 4 modules (# 0f virtual CPU's)  (Be sure to edit .config file so CONFIG_SYSTEM_TRUSTED_KEYS="" and CONFIG_SYSTEM_REVOCATION_KEYS="")
- make -j 4
- sudo make INSTALL_MOD_STRIP=1 modules_install  
- sudo make install
- sudo reboot
- vi cmpe283-1.c
(At the end of the file type "MODULE_LICENSE ("GPL v2");)
- make
- ls *.ko
- sudo insmod cmpe283-1.ko 
- lsmod | grep cmpe283
- dmesg
- sudo rmmod cmpe283-1
- dmesg
- sudo insmod cmpe283-1.ko
- cd linux
- mkdir cmpe283
- cd cmpe283/
- cp ~/Makefile ~/cmpe283-1.c .
- git add Makefile cmpe283-1.c
- git commit Makefile cmpe283-1.c
- git push

## OUTPUT for dmesg
- [ 7841.360870] Pinbased Controls MSR: 0x3f00000016
- [ 7841.360873]   External Interrupt Exiting: Can set=Yes, Can clear=Yes
- [ 7841.360875]   NMI Exiting: Can set=Yes, Can clear=Yes
- [ 7841.360876]   Virtual NMIs: Can set=Yes, Can clear=Yes
- [ 7841.360878]   Activate VMX Preemption Timer: Can set=No, Can clear=Yes
- [ 7841.360879]   Process Posted Interrupts: Can set=No, Can clear=Yes
- [ 7841.360882] Procbased Controls MSR: 0xfff9fffe0401e172
- [ 7841.360885]   Interrupt-window exiting: Can set=Yes, Can clear=Yes
- [ 7841.360886]   Use TSC offsetting: Can set=Yes, Can clear=Yes
- [ 7841.360887]   HLT exiting: Can set=Yes, Can clear=Yes
- [ 7841.360888]   INVLPG exiting: Can set=Yes, Can clear=Yes
- [ 7841.360889]   MWAIT exiting: Can set=Yes, Can clear=Yes
- [ 7841.360890]   RDPMC exiting: Can set=Yes, Can clear=Yes
- [ 7841.360891]   RDTSC exiting: Can set=Yes, Can clear=Yes
- [ 7841.360893]   CR3-load exiting: Can set=Yes, Can clear=No
- [ 7841.360894]   CR3-store exiting: Can set=Yes, Can clear=No
- [ 7841.360895]   CR8-load exiting: Can set=Yes, Can clear=Yes
- [ 7841.360896]   CR8-store exiting: Can set=Yes, Can clear=Yes
- [ 7841.360900] Secondary Procbased Controls MSR: 0x553cfe00000000
- [ 7841.360902]   Virtualize APIC accesses: Can set=No, Can clear=Yes
- [ 7841.360903]   Enable EPT: Can set=Yes, Can clear=Yes
- [ 7841.360904]   Descriptor-table exiting: Can set=Yes, Can clear=Yes
- [ 7841.360905]   Enable RDTSCP: Can set=Yes, Can clear=Yes
- [ 7841.360907]   Virtualize x2APIC mode: Can set=Yes, Can clear=Yes
- [ 7841.360908]   Enable VPID: Can set=Yes, Can clear=Yes
- [ 7841.360909]   WBINVD exiting: Can set=Yes, Can clear=Yes
- [ 7841.360910]   Unrestricted guest: Can set=Yes, Can clear=Yes
- [ 7841.360912]   APIC-register virtualization: Can set=No, Can clear=Yes
- [ 7841.360913]   Virtual-interrupt delivery: Can set=No, Can clear=Yes
- [ 7841.360914]   PAUSE-loop exiting: Can set=Yes, Can clear=Yes
- [ 7841.360915]   RDRAND exiting: Can set=Yes, Can clear=Yes
- [ 7841.360917]   Enable INVPCID: Can set=Yes, Can clear=Yes
- [ 7841.360918]   Enable VM functions: Can set=Yes, Can clear=Yes
- [ 7841.360919]   VMCS shadowing: Can set=No, Can clear=Yes
- [ 7841.360920]   Enable ENCLS exiting: Can set=No, Can clear=Yes
- [ 7841.360922]   RDSEED exiting: Can set=Yes, Can clear=Yes
- [ 7841.360923]   Enable PML: Can set=No, Can clear=Yes
- [ 7841.360924]   EPT-violation #VE: Can set=Yes, Can clear=Yes
- [ 7841.360925]   Conceal VMX non-root operation from Intel PT: Can set=No, Can clear=Yes
- [ 7841.360929] Exit Controls MSR: 0x3fefff00036dff
- [ 7841.360930]   Save debug controls: Can set=Yes, Can clear=No
- [ 7841.360932]   Host address- space size: Can set=Yes, Can clear=Yes
- [ 7841.360933]   Load IA32_PERF_GLOB AL_CTRL: Can set=No, Can clear=Yes
- [ 7841.360934]   Acknowledge interrupt on exit: Can set=Yes, Can clear=Yes
- [ 7841.360935]   Save IA32_PAT: Can set=Yes, Can clear=Yes
- [ 7841.360937]   Load IA32_PAT: Can set=Yes, Can clear=Yes
- [ 7841.360938]   Save IA32_EFER: Can set=Yes, Can clear=Yes
- [ 7841.360939]   Load IA32_EFER: Can set=Yes, Can clear=Yes
- [ 7841.360940]   Save VMX- preemption timer value: Can set=No, Can clear=Yes
- [ 7841.360941]   Clear IA32_BNDCFGS: Can set=No, Can clear=Yes
- [ 7841.360943]   Conceal VM exits from Intel PT: Can set=No, Can clear=Yes
- [ 7841.360944]   (null): Can set=Yes, Can clear=No
- [ 7841.360946]   (null): Can set=Yes, Can clear=No
- [ 7841.360947]   (null): Can set=Yes, Can clear=No
- [ 7841.360948]   (null): Can set=Yes, Can clear=No
- [ 7841.360949]   (null): Can set=Yes, Can clear=No
- [ 7841.360952] Entry Controls MSR: 0xd3ff000011ff
- [ 7841.360954]   Load debug controls: Can set=Yes, Can clear=No
- [ 7841.360955]   IA-32e mode guest: Can set=Yes, Can clear=Yes
- [ 7841.360957]   Entry to SMM: Can set=No, Can clear=Yes
- [ 7841.360958]   Deactivate dual-monitor treatment: Can set=No, Can clear=Yes
- [ 7841.360959]   Load IA32_PERF_GLOBA L_CTRL: Can set=No, Can clear=Yes
- [ 7841.360960]   Load IA32_PAT: Can set=Yes, Can clear=Yes
- [ 7841.360962]   Load IA32_EFER: Can set=Yes, Can clear=Yes
