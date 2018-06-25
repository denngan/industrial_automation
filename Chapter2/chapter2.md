## Chapter 2.1 - Instrumentation

### Keywords
* sensors and actuators
* precision vs accuracy
* Measuring Displacements
* Measuring Temperature
* P&ID - Instrumentation Diagrams

### Exam Questions

Q59. **What is the difference between precision and accuracy for sensors?**

>**terms:** sensor
>
>*sensor:* measures some process variable, returning a value either digital or continuous
>
>*Precision (repeatability):* how reproducable, close are identical measurements - percentage of full scale
>*Accuracy (deviation):* how close is the measurement to the true value - if bad then systematic error or bad calibration
>
>*resolution:* smallest change/unit that can be measured/displayed. (How many differnet levels can be distinguished)
>
>**examples:**  ...

Q60. **What is the precision of a sensor? How is it linked to the accuracy of a sensor?**

>what exactly is the difference to question 59?

Q61. **Explain the principle of a LVDT sensor (Linear Variable Differential Transformer).**

>**terms:** LVDT sensor (Linear variable differential transformer)
>
>The LVDT sensor measures linear displacement.  
>coil - establishinga magnetic flux + one secondary coil on each side in series but opposite directions  
>moving armature in the middle  
>If the armature is in the center, the magnetic flux is equal in both secondaries (180 degrees out of phase)  
>When the armature moves voltage is produced proportional to the displacement
>
>**examples:** ..

Q62. **Explain the principle of a capacitive angular sensor.**

>**terms:** capacitive angle
>
>*capacitive angle:* measures agle/position  
>Using the capacitance between two areas. The capacitance depends on the area that overlaps. If the angle changes, the capacitance changes proportional to the area and angle.
>
>**example:** .. 

Q63. **Explain the principles of strain gauges.**

>**terms:** strain gauge
>
>*strain gauge:* measure small displacements  
>resistance of wire (with resistivity p) increases when the wire is streched.  
>Measure the resistance change ang get the displacement through the formula R=l^2  (use the wheatstone bridge to measure the resistance change, is uses dummy gauges for temperature compensation)
>
>**examples:** detect movements in buildings, bridges, dams

Q64. **What are the main families of temperature sensors?**

>**terms:** temperature sensor
>
>*Temperature sensor:* measure temperature, very frequently used in industry
>
> * Thermistance: (RTD resistance temperature detector) metal's resistance depends on its temperature - cheap, robust, high temperature range; requires current source, non-linear
>
> * Thermistor: (NTC negative temperature coefficient) semiconductor's resistance depends on the temperature - very cheap, sensible; strongly non-linear, fragile, self-heating 
>
> * Thermo-element: pair of dissimilar metals generates a voltage proportional to the temperature difference between the cold and warm junction (Seebeck effect) - high precision, high temperature, punctual measurement; low voltage, requires cold junction compensation, high amplification, linearization
>
> * Spectrometer: measures infrared radiation by photo sensitive semiconductors - highest temperature, measures surface, no contact; highest price
>
> * Bimetal: mechanical (yes/no or on/off temperature indication), difference in dilation coefficients of two metals - very cheap, widely used; limited representation power
>
>**examples:** bimetal - toaster, when too hot - spectrometer, when very precise - thermo-element or thermistor

Q65. **Explain the principle of a cold box junction.**

>**terms:** cold box junction, thermo-element
>
>*thermo-element:*  two dissimilar conductors (metals) generate a voltage proportional to the temperature difference between the cold and warm junction (Seebeck effect). The hot junction measures the actual temperature while the cold junction has the reference temperature.
>
>**examples:** .. 

Q66. **What is a P&ID?**

