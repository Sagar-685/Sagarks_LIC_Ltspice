# **Differential Amplifier Report and Analysis**

## **Introduction**

A **differential amplifier** is an essential component in analog circuits that amplifies the difference between two input voltages while rejecting common-mode signals. It plays a vital role in many applications such as sensor signal conditioning, operational amplifier circuits, and analog signal processing.  

Differential amplifiers provide high common-mode rejection, making them ideal for applications where noise and interference must be minimized. These amplifiers are widely used in communication systems, medical instrumentation, and control systems.  

The working principle of a differential amplifier is based on transistor pair operation, where two identical transistors share a common bias current source. When a differential input is applied, the current is steered between the two transistors based on the voltage difference, allowing for signal amplification.  

Mathematically, the differential mode gain (Ad) and common mode gain (Ac) are given by:  
```
Ad = RD / re
Ac = (gm * RD) / (2 + gm * re)
```
where:  
- **RD** is the drain resistor  
- **re** is the small-signal emitter resistance  
- **gm** is the transconductance  

A perfect differential amplifier ideally has an infinite common-mode rejection ratio (CMRR), but practical limitations lead to finite CMRR. The **CMRR** is expressed as:  
```
CMRR = 20 * log(Ad / Ac)
```

## **Problem Statement**

To design the circuit with following soecification and also determine the process technology:
- **Vdd** = 3.3V
- **L** = 180nm
- **Power** = 3mW
- **Vicm** = 1.72V
- **Vocm** = 1.81V
- **Vp** = 0.7V

### **Circuit 1: Differential Amplifier with Resistor**

