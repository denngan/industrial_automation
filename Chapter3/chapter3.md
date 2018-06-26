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

Q24. **What is a fieldbus, what distinguishes it from an office automation bus (data network in an office) and which are the criteria for selecting a fieldbus for a given application?**

>**terms:** fieldbus
>A fieldbus is a data network interconnecting an automation system: It usually sends small data values(process variables) and has a bounded delay to ensure realtime. It can operate in a harsh environment and must be robust and easily instaled by skilled people. It offers high integrity and availability, uses cock synchronization works over a long range but has mioderate data rates.
>An office automation bus is just used to connect devices around an office. The data sent is much bigger, like e-mails or pictures or documents. Real time and robustness are not needed on the other hand.
>
>*Criteria for choosing a fieldbus for an application:*
>* data density per unit of length or surface (e.g. 16 Mbits/s on 2m 200kbit/s on 30m)
>* response time
>* throughput over each link
>
>Decide based on: long messages or short messages needed? Realtime bounds, what speed, data rate and poll time needed? distance of cables (where are PLCs and sensors placed in architecture), intrinsically safe, bus powered? 
>
>Over all criteria: device complexity, cost, bus powered, message length type, safety, cable, distance, speed
>
>**examples:** Not very important/complex task pick slow fieldbus, with small data density, If important, big data density, pick faster fieldbus.

Q25. **What kinds of fieldbus categories exist?**

>**terms:** fieldbus
>
>fieldbus types: sensor bus, high speed field/control bus, low speed fieldbus, data network
>
>*Sensor Bus:* simple devices, low cost, bus powered, short messages(bits), fixed configuration, not intrinsically safe, twisted pair, max distance 500m, very fast <10ms  
>*High speed field/control bus:* PLC, DCS, remote I/O, motors, medium cost, not bus powered, message: values/status, not intrinsically safe, shielded twisted pair, max distance 800m, fast ca. 100ms  
>*Low Speed Fieldbus:* process intruments, valves, medium cost, bus powered (2 wire), messages: values, status, intrinsically safe, twisted pair (reuse 4-20mA), max distance 1200m, slow >1000ms  
>*Data Network:* Workstation, PCs, high cost, not bus powered, long messages (e-mails, files), not intrinsically safe, coax cable, fiber, max distance miles  
>
>**examples:** ..

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
>**examples:** temperature from sensor 1 23 celsius, 1 second ago

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

>**terms:** HART, fieldbus
>
>*HART (Highway Adressable Remote Transducer)* retrofits 4-20mA current loop transducer with digital communication (not for closed loop communication) 
>It modulates  the 4-20mA current  with low-level frequency shift key (fsk) sine wave signal, without affecting the average analog signal. It uses low frequency to deal with bad cabling and a rate of 1200 Bd, which is sufficient.
>Hart communicates point to point with the control of a master. It uses frequencies 1200 Hz for 1 and 2200 Hz for 0, hence commands can be decoded in the frequencies. A Hart frame is charachter oriented and holds universal mandatory commands.
>
>**examples:** nowadays all 4-20 transducers are normally fit with HART. 


Q29. **What is the difference between hierarchical and peer-to-peer communication?**

>**terms:** hierarchical vs peer-to-peer communication
>
>Ways of communication over a fieldbus/controlbus
>*hierarchical:* central master slave, all communication passes through the master (PLC); adding a new PLC is complicated and costly, but simpler abstraction to top
>*peer to peer:* many PLCs exchange data, share inputs and outputs; direct communication, distributed intelligence, redundancy
>
>**examples:** three autonomous carts in a warehouse controlled by a plc each, could commmunicate directly and decide on best strategy via distributed intelligence or be controlled by master that decides on the routes for all.

Q30. **What are the (dis)advantages of datasets?**

>**terms:** dataset
>
>*dataset:* dataframe with grouped variables for devices. 
>As fieldbusses have a low datarate and transmit the same vbraiables all the time it makes sense to group the variables in a dataset and treat the dataset as a whole. The varaibles can be accessed through an offset. Value 1 menas unused, value zero indicates an invalid value. Check values are needed to be sure about the data. Unused values are kept for extensons later.  
>*negative:* not completely extensible because variable identifiers and unused variables are hardcoded, sending more data than needed becasue of the chosen extensibility, different cyclic times not always possible or complicated   
>*positive:* less complexity, variables easier to understand, better structured, each sent variable does not have to be identified 
>
>**examples:** .....?

