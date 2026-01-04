# Introduction
This is a 10-day workshop on "FinFET Circuit Design and Characterization using ASAP7 PDK" carried out by VSDIAT. This focuses on FinFETs, mainly the asap7nm opensource technology where we characterize a NMOS transistor, inverter circuit using the asap7nm node. The document also comprises a brief introduction to FinFETs and the journey from large gate sized, to sub 1nm nodes. The duration of this workshop is from 26th Dec to 4th Jan.

# 1. History of Transistors 
<img width="1092" height="576" alt="image" src="https://github.com/user-attachments/assets/d54985be-b8a9-4378-a3a5-4604510b4a7a" />


## 1.1 Microprocessor trend 
<img width="1049" height="564" alt="image" src="https://github.com/user-attachments/assets/70d8f593-7171-4624-b4b2-4c18255fbabe" />


## 1.2 Path to Zeta Scale Computing 
<img width="1128" height="587" alt="image" src="https://github.com/user-attachments/assets/7ac1999a-7df4-4973-9d07-16aefe982a9a" />


## 1.3 CMOS Evolution 
- Beyond a certain node size, Denard scaling was observed to be deifficult to follow, thus causing device scaling to include next geeration innvoations such as Patterning, using different Channel Material, Gate Stack, Interconnection Material, Device Architecture, Chiplet/3D integration. 

<img width="1632" height="764" alt="image" src="https://github.com/user-attachments/assets/8879f117-5ada-4aff-a347-239d023c586c" />


## 1.4 Introduction to FinFETs
FinFETs are a type of field effective transistor that has a fin like structure rather than being completely planar. The gate wraps around the fin on all three side, which connect to the source and drain terminals of the device. FinFETs came into play in the early 2010s when planar transistors could not be scaled down below 30nm due to short-channel effects. These devices proved to have enchanced `gate controll, faster switching speeds, increased drive current` all at a low supply voltage (VDD).

<img width="1565" height="848" alt="image" src="https://github.com/user-attachments/assets/7e0e965a-0b33-4e39-95e4-15f71abe7d9e" />


<img width="1630" height="883" alt="image" src="https://github.com/user-attachments/assets/86b38a36-eb75-465d-a8f6-c08c1e4d3562" />


### 1.4.1 Why FinFETs

1) Short Channel Effects
- In a planar CMOS below 30nm gate length, as Vds increases, the potential barrier around the gate starts to grow. In short channel devices, as the potential barrier of gate increases, there is a high chance for it to overlap the potential barrier of source terminal. 
- This causes charges to flow in absence of Gate control called as Drain Induced Barrier Leakage (DIBL) and increased threshold voltage (Vt).
FinFETs on the other hand are double gated or tri gated structures that supress short channel effects 

2) Reduced Leakage and Faster Switching
- Compared to planar CMOS, FinFETs have improved subthreshold swing (ability to turn on and off quicker) as the gate controlls the channel from multiple directions.
- Subthreshold swing is directrly proportional to (1+Cd/Cox)
- As a result, the static leakage current is also reduced.

3) Enhanced Drive Current 
- The introduction of fin in transistors, cause a change in the effective width of device, where Weff = 2Hfin + Tfin
Hfin is the height of fin and Tfin is the thickness of fin. 
- With increase in fin height along with multiple fins in place, the transistors drive current density increases significantly.

4) Power Efficiency
- FinFETs have observed to have lower dynamic and static leakage currents at the same threshold voltage (Vt) as that of planar transistors. This leads to improved power efficiency (P∝CV2f)
- At the same leakage current as planar devices, FinFETs observe lower Vt which translates to a lower suppy voltage Vdd. 

<img width="1569" height="859" alt="image" src="https://github.com/user-attachments/assets/e0c2619e-191f-43b2-9ccf-db5df652d4f1" />


5) Reduced Variablity
- The variability in planar transistors started to increase because doping concentration in channel increased.
- With the introduction to FinFETs, variability started to drop as they displayed better channel control as it is made of less doped channels. 

<img width="1603" height="873" alt="image" src="https://github.com/user-attachments/assets/84f6b0ea-bacf-487e-9c0f-aaed5673dce6" />


## 1.5 Front End of Line Inovations
FEOL innovations affected design rules changes that resulted in modified ways to lay down the standard cells in a chip. 

### 1.5.1 CMOS Technology Inflection Points
- Moore's law does not specify the performance of IC's as no. of transistors increase on a chip. However Bob Denard came up with a methodology to predict the performance of a transistor by figuring out the supply voltage at a given gate lenght. 