#### **Circuit Diagram**  
 ![image](https://github.com/user-attachments/assets/e6760cbf-1ddd-4988-a2d1-cd0d9dfc7568)


By designing, it is found that:
```
Rd1 = Rd2 = 3.278 kΩ
Rss = 770.077 Ω
Total current Iss = 0.909 mA
Id1 = Id2 = 0.4545 mA
Q-point for M1 and M2 (NMOS):
Vds = 1.11V, Id = 0.4545mA, Vgs = 1.02V
```

### **DC Analysis**  
 ![image](https://github.com/user-attachments/assets/8d358a19-25d5-46aa-b4ae-c3aa2f26eb75)
 ![image](https://github.com/user-attachments/assets/46adb0ef-5ed4-49fa-8813-370cb41edf64)
![image](https://github.com/user-attachments/assets/424aca1d-b8d1-4ddd-95c8-11eca5efad98)


```
W = 2.4956 um
Total current Iss = 0.909 mA
Id1 = Id2 = 0.4545 mA
Q-point for M1 and M2 (NMOS) matches theoretical values:
Vds = 1.11V, Id = 0.4545mA
```
Values obtained in dc analysis matches the values theoretical values obtained

### **Transient Analysis**  
![image](https://github.com/user-attachments/assets/a5ebc873-3598-4013-af78-e81c4ec27d03)

```
By observing the waveform, the gain is:
Gain = (Vout / Vin) = ((1.87 - 1.85) / 100m) = 1.12
```

#### **Max Input Swing**:- it is the largest possible voltage change that can be applied to an electrical circuit without causing it to become unstable .
```
Maximum input swing = 750mV
Beyond this, output peak starts clipping.

```
![image](https://github.com/user-attachments/assets/5647f7ee-6d36-4131-8d88-9ac48bf48f15)

#### **Max Output Swing** :- it the maximum voltage range that an amplifier or circuit can output without distortion.

```
Maximum output swing = 1.375V

```
![image](https://github.com/user-attachments/assets/8d53c4fa-66ff-494f-a045-5c07f4df35ac)



### **AC Analysis**  

 ![image](https://github.com/user-attachments/assets/6292e7da-32a1-4182-a7c2-562b07db3602)

```
Gain obtained from AC analysis = 2.8 dB
```


---

### **Circuit 2: Differential Amplifier with Current Source**
![image](https://github.com/user-attachments/assets/397f66e9-cf0e-4450-ad0c-0def36d92493)


#### **DC Analysis**  
 ![image](https://github.com/user-attachments/assets/39f623ae-d8fa-45d2-9523-095e048aa1df)

```
W = 2.4956 um
Total current Iss = 0.909 mA
Id1 = Id2 = 0.4545 mA
Q-point for M1 and M2 (NMOS) matches theoretical values:
Vds = 1.11V, Id = 0.4545mA
```
Values obtained in dc analysis matches the values theoretical values obtained

### **Transient Analysis**  
 ![image](https://github.com/user-attachments/assets/30b03a40-40c4-451f-8488-165fba46f6f5)

```
By observing the waveform, the gain is:
Gain = Vout / Vin = 3.2
```

#### **Max Input Swing** :- it is the largest possible voltage or current change that can be applied to an electrical circuit without causing it to become unstable .

```
Maximum input swing = 1.42V
Beyond this, output peak starts clipping.
```
![image](https://github.com/user-attachments/assets/470301e7-7739-4888-9595-dbee65355fbf)

#### **Max Output Swing** :- it the maximum voltage range that an amplifier or circuit can output without distortion.

```
Maximum output swing = 2.984V

```
![image](https://github.com/user-attachments/assets/d3e42fdd-4b27-418f-9ce0-06b1a851fc8b)


### **AC Analysis**  
![image](https://github.com/user-attachments/assets/b8f2a9ad-83aa-4ae0-87ec-5ec43386d2ac)

```
Gain value obtained from AC analysis = 9.001 dB
```
Ac analysis gain is around 9db where as if we calculate theoretical gain using 20logAv=20log(3.2)= 10.10299db

---

### **Circuit 3: Differential Amplifier with NMOS**

![image](https://github.com/user-attachments/assets/e26055a7-1a22-4661-a89b-82af2d51e471)

#### **DC Analysis**  

 ![image](https://github.com/user-attachments/assets/da6307e9-8bd6-4782-bb63-23a8da5cb0ff)

```
W = 2.4956 um
Total current Iss = 0.909 mA
Id1 = Id2 = 0.4545 mA
Q-point for M1 and M2 (NMOS) matches theoretical values:
Vds = 1.11V, Id = 0.4545mA, Vb = 1.456945V
```
Values obtained in dc analysis matches the values theoretical values obtained

### **Transient Analysis**  
![image](https://github.com/user-attachments/assets/c4caa251-afb7-4ecb-b899-9bd48795559e)

```
By observing the waveform, the gain is:
Gain = Vout / Vin = 1.8
```

#### **Max Input Swing** :- it is the largest possible voltage or current change that can be applied to an electrical circuit without causing it to become unstable .

```
Maximum input swing = 1V
Beyond this, output peak starts clipping.
```
![image](https://github.com/user-attachments/assets/25d8aac0-9057-42a8-879c-765377537be3)




#### **Max Output Swing** :- it the maximum voltage range that an amplifier or circuit can output without distortion.

```
Maximum output swing = 2.549V
```
![image](https://github.com/user-attachments/assets/b9a67552-6467-49db-b900-a6f870772040)


### **AC Analysis**  
![image](https://github.com/user-attachments/assets/b9abc833-ce85-4531-a284-72cf211975f0)

```
Gain obtained from AC analysis= 5.355 dB
```
Ac analysis gain is 5.355db where as if we calculate theoretical gain using 20logAv=20log(1.8)= 5.104db


---
## Result Comparison
| Circuit | Transient Gain | Max Input Swing | Max Output Swing |
|---------|------|----------------|------------------|
| circuit 1 with resisitor| 1.12 | 750mV | 1.375V |
| circuit 2 with current source | 3.2  | 1.42V  | 2.984V |
| circuit 3 with NMOS | 1.8  | 1V    | 2.549V |

## **Inference**

1.The differential amplifier with a current source provides the highest gain (3.2) due to improved biasing.
2.The resistor-loaded differential amplifier has the lowest gain but a stable output swing.
3. The NMOS load amplifier is a balance between both, providing moderate gain and swing.
4. The differential amplifier with a current source provides the highest gain and best performance.
5. The resistor-loaded amplifier has the lowest gain but is simplest to design.
6. The NMOS-loaded amplifier provides a balance between complexity and gain.
7. The Q-point analysis confirms that theoretical and simulated values match closely.
8. The maximum input and output swings define the operating range for each circuit.
9. Each design has trade-offs between gain, linearity, and complexity, depending on the application requirements.
10. Practical values closely match theoretical calculations.
