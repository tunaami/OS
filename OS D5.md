#operating-systems #process-scheduling
#### Some algorithms 

**FCFS** **(First Come First Service)** - Selection Criteria is arrival time. Operates in **Non Pre-emptive OS**. Prefers lower process ID during conflicts. However it causes starvation.

Assumptions in FCFS are -
1. time is in clock ticks
2. no IOBTs
3. scheduling overhead = 0

Now including delta and IOBT. **Delta** is basically time taken by the dispatcher to load the process from ready to running state. 

< BT, IOBT, BT >

**SJF (Shortest Job First)** - Selection criteria is burst time. Operates in **Non Pre-emptive OS**. Prefers lower process ID during conflicts.

*Among the processes present in RQ select the process with least burst time and schedule it to CPU.*

**Shortest Time Remaining First (Pre-Emptive SJF)** - Selection criteria is burst time. Operates in **Pre-Emptive OS**. Pre-emption of running process is based on the availability of strictly shorter process. 

*Out of the processes present in the Ready Queue select the one having least Burst Time and continue to run that process in the CPU until a new process with a smaller Burst Time arrives.*

It starts behaving like normal SJF when new processes stop coming.

**MOST OPTIMAL SCHEDULING ALGORITHM IS SJF**

**Longest Time Remaining First** - Selection criteria is burst time. Operates in **Pre-Emptive OS**. Pre-emption of running process is based on the availability of strictly longer process. 

**Priority Based Scheduling** - Works just like SJF/SRTF except it looks for priority. Selection criteria is burst time. Operates in both **Non Pre-Emptive** and **Pre-Emptive** OS.

f(type, size, resources ...) = some integer value
In **Dynamic** method, lower priority processes become higher priority after some time due to starvation using the **Aging Algorithm**.

**READ ROUND ROBIN AGAIN**

**Asymmetric** - one processor access all system data structs, no need for data sharing, process given to any processor.
**Symmetric** - similar function, uniform memory access, shared IO and memory, global and local ready queue