>**terms:** P&ID
>
>*P & ID:* (piping and instrumentation diagram) shows flows in a plant and corresponding sensors and actors; It assigns a name/tag and parameters to each instrument, the tag identifies the instrument in the field  
>The P&ID uses symbols and circles for each instrument and shows the overall connections, naming parts and identifying functions  
>Hydraulic/pneumatic, electrical elements and instruments are mixed.  
>For clarity a set of symbols from the standard ISA S5.1 is used.  
>All in all a P&ID provides a standardized way to draw a plant's architecture.
>
>**examples:** ...


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
>  - send commands to actuators to stabilize output within useful time
>
>*Designing:* Plant to be controlled has to be known (how variables influence each other and the output)
> - get a plant model through plant identification and specify all parameters (testing)
> - still some disturbances from outer world possible
>
>**example:** controller wants to maintain speed with electrical motor. current could be proportional to speed. Find out with which factor.

Q8. **How is a plant modelled? What is a process variable? What is the control output?**

>**terms:** plant, process variable
>
>*model of a plant:* modelled as a process with relations between parts of plant; correlation between input and output of the plant either as a function (continious) or state change (discrete)
>
>*process variable:* measured output from the plant's process, defines state of plant, influenced (~controlled) by control system.
>
>*control output:* command from controller; controller gets set-point (desired value of process variable) and meausured process var (as-is state). Based on the error (differents between desired and measured) the controller creates an output to stabilize the controll objective. (Feedback loop/closed loop control) Additionally disturbances have to be taken into account, as they also influence the process variable.
>
>**examples:** vebntilation system. process: fan cools the air based on fan speed (maybe proportional/exponential etc.); temperature - process var (fan speed too); controller output - command to make fan slower because room was colder than desired.

Q9. **What are the differences between modelling for continuous and discrete processes?**

>**terms:** contiuous, discrete process
>
>*continuous process:* analog variables (goal of control: keep level, trajectory); output modelled as function based on input; controlled variable continuously measured and compared to a reference; then influence the process to adjust to the reference - closed loop control (controlled variable influences itself in a closed action path). 
>
>*discrete process:* binary variables (goal of control: stay in desired state); output modelled as state transitions/state change; input influences output based on defined system laws but output does not continuously influence itself.
>
>**examples:** plane vs traffic lights or door open/closed/locekd mechanism

Q10. **What is the difference between hysteresis and deadband?**

>**terms:** hysteresis, deadband
>
>effects that cause diifferent than expected behaviour in control systems
>
>*hysteresis:* difference of valve position on up- and down-stroke
>
>*deadband:* no movement of valve due to slack space (usually when changing directions)
>
>Include the effects in switchpoint calculation (for two-point controller) when the process is not slow enough to avoid waring off the contacter (and limit switching frequency)
>
>**examples:** valve controlling water flow in pipe or air flow for temperature

Q11. **What is plant identification? How is it carried out? Explain a step response.**

>**terms** plant identification
>
>*plant identification:* finding an exact model describing the plant
>if countinuous plant find find the relation between input and output variables and formulate it as a function, if discrete define stage transitions based on input
>realtions usually approximately knwon -> determine exact parameters by measuring (signal correlation between response to pulse at input and response to noise at input yields parameters)
>
>**examples:** electric car, speed control: speed might be proportional to voltage, but parameter depends on fraction of tires and street. So drive the car and measure speed with different voltages and different streets (noise)

Q12. **How does a two point regulator operate? Is it a linear system? How is it analyzed?**

>**terms**: two-point regulator
>
>binary control output (on/off) based on upper and lower switch-point (keep value between to set-points). Take hysteresis and deadband into account for lower switching frequency.
>
>**examples:** regulate temperature in a room with heating instrument. Cooling happens slower than heating -> not linear. Turn heating on when colder that 17 degrees and off if warmer than 20 degrees.

Q13. **How does a PID regulator work? What is the influence of each coefficient?**