Q31. **Explain the difference between communication by shared memory and by message passing.**

>**terms:** shared memory vs message passing
>
>Ways of communication over a fieldbus/controlbus on a packet level. The *traffic memory* decouples the bus and an application. Shared memory means using one traffic memory place for all applications. They can access variables directly (two pages for read and write). Each port holds different datasets. For message passing, the values are saved in queues for each application.  
>*shared memory:* newer value overwrites the old one, no guarantuees for same views, changes may be missed based on polling period   
>*message passing:* events kept in a queue until all clients have read it or until it times out, all clients see events in same sequence 
>
>**examples:** either temperature saved in shared memory, then state is important, or as message passing, then every device sees the changes

Q32. **Explain how a traffic memory works.**

>**terms:** traffic memory
>
>*traffic memory:*  decouples the bus and an application and makes process variables directly available.
>Consists of two pages to enable write and read at same time. Saves messages for each port (associated to devices/datasets). Ports hold different datasets. Associateive memory decodes addresses of the subscribed datasets. A bus controller moves data between bus and traffic memory.  
>Freshness supervision needed, becasue stale data is useless and may be dangerous.   
>*freshness counter* for each port in traffic memory. reset by bus or application when writing toi that port. incremented regularly by application or bus controller. app reads counter and compares it to tolerance
>
>**examples:** app x subscribed to port 1 and 3 for temperature info in two rooms. associative memory maps those two ports two places (bytes or offsets) in the traffic memory. app x reads the data, checks if fresh

Q33. **Explain the advantages and respective disadvantages of cyclic and event-driven transmission.**

>**terms:** event driven vs cyclic transmission
>
>Ways of transmitting data
>*cyclic:* send value strictly every x milliseconds. bus master polling addresses in fixed sequence, data trannsmission in fixed intervals  
> + pros: delivery rate and refresh rate deterministic  
> - cons: roundtrip delay limit bus extension, cycles have to be preconfigured and cannot be changed later, no explicit error recovery, unnecessary traffic under steady state  
>
>*event driven:* send when value changes by more than x percent, transmission only when state changes  
> + pros: large numbers of events can be handled if not at same time and thus large number of stations, idle under steady state, better resource use, suitable for standard OS, uses write only transfers, good for LANs with long propagation time.  
> - cons: intelligent stations needed for event building, shared access to resources needed (arbitration), no upper access time limit if some component undeterministic, response time difficult to estimate, limited by congestion effects. Background cyclic operation for liveness, collisions possible
>
>**examples:** temperature maybe quick changes are more important -  maybe events, valve/door only open or close - cyclic

Q34. **Explain the operation of a cyclic bus with source address broadcast (publisher/subscriber).**

>**terms:** cyclic, address broadcast
>
>As ususllay variables are only read by a few devices, broadcasting messages indentified by their source is more efficient. One variable can only have one source (publisher) but multiple subscribers. Each station (subscriber snoops the bus and reads the variables it is interested in). Bus refreshes plant image in the background.
>
>**examples:** ..


Q35. **Given a cyclic bus of a given propagation time from end to end, a set of variables with their individual period and their frame length, calculate the load of the bus.**

>**terms:** cyclic bus
>
>compute: number_of_data_transmitted * duration_of_each_poll  
>..

Q36. **Where and how does non-determinism influence industrial communication networks?**

>**terms:** non-determinism, medium access 
>
>especially when transmission is event driven - events unpredictable  
>non-deteerminism in medium-access (MAC layer - packets), transmission time has to be predictable but depends on medium access procedure of the bus  
>collisons possible with event driven transmission: non-deterministic, use CSMA/CA medium access; Token Passing, Central Master, Binary bisection are deterministic medium access algorithms  
>Additionally queues are not deterministic  
>
>**examples:** Queue length cannot be predicted. Maybe two events happen at similar times becasue of correlations, then messages will cause a collision. CSMA/CA deals with collisions and sends later but its unclear when the package will arrive.

Q37. **Why should a fieldbus provide at the same time a cyclic and event-driven transmission and what is the corresponding application interface for each traffic type?**

