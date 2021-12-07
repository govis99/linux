# CMPE283 Assignment 4

1. For each member in your team, provide 1 paragraph detailing what parts of the lab that member 
implemented / researched. (You may skip this question if you are doing the lab by yourself).
- COMPLETED BY MYSELF

2. Include a sample of your print of exit count output from dmesg from “with ept” and “without ept”. 

Nested Paging
<img width="960" alt="Assignment 4 before ept" src="https://user-images.githubusercontent.com/90219670/144963077-e8aba0e2-5a49-424b-92d2-10d2659bdf98.png">

Shadow Paging ept=0
<img width="959" alt="Assignment 4 after ept=0" src="https://user-images.githubusercontent.com/90219670/144963086-bfa1f43a-e94a-4e4c-9759-6d78ab4ec858.png">

- [ 8406.004522] Printing Exits, exit number 0 exits=8859/n
- [ 8406.004524] Printing Exits, exit number 1 exits=113015/n
- [ 8406.004525] Printing Exits, exit number 2 exits=0/n
- [ 8406.004526] Printing Exits, exit number 3 exits=0/n
- [ 8406.004527] Printing Exits, exit number 4 exits=0/n
- [ 8406.004528] Printing Exits, exit number 5 exits=0/n
- [ 8406.004529] Printing Exits, exit number 6 exits=0/n
- [ 8406.004531] Printing Exits, exit number 7 exits=20600/n
- [ 8406.004532] Printing Exits, exit number 8 exits=0/n
- [ 8406.004533] Printing Exits, exit number 9 exits=0/n
- [ 8406.004534] Printing Exits, exit number 10 exits=140744/n
- [ 8406.004536] Printing Exits, exit number 11 exits=0/n
- [ 8406.004537] Printing Exits, exit number 12 exits=26687/n
- [ 8406.004538] Printing Exits, exit number 13 exits=0/n
- [ 8406.004539] Printing Exits, exit number 14 exits=0/n
- [ 8406.004540] Printing Exits, exit number 15 exits=0/n
- [ 8406.004541] Printing Exits, exit number 16 exits=0/n
- [ 8406.004542] Printing Exits, exit number 17 exits=0/n
- [ 8406.004544] Printing Exits, exit number 18 exits=0/n
- [ 8406.004545] Printing Exits, exit number 19 exits=0/n
- [ 8406.004546] Printing Exits, exit number 20 exits=0/n
- [ 8406.004547] Printing Exits, exit number 21 exits=0/n
- [ 8406.004548] Printing Exits, exit number 22 exits=0/n
- [ 8406.004549] Printing Exits, exit number 23 exits=0/n
- [ 8406.004551] Printing Exits, exit number 24 exits=0/n
- [ 8406.004552] Printing Exits, exit number 25 exits=0/n
- [ 8406.004553] Printing Exits, exit number 26 exits=0/n
- [ 8406.004554] Printing Exits, exit number 27 exits=0/n
- [ 8406.004555] Printing Exits, exit number 28 exits=19155/n
- [ 8406.004557] Printing Exits, exit number 29 exits=2/n
- [ 8406.004558] Printing Exits, exit number 30 exits=170394/n
- [ 8406.004559] Printing Exits, exit number 31 exits=672/n
- [ 8406.004560] Printing Exits, exit number 32 exits=124791/n
- [ 8406.004561] Printing Exits, exit number 33 exits=0/n
- [ 8406.004562] Printing Exits, exit number 34 exits=0/n
- [ 8406.004564] Printing Exits, exit number 35 exits=0/n
- [ 8406.004565] Printing Exits, exit number 36 exits=0/n
- [ 8406.004566] Printing Exits, exit number 37 exits=0/n
- [ 8406.004567] Printing Exits, exit number 38 exits=0/n
- [ 8406.004568] Printing Exits, exit number 39 exits=0/n
- [ 8406.004570] Printing Exits, exit number 40 exits=6539/n
- [ 8406.004571] Printing Exits, exit number 41 exits=0/n
- [ 8406.004572] Printing Exits, exit number 42 exits=0/n
- [ 8406.004573] Printing Exits, exit number 43 exits=0/n
- [ 8406.004574] Printing Exits, exit number 44 exits=0/n
- [ 8406.004575] Printing Exits, exit number 45 exits=0/n
- [ 8406.004577] Printing Exits, exit number 46 exits=0/n
- [ 8406.004578] Printing Exits, exit number 47 exits=0/n
- [ 8406.004579] Printing Exits, exit number 48 exits=686273/n
- [ 8406.004580] Printing Exits, exit number 49 exits=35876/n
- [ 8406.004581] Printing Exits, exit number 50 exits=0/n
- [ 8406.004583] Printing Exits, exit number 51 exits=0/n
- [ 8406.004584] Printing Exits, exit number 52 exits=0/n
- [ 8406.004585] Printing Exits, exit number 53 exits=0/n
- [ 8406.004586] Printing Exits, exit number 54 exits=3/n
- [ 8406.004587] Printing Exits, exit number 55 exits=3/n
- [ 8406.004589] Printing Exits, exit number 56 exits=0/n
- [ 8406.004590] Printing Exits, exit number 57 exits=0/n
- [ 8406.004591] Printing Exits, exit number 58 exits=0/n
- [ 8406.004592] Printing Exits, exit number 59 exits=0/n
- [ 8406.004593] Printing Exits, exit number 60 exits=0/n
- [ 8406.004594] Printing Exits, exit number 61 exits=0/n
- [ 8406.004596] Printing Exits, exit number 62 exits=0/n
- [ 8406.004597] Printing Exits, exit number 63 exits=0/n
- [ 8406.004598] Printing Exits, exit number 64 exits=0/n
- [ 8406.004599] Printing Exits, exit number 65 exits=0/n
- [ 8406.004600] Printing Exits, exit number 66 exits=0/n
- [ 8406.004602] Printing Exits, exit number 67 exits=0/n
- [ 8406.004603] Printing Exits, exit number 68 exits=0/n