>**terms:** PID regulator
>
>The PID regulator is widely used and is based on a control loop. That means the controller calculates the error between the measured output (obtained from the feedback loop) and the set-point. Then it minimizes this error by adjusting the control output. 
>The realtion between the error and the control output is described as a differential equation, based on the plant model. PID is a combination of three control parts:
>*P - conttrol:* proportional factor; amplifies the error. A little error still stays even after convergence. This error increases with a bigger set-point or load change. The bigger the factor the smaller the final errro but the bigger the oscillation. *proportional output to error but small error still exists*
>*PI - control:* proportional integrator; reduces the error asymptotically to zero, but very slow; Gets faster with bigger factor but also more unstable *reduces error completely but slow*
>*PD - control:* proportional differentiation; reacts proportional to slope of error change  *speeds up a stable response*
>
>**examples:** adjustion to step response

Q14. **Explain the Ziegler-Nichols method to adjust a PID controller.**  

>**terms:** PID controller
>
>Goal: adjust PID controller, meaning right values for {K_p}, {T_i}, {T_D}. Configuring these parameters is done by setting them empirically. Times and values to consider/ minimize are Risetime (time until control response first reaches set point), Overshoot/undershoot (Biggest oscillation over and under set value), Settling time (Time until output has stabilized enough to be close enough to required output), Steady state error (error still left after output has stabilized).
>Steps (Assuming that the process is stable at the operating value):  
>*Step 1:* set {T_i}, {T_D} to off.
>*Step 2:* actual value differs now from solicited value by proportional factor. 
>*Step 3:* wait for value to stabilize and reduce {K_p} until process var starts to oscillate (Oscillation value T)
>*Step 4:* increase {K_p} until value stabilizes again (Band value B)
>Set value according to B,T and valie on table on slide 55 (not preventing overshoot..)
>
>**examples:** EPFL bought PID controller for temperature in a room. Some PID controllers do configuration more or less automatically. Other wise an expert has to manually set it.

Q15. **What are nested controllers and what is the influence of nesting on their time response?**

>**terms:** nested controller, time response
>
>Nested conrollers are layers of control loops. One controllers output is then the set point of the inner controller. The inner controller's influenced process variable influences the process var that the outer controller wants to control.
>The goal of nested controllers is to maintain an output variable without exceeding other variable limitations.
>The time response measures how fast the controllers output influences the process variable and how fast the controller gets back the measured variable through the feedback loop. The time response in the inner loop is the fastest while the outer loop is the longest.
>
>**examples:** speed control for wheels. outer controller decides on accelaration to reach a speed, inner controller computes rotation speed for the wheels (might have some maximum rotation)

Q16. **What is feed-forward control used for?**  

>**terms:** feed forward control
>
>A feed forward controller is used when the plant is known and also the disturbances. First the controller gets the output close to the set-point. The controller output can be corrected based on the measured disturbances (feed forward).
>Then the controller regulates based on the error(feedback) and corrects small deviations.
>
>**examles:** Plane, the wind could be a disturbance, if flying in direction of wind the plane needs to use less energy for the same speed, that can be computed before hand if wind is measured.

Q17. **What characterizes a PLC, which kinds exist and what is their application field?**  

>**terms:** PLC
>
>*PLC (Programmable logic controller)*: small computer, dedicated to automation tasks in industrial environments; today real-time(embedded) computer with extensive input/output
>A PLC measures, controls, commands, protects and might log and have a small HMI. It is connected to a network and has both digital and analog inputs and outputs.
>There are three kinds of PLCs: Compact(monolithic), modular (backplane extensible), Soft-PLC
>
>*Compact:* one piece, fixed case, fixed I/O number, no additional processing power, cheap, fieldbus extension possible, sometimes LAN connection; Application: simple control tasks of small sonsors or actuators, number of I/O is limited
>
>*Modular:* has modules, can be tailored/is extensible, high processing power, large I/O choice, requires marshalling of signals; Applications: Complex control task, very specialised, many I/O, a lot of data to process. Cost effective if rack can be filled, if I/Os could be extended.
>
>*Soft-PLC:* used as engineering workstation, real-time processing, HMI, Linux or Windows-based automation products,Direct use of CPU or co-processors; Application: fieldbus gateway to distributed I/O system, Or for sensors/ actuators who use linux, when HMI is needed, task rather simple and security not so important.
>
>**examples:** use a compact PLC for controlling a simple fan, modular for control of big factory or some complex machine, Soft PLC for simple not critical task

