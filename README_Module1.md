

## Overview of the Workshop

This document summarizes a **10-day hands-on workshop** titled
**“FinFET Circuit Design and Characterization using ASAP7 PDK”**, conducted by **VSDIAT** from **26th December to 4th January**.

The workshop centers on:

* Understanding **FinFET device physics**
* Exploring **technology scaling trends**
* Characterizing **NMOS transistors and inverter circuits**
* Using the **open-source ASAP7 (7nm) FinFET technology**

It also traces the **evolution of CMOS technology**, from early planar devices to emerging sub-nanometer architectures.

---

## From Early Transistors to Modern Computing

### Evolution of Transistor Technology

The development of transistors has been driven by the need for:

* Higher performance
* Lower power
* Increased integration density

<img width="1092" height="576" alt="image" src="https://github.com/user-attachments/assets/d54985be-b8a9-4378-a3a5-4604510b4a7a" />

As transistor counts increased, microprocessors followed a clear scaling trend:

<img width="1049" height="564" alt="image" src="https://github.com/user-attachments/assets/70d8f593-7171-4624-b4b2-4c18255fbabe" />

This growth trajectory ultimately points toward **Zeta-scale computing**, where energy efficiency and architecture innovation become critical:

<img width="1128" height="587" alt="image" src="https://github.com/user-attachments/assets/7ac1999a-7df4-4973-9d07-16aefe982a9a" />

---

## Limits of Planar CMOS and the Need for Change

### Why Traditional Scaling Failed

At advanced nodes, **Denard scaling** began to break down due to:

* Power density constraints
* Short-channel effects
* Increased leakage and variability

To continue scaling, the industry adopted innovations across:

* Lithography and patterning
* Channel and gate materials
* Device architectures
* 3D integration and chiplets

<img width="1632" height="764" alt="image" src="https://github.com/user-attachments/assets/8879f117-5ada-4aff-a347-239d023c586c" />

---

## FinFET Devices: A Structural Shift

### What Makes FinFETs Different?

FinFETs replace planar channels with **vertical fins**, allowing the gate to wrap around the channel on multiple sides.

Key structural advantages:

* Stronger electrostatic control
* Reduced short-channel effects
* Operation at lower supply voltages

<img width="1565" height="848" alt="image" src="https://github.com/user-attachments/assets/7e0e965a-0b33-4e39-95e4-15f71abe7d9e" />

<img width="1630" height="883" alt="image" src="https://github.com/user-attachments/assets/86b38a36-eb75-465d-a8f6-c08c1e4d3562" />

FinFETs became mainstream when planar CMOS scaling stalled below **~30 nm**.

---

## Why FinFETs Outperform Planar CMOS

### Suppression of Short-Channel Effects

* Planar devices suffer from **DIBL** due to weak gate control
* FinFETs use **double or tri-gate control**, minimizing leakage

### Switching Speed and Leakage Reduction

* Improved **subthreshold swing**
* Lower static leakage current
* Faster ON/OFF transitions

### Higher Drive Current

* Effective width increases as:

  **Wₑff = 2 × Hfin + Tfin**

* Multiple fins further boost current density

### Improved Power Efficiency

* Lower leakage at the same threshold voltage
* Enables **lower VDD**, reducing dynamic power (P ∝ CV²f)

### Reduced Device Variability

* Less channel doping
* Better electrostatic integrity

<img width="1569" height="859" alt="image" src="https://github.com/user-attachments/assets/e0c2619e-191f-43b2-9ccf-db5df652d4f1" />

<img width="1603" height="873" alt="image" src="https://github.com/user-attachments/assets/84f6b0ea-bacf-487e-9c0f-aaed5673dce6" />

---

## Technology Scaling Milestones

### Key CMOS Inflection Points

Scaling innovations over time include:

* **~1 µm – 180 nm**: Denard scaling holds
* **130 nm**: Copper replaces aluminum interconnects
* **90 nm**: Strained silicon introduced
* **65 nm**: Ultra-low-K dielectrics
* **45 nm**: High-K Metal Gate (HKMG)
* **32 nm**: Reduced random variation
* **22 nm**: FinFET introduction
* **14 nm**: SADP and diffusion breaks
* **10 nm**: LELELE patterning, gate on active
* **7 nm**: EUV lithography
* **5 nm**: SiGe PMOS channels
* **3 nm and below**: GAA / nanosheets
* **Sub-1 nm**: CFETs and 2D materials