<img width="1607" height="870" alt="image" src="https://github.com/user-attachments/assets/2bcd4fbd-16c3-4f86-bcd3-5074e8390f2f" />

<img width="1670" height="920" alt="image" src="https://github.com/user-attachments/assets/8c56b94d-12e2-4303-b68f-3f3ea959633d" />


- Devices of size in range ~1 µm to 180 nm followed Denards scaling i.e. supply voltage scaling.
- 130 nm - The BEOL RC was affected and Aluminim BEOL was too resistive so Copper interconnects were introduced. 
- 90 nm - uniaxial strained Si NMOS 
- 65nm - Introduction to Ultra Low K Dielectric to minimize BEOL RC
- 45 nm - In HKMG transistors, a polysilicon doped gate is replaced by a metal gate to reduce electrical oxide thickness and gate leakage. 
- 32 nm - Observed a second generation HK MG which notriced that random variation went down substantially. 
- 22 nm - FinFETs were introduced. More powerful compared to previous generation transistors due to improved gate control and 3D nature. 
- 14 nm - Single diffusion break was introduced along with SADP that reduces pitch by 2, helping in redction of cell height. 
- 10 nm - Transistioned from gate contact being on the STI to gate contact being on the active regions. Moved onto bi-directional litho edge (LELELE) where printing was done in three different steps.
- 7 nm - introduction of EUV, which is a single patterned lithograpgy compared to multi-pattern lithograpgy cone with LELELE.
- 5 nm - Significant change in channel material. PMOS was made of SiGe fin that had higher mobility than Si channel. 
- 3/2/1.4 nm - Introduction to GAA/nanosheet. Channel thickness on vertical side can be controlled much easier that chaneel thickness done by lithography on horizontal side. 
- Sub 1 nm - Introduction to Conplementary FET architecture. Use of different 2D material to reduce source to drain tunneling such as MoS2. 

### 1.5.2 Standard Cell Area Scaling
<img width="1595" height="826" alt="image" src="https://github.com/user-attachments/assets/25eebdf6-c3fc-4fb1-a7a7-6903b8513010" />


- Standard cell area scaling in FinFET technologies refers to how the physical footprint of logic standard cells (like INV, NAND2, etc.) shrinks as the front‑end device geometries and cell architecture are scaled from node to node.
- Area can be decreased by modifying vertical (cell height) or horizaontal dimensions (cell width) 
- Fin depopulation is used to scale the cell height and also reduce capacitive load on standard cell inputs.
- Diffusion break prevents cross talk between transistors. 

<img width="1623" height="862" alt="image" src="https://github.com/user-attachments/assets/84206a82-02f2-473f-a841-e1720104b3e8" />


- Double Diffusion Break - Diffusion Break exists between two polysilicon or gate lines and cuts through active STI regions.
- Single Break - takes only one polysilicon and cuts through active region. 
- Contact Over Field Gate - Gate contact is placed directly on STI
- Contact Over Active Gate - Gate contact is either on active region or STI. This offers an inproved interconnection between cells and also reduces cell height

### 1.5.3 Parasitic Resistance
<img width="1074" height="579" alt="image" src="https://github.com/user-attachments/assets/831a108d-ca38-4f70-ba1f-f0bba6a6ac9f" />


- Parasitic resistance is important in transistors.
- In planar transistors, the width of contact Wc is similar to width of channel Wg, where as in FinFETs, width of channel becomes smaller.
- In GAA, the channel length is even smaller because of stacking nature of device.
- In CFETs, extrinsic reistance is expected to by high.

<img width="1098" height="584" alt="image" src="https://github.com/user-attachments/assets/b01b5eea-8035-4b55-b11a-010e8cb0a815" />


### 1.5.4 Parasitic Capacitance
<img width="1087" height="581" alt="image" src="https://github.com/user-attachments/assets/69eb3549-3320-4fef-a98f-c4539f53cda8" />

- The gate capacitance decreases as you scale down technology and parasitic capacitance goes up upon scaling down.
- One way to minimize parasitic capacitence is by inserting a lower K material in the gap between gate and source-drain contact.
- Upon reducing K value, we get a lower effective capacitance. 

### 1.5.5 Device Scaling Using Layered Materials
<img width="1570" height="848" alt="image" src="https://github.com/user-attachments/assets/80ed124f-a354-4213-b3a5-d1a6ba326505" />


