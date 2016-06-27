[Virtual Memory](https://www.youtube.com/watch?v=EWwfMM2AW9g)

Extract:
Single Addressing Space:-
- Memory and Peripherals share the same memory address space.
- One part of memory is mapped to actual physical memory and another part is mapped to peripherals.
- All processes and Kernel share the same memory address space.
- No memory protection,Processes stomp each other and kernel.
- Used in: Microcontrollers,ARM Cortex-M

Address spaces:
Physical address space:
- Used by hardware to talk to one another.
- DMA

Virtual Address Space:
- Used by software.
- **Both Kernel and Userspace,always use virtual address**
- System for address mapping.
- Maps virtual address to physical address or to hardware (PCI ,GPU RAM)
- Mapping is done by hardware(no performance penalty).Also takes care of Permissions.
- Same instructions can be used to access both memory and hardware.
- Advantages
  - Each Process can have a different mapping.One process's RAM is in accesibl to other processes.
  - Kernel RAM is also inaccessible.
  - Memory can be moved from one physical frame to another
  - Memory can be swapped to disk.
  - Hardware devices can be mapped to Process's memory
  - One physical memory can be mapped to two different processes (Shared memory)

MMU:
<pre>
+-------------------------------------------------------------+           +--------------+
|                                                             |           |              |
|                                                             |           |              |
|                                     +----------------+      |           |              |
|                                     |                |      |           |              |
|                                     |                |      |           |              |
|                                     |    ALU         |      |           |              |
|                                     |                |      |           |              |
|                                     +-------+--------+      |           |              |
|                                             |               |           |              |
|                                             |               |           |              |
|     +----------------+              +-------v--------+      |           |    RAM       |
|     |                |              |                |      |           |              |
|     |    TLB         +--------------+     MMU        |      |           |              |
|     |                |              |                |      |           |              |
|     +----------------+              ^                |      |           |              |
|     |                |              +-------+--------+      |           |              |
|     +----------------+                      |               |           |              |
|     |                |                      |               |           |              |
|     +----------------+              +-------v--------+      |           |              |
|     |                |              |                |      |           |              |
|     +----------------+              |   Memory       +----------------> |              |
|     |                |              |   Controller   |      |           |              |
|     +----------------+              |                |      |           |              |
|     +----------------+              +----------------+      |           |              |
|                                                             |           |              |
|                                                             |           |              |
+-------------------------------------------------------------+           +--------------+



[Thanks to asciiflow.com](http://asciiflow.com/)
</pre>
