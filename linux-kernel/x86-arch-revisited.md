Control registers(CR0,CR1,CR2,CR3 and CR4)

Shamelessly copied from Wikipedia article :P
<pre>
CR0:
* 32bits or 64 bits long
  Bit Name 	Full Name 	            Description
  0 	PE 	  Protected Mode Enable 	If 1, system is in protected mode, else system is in real mode
  1 	MP 	  Monitor co-processor 	  Controls interaction of WAIT/FWAIT instructions with TS flag in CR0
  2 	EM 	  Emulation 	            If set, no x87 floating point unit present, if clear, x87 FPU present
  3 	TS 	  Task switched 	        Allows saving x87 task context upon a task switch only after x87 instruction used
  4 	ET 	  Extension type 	        On the 386, it allowed to specify whether the external math coprocessor was an 80287 or 80387
  5 	NE 	  Numeric error 	        Enable internal x87 floating point error reporting when set, else enables PC style x87 error detection
  16 	WP 	  Write protect 	        When set, the CPU can't write to read-only pages when privilege level is 0  
  18 	AM 	  Alignment mask 	        Alignment check enabled if AM set, AC flag (in EFLAGS register) set, and privilege level is 3
  29 	NW 	  Not-write through 	    Globally enables/disable write-through caching
  30 	CD 	  Cache disable 	        Globally enables/disable the memory cache
  31 	PG 	  Paging 	                If 1, enable paging and use the CR3 register, else disable paging
</pre>
[Usage of PE bit to evolve to Protected mode(in u-boot)](http://lingrok.org/xref/u-boot/arch/x86/cpu/start16.S#43)
[Disabling Pagin](http://lingrok.org/xref/linux-linus/arch/x86/boot/compressed/efi_thunk_64.S#124)

CR1:
Reserved

CR2:
Contains PFLA(Page Fault Linear Address).The address of program which created a Page Fault.

CR3:
Savior for Virtual addressing.Contains address of Page tables for the currently running process.
[Example for reloading pagetables](http://lingrok.org/xref/linux-linus/arch/x86/boot/compressed/efi_thunk_64.S#120)

There are other Control registers which are used.
[More info on Wiki](https://en.wikipedia.org/wiki/Control_register)
