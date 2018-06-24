## Chapter 4 - Device Access (Application Layer Protocols)

### Keywords

* SNMP
* MMS
* OPC: Data Access (DA), Alarms and Events (AE), Historical Data Access (HDA)
* Manufacturing Execution System

### Exam Questions

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

Q43. **What is the MMS standard used for and which are its principal services in relation with the engineering, programming and operation of a PLC?**

>**terms:** MMS (Manufacturing Messaging System)
>
>*MMS:* Communication between SCADA and PLCs or little sensors and actuators. Abstraction to access all controllers regardless of the manufacturer . Main principle: Read and write equipment variables using standard messages.
>MMS server (controller) can be any technology; it specifies the MMS objects. MMS client is the SCADA  
>MMS defines communication and commands, so there is no need to program/command each PLC differently. Encoding, message exchange, control is specified. It is not suitable for real-time communication but can access real-time variables. MMS offers some EVent services. The adressing is not specified, MMS usually addresses by IP address using server port 102 with a communication reference for connection identification. MMS has high complexity but is very general and gave rise to simpler models. It is part of almost all PLCs today.
>
>**examples:**

Q44. **Which is the goal of OPC and which specifications does this standard offer?**

>**terms:** OPC (Open Process Protocol)
>
>*OPC:* API for automation  
>*goal:* manufacturer independent application promgramming interface.
>That allows to implement clients accessing data from remote devices easily by defining a set of commands  accessing OPC servers (objects, methods)  
>
>*OPC server:* 
> * supplied by manufacturer of device 
> * communication with devices through proprieterity protocol
> * manages several devices of same type, several servers can run in parallel
>
>*OPC client:*
> * read/write variables
> * read alarms, events; achnowledge alarms
> * retreive historical data (from database)
> * implemented on automation platforms (many act as OPC servers themselves)
>
>Before there was a driver installed for each device, now all this is hidden behind OPC.The major components are OPC DA (data access), OPC AE (Alerms and Events), OPC HDA (Historian Data Access
>
>**examples:**

Q45. **What are the communication technologies on which OPC UA relies?**

>**terms:** OPC UA (Uniform Access)
>
>OPC UA is an enhancement of OPC. It defines generic services and standardizes interfaces and thus it is a service oriented communication framework for exchange of information models. But as opposed to classic OPC, which is based on Microsoft DCOM communication OPC UA also standardizes the transmitted data and enables the encryption and authentication of process data.   
>The UA binary protocol is TCP based, while the HTTP(s) service works with binary and XML messages. So it relies on TCP and HTTPS (UA XML Soap - Webversion or UA Binary - TCP like)
>*Data Model:* Base Node is extended by adding functionality (Object Method Types)  
>*Discovery Mechanism:* identification of devices and their functions within network; aggregation across subnets and intelligent configuration -  less procedure to identify and address network participants
>
>**examples:**  

Q46. **Which services does OPC DA offer and how are variables organized on the client and on the server side?**

>**terms:** OPC DA (data access)
>
>OPC DA provides data access to process variables.
>Process variables sent upon a change, on demand or when given time elapsed. The OPC DA (Data Access) specification addresses collecting Process Variables. Main clients of OPC DA are visualization and (soft-) control.  
>Services offered: read, write of process variables  
>*read:* synchronous, asynchronous, subscribe (notified on change)  
>*write:* synchronous, asynchronous  
>
>The communication is done by groups.   
>The structure is defined during engineering of the attached devices and sensor/actors.  
>*client view:* needs only a subset of PLC items; builds flat groups of items with similar time requirements. The client builds flat groups of items with similar time requirements.   
>*server view:* The client registers groups at server and the server keeps a structure of all its clients. Operations are then done per group.  
>
>OPC DA uses shared memory for communication and thus has no guarantees.  
>
>**examples:**

Q47. **Which modes of reading and writing are available to an OPC client?**

>**terms:** OPC DA (data access)
>
>OPC DA provides data access to process variables.
>Process variables sent upon a change, on demand or when given time elapsed. The OPC DA (Data Access) specification addresses collecting Process Variables. Main clients of OPC DA are visualization and (soft-) control.  
>Services offered: read, write of process variables  
>*read:* synchronous, asynchronous, subscribe (notified on change)  
>*write:* synchronous, asynchronous  
>
>The communication is done by groups. The client registers groups at server and the server keeps a structure of all its clients. The client builds flat groups of items with similar time requirements.  
>OPC DA uses shared memory for communication and thus has no guarantees.  
>
>**examples:**

Q48. **What are the services offered by OPC AE and how are the variables offered to the client?**

>**terms:** OPC AE (Alarms and Events)
>
>The servers registers alarms and events and  makes them available to clients. Those messages should not get lost, thus message passing is used (events in a queue, that all clients have to read). That guarantees the same sequence view and no lost data. The event list can be long, so the entries are not cleared when the state is normal again. The alarm list should be short though, so the alarms are cleared when they are gone.  
>
>*services:*  
> * browse for predefined events
> * enable/disable alarms, events
> * subscribe to alarms and events of interest
> * receive events, alarm notifications with associated attributes
> * acknowledge alarms
>
>**examples:** ..

Q49. **Which is the difference between an alarm and an event and how are these two types of information generated and treated by the SCADA (Operator workplace)?**

>**terms:** alaram vs event
>
>*event:* informative indication of a (normal) process, that is not dangerous if it was ignored; not dangerous change of state   
> * simple: related to process control sytem (change of variable)
> * condition-related: notification about a change of an alarm condition (cleared, acknowledged)
> * tracking-related: origin outside process (operator related)
>
>identified by source, event name + message, time stamp (at different stages: device, controller, OPC server)
>
>*alarm:* indication of an abnormal condition requiring action; critical change of a variable, requiring action or acknowledgement, can be seen as a named state machine.  
>An alarm (in OPC) can have different states: enabled, active (alarm), acknowledged (field acknowledgement - at PLC, client acknowledged - by operator). The alarm condition is active when PLC produces alarm signal for abnormal state. An alarm should never get lost  
>identified by source, alarm name + message, time stamp (at different stages), condition, subcondition, severity, type
>
>Alarms and messages are communicated by message passing. Creating queues and guaranteeing that different clients will see all events in the same sequence. That creates an alarm queue (rather short; the appearance changes when an alarm is acknowledged an the entry is cleared when the alarm signal is cleared) and an event queue (can become long as entries only cleared when read or timed out)  
>The SCADA should show a time stamp, priority, title, description, and the remedial action of an alarm or event. The frequency for an alarm should not be too high (1 alarm/10 min). Events/alarms can be created on level, on deviaton or on rate change. While in SCADA an event is just shown and read/seen, an alarm requires action and has to be acknowledged.
>
>**examples:** event: production start, operator pressed button;  alarm: low tank level (needs to be handled).

Q50. **Explain the mechanism to acknowledge an alarm in a PLC with OPC AE**

>**terms:** alaram
>
>*alarm:* indication of abnormal state form PLC  
>An alarm needs to be acknowledged in OPC AE. There are two possibilities to do so.
> * operator acknowledges condition (client ack)
> * button at PLC is pressed (field ack)
>
>For logging each acknowledge carries an ack ID. Also each acknowledge creates an event and when an alarm turns inactive or is cleared another event is sent.
>
>**examples:** Field Ack: A mechanic changed something in the controlled machine itself and acknowledges the alarm directly at the PLC (maybe some leak in the tank cause a tank empty alarm but the leak was fixed); Client Ack: Some other part of the system was causing the alarm indirectly, but was fixed, so the operator acknowledges the alarm at the SCADA level (Water flow was set to a too high value causing a tank spilling alarm)

Q51. **Explain the difference between the communication paradigms of OPC DA and OPC AE**

>**terms:** message passing vs shared memory, and data access vs alarms amnd events
>
>*Data Access uses shared memory:* offering read, write services  
>returning last value stored, newer ones overwrite old ones  
>no guarantuees: different views and missed changes possible  
>As Data Access is interested in the value right now, not the history or the change it is appropriate  
>
>*Alamrs and Events uses message passing:* offering notifications on change    
>queues of events until read, all clients see the same sequence, nor alarms should be lost   
>guarantuees: no missed changes, same views  
>As alarms and events should not be lost and the change is the priority, message passing is appropriate here
>
>**examples:** Message passing with alarms dangerous, because new one overwrites old one and client cannot keep track, and alarms are lost. If some data should just be accessed though it is an overkill to go through the whole queue that can be very big. This is a danger to real time guarantuees.

Q52. **What is OPC HDA used for and what are the services it offers?**

>**terms:** OPC HDA (Historian Data Access)
>
>*Historian Data Access:* offers access to the historian (raw and ordered) data. The server has access to a historian database and offers the client ordered access to that data with services as follows:
> * browse database
> * retreive data trough filtering
> * aggregates
> * new entries, correct, delete
> * annotations
>
>**examples:** Trend analysis of the system or some parts, business optimization through data analyzation, Event Logger

Q53. **What is a Manufacturing Execution System and how is tied to the performance of a plant?**

>**terms:** MES (Manufacturing Execution System)
>
>*Manufacturing Execution System:* A system for manufacturing, one layer over SCADA for order tracking, resource planning and workflow planning. Handling and using the MES requires a good knowledge of the manufacturing process and organization skills. Areas the MES is used in/for:  
>
> * Resource allocation
> * Quality management
> * Performance analysis
> * Labour management
> * Process management 
> * Document Control 
> * Maintenance management
> * Product tracking etc..
>
>The MES connects the control and the plant itself with the engineering, the suppply chain and other departments of the business.  
>ISA S95 standard defines good practices and gives definitions in that area (interface between enterprise and control system)
>
>**examples:** ..

