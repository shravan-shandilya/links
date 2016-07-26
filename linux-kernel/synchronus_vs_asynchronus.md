 * A synchronous operation blocks a process till the operation completes.
 * An asynchronous operation is non-blocking and only initiates the operation. 
   - The caller could discover completion by polling, by software interrupt, or by waiting explicitly for completion later.
   - An asynchronous operation needs to return a call/transaction id if the application needs to be later notified about the operation. 
   - At notification time, this id would be placed in some global location or passed as an argument to a handler or wait call.

[More](http://cs.unc.edu/~dewan/242/f97/notes/ipc/node9.html)
