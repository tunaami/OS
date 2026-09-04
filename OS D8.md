#operating-systems 

**Requirements of Critical Section Problem in** [[OS D7]] **to be satisfied by the sync mechanism** -
1. *Mutual Exclusion* - no two processes should be present in the Critical Section at the same time. **Inconsistency and Data Loss**
2. *Progress* - a process which isn't interested in the critical section should not block other processes from it. **Starvation**
3. *Bound waiting* - no process has to wait to access the Critical Section. there should be a bound on number of times a process accesses the critical section. **Unfair Solution**