- We can use layered materials to modify the gate lenghts to 5nm. 
- The main challenge faced in transistors is direct source to drain tunnelling, which prevents gate length scaling to short channels.
- 2D materials can be deposited with atomic scale precision. For eg. a layer of MoS2 is about 0.65nm thich and can be placed on a wafer with precision. 
- Channel thickness is a significant contributor to variability in transistors
- 2D materials have a slighlty higher effective mass compared to silicon. The source to drain tunnelling can be reduced by increasing effective mass of carriers.

### 1.5.5 Transistor Scaling to Sub 5nm Gate Lenghts
<img width="1578" height="849" alt="image" src="https://github.com/user-attachments/assets/7bb097b8-9a7b-4791-b6c0-959d58cbea40" />


- Ideally, charge leakage should be outside the channel, but it is observed both outside as well as inside the channel, which is a major problem in short channel transistors.
- Upon scaling, problems such as low inplane dielectric constant arises. In order to fix this, the drain terminal cpacitnce should be lower than oxide capacitance.

### 1.5.6 MoS Transistor with 1nm Gate Length
<img width="1561" height="859" alt="image" src="https://github.com/user-attachments/assets/4ce56806-6b4f-49a6-bdee-77f13e79b53d" />


- Transistors are made of MoS2 channel and 1nm, single walled carbon nanotube gate. 
- The gate oxide is made up of ZrO2 (Zirconium Di-Oxide).
- Such transistors have a on/off current ratio of approximately 10^6 and a near sub threshold swing of 65 mV/decade.

### 1.5.7 All 2-D MOSFET
<img width="1510" height="818" alt="image" src="https://github.com/user-attachments/assets/4495790f-66d1-4f29-a16a-33663b32a79e" />


- 2D materials are atomically thin, precise and have no dangling bonds.

- Electrical Characteristics of all 2D FET
    - Excellent on/off current ratio.
    - Good output characteristics.
    - Constant mobility with gate electric field - scattering of electrons is less due to less surface roughness. 
    - The mobility does not degrade at high electric fields, allows for high drive current adn also Vdd scaling.

### 1.5.8 Body-Bias Effect
<img width="1545" height="851" alt="image" src="https://github.com/user-attachments/assets/0bdd92af-7efd-479a-9c07-6f35733dce5d" />


- In planar transistors, the threshold voltage (Vt) can be changed due to body effect.
- However. in FinFETs applying body effect is quite challenging. But by forming a fin by placing oxide between channel material and body, Vt scaling can be performed.
- Along with that, channel potential can also be modified.
- By modifying the oxide thickness, Vt can be changed by several 100vm with about 2V change in body voltage

### 1.5.9 Transistor Level Monolithics
<img width="1549" height="865" alt="image" src="https://github.com/user-attachments/assets/e86e8eeb-250b-4516-bd24-3910ba40df6d" />


- Monolithic 3D two layer CMOS have N and P transistors placed on top of each other. thereby reducing the area upto 50%

<img width="1527" height="843" alt="image" src="https://github.com/user-attachments/assets/3b3a9488-20e9-4c2c-aed4-4b49385e898b" />

<img width="1536" height="857" alt="image" src="https://github.com/user-attachments/assets/e4da6682-077f-43af-a2af-d9e6b4385eca" />

- For an inverter, the gain has to be greater than 1 to operate. From the graph, Gain = 1 at 150mV, which shows that device operates at low supply voltage.

### 1.5.10 Interconnects 
<img width="1551" height="833" alt="image" src="https://github.com/user-attachments/assets/5f478fcd-462a-4c75-b533-aab85404df46" />

- Dual Damascene Copper interconnects are successors of Al interconnects due to their high resistance
- As technology shrinks down, the hole becomes narrower so we go to a single damascene process where via and metal are filled separatley.
- We can replace Cu with other metals that require no barrier or thinner barriers.
- Metals like Rutherium have low resistance, low feature size and do not require thick barriers.

<img width="1537" height="834" alt="image" src="https://github.com/user-attachments/assets/d722249f-3fba-45ba-ba27-492e33cb8cc6" />


- Extended Cu interconnects are used as there is high resistance in normal interconnects due to barriers
- Removing the top plate barrier, allows via resistance to reduce by 50%.

### 1.5.11 Backside Power Distribution Network
<img width="1637" height="853" alt="image" src="https://github.com/user-attachments/assets/05cd5f76-d175-442d-8e46-23a3fb69052f" />


- If we choose a front side power delivery metwork, it has to go through almost 17 interconnect layers. Also there are more routing tracks for power and ground delivery to transistors.
- A better solution is to supply power from backside, as vias have larger resistance and thus signal takes time to reach the destination. 
- Backside Power Delivery Method can also help in reducing the standard cell area without losing signal tracks. 

