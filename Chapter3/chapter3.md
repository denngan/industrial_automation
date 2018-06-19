## Chapter 3 - Communication Networks

### Keywords

* Field Bus
* hierarchical vs peer-to-peer communication
* cyclic vs event-driven transfer
* Medium access: NTP, PTP
* Synchronization
* Proctocols: 4-20mA, HART, CAN
* Wireless

### Exam Questions

Q24. **What is a fieldbus, what distinguishes it from an office automation bus and which are the criteria for selecting a fieldbus for a given application?**

>**terms:** fieldbus
>A fieldbus is a data network interconnecting an automation system: It usually sends small data values(process variables) and has a bounded delay to ensure realtime. It can operate in a harsh environment and must be robust and easily instaled by skilled people. It offers high integrity and availability, uses cock synchronization works over a long range but has mioderate data rates.
>An office automation bus is just used to connect devices around an office. The data sent is much bigger, like e-mails or pictures or documents. Real time and robustness are not needed on the other hand.
>
>*Criteria for choosing a fieldbus for an application: *
>* data density per unit of length or surface (e.g. 16 Mbits/s on 2m 200kbit/s on 30m)
>* response time
>* throughput over each link
>
>Decide based on: long messages or short messages needed? Realtime bounds, what speed, data rate and poll time needed? distance of cables (where are PLCs and sensors placed in architecture), intrinsically safe, bus powered? 
>
>Over all criteria: device complexity, cost, bus powered, message length type, safety, cable, distance, speed
>
>**examples: ** Not very important/complex task pick slow fieldbus, with small data density, If important, big data density, pick faster fieldbus.

Q25. **What kinds of fieldbus categories exist?**

>**terms:** fieldbus
>
>fieldbus types: sensor bus, high speed field/control bus, low speed fieldbus, data network
>
>*Sensor Bus: * simple devices, low cost, bus powered, short messages(bits), fixed configuration, not intrinsically safe, twisted pair, max distance 500m, very fast <10ms
>*High speed field/control bus: * PLC, DCS, remote I/O, motors, medium cost, not bus powered, message: values/status, not intrinsically safe, shielded twisted pair, max distance 800m, fast ca. 100ms
>*Low Speed Fieldbus: *process intruments, valves, medium cost, bus powered (2 wire), messages: values, status, intrinsically safe, twisted pair (reuse 4-20mA), max distance 1200m, slow >1000ms
>*Data Network:* Workstation, PCs, high cost, not bus powered, long messages (e-mails, files), not intrinsically safe, coax cable, fiber, max distance miles

Q26. **Which information has to be transmitted for each process variable?**

>**terms:** process variable
>
>A process variable is the measured outout from the controlled process. With each process variable we need to retransmit:
>* source identification (naming scheming) 
>*acuurate process value unad units
>* quality indication: {good, bad, substituted}
>* time indication: how long ago was the value produced 
>* optional description
>
>Format could be XML but it is expensive or in datasets that combine devices. Datasets group variables and tret them as offsets. They lead to a low data rate and always the same variables are sent.
>
>**examples: ** temperature from sensor 1 23 celsius, 1 second ago

Q27. **How does a 4-to-20 mA transducer operate?**

>**terms:** 4-20mA
>
>*4-20mA:* most common analog transmission standard. 
>Sensors can connect to the transducer. It limits the current to a value between 4 mA and 20 mA, proportional to the measured value. 0 is the error signal. the voltage drop throughou the cable and due to multiple readers does not produce any error. 
>Simple devices that can be powered by the residual current (4mA)
>So the power and the signal are ransmitted through one cable. Basically the transducer offers point to multipoint communication
>
>**examples: ** flow sensor of water, rotation produces some current that is translated to 4-20mA

Q28. **What is the HART protocol?**

Q29. **What is the difference between hierarchical and peer-to-peer communication?**

Q30. **What are the (dis)advantages of datasets?**

Q31. **Explain the difference between communication by shared memory and by message passing.**

Q32. **Explain how a traffic memory works.**

Q33. **Explain the advantages and respective disadvantages of cyclic and event-driven transmission.**

Q34. **Explain the operation of a cyclic bus with source address broadcast (publisher/subscriber).**

Q35. **Given a cyclic bus of a given propagation time from end to end, a set of variables with their individual period and their frame length, calculate the load of the bus.**

Q36. **Where and how does non-determinism influence industrial communication networks?**

Q37. **Why should a fieldbus provide at the same time a cyclic and event-driven transmission and what is the corresponding application interface for each traffic type?**

Q38. **How are control system devices synchronized to a reference clock? Explain the difference between NTP and IEEE 1588 synchronization.**

Q39. **Discuss advantages and disadvantages of CAN.**

Q40. **Why are wireless solutions both useful and problematic for industrial automation?**

Q41. **Compare HART and WirelessHART**

Q42. **Compare HART and SNMP**