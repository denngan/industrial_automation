
## Chapter 6 - Real Time

### Keywords

* hard vs soft real time
* determinism vs non-determinism
* task scheduling

### Exam Questions

Q67. **Explain the difference between hard- and soft real time from a probabilistic point of view.**

>**terms:** hard and soft real time
>
>*real time:* produce output that respects predifined time constraints  
>
> * hard real time: meet all time constraints exactly; the probability to make the deadline is 100%  
>probability of a delay to exceed an arbitrary value is zero under normal operating and recovery from error conditions; needed if missing deadline may cause catastrophic consequences on controlled environment   
>*Determinism:* process (time) deterministic, probability to finish in an interval can be expressed in a density function. Thus the probability for a dedaline is predictable.  
>
> * soft real time: meet time constraints most of the time with high probability; the probability to make the deadline is close to 100%  
>probability of delay to exceed an arbitrary value is small but not equal to zero in normal conditions.; meeting the deadline is desirable but no serious damage or danger to the system happens if deadline not met  
>*Non-Determinism:* unpredictable process (times), infinite time in worst case (especially possible with shared resources). Thus there is no 100% guarantee, but only a high probability that a deadline is met. 
>
>missed deadlines can have different effects in different environments: jitter/ deadtime (computers, regulating tasks), overall delays (sequential tasks), endanger safety of process (control system)
>
>**examples:** taking the train, deterministic deadlines, even when late just one train later; taking car, due to traffic and lights a deadline is not 100% predictable.

Q68. **Why should a control system behave deterministically and how can this goal be reached?**

>**terms:** determinism, control system
>
>A *deterministic system* reacts within known bound delays under all conditions (normal and during a recovery from error). This leads to hard-real time behaviour and the guarantee deadlines always being met. That is important becasue delays can endanger the control system environment as a missed deadline can have catastrophic consequences. 
>
>How:
> * all elements form sensor to actor must be deterministic
> * some non-deterministic behavior could be encapsulated
> * base communication on cyclic message operation (with a little idel time inbetween)
> * ensure timely transmission of variables (lost transmission after a few cilces very unprobable, like hardware errors); signal delays should be controlled for safety and availabilty, to not casue false alarms
> * use fast algorithms
>
>Deterministic behavior requires to previosly reserve all resources (CPU and time are underutilized), the communication should be done in a non-blocking fashion and the maximum execution time for each task is fixed.
>
>**examples:** travel to a wedding, important to arrive on time, thus better take the train which has deterministic arrival time

Q69. **Which components of a computer behave non-deterministically?**

>**terms:** non-determinism
>
>*non-determinism:* time bound is unpredictable, delay cannot be predcited to 100% 
>
>non-deterministic parts of computers are: 
> * interrupts (response to asynchronous events form outside world)
> * shared resource access (computing power, shared memory, resource access, network driver)
> * use of non-deterministic devices
>
>further examples are:
> * Scheduling: Operating Systems with preemtive scheduling or virtual memory (UNIX, Windows)
> * Programming languages with garbage collection (Java)
> * Communication collisions: Communication systems using shared mediawith collision (Ethernet)
> * Queues: e.g. for network access (ports, sockets)
> * Interrupts: interrupt latency
> * Caching effects (multi processors) 
> * Shared resources: Memory access latency
>
>**examples:** Interrupts cannot be planned as they happen from the outside and the maximum delay is also unknown, thus non-deterministic

Q70. **What are the classes of scheduling algorithms?**

>**terms:** scheduling
>
>*scheduling:* assignment of processing resources to tasks over time such that each task is executed to completion.
>
> * preemtive: running task interruptable any time to assign CPU to another task based on a predefinde schedule. (rate montonic, online, static priorities, periodic; optimal)
> * non-preemptive: task once started executed by processor until completion without interrupts
>
> * static alorithms: scheduling decisions based on fixed parameters, assigned to tasks before their activation
> * dynamic algorithms: scheduling based on dynamic parameters, changing during system execution
>
>also aperiodic, periodic task scheduling and static deadline monotonic - fixed priority based on deadline
>
>**examples:** ..

Q71. **In the context of real time schedulers, what is a deadline, lateness and slack time (or laxity)?**

>**terms:** real-time, scheduling
> 
>*deadline:* time by which the task execution must be done/completed. This is important for real-time behavior as the deadline must be met alsways or almost always. 
>
>*lateness:* difference between task completion and deadline (should be always or almost always below or equal to zero for real-time)
>
>*slack time (laxity):* maximum time that a task can be delayed but still completed in time/according to deadline. (For real-time: in that time other tasks can be scheduled, but if no laxity other tasks should be interrupted)
>
>**examples:** starting at timestep 0 a task has to be completed at step 10 (deadline) it takes 4 steps to do so the laxity is 6, it is started at step 2 and finished at step 6 so the lateness is -4

