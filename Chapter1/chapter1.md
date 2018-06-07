## Chapter 1


### Keywords

* plants: continuous vs discrete
* processes: continuous vs batch
* control: open loop vs closed loop

### Exam Questions

Q1. **What are the two principal kinds of plants, the way of modeling them and of controlling them?**

> **terms:** plant, control
>
> **discrete vs continuous plants**  
>
> *discrete:* states well defined, non-overlapping; abrupt transitions caused by events. (binary variables - on/off) mainly reversible but not monotone (removing stimulus does not imply previous state)  
>   model: Finite State Machines, Petri Nets, State Transition Tables, Sequential Flow charts etc.  
>   control task: command (control state transitions)  
>
> *continuous:* states described by continuous (analog) variables (temperature, voltage, speed); reversible: output can be brought back to previous value by ackting on input; monotone: increasing input causes output to react monotonous.  
>   model: continuous function F(p)  
>   control task: regulation (maintain state on a determined level or trajectory)  
>
> **examples:** discrete - lift, robot, traffic lights; continuous - oven, plane, car, chemical reactor

Q2. **What are the principal categories of processes? Give examples.**

> **terms:** process
>
> **continuous vs batch process**  
>
> *batch:* discrete processes, handling individual elements/modules  
>   control task: command (control state transitions)  
>   open-loop control
>
> *continuous:* continuous flow of material or energy  
>   control task: regulation (maintain state on a determined level or trajectory)  
>   closed-loop control
>
> **examples:** batch - numerically controlled machine, packaging, bottle filling, manufacturing, chemical process; continuous - motor control, cement, glass, paper production, newspapers (everything with a flow of material, e.g. 90 m/s)


Q3. **To which category do the following applications belong: production of cement, chocolate packaging, traffic lights of crossroads, waste water, bottle-filling, power plant, pulp&paper and which effect does the plant have on the operation of the automation system?**

> **terms:** categories of application: process control, batch control, manufacturing
>
> **categories of application**  
>
> *process control:* continuous processes (flux, flows)  
> power plant, cement, waste water, pulp and paper
>
> *batch control:* semi continuous processes (individual products)
> traffic lights? (because traffic is a flow, but lights are discrete)
>
> *manufacturing:* discrete processes (transformation of parts, factory automation)
> bottle filling, chocolate packaging
>
> **examples:** discrete - lift, robot, traffic lights; continuous - oven, plane, car, chemical reactor
