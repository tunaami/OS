#operating-systems 

###### Inter-process Communication and Process Synchronization

Two functions communicate with each other using parameter passing/global variables. Processes are of two types - **Independent** and **Coordinating**. 
Problems caused when there's no synchronization -
1. Inconsistency
2. Data Loss
3. Deadlock

There are two types of synchronization - **Competitive** and **Cooperative**.
**Competitive** - Processes compete for the accessibility of a shared resource.
**Cooperative** - Execution of on process affects the other. Ex - producer consumer problem.

###### Producer Consumer Problem
Producer attempts to put data into the buffer. Consumer attempts to consume the data from the buffer. If the buffer is full, the producer cannot produce and if the buffer is empty, the consumer cannot consume.
*But there might be competition too to update the shared buffer count. There is a need of a sync tool to solve this problem.*

```c
int N = 100;
int count = 0;  //Count = number of items in the buffer
int buffer[N];

void producer(void){
	int itemp, in = 0;
	while(1){
		itemp = produce_item();
		while (count == N);  // busy waiting -> producer produces but cant place
		buffer[in] = itemp;
		in = (in + 1) % N;
		count++;
	}
}

void consumer(void){
	int itemc, out = 0;
	while(1){
		while(count == 0);
		itemc = buffer[out];
		out = (out + 1) % N;
		count--;
		consume_item(itemc);
	}
}
```

###### Sync Problem

**Critical section** - part of the section where the shared resources are accessed.
**Non-Critical section** - no shared resources, mostly local variables.
**Race Condition** - situation wherein processes are trying to access Critical sections and the final result depends on the order they finish their update.

Premature pre-emption causes the sync problem. There is a requirement of a mechanism that doesn't allow another process to use critical section when the other process has been prematurely pre-empted.

**Entry Section** and **Exit Section**.
< Non Critical Section >
< Entry Section >
< Critical Section >
< Exit Section >
< Non Critical Section >

