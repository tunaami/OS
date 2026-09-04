#operating-systems

**Hardware** - Control unit (Input-output, memory), Arithmetic Logical Unit, Central Process Unit
**Control unit** - sequence and execution of microprocesses
**Memory** - Primary (RAM, ROM, Cache, Registers) and Secondary (Hard disks, Pen Drives). Secondary memory is a part of input-output systems according to Von Neumann Architecture.

**Program ---> Compiler ---> .exe (Executable file) ---> Main Memory**

CPU cannot execute program directly from hard disk.
	1. Hard Disks are very slow
	2. Program is first transferred into the main memory then executed.

**Kernel** - core/nucleus of the OS with several modules like process management, memory management, file management, device management, protection management.
1. **MicroKernel** - user and kernel service in diff places, complex design, small in size, easy to add new functions, severe performance overhead for naive implementation
2. **Monolithic** - user and kernel in the same place, easy to desing, large, diff to add new functions, less code.

OS's are of two types essentially - uniprogrammed and multiprogrammed
**Uniprogrammed** - can hold only one program in the main memory
**Multiprogrammed** - OS is stored in system area of the memory and the programs are loaded in the user area

OS's operating on strict deadlines are called **Real Time OS**.
###### Types of Multiprogramming-
**Pre-Emptive** - forceful deallocation from the CPU whenever a high priority job appears or when a certain job is taking longer time than usual. Also called Multi-Tasking OS.
**Non Pre-Emptive** - no forceful deallocation, the CPU is released voluntarily when all instructions are complete/needs IO/system calls.

Most modern OS's are pre-emptive. Hardware requirements -
1. Secondary storage device which is DMA(Direct Memory Access) compatible.
2. Memory system should support address translation (Program consists of logical address and needs to be converted to physical address). Logical address provides a layer of **abstraction** as a security measure.
3. CPU with dual mode support (user mode and kernel mode). **Kernel Mode** - code has complete and unrestricted access to system hardware. This mode reserved for the lowest-level and most trusted functions of the OS. Crashes in kernel mode are lethal and halt the entire PC. **User Mode** - Code must delegate to using system API's to access hardware or memory. Crashes in this mode are recoverable.