>**terms:** cyclic vs event driven transmission
>
>Both transmission types needed for different tasks  
>*cyclic transmission:* large bandwidth, only for critical variables; **process data:** state of plant, short urgent data  
>*message transmission:* for not critical long messages (e.g. diagnostics) needed **message data:** changes of plant, infrequent long messages  
>
>**examples:** process data - motor current, axel speed, computer's commands; message data - set points, diagnostics (users), initialization, downloading (system)

Q38. **How are control system devices synchronized to a reference clock? Explain the difference between NTP and IEEE 1588 synchronization.**

>**terms:** reference clock
>
>Often the exact sampling time of a variable is needed, so clocks need to be synchronized to recinstruct events.  
>*master-slave bus: * master distributes  time as a bus frame, the time is relative to the master  
>*demanding system:* time distribution of seperate lines as relative time, e.g. PPS (pulse per second) or as absolute time e.g. IRIG -B; very accurate  
>*Data Networks:* reference clock distribution, protocol evaluates path delays - NTP (Network Time Protocol, 1ms accuracy), PTP (Precise Time Protocol 1 microsecond accuracy)  
>*NTP:* client sends time request and gets time response, get network delay and the current time; assysmetric nets pose a problem  
>*PTP (IEEE 1588):* all devices collaborate to estimate the delays, compute residence time from master clock and peer delay (path delay to neighbour), adjust residence time based on peer delay  
>
>NTP and PTP both take delays into accounts. NTP is less precise and a little more simple. PTP computes all residence delays in all directions to deal with asynchronous nets.
>
>**examples:** ..

Q39. **Discuss advantages and disadvantages of CAN.**

>**terms:** CAN
>
>*CAN:* fieldbus; mastership: multi-master, 12 bit-bisection, bitwise arbitration; link-layer control: connectionless (command/reply/acknowledgement); upper layers: no transport, no session, implicit representation  
>
>*pros:* supperted by user organizations (Honeywell etc.), many low cost chips often free with embedded controllers, application layer definition, application layer profiles, bus analysation and configuration tools available, market: industrial automation, cars  
>*cons:* limited product distance x rate, sluggish real time response (2,5ms), non-deterministic medium-access, several incompatible application layers (CanOpen, DeviceNet) strongly protected by Bosh patents, interoperability questionable (many different implementations), small data size, limited number if registers in chips, no standard message services  
>
>**examples:** .. when is it usable?

Q40. **Why are wireless solutions both useful and problematic for industrial automation?**

>**terms:** wireless
>
>*wireless connection:* wireless fieldbus  
>*useful:* reduced installation and configuration costs, easy access to machines (for diagnostics or programming), improved factory floor coverage, eliminates cable damaging, globally accepted standards  
>*problematic:* communication less reliable (high bit error rate, burst channel errors happen, inference fading) while deadlines and reliability are needed. So correction codes and special transmitter designes need to be used (forward error correction - redundancy encoding, Automated Repeat Request, Deadline dependent coding)  
>
>**examples:** soft or hard real time needed for automation task while at home no real time needed. So at home all the errors are ok but in control task it is critical

Q41. **Compare HART and WirelessHART**

>**terms:** HART, Wireless
>
>The protocols differ in the network, data link and physical layer. On top of those layers they use the same protocol.
>
>*Network layer:* routing  
>HART: No need for special protocols  
>WirelessHART: Power-Optimized, redunant Path, Self-Healing Wireless Mesh Net  
>
>*Data Link:* Data packet structure, framing, error detection  
>HART: Binary, Byte oriented, Token Passing Master Slave Protocol  
>WirelessHART: Secure and reliable, time synchronized, TDMA/CSMA, Frequency agile with ARQ (Collision and inference avoidence, channel hopping and black lists)  
>
>*Physical:*   
>HART: Simultaneous analog and digital signaling, 4-20 mA copper wiring  
>WirelessHART: 2,4 GHz radios, 10 dBm Transmission power 250 kbit/s data rate  
>
>**examples:** 

Q42. **Compare HART and SNMP**

>**terms:** HART, SNMP


| citeria      | HART           | SNMP |
| ------------- |:-------------:| :-----:|
| Resources    | less | more |
| Application     | sensors/actors to PLS      |   network management |
| monitoring | yes      |   yes |
| events   | no | (yeah but often not used) |
| communication pattern     | request, response     |   request, response (+traps) |
| real time | ..   |    .. |
| security |..|..|


>**examples:** 
