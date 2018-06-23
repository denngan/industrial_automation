## Chapter 4 - Device Access (Application Layer Protocols)

### Keywords

* SNMP
* MMS
* OPC: Data Access (DA), Alarms and Events (AE), Historical Data Access (HDA)
* Manufacturing Execution System

### Exam Questions

Q42. **Compare HART and SNMP**

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
>
>
>

Q47. **Which modes of reading and writing are available to an OPC client?**

Q48. **What are the services offered by OPC AE and how are the variables offered to the client?**

Q49. **Which is the difference between an alarm and an event and how are these two types of information generated and treated by the SCADA (Operator workplace)?**

Q50. **Explain the mechanism to acknowledge an alarm in a PLC with OPC AE**

Q51. **Explain the difference between the communication paradigms of OPC DA and OPC AE**

Q52. **What is OPC HDA used for and what are the services it offers?**

Q53. **What is a Manufacturing Execution System and how is tied to the performance of a plant?**



