#operating-systems 

Mode shifting is required to avail special services. Such special services are only available in the privileged kernel mode.
Predefined functions or user defined functions are executed in User Mode.
**Compile Time** - BSA (branch and save address --> when a normal function is being called in the code) and SVC (supervisory call --> instructions which are to be executed in the kernel mode).

The SVC generates system interrupts (**hardware** and **software**) to inform the OS of some activity.
OS maintains a table of all the services it provides in the kernel mode called the **dispatch table**.

**Program** - usually an executable file. Contains data and instructions.
**Process** - when program is loaded from disk to memory. It is an instance of a program.

Processes are defined by 4 characteristics. **Definition, Representation, Operations and Attributes**.

Data is static and dynamic. Memory for dynamic data is allocated at runtime, and for static data at load time (NOT compile time because compile time is only to check for syntax errors and logical errors).
When the process is loaded into memory it has 4 parts.
1. Text (the code)
2. Data (variables)
3. Heap (memory allocation)
4. Stack (activation records of function calls)

**Activation Record** - information and space of the local variables + return address of functions.

Processes have **operations** - create, schedule, execute, block, suspend, resume, terminate.
**Attributes** of processes - process_id, parent_process_id, group_id, program_counter, priority, state.




