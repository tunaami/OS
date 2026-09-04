#operating-systems

All the attributes mentioned in [[OS D2]] are stored in a PCB (**Process Descriptor Block**).
The total content of the PCB is process context/environment.
##### Process Life Cycle
This diagram is for a Non Pre-emptive OS. 

```mermaid
flowchart TD
    New([New]) -->|Create| Ready([Ready])
    Ready -->|Scheduling / Dispatch| Running(["<CPU> Running"])
    Running -->|Completed| Terminated([Terminated])
    Running -->|I/O or System Call| Block([Block / Wait])
    Block -->|I/O or Sys. Call Completion| Ready

    style Ready fill:#b8a9e3,stroke:#333
    style Running fill:#ffffff,stroke:#333
```

Maximum processes in ready/blocked state = theoretically infinite (Honestly depends on RAM)
Maximum processes in the Running state = Number of CPU's

The main memory contains the processes in ready, running and blocked state.
The moving of some processes from main memory to hard disk to improve performance is called **suspension**.
Best states for suspension is the **Ready** state.
Let a process be in the ready state, its waiting for IO services, the process will be moved to **suspended block** state. Once the data is ready, process becomes **suspended ready** and can be scheduled to run by OS.

#### Process State Diagram

```mermaid
flowchart TB
    New([New])
    Ready([Ready])
    SuspendReady([Suspend Ready])
    Running([Running])
    Terminate([Terminate])
    Block([Block])
    SuspendBlock([Suspend Block])

    New -->|create| Ready
    Ready -->|scheduling / dispatch| Running
    Running -->|Preempt| Ready
    Running -->|I/O services on system call| Block
    Running --> Terminate
    Block -->|I/O on sys. comp. call| Ready

    Ready -.->|r1 preempted by OS| SuspendReady
    SuspendReady -.-> Ready

    Block -.->|R.P *| SuspendReady
    Block -.->|suspend| SuspendBlock
    SuspendBlock -.->|Resume| Block
    SuspendBlock -.->|I/O completion| SuspendReady

    %% R.P = Resource Preemption
```

