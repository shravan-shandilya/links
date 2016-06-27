Ways of coomunicating between programs(Broadly classified)

1.ABI (Application Binary Interface) : One program writes to a memory,in a particular format and the other program reads it
2.API (Application Programming Interface): One program calls a funciton in another program,and gets the work done.

Usage:
ABI: Psuedofile systems in linux (/proc,/sys)
API: System calls,Ioctls

Advantages:
ABI: Resources/Resource information are exported by the kernel to an userland application.Because all we have to do is just file i/o and every language supports file io.

How ABI works:
The kernel exports some information(on a resource) as a psuedo file,along with file operations callback handler structure.
This structures will contain the function pointers(either default or custom) for every operation that can be done on the file.
Whenever someone tries to read from psuedofile,the kernel will call the registered callback function for read operation.

[Links]()

Food for thought:
When we look at the working of ABI,is it simply an abstraction that handles the complexities of an API in a simpler way,facilated by the kernel ?

