# Chapter 9 - Dependability


## Chapter 9.1 - Overview

### Keywords

* fault, error, failure
* safety vs security
* reliability, availability, maintainability
* failure modes
* persistency vs integrity

### Exam Questions

Q72. **What is the difference between a fault, a failure and en error?**

>**terms:** fault, failure, error, mission
>
>*mission:* required function of a device in a given time
>
>*fault:* **abnormal condition** that may cause reduction/loss of the required functionality (state) - internal, connected to a component
>
>*error:* **deviation** from a required operation; logical manifestation of a fault in an application leading to a difference between the computed and the true value - internal, connected to a subsystem
>
>*failure:* termination/loss of the ability of item to perform the required function (event) - external, connected to the system
>
>A fault casues an error causes a failure. 
>
>There are different classification for faults and for errors.
>
>**examples:** software bug somewhere in code (line where division by zero happens), software bug becommes apparent when program runs through that if clause and returns an exception instead of a number, computer shuts down.   
>transistor - memory bit stuck/software bug, memory chip - software bug becomes apparent/reading stuck memory, thus wrong result, computer shuts down 

Q73. **What is the difference between reliability, availability and safety?**

>**terms:** reliability, availability, safety
>
>*availability:* ability to be in a state to perform a required function under given conditions at a given instance of time, assuming all external sources are provided. Probability that an item will perform the required function at a given time. A = MTTF / (MTTF+MTTR)
>
>*reliability:* ability (probability) of item to perform a required function under given conditions for a given time interval. R(t) is a function of time. A is the integral of R(t).
>
>*safety:* not that close to dependability. freedom/independence from or elimination of an acceptable risk. Probability that system does not behave in a dangerous way (dangerous states not entererd). If safe states exist - sensitive system, if safe states do not exist - critical system.  
>safety against: 
> * hazards caused by the presence of the control system itself (explosion proof design of equipment)
> * hazards from system, protection by control system
> * hazards from control system malfunction
>
>**examples:** a machine that is down six minutes per hour has availability of 90 %  but the reliability after 57 minutes R(57) could be close to zero. 

Q74. **What is the difference between safety and availability and why do they conflict?**

>**terms:** safety, availability
>
>*availability:* probability that an item performs the required function at a given time.  
>economical objective, increases productive time and yield of the plant, thus increasing productivity; relies on operational redundancy and quality of maintenance
>
>*safety:* probability that the system does not enter a dangerous state  
>regulattory objective, reduces risks to process and environment, thus it lowers insurance rates and overall incident costs; relies on introduction of check redundancy (fail stop systems) and/or operational redundancy
>
>Eeven though both concepts need redundnacy they are contradictory. That is becasue safe states, increasing the safety  are usually considered as unavailable time (not using the system would be saftest). So there is a conflict between payoff and safety.
>
>**examples:** traffic lights when fault detetcted, switch to red or to green?

Q75. **What is the difference between corrective, preventive and predictive maintenance?**

>**terms:** corrective, preventive, predictive maintenance
>
>*maintenance:* ability to restore a system, bringing it back to an upstate; restoring system to an intact, fault-free state, maining restoring failed parts, redundancy and degraded parts and test for and restore faults
>
>*corrective:* repair when part actually fails
>
>*preventive:* restoring to fault free state (only fixing faults), does not stop production if redundnacy is available
>
>*predictive:* condition based maintenance before fault or error detected; *scheduled:* time based maintenance
>
>*deffered maintenance:* postponed maintenance to no productive time
>
>**examples:** bring car to garage when lights fail - corrective; change oil, pump reserve tire - preventive, change oil every year - scheduled; bring to garage after 10 000 kilometers, or when you hear smth - predictive 

Q76. **Which kinds of faults exist in computers and how are they distinguished?**

>**terms:** fault, failure modes in computers
>???
>*software faults:* design faults, systematic faults
>*hardware faults:* physical faults, random faults
>
>**examples:**

Q77. **How can availability of a system be improved?**

>**terms:** availability, operational redundancy
>
>availability can be improved by operational redundancy (and safety check redundancy to find faults)   
>This increases realiability and maintenance quality and fault tolerance, thus also increasing availability. Operational redundnac can be achieved on many levels:  
> * massive redundancy (hardware) -  extend system with redundant components
> * functional redundancy (software) - extend system with unnecessary functions, back-up functions, diversity due to different implementations
> * informative redundancy - encode data with redundant bits (parity bits, checksum crc, hamming code)
> * time redundancy - use additional time (to check or repeat operations)
>
>**examples:** If you have two cars, your availability is increased; or an emergency tire in the trunk. Or two different programs to control PLCs

Q78. **What is the difference between persistency and integrity?**

>**terms:** persistancy vs integrity
>
>*persistency:* output is delivered (otherwise control loss); no safe side, discrete systems - fail-compute
>*integrity:* output is correct and on time or not delivered at all (control loss irreversible and bad for process); continuous system - fail silent
>
>**examples:** hard question in exam - answer question even if wrong or keep it blank


## Chapter 9.2 - Dependability Evaluation

### Keywords

* failure rate
* bathtub curve
* calculate reliability, availability
* markov chains

### Exam Questions

Q79. **Explain why it is a valid assumption to consider the failure rate being constant for reliability calculations.**

Q80. **How can infant mortality be avoided in industrial systems?**

Q81. **Explain the notion of failure rate and its relation to the MTTF.**

Q82. **Calculate the reliability of a system that depends on a set of N elements.**

Q83. **Calculate the reliability of a system that depends on K out of N elements.**

Q84. **How does the reliability of a 2oo3 (TMR, voter) compare with a simplex (1oo1) system?**

Q85. **Calculate the reliability of a system that has a 2oo3 redundancy with repair.**

Q86. **Calculate the reliability of a 1oo2 redundant system (different failure rates).**

Q87. **Calculate the availability of a 1oo2 redundant system (different failure rates and different repair rates).**

Q88. **Set up the equations for calculating the MTTF of a redundant system with repair.**

Q89. **How is the availability of a system that has a 2oo3 structure with repair calculated?**

Q90. **Set up the calculation for the availability of a system given its Markov Diagram.**


## Chapter 9.4 - Dependable Architectures

### Keywords

* computer architectures. integer, persistent
* error detection: online, offline, absolute, relative
* workby vs standby redundancy
* byzantine fault

### Exam Questions

Q91. **Explain/describe the following dependable computer architectures: integer, persistent, integer & persistent.**

Q92. **Present a classification of the different error detection methods.**

Q93. **Illustrate the principles of workby and standby redundancy approaches in the case of a network protocol.**

Q94. **What are the main issues of workby redundant architectures? How are they solved?**

Q95. **What are the main issues of standby redundant architectures? How are they solved?**

Q96. **What are byzantine faults?**

Q97. **Explain different examples of voters in the context of input matching.**


## Chapter 9.6 - Safety Evaluation

### Keywords

* FMEA
* FTA
* SIL

### Exam Questions

Q98. **Explain the main principles of FMEA and FTA.**

Q99. **What is the difference between FMEA and FMECA?**

Q100. **In the context of safety function, what does SIL mean? What is the highest level?**
