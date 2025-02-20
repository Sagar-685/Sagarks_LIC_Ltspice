# **Experiment 1: Common Source (CS) Amplifier Report and Analysis**

## **1. Introduction**  

A Common Source (CS) Amplifier is a fundamental MOSFET amplifier configuration widely used in analog circuit design. It provides voltage gain by using a transistor to amplify an input signal. The amplifier’s gain is determined by the transconductance of the MOSFET and the load resistance or active load. The CS amplifier is known for its high voltage gain and moderate input impedance, making it suitable for various signal processing applications.  

 To find the drain the drain current in saturation mode following formula is used
 
 $$ I_D = \frac{1}{2} \mu_n C_{ox} \frac{W}{L} (V_{GS} - V_{TH})^2 (1 + \lambda V_{DS}) $$  

Where:  

ID = Drain Current (A) ,
Un = Electron Mobility (cm²/V·s) ,
Cox = Oxide Capacitance per Unit Area (F/m²) ,
W = Channel Width (m) , 
L = Channel Length (m) ,
VGS = Gate-to-Source Voltage (V) ,
VTH = Threshold Voltage (V) ,
λ = Channel Length Modulation Parameter ,
VDS = Drain-to-Source Voltage (V).

---

## **2. Problem Statement**  

The objective of this analysis is to determine the process technology and current Id for the given CS amplifier circuits while ensuring the design meets the following specifications:  

Supply Voltage (VDD): 1.8V,
MOSFET Channel Length (L): 180nm,
Total Power Dissipation: 50uW.

---

## **3. Circuit 1: CS Amplifier with Resistor Load**  

In the first circuit, a resistor(Rd) acts as the load for the NMOS transistor. For this the obtained values are:  

VDD: 1.8V ,
Load Resistance: 1kohm ,
NMOS Transistor:
L: 180nm 
W: 1.12um ,
Gate Voltage: 0.6V .

![exp1_circuitdiagram](https://github.com/user-attachments/assets/46fb5c13-9adc-42b4-94d5-b56f84276bb6)

![image](https://github.com/user-attachments/assets/0565a976-9763-4c96-847c-6ca044e5edd7)



### **➤ Transient Analysis**  

For the circuit transient analysis is performed by fixing some values of the gate voltage of the NMOS:

DC Offset: 0.6V ,
Amplitude: 50mV ,
Frequency: 1kHz ,
AC Amplitude: 1V ,

such that the result obtained is:
VDS: 1.7724V ,
Drain Current (Id): 27.76uA .
![exp1_transient waveform](https://github.com/user-attachments/assets/b283161c-8669-4a12-9299-e71aecb895e7)


### **➤ AC Analysis**  

In next phase ac analysis is perfomed by fixing some values which are:

Type of Sweep: Decade ,
Number of Points per Decade: 20 ,
Start Frequency: 0.1 Hz ,
End Frequency: 1 THz .

![exp1_acwaveform](https://github.com/user-attachments/assets/62b58b0b-f236-4779-b27a-20096ac2088e)

## **4. Circuit 2: CS Amplifier with PMOS as Load**  

In the second circuit, a PMOS transistor replaces the resistor as the active load. The circuit specifications are:  

In this circuit the length and width of both NMOS and PMOS has been kept same ,
L: 180nm ,
W: 0.61um.

Now before performing the analysis voltages has been set in the circuit such that:
VDD: 1.8V ,
VG (NMOS): 0.9V ,
VG (PMOS): 0.9V.
![image](https://github.com/user-attachments/assets/c7ad8f6b-a665-4723-be33-c4f2c68ab450)




### **➤ Transient Analysis**  
 Transient analysis is performed by keeping stop time value as 5m such that the results obtained are:

VDS : 1.2812V ,
Drain Current (Id): 27.75uA.

![exp1_nmos_pmos_transient](https://github.com/user-attachments/assets/686f8b8b-fc07-4f60-9079-ab72ae7b4b80)

![image](https://github.com/user-attachments/assets/f349669a-547d-4688-b52b-43d3606768b6)

### **➤ AC Analysis**  

AC analysis performed by fixing some values :

Type of Sweep: Decade
Number of Points per Decade: 20
Start Frequency: 0.1 Hz
End Frequency: 1 THz

for which following results is obtained :

![pmos_nmos_ac_analysis](https://github.com/user-attachments/assets/20dcdfd3-5d61-4561-8877-86aeb0e8d4ac)


## **5. Inference **  

This report analyzed the Common Source (CS) Amplifier using two configurations:  
1. Resistor Load 
2. PMOS Active Load

The Transient and AC Analyses provided insights into the operating point and voltage characteristics. The drain current Id was found to be approximately 27.76uA in both cases, which is almost same as the value of Id obtained by solving power and Vdd given in the problem statement.
The PMOS load configuration offers advantages such as higher gain and improved linearity compared to the resistor load setup. Future work can explore optimizing W/L ratio,biasing techniques and  to enhance performance further. Also one thing which was observed that changes in W/L ratio can lead in the entirely different behavior of the circuit.  


