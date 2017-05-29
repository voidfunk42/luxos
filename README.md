# luxos
x86_64 operating system for intel/amd systems

>>> basic goals for now. readme will be extended with documentation as the project grows.
>>> once we get into the core the more interesting things will happen. For now
>>> we need to still create memory map from bootloader, get some offsets supplied by BIOS for apic tables etc.
>>> and save some other misc boot information to be accessed by the core_loader.
>>> core_loader will extend and utilise this information to enumerate the system further
>>> and load the core while passing the core this information.

[boot]
> assembly code
  - map system memory
  - initialise basic 32-bit mode to transition to long mode later(flat gdt no interrupts)
  - load core_loader from disk (32 bit binary code)
  - jump to core_loader

[core_loader]
> c code
  - map system devices / information using cpuid / pci etc.
  - load x64 data structures (gdt/idt etc.)
  - initialise long mode + paging + interrupts
  - load core code from disk into higher half memory
  - jump to core
  
[core]
> c code
  - n/a
