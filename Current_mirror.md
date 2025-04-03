# Experiment 3: Current Mirror Circuit

## Part A: Design and Analysis of Current Mirror as Active Load in an Amplifier Circuit

### **Aim:**
To design and analyze a current mirror circuit functioning as an active load in an amplifier circuit.

**Given Specifications:**
- Power Supply (V<sub>DD</sub>) = 1.8V
- Power Consumption (P) ≤ 1mW
- Gain (A<sub>v</sub>) > -10V/V

### **Analysis to be Performed:**
- DC Analysis
- Transient Analysis
- AC Analysis
- Extraction of required parameters

### **Components Required:**
- NMOS and PMOS Transistors
- Resistors
- Current Source
- Voltage Supply
- Connecting Wires

## **Theory**

### **Function of a Current Mirror Circuit**
A current mirror is an essential analog circuit block primarily used for precise current replication. The circuit ensures that the output current remains proportional to a reference current despite variations in voltage conditions or load resistance. In MOSFET-based implementations, PMOS transistors form the current mirror, while an NMOS transistor typically acts as a current source or sink.

### **Working Principle**
```plaintext
- The reference current (I_ref) flows through the input PMOS transistor (M2), establishing a corresponding voltage across its drain-source terminals.
- The second PMOS transistor (M3) mirrors this current due to its identical gate-source voltage, thereby ensuring that I_out ≈ I_ref.
- The NMOS transistor (M1) serves as a current sink, providing a stable current path to maintain circuit operation.
- By adjusting the width-to-length (W/L) ratio of the transistors, the current mirror ratio can be modified to control the output current precisely.
```

### **Significance in Amplifier Circuits**
In amplifier design, current mirrors are widely employed as active loads to improve gain and stability. Unlike resistive loads, current mirrors offer higher output resistance, leading to greater voltage gain and better linearity.

## **Circuit Diagram**

![Screenshot 2025-04-03 234826](https://github.com/user-attachments/assets/e2966fac-c35a-493d-b8d1-71ef8e7d18d7)


### **Explanation of Circuit Components:**
```plaintext
- Bias Voltages (V2 and V3) = 0.95V: Establish an appropriate operating point to ensure proper transistor functionality.
- Power Supply (VDD = 1.8V): Provides necessary voltage levels for the MOSFETs.
- Output Node (Vout1): The output voltage is measured from this terminal.
- PMOS (M2, M3) and NMOS (M1): The PMOS transistors implement the current mirror, while NMOS acts as a current sink.
- Current Source (I_ref): Ensures a stable reference current for mirroring.
```

## **DC Analysis** (For Mirror Ratio 1:1)

### **Calculation of Reference Current:**
```math
I_t = \frac{P}{V_{DD}} = \frac{1mW}{1.8V} = 0.555mA
I_{ref} = \frac{I_t}{2} = 0.2778mA
```
![Screenshot 2025-04-03 234851](https://github.com/user-attachments/assets/5d70bcbc-1770-424c-8d29-4f28e9b41d31)

For W/L values:
```plaintext
M1: 3.3um / 180nm
M2: 3.3um / 180nm
M3: 3.3um / 180nm
Vin = 0.816V
```

### **Analysis by Varying L while Maintaining the Ratio**
```plaintext
| L (nm) | W (um) | Id (M1) | Id (M2) | Id (M3) |
|--------|--------|----------------|----------------|----------------|
| 180    | 3.3    | 0.0002778 A    | 0.0002773 A    | 0.0002773 A    |
| 500    | 9.165  | 0.0002778 A    | 0.0002848 A    | 0.0002848 A    |
| 1000   | 18.33  | 0.0002778 A    | 0.0002803 A    | 0.0002803 A    |
```

### **Transient Analysis**
```plaintext
Expected gain = -10V/V
Obtained gain = -10.3737V/V
```
![Screenshot 2025-04-03 235357](https://github.com/user-attachments/assets/d716d812-7bf2-42af-b76b-52fee7afd7ea)


### **AC Analysis and Frequency Response**
```plaintext
Expected gain = 20 dB
Obtained gain = 22.860 dB

```
![Screenshot 2025-04-03 235849](https://github.com/user-attachments/assets/2170bfa3-5c24-4056-ab11-14da7c45f81c)


## **DC Analysis (For Mirror Ratio 1:2)**
```math
I_{ref} = \frac{I_t}{3} = 0.185mA
```

W/L values:
```plaintext
M1: 2.9um / 180nm
M2: 5.8um / 180nm
M3: 5.8um / 180nm
```


### **Transient Analysis and AC Response**
```plaintext
Expected gain: -10V/V
Obtained gain: -12.1326V/V

Obtained gain (dB): 24.306 dB

```
![Screenshot 2025-04-04 002616](https://github.com/user-attachments/assets/f2a8ccb3-5cda-4365-8fde-702007e09fff)
![Screenshot 2025-04-04 002719](https://github.com/user-attachments/assets/556a840c-2a33-46d9-a513-962d1fe76e2c)



## **Inference:**
- The current mirror accurately reproduces the reference current with minimal deviations.
- Altering the W/L ratio proportionally maintains a nearly constant drain current, demonstrating the robustness of the mirror circuit.
- Gain measurements slightly exceed theoretical predictions, likely due to parasitic effects or transistor mismatches.
- Increasing the mirror ratio improves gain but reduces bandwidth.
- Results align well with theoretical expectations, verifying the circuit's reliability.

---

## **Part B: Differential Amplifier Design**

### **Aim:**
To design and analyze a differential amplifier using the same design specifications as in Part A.

### **DC Analysis and Biasing**
Ensuring the MOSFETs operate in the saturation region while matching expected results.
![Screenshot 2025-04-04 004350](https://github.com/user-attachments/assets/1ed4af0c-0b13-46b4-b021-4fa1058f2b1d)

![Screenshot 2025-04-04 004456](https://github.com/user-attachments/assets/47eb2c6e-a84e-451d-b549-3e80fefb33b0)


### **Transient Analysis:**

![image](https://github.com/user-attachments/assets/25958cf1-d96a-4a11-acdb-02d08db0a74c)


### **AC Analysis and Frequency Response:**

![image](https://github.com/user-attachments/assets/c0263f48-b934-4a35-b3cf-bb242005c5c8)


## **Inference:**
- The observed gain exceeds theoretical predictions due to possible parasitic capacitances or inaccuracies in device modeling.
- The amplifier demonstrates a high bandwidth, making it suitable for high-speed applications.
- The gain discrepancy may stem from underestimated drain resistance or deviations in transconductance.
- The differential configuration provides excellent common-mode rejection and improved noise immunity.
- The obtained frequency response suggests that the amplifier is effective for signal amplification in RF and high-frequency analog circuits.