Q18. **What criteria need to be evaluated when selecting PLCs for an application?**  

>**terms:** PLC
>Criteria for PLC evaluation and selection for specific task: 
>* number of points (1024/640)
>* memory (10/16KB)
>* programming language (ladder diagram, instruction lists, basic, hand-terminal, logic symbols)
>* programming tools (graphical on PC)
>* download (no/yes)
>* real estate per 250 I/O - how much space does it take (1000/2000 cm^2)
>* label surface per line/per point (5,3/6mm^2)/(7/6 characters)
>* Network (10/19.2 Mbits)
>* Mounting (DIN rail/cabinet)
>
>**examples:** controller in a car or machine could not have much space, some apps need faster connection, different memory for computations

Q19. **Describe the chain of signal processing from the sensor to the actors in a PLC.**

>**terms:** chain of signal processing, PLC, signals, actuators
>
>describes the flow of signal coming from a sensor going to PLC and leaving as a command for an actuator. 
>
>*analog input:* filter and scan, sample, convert to digital
>*binary input:* filtering, sample
>controller procceses, while able to use memory
>*analog output:* convert to analog, amplifying
>*binary output:* transistor relay
>
>**example:** temperature processing 



## Chapter 2.3 - PLC Programming 

### Keywords

* IEC 61131, Programming Langauges
* Graphical: FBD, SFC, Ladder Diagram
* Textual: Instruction List, Structured Text

### Exam Questions 

Q20. **Which programming languages are specified in IEC 61131 and what are they used for?**

>**terms:** IEC 61131
>
>IEC 61131 is a standard to program PLCs. It specifies data types (where operations are executed on), languages (for real time or cyclic), software structure and execution.
>*Graphical languages:*
>* Function Block Diagram: expresses programs in similar way as circuits, for continuous functions and combinatorial logic, blocks (black box behavior): Functions (no memory, library), EFB (Function blocks with memory, library), Programs (Compound blocks, defined by user)
>* Sequential Flow Chart: describes sequences of operations/interactions between parallel processes. Has states, transitons, tokens, execution period. One flow chart as whole can be seen as a discrete function.
>* Ladder Diagrams: based on relay intuition of electritians, very old and widely used, complex for large projects, has conditions (input parameters) and actions. no subprograms, no data encapsulation, no structured data types. 
> 
>*Textual Languages:* 
>* Structured Text: imperative language, complex data manipulation, writing blocks, could break real-time
>* Istruction List: machine language of PLCs (21 commands), accumulator based programming, conditionals supported, hard to write for big projects, no structure, machine dependant, weak semantics, but for specialists most efficient way, not suitable to make reusable models, used mostly in maufacturing, not process control
>
>**examples:** discrete process good to model with sequence diagram, analog maybe Function block diagram or if complex stuff structured text

Q21. **Program a simple example in FBD (e.g. a saw tooth generator, a sine wave generator)**

Q22. **Program a simple sequence in SFC (e.g. a recipe, a coffee dispenser)**

Q23. **How is a program executed on a PLC and how does it ensure its real time behavior?**

>**terms:** PLC, real time
>
>A PLC is programmed with programming languages defined in IEC 61131 
>The program is translated to machine code or some intermediate language. This is then interpreted or compiled into assembly language and can then be fed to the machine. 
>
>The languages are developed for cyclic execution and thus can ensure real time. The computer, PLC is binary sequential and discrete, thus it has non overlapping value and abrupt trasitions. Still it can model continuous plants. The time constant of the control system /PLC must at least be one magnitude smaller the set time constant that should not be exceeded.
>Whatch out: Structured Text could break real time with bad implementation or wrong loops
>
>**examples:** PLC computes every 1 ms thus making sure that after that there will always be a value
