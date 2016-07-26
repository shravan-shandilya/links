[Basics] (http://www.makelinux.net/books/lkd2/ch06lev1sec6)
Why interrupts?
  * Because we need some mechanism to gather the attention of CPU for some particular reason.
  * Synchronous calls are inefficient (Waiting for a blocking call to return is wastage to time,where we can execute any other processes)

[Block diagram] (http://www.tldp.org/LDP/tlk/dd/interrupts.gif)

Role of Interrupt Controller:
* Selective enable/disable using programable registers.
* Multiplexing: Only one pin needed in CPU. Scaling is not a problem.
* Ex: PIC(Programable Interupt Controller - 8259),Advanced PIC
* Control register are directly addressable from the CPU.
* Dedicated instructions to enable and disable interrupt(maskable) like "sti" and "cli".

Types:
* Maskable
  * can be disabled with "cli"
* Non - maskable
  * Usually reserved for hardware failure interrupts
  
Prioroties:
Used to select an interrupt to service,if multiple interrupts occur at the same time.

Interrupts and Exceptions:
* Interrupts: Way to communicate or grab the attention of CPU. (ex: keypress)
* Exceptions: Special (sometimes faulty) condtion during execution (ex: divide by zero (faulty code), page fault, syscall mechanism)

IDT:
* Mapping between interrupt number and the address of the interrupt service routine(handler).
* Base address is stored in IDTR.
* Entries are called "gates"
* It can contain interrupt gate,task gate or trap gate.

