## Chapter 2.1 - Instrumentation

### Keywords

* sensors and actuators
* precision vs accuracy
* Measuring Displacements* Measuring Temperature
* P&ID - Instrumentation Diagrams

### Exam Questions

Q59. **What is the difference between precision and accuracy for sensors?**

Q60. **What is the precision of a sensor? How is it linked to the accuracy of a sensor?**

Q61. **Explain the principle of a LVDT sensor (Linear Variable Differential Transformer).**

Q62. **Explain the principle of a capacitive angular sensor.**

Q63. **Explain the principles of strain gauges.**

Q64. **What are the main families of temperature sensors?**

Q65. **Explain the principle of a cold box junction.**

Q66. **What is a P&ID?**

## Chapter 2.2 - Control And Field Level Devices

### Keywords
* PLC
* signal chain
* Control
* Hysteresis and Deadband
* Controllers: Two-point, PID

### Exam Questions

Q7. **What is a controller and what is its purpose? What has to be taken into account when designing it?**

>**terms:** controller
>
>*Controller:* controls plant to reach the preferred output;
>  - measures states fromsensors
>  - send commandsto actuators to stabilize output within useful time
>
>*Designing:* Plant to be controlled has to be known (how variables influence each other and the output)
> - get a plant model through plant identification and specify all parameters (testing)
> - still some disturbances from outer world possible
>
>**example:** controller wants to maintain speed with electrical motor. current could be proportional to speed. Find out with which factor.

Q8. **How is a plant modelled? What is a process variable? What is the control output?**

Q9. **What are the differences between modelling for continuous and discrete processes?**

Q10. **What is the difference between hysteresis and deadband?**

Q11. **What is plant identification? How is it carried out? Explain a step response.**

Q12. **How does a two point regulator operate? Is it a linear system? How is it analyzed?**

Q13. **How does a PID regulator work? What is the influence of each coefficient?**

Q14. **Explain the Ziegler-Nichols method to adjust a PID controller.**

Q15. **What are nested controllers and what is the influence of nesting on their time response?**

Q16. **What is feed-forward control used for?**

Q17. **What characterizes a PLC, which kinds exist and what is their application field?**

Q18. **What criteria need to be evaluated when selecting PLCs for an application?**

Q19. **Describe the chain of signal processing from the sensor to the actors in a PLC.**


## Chapter 2.3 - PLC Programming 

### Keywords

* IEC 61131, Programming Langauges
* Graphical: FBD, SFC, Ladder Diagram
* Textual: Instruction List, Structured Text

### Exam Questions 

Q20. **Which programming languages are specified in IEC 61131 and what are they used for?**

Q21. **Program a simple example in FBD (e.g. a saw tooth generator, a sine wave generator)**

Q22. **Program a simple sequence in SFC (e.g. a recipe, a coffee dispenser)**

Q23. **How is a program executed on a PLC and how does it ensure its real time behavior?**

