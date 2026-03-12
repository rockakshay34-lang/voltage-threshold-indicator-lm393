# System Design

## Overview

The **Voltage Threshold Indicator** is designed to monitor an input voltage and indicate whether it is above or below a predefined threshold level. The system uses the **LM393 Comparator** to compare the input voltage with a reference voltage. Based on the comparison result, LEDs provide a visual indication of the voltage condition.

This design is simple, cost-effective, and suitable for applications such as battery monitoring, power supply supervision, and protection circuits.

---

## System Architecture

The system consists of the following main modules:

1. **Input Voltage Source**
2. **Voltage Divider Network**
3. **Reference Voltage Setting**
4. **Comparator Unit**
5. **Output Indicator (LEDs)**

The input voltage is compared with a preset reference voltage using the LM393 comparator. Depending on the result, the comparator output drives LEDs to indicate the voltage status.

---

## Block Diagram

```
Input Voltage
      │
      ▼
Voltage Divider Network ─────► Comparator (LM393) ◄──── Reference Voltage (Potentiometer)
                                      │
                                      ▼
                               LED Indicator
                           (Red / Green Status)
```

---

## Module Description

### 1. Input Voltage

The input voltage is the signal that needs to be monitored. This voltage is supplied to one input of the comparator. The system continuously checks whether this voltage crosses the predefined threshold.

### 2. Voltage Divider Network

A voltage divider formed by resistors is used to scale the voltage and provide appropriate levels for the comparator inputs.

Functions:

* Reduces voltage to safe levels
* Helps create reference levels for comparison
* Stabilizes the comparator input

---

### 3. Reference Voltage Setting

A **potentiometer (RV1)** is used to generate an adjustable reference voltage. This voltage acts as the threshold level.

By adjusting the potentiometer:

* The trigger voltage can be increased or decreased
* The system becomes flexible for different applications

---

### 4. Comparator Unit

The **LM393 comparator** compares two voltages:

* **Non-inverting input (+)** → Reference voltage
* **Inverting input (−)** → Input voltage

Operation:

* If `Vin > Vref` → Comparator output switches state
* If `Vin < Vref` → Comparator output remains in the opposite state

The output of the LM393 controls the LED indicators.

---

### 5. Output Indicator

Two LEDs are used to indicate the voltage condition:

* **Green LED** → Voltage within safe or below threshold level
* **Red LED** → Voltage exceeds the preset threshold

Resistors are connected in series with LEDs to limit current and protect them from damage.

---

## Design Considerations

* Proper resistor values were selected to ensure correct voltage division.
* Current limiting resistors were used for LEDs.
* The comparator output configuration ensures reliable switching.
* PCB layout was designed to minimize noise and maintain good grounding.

---

## Tools Used

* **KiCad** – Schematic design and PCB layout
* **LM393 Comparator IC** – Voltage comparison
* Standard electronic components (resistors, LEDs, potentiometer)

---

## Summary

The system design provides a simple and effective method to monitor voltage levels using a comparator-based circuit. The architecture allows easy adjustment of the voltage threshold and provides clear visual feedback through LEDs, making it suitable for practical electronic monitoring applications.

