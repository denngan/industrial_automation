## Chapter 5 - SCADA

### Keywords

* Supervision
* Data Aquisition
* HMI
* Alarms and Events
* Historian, Logging, Trends

### Exam Questions

Q54. **What are the main functionalities of a SCADA?**

>**terms:** SCADA (Supervision Control and Data Aquisition)
>
> * Data Aquisition: store process data in database
> * HMI (Human Machine Interface): graphical object state presentation, lists, reports
> * Operator command handling: change binary commands, set points, prepare and run recipes, batches, scripts (command procedures)
> * Alarms and Events: Alert the operators of a specific event, record specified changes and operator actions
> * History database: keep record of process values and fiter them
> * Measurement processing: calculate derived values (limit supervision, trending)
> * Logging: keep logs on the operation of the automation system
> * Reporting: generate incident reports
> * Interfacing to planning & analysis functions: Forecasting, Simulation, historian, etc.
>
>**examples:** 

Q55. **What is a process database and what is the difference with an historical database?**

>**terms:** process data base, historian database
>
>*process data base:* represents the current state of plant, older values are irrelevant and overwritten.   
>actaulized by: *polling* - synoptic view fetches data regularly from database or devices; *events* - devices send data that changed in database triggering the views
>
>*history database:* stores process data from history over time (data compression), offers trends and a historian (offering performance indicators, quality monitoring, data mining, analysis of situations)  
>
>So while the process database represents the current state of the pplant very precisely the history database stores many plant states from history with less precision.
>
>**examples:** ..

Q56. **What are the typical pitfalls to avoid when designing synoptic views?**  

>**terms:** synoptic views
>
>*synoptic views:* views of a process variables displayed visually on the HMI. The HMI is important for good supervision and alarm handling
>
>common mistakes:  
> * lots of numbers without structure on screen
> * inconsistent use of colors
> * too many colors
> * no trend shown
> * no condition information
> * no global overview
> * inefficient space use
>
>data is not information: always add the possibility to assess, compare, rate the results (indication and trend)
>
>tips:
> * get rid of necessary details
> * do not get too fancy
> * bright colors - alarms
> * no unnecessary animation
> * no capital letters
> * grids for order
> * columns, sections (12 column design)
> * use similar icons
> * use same data format and terminology
>
>**examples:** ..

Q57. **Which is the difference between an alarm and an event?**  

>**terms:** alarm, event
>
>*alarm:* audible/visual indication of an abnormal condition. Requires some response or action otherwise, leading to dangerous situations.  
>Compute alarm level: critical level - safety margin - operation reaction time * max rate    
>frequencies: 1 alarm/10 min per operator (nominal), 1 alarm/5 min (maximal), more than 10 alarms/10 minutes (avalanche situation); recommended average number of active alarms: less than 10  
>alarm consist of: title, priority, description, timestamp, remedial action. (on levels, deviation, change rate)
>
>*event:* informative indication of normal/abnormal process/function which if ignored does not put the process in danger (no immediate action required)  
>event consists of: title, description, timestamp
>
>**examples:** event - periodic maintenance required; alarm - tank spilling

Q58. **What is an Historian for SCADA and what is its purpose?**

>**terms:** historian
>
>*historian:* keeps old relevant process data in low granularity but large quantity  
>The historian stores aggregated data form different sources in one database using data compression. It allows to analyse data to retreive metrics (perormance indications, quality monitoring, situation analysis)

