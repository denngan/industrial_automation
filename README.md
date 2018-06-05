## EPFL - Industrial Automation

This site is supposed to support the exam preparation for the EPFL course **Industrial Automation**. 
For more information and chapter slides visit the course's [moodle page](https://moodle.epfl.ch/course/view.php?id=14114).


### Course Structure

The course consits of 7 chapters (chapter 1-6 and chapter 7):

* Chapter 1: Automation Overview
* Chapter 2: Sensors, Actuators and Control
* Chapter 3: Communication Networks 
* Chapter 4: Device Access - Application Layer Protocols
* Chapter 5: Supervision 
* Chapter 6: Real Time
* Chapter 9: Dependability


### Exam

#### Exam Conditions

The exam comprises the course as it is downloadable as power point slides and/or pdf on Moodle on May 31st, 2018. There will be no change to the slides after that date.  
 
The exam lasts 15 minutes per candidate; it consists of three questions taken from this list. There is no preparation time at the exam. The exam is conducted in English.  
 
You are allowed to bring two handwritten A4 sheets to the exam but no electronic, photocopied or printed material.  You can write on both sides of the two sheets, so you can fill four pages in total. 
 
*2018.06.01 Y.A. Pignolet and J.C. Tournier*


#### Answering Exam Questions

To answer questions in the exam you should be able to follow the following three steps:

1. Understand all technical terms in or connected to the question and be able to define them first if necessary
2. Answer the actual question theoretically
3. Be able to give examples to show practical understanding of concepts


#### Exam Quetions

The list of possible exam questions can be found either below or on moodle.

