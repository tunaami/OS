#operating-systems 

SJF ([[OS D5]]) is the most optimal scheduling algorithm but we do not know about the burst times of process beforehand.
### Prediction Techniques

**Static** - By size; you can say take a process of 100kB and realize its running for 20 seconds, so another process of similar size will run for almost 20 seconds as well.
By type; **OS** - 5s, **Interactive** - 10s, **Foreground** - 15s, **Background** - 30s

**Dynamic** - Exponential Average Technique
T(n+1) = k t(n) + (1-k)T(n)

t = completed BT
T = predicted BT

*However the problem of starvation of longer processes against shorter processes still continues*.

#### Highest Response Ratio

**Selection Criteria** - (WT + BT) / BT
Sometimes BT is also called service time (S).


