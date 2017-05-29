# luxos
x86_64 operating system project for intel/amd systems

files:
> BOOT
/src/boot/boot.s - bootloader
/src/boot/bios/* - bios interrupt functions
/src/boot/cpu/*  - cpu data structures and functions

> OS LOADER
/src/boot/core_loader.c - completes system init and jumps to core

> CORE
not started yet.


>> CURRENT RESEARCH TOPICS
 - complete system enumeration & initialisation
 - paging / memory management 
 - boot protocol to enumerate system via boot / os loader.
 - cpu multi-core initialisation
 - pci busmastering / enumeration (os loader)
 - x64 non cpu based interrupts 
 - memory model for core
 - executable file types & file system
 - block devices & network devices (need pci first)