1. What are the two principal kinds of plants, the way of modeling them and of controlling them? 
2. What are the principal categories of processes? Give examples.  
3. To which category do the following applications belong: production of cement, chocolate packaging, traffic lights of crossroads, waste water, bottle-filling, power plant, pulp&paper and which effect does the plant have on the operation of the automation system?  
4. List the layers in a control system and their functions. How are the response time and the complexity of the decisions related to each other? 
5. Draw the hierarchy of an automation system with its communication networks and characterize the traffic. 
6. What is the difference between a centralized and a distributed control system? What are their advantages and disadvantages? 
7. What is a controller and what is its purpose? What has to be taken into account when designing it?
8. How is a plant modelled? What is a process variable? What is the control output?  
9. What are the differences between modelling for continuous and discrete processes?  
10. What is the difference between hysteresis and deadband?
11. What is plant identification? How is it carried out? Explain a step response.
12. How does a two point regulator operate? Is it a linear system? How is it analyzed?  
13. How does a PID regulator work? What is the influence of each coefficient?  
14. Explain the Ziegler-Nichols method to adjust a PID controller.
15. What are nested controllers and what is the influence of nesting on their time response?  
16. What is feed-forward control used for?  
17. What characterizes a PLC, which kinds exist and what is their application field? 
18. What criteria need to be evaluated when selecting PLCs for an application?
19. Describe the chain of signal from the sensor to the actors in a PLC
20. Which programming languages are specified in IEC 61131 and what are they used for?  
21. Program a simple example in FBD (e.g. a saw tooth generator, a sine wave generator)
22. Program a simple sequence in SFC (e.g. a recipe, a coffee dispenser) 
23. How is a program executed on a PLC and how does it ensure its real time behavior? 
24. What is a fieldbus, what distinguishes it from an office automation bus and which are the criteria for selecting a fieldbus for a given application?  
25. What kinds of fieldbus categories exist? 
26. Which information has to be transmitted for each process variable? 
27. How does a 4-to-20 mA transducer operate? 
28. What is the HART protocol? 
29. What is the difference between hierarchical and peer-to-peer communication?  
30. What are the (dis)advantages of datasets?
31. Explain the difference between communication by shared memory and by message passing.
32. Explain how a traffic memory works.
33. Explain the advantages and respective disadvantages of cyclic and event-driven transmission. 
34. Explain the operation of a cyclic bus with source address broadcast (publisher/subscriber).
35. Given a cyclic bus of a given propagation time from end to end, a set of variables with their individual period and their frame length, calculate the load of the bus.
36. Where and how does non-determinism influence industrial communication networks?
37. Why should a fieldbus provide at the same time a cyclic and event-driven transmission and what is the corresponding application interface for each traffic type? 
38. How are control system devices synchronized to a reference clock?  Explain the difference between NTP and IEEE 1588 synchronization. 
39. Discuss advantages and disadvantages of CAN.
40. Why are wireless solutions both useful and problematic for industrial automation?
41. Compare HART and WirelessHART 
42. Compare HART and SNMP  
43. What is the MMS standard used for and which are its principal services in relation with the engineering, programming and operation of a PLC? 
44. Which is the goal of OPC and which specifications does this standard offer? 
45. What are the communication technologies on which OPC UA relies?
46. Which services does OPC DA offer and how are variables organized on the client and on the server side?  
47. Which modes of reading and writing are available to an OPC client?  
48. What are the services offered by OPC AE and how are the variables offered to the client?  
49. Which is the difference between an alarm and an event and how are these two types of information generated and treated by the SCADA (Operator workplace)? 
50. Explain the mechanism to acknowledge an alarm in a PLC with OPC AE  
51. Explain the difference between the communication paradigms of OPC DA and OPC AE 
52. What is OPC HDA used for and what are the services it offers?
53. What is a Manufacturing Execution System and how is tied to the performance of a plant?  
54. What are the main functionalities of a SCADA? 
55. What is a process database and what is the difference with an historical database? 
56. What are the typical pitfalls to avoid when designing synoptic views? 
57. Which is the difference between an alarm and an event?
58. What is an Historian for SCADA and what is its purpose?
59. What is the difference between precision and accuracy for sensors? 
60. What is the precision of a sensor? How is it linked to the accuracy of a sensor?
61. Explain the principle of a LVDT sensor (Linear Variable Differential Transformer).
62. Explain the principle of a capacitive angular sensor.
63. Explain the principles of strain gauges.
64. What are the main families of temperature sensors? 
65. Explain the principle of a cold box junction. 
66. What is a P&ID? 
67. Explain the difference between hard- and soft real time from a probabilistic point of view.
68. Why should a control system behave deterministically and how can this goal be reached? 
69. Which components of a computer behave non-deterministically? 
70. What are the classes of scheduling algorithms?
71. In the context of real time schedulers, what is a deadline, lateness and slack time (or laxity)? 
72. What is the difference between a fault, a failure and en error?
73. What is the difference between reliability, availability and safety? 
74. What is the difference between safety and availability and why do they conflict? 
75. What is the difference between corrective, preventive and predictive maintenance?
76. Which kinds of faults exist in computers and how are they distinguished? 
77. How can availability of a system be improved? 
78. What is the difference between persistency and integrity?
79. Explain why it is a valid assumption to consider the failure rate being constant for reliability calculations. 
80. How can infant mortality be avoided in industrial systems?
81. Explain the notion of failure rate and its relation to the MTTF. 
82. Calculate the reliability of a system that depends on a set of N elements. 
83. Calculate the reliability of a system that depends on K out of N elements.
84. How does the reliability of a 2oo3 (TMR, voter) compare with a simplex (1oo1) system? 
85. Calculate the reliability of a system that has a 2oo3 redundancy with repair. 
86. Calculate the reliability of a 1oo2 redundant system (different failure rates). 
87. Calculate the availability of a 1oo2 redundant system (different failure rates and different repair rates). 
88. Set up the equations for calculating the MTTF of a redundant system with repair. 
89. How is the availability of a system that has a 2oo3 structure with repair calculated?
90. Set up the calculation for the availability of a system given its Markov Diagram.
91. Explain/describe the following dependable computer architectures: integer, persistent, integer & persistent. 
92. Present a classification of the different error detection methods.
93. Illustrate the principles of workby and standby redundancy approaches in the case of a network protocol. 
94. What are the main issues of workby redundant architectures? How are they solved? 
95. What are the main issues of standby redundant architectures? How are they solved?
96. What are byzantine faults?  
97. Explain different examples of voters in the context of input matching. 
98. Explain the main principles of FMEA and FTA.
99. What is the difference between FMEA and FMECA? 
100. In the context of safety function, what does SIL mean? What is the highest level? 
 