<img width="1607" height="870" alt="image" src="https://github.com/user-attachments/assets/2bcd4fbd-16c3-4f86-bcd3-5074e8390f2f" />

<img width="1670" height="920" alt="image" src="https://github.com/user-attachments/assets/8c56b94d-12e2-4303-b68f-3f3ea959633d" />

---

## Standard Cell Design in FinFET Nodes

### Area Scaling Strategies

<img width="1595" height="826" alt="image" src="https://github.com/user-attachments/assets/25eebdf6-c3fc-4fb1-a7a7-6903b8513010" />

Key techniques:

* Cell height reduction via fin depopulation
* Cell width optimization
* Diffusion breaks to reduce coupling

<img width="1623" height="862" alt="image" src="https://github.com/user-attachments/assets/84206a82-02f2-473f-a841-e1720104b3e8" />

Types of breaks and contacts:

* Single vs double diffusion breaks
* Contact over field gate vs contact over active gate

---

## Parasitics: Resistance and Capacitance

### Resistance Challenges

<img width="1074" height="579" alt="image" src="https://github.com/user-attachments/assets/831a108d-ca38-4f70-ba1f-f0bba6a6ac9f" />

* FinFETs reduce channel width
* GAA and CFETs increase extrinsic resistance

<img width="1098" height="584" alt="image" src="https://github.com/user-attachments/assets/b01b5eea-8035-4b55-b11a-010e8cb0a815" />

### Capacitance Trends

<img width="1087" height="581" alt="image" src="https://github.com/user-attachments/assets/69eb3549-3320-4fef-a98f-c4539f53cda8" />

* Gate capacitance decreases with scaling
* Parasitic capacitance increases
* Low-K dielectrics reduce effective capacitance

---

## Beyond Silicon: New Materials and Architectures

### Layered and 2D Materials

<img width="1570" height="848" alt="image" src="https://github.com/user-attachments/assets/80ed124f-a354-4213-b3a5-d1a6ba326505" />

* Atomic-scale thickness control
* Reduced source-drain tunneling
* Improved variability control

### Sub-5 nm and 1 nm Devices

<img width="1578" height="849" alt="image" src="https://github.com/user-attachments/assets/7bb097b8-9a7b-4791-b6c0-959d58cbea40" />

<img width="1561" height="859" alt="image" src="https://github.com/user-attachments/assets/4ce56806-6b4f-49a6-bdee-77f13e79b53d" />

* MoS₂ channels
* CNT gates
* High-K oxides (ZrO₂)
* On/off ratio ≈ 10⁶

### All-2D MOSFETs

<img width="1510" height="818" alt="image" src="https://github.com/user-attachments/assets/4495790f-66d1-4f29-a16a-33663b32a79e" />

Advantages:

* High mobility
* Minimal surface scattering
* Excellent scaling potential

---

## Advanced Concepts

### Body Biasing in FinFETs

<img width="1545" height="851" alt="image" src="https://github.com/user-attachments/assets/0bdd92af-7efd-479a-9c07-6f35733dce5d" />

* Challenging compared to planar CMOS
* Achieved via oxide engineering
* Enables Vt tuning and channel control

### Monolithic 3D Integration

<img width="1549" height="865" alt="image" src="https://github.com/user-attachments/assets/e86e8eeb-250b-4516-bd24-3910ba40df6d" />

* Vertical stacking of NMOS and PMOS
* Up to **50% area reduction**

---

## Interconnect and Power Delivery Evolution

### Interconnect Scaling

<img width="1551" height="833" alt="image" src="https://github.com/user-attachments/assets/5f478fcd-462a-4c75-b533-aab85404df46" />

* Transition from dual to single damascene
* Exploration of Ru and barrier-free metals

<img width="1537" height="834" alt="image" src="https://github.com/user-attachments/assets/d722249f-3fba-45ba-ba27-492e33cb8cc6" />

### Backside Power Delivery

<img width="1637" height="853" alt="image" src="https://github.com/user-attachments/assets/05cd5f76-d175-442d-8e46-23a3fb69052f" />

Benefits:

* Reduced IR drop
* Fewer routing layers
* Smaller standard cell footprint

---
Thank you for all the efforts @VSD Team!