AFTER EPT=0
- [10901.550684] Printing Exits, exit number 0 exits=2601865/n
- [10901.550685] Printing Exits, exit number 1 exits=348882/n
- [10901.550685] Printing Exits, exit number 2 exits=0/n
- [10901.550686] Printing Exits, exit number 3 exits=0/n
- [10901.550687] Printing Exits, exit number 4 exits=0/n
- [10901.550688] Printing Exits, exit number 5 exits=0/n
- [10901.550688] Printing Exits, exit number 6 exits=0/n
- [10901.550688] Printing Exits, exit number 7 exits=84742/n
- [10901.550689] Printing Exits, exit number 8 exits=0/n
- [10901.550689] Printing Exits, exit number 9 exits=0/n
- [10901.550690] Printing Exits, exit number 10 exits=286066/n
- [10901.550690] Printing Exits, exit number 11 exits=0/n
- [10901.550691] Printing Exits, exit number 12 exits=264301/n
- [10901.550691] Printing Exits, exit number 13 exits=0/n
- [10901.550692] Printing Exits, exit number 14 exits=241660/n
- [10901.550692] Printing Exits, exit number 15 exits=0/n
- [10901.550693] Printing Exits, exit number 16 exits=0/n
- [10901.550693] Printing Exits, exit number 17 exits=0/n
- [10901.550693] Printing Exits, exit number 18 exits=0/n
- [10901.550694] Printing Exits, exit number 19 exits=0/n
- [10901.550694] Printing Exits, exit number 20 exits=0/n
- [10901.550695] Printing Exits, exit number 21 exits=0/n
- [10901.550695] Printing Exits, exit number 22 exits=0/n
- [10901.550696] Printing Exits, exit number 23 exits=0/n
- [10901.550696] Printing Exits, exit number 24 exits=0/n
- [10901.550696] Printing Exits, exit number 25 exits=0/n
- [10901.550697] Printing Exits, exit number 26 exits=0/n
- [10901.550697] Printing Exits, exit number 27 exits=0/n
- [10901.550698] Printing Exits, exit number 28 exits=173129/n
- [10901.550698] Printing Exits, exit number 29 exits=4/n
- [10901.550699] Printing Exits, exit number 30 exits=597727/n
- [10901.550699] Printing Exits, exit number 31 exits=5545/n
- [10901.550699] Printing Exits, exit number 32 exits=693906/n
- [10901.550700] Printing Exits, exit number 33 exits=21948/n
- [10901.550700] Printing Exits, exit number 34 exits=0/n
- [10901.550701] Printing Exits, exit number 35 exits=0/n
- [10901.550701] Printing Exits, exit number 36 exits=0/n
- [10901.550702] Printing Exits, exit number 37 exits=0/n
- [10901.550702] Printing Exits, exit number 38 exits=0/n
- [10901.550703] Printing Exits, exit number 39 exits=0/n
- [10901.550703] Printing Exits, exit number 40 exits=27723/n
- [10901.550703] Printing Exits, exit number 41 exits=0/n
- [10901.550704] Printing Exits, exit number 42 exits=0/n
- [10901.550704] Printing Exits, exit number 43 exits=0/n
- [10901.550705] Printing Exits, exit number 44 exits=0/n
- [10901.550705] Printing Exits, exit number 45 exits=0/n
- [10901.550706] Printing Exits, exit number 46 exits=0/n
- [10901.550706] Printing Exits, exit number 47 exits=0/n
- [10901.550706] Printing Exits, exit number 48 exits=786150/n
- [10901.550707] Printing Exits, exit number 49 exits=51263/n
- [10901.550707] Printing Exits, exit number 50 exits=0/n
- [10901.550708] Printing Exits, exit number 51 exits=0/n
- [10901.550708] Printing Exits, exit number 52 exits=0/n
- [10901.550709] Printing Exits, exit number 53 exits=0/n
- [10901.550709] Printing Exits, exit number 54 exits=7/n
- [10901.550710] Printing Exits, exit number 55 exits=6/n
- [10901.550710] Printing Exits, exit number 56 exits=0/n
- [10901.550710] Printing Exits, exit number 57 exits=0/n
- [10901.550711] Printing Exits, exit number 58 exits=2654/n
- [10901.550711] Printing Exits, exit number 59 exits=0/n
- [10901.550712] Printing Exits, exit number 60 exits=0/n
- [10901.550712] Printing Exits, exit number 61 exits=0/n
- [10901.550713] Printing Exits, exit number 62 exits=0/n
- [10901.550713] Printing Exits, exit number 63 exits=0/n
- [10901.550713] Printing Exits, exit number 64 exits=0/n
- [10901.550714] Printing Exits, exit number 65 exits=0/n
- [10901.550714] Printing Exits, exit number 66 exits=0/n
- [10901.550715] Printing Exits, exit number 67 exits=0/n
- [10901.550715] Printing Exits, exit number 68 exits=0/n


