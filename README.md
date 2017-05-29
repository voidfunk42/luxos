# luxos
x86_64 operating system for intel/amd systems

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
