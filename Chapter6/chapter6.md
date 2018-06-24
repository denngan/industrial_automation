
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
> * hard real time: meet all time constraints exactly; the probability to make the deadline is 100%  
>probability of a delay to exceed an arbitrary value is zero under normal operating and recovery from error conditions; needed if missing deadline may cause catastrophic consequences on controlled environment   
>*Determinism:* process (time) deterministic, probability to finish in an interval can be expressed in a density function. Thus the probability for a dedaline is predictable.  
>
> * soft real time: meet time constraints most of the time with high probability; the probability to make the deadline is close to 100%  
>probability of delay to exceed an arbitrary value is small but not equal to zero in normal conditions.; meeting the deadline is desirable but no serious damage or danger to the system happens if deadline not met  
>*Non-Determinism:* unpredictable process (times), infinite time in worst case (especially possible with shared resources). Thus there is no 100% guarantee, but only a high probability that a deadline is met. 

Q68. **Why should a control system behave deterministically and how can this goal be reached?**

Q69. **Which components of a computer behave non-deterministically?**

Q70. **What are the classes of scheduling algorithms?**

Q71. **In the context of real time schedulers, what is a deadline, lateness and slack time (or laxity)?**