3. What did you learn from the count of exits? Was the count what you expected? If not, why not? 
- I learnt that the count of exits greatly increased after we had inserted ept=o into our kvm_intel using insmod /lib/modules/5.15.0+/kernel/arch/x86/kvm/kvm-intel.ko ept=0. With shadow paging we noticed a lot of exits and with the nested paging it wasn't as much as shadow paging. I did predict a jump, but not that much of a jump in exits. 

4. What changed between the two runs (ept vs no-ept)?
- 0 - Exception: A huge increase in exits for shadow paging
- 1 - External: small increase in exits for shadow paging
- 7 - Interrupt Window: small increase in exits for shadow paging
- 10 - CPUID: small increase in exits for shadow paging
- 12 - HLT: small increase in exits for shadow paging
- 14 - INVLPG: For shadow paging we had a lot of exits and 0 for nested
- 28 - Control Register: small increase in exits for shadow paging
- 30 - I/O: A huge increase in exits for shadow paging
- 31 - RDMSR: small increase in exits for shadow paging
- 32 - WRMSR: small increase in exits for shadow paging
- 33 - VM ENTRY FAIL: For shadow paging we had a lot of exits and 0 for nested
- 40 - PAUSE: small increase in exits for shadow paging
- 48 - EPT Violation: Small increase in exits for shadow paging
- 49 - EPT misconfiguration: Small increase in exits for shadow paging
- 58 - INVPCID: For shadow paging we had a lot of exits and 0 for nested
