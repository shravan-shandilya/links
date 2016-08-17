IPC is divided into
1. Communnication: Exchanging data
2. Synchronisation: Co-ordination between different processes
3. Signals: Can be both communication mechanism and synchronising mechanism,but poor for both

Communication:
 * Data transfer
  * Byte oriented: writer writes as many bytes,reader read as many bytes
  * Messages: writer writes a message and reader reads it (no partial data transfers,no double reads)
  * Psuedo terminals
 * Shared Memory: Sharing some physical memory pages.writing and reading into physical memory.

Synchronisation:
 * Semaphores
 * Event File descriptors
 * File locks
 * Futexes
 * Thread synchronisation methods
 
Pipes:
 * Bytestream: writer can write any number of bytes
 * Unidirectional
 * Two end: write end and read end
 * Nothing but a bytestream buffer in the kernel
 * One cannot seek on it.Only seq read and write.
 * Multiple readers and writers is a difficult scenarios. [Can be done with some pain](http://linux.die.net/man/1/tee)
 * How to use?
  - Use [pipe](http://tldp.org/LDP/lpg/node11.html) system call
  - Integer array(2 elements) are used to store file descriptors
  - The 0'th index is the reading end, 1st index is the writing end.
  - Normal read and write on these files should work.
  - How do we share these filedescriptors with the other process that we want to communicate with?
   - That's the limitation.The processes have to be related processes
   - One process creates a pipe and creates another process using fork() 
   - Fork duplicates the file descriptors of parent in the child.
   - Close the end of the pipe that is not being used.(i.e. close reading end from writing process)
   - EOF:
     * If writer closes the write descriptor,the reader will get SIGPIPE or EOF when he tries to read using the read desriptor.





[linux.conf.au](https://www.youtube.com/watch?v=8hxb0kwnzGI)
