---
layout: post

---

## Assumptions

To tackle designing this system we needed to reduce its complexity by providing assumptions and justifications. The main assumptions we made are below:

- Steady heat in from the flame:
- leakage from the piston is negligible
- We can apply a large enough pulling force to start the system  
- The efficiency of our system is 0.3 (A typical Stirling Engine is 0.4)

## Analysis

![PV](https://eliaswheatfall.github.io/StirlingEngineOne/assets/pv.png){: .center-image width="600" }

{: .subtext}
Figure (1): P-V Diagram

The first step for analyzing the system was to create a P-V Diagram. This diagram gives us an understanding of how much work is produced in the system over time. To produce this graph we used the variables below:


Variable       |           Value            |
--------------------- | --------------------- | 
T_Hot        | 1,700 (K)                   | 
T_Cold       | 294 (K)              | 
R            | 287 (J/kg-K)               | 
C            | 2         | 
P            | 101,325 (Pa)             |
V1, V4       | 2.8 E-5 (m^3)         |
V2, V3       | 1.4 E-5 (m^3)         |

{: .subtext}
Table (1): P-V Diagram Values

Based on this graph we found that the net-work being produced is 2.6 J/ cycle

![A1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/ODE.png){: .center-image width="600" }

{: .subtext}
Figure (2): Engine Angular Velocity Over Time

While a P-V diagram is useful for determining the work done in the system it doesn't give us an understanding of how fast the work is done, or how fast the system is oscillating. To understand this we created an ODE for the system that can be visualized in Figure (2). This figure shows that the steady-state response for the system is ~63 rad/s or 600 rpm. 

To create this table the following equations were used in ODE 45: 

![EQ](https://eliaswheatfall.github.io/StirlingEngineOne/assets/eq.png){: .center-image width="400" }




![A2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/PvA.png){: .center-image width="600" }

{: .subtext}
Figure (1): Graph of Pressure Vs Angle

Another step of our analysis was to understand the pressure our system was experiencing. The Cylinder Assembly is made from glass, so the limiting working pressure of the system is --. The graph above displays that we will experience a max pressure of 0.7 MPa, delivering a factor of safety of ---.


![A3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/TLC.png){: .center-image width="600" }

{: .subtext}
Figure (1): Alpha-Type Stirling Engine


![A4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Goodman.png){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine

## Evaluation

## Finite Element Analysis

For this project, there were three main areas of concern we wanted to address with FEA. This includes the pressure in our fuel tank, clamping force on our flextures, and steady state response of our system.

### Fuel Tank Pressure

### Clamping Force
![CF1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/mesh_overall_flexure.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine

![CF2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/800N_FOS_Min.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine

![CF3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/coldclamp_mesxh.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine


![CF4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/x550N_FOS_sus_coldclamp.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine


![CF5](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_625N_FOS.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine


![CF6](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_Disp_625N.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine


### Steady State Response
![SS1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/thermal_nocut.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine

![SS2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/thermal_screenshot1.jpg){: .center-image width="600" }

{: .center-text subtext}
Figure (1): Alpha-Type Stirling Engine

Ethanol Burner       |                       |
--------------------- | --------------------- | 
Air Fuel Ratio        | 9:1                   | 
Max Flame Temperature | 1,920 (C)              | 
Boiling Temperature   | 78.4 (C)               | 
Specific Heat         | 8.46E+05 J/kg         | 
Density               | 2460 J/kg             |
Energy Density        | 3.00E+07 J/kg         |


Burner       |                       |
--------------------- | --------------------- | 
Heat Input            | 500 (W)                   | 
Burner Efficiency      | 0.5                      |
Fuel Mass Flow Rate   | 0.0333(g/s)               | 

Regenerative Cooling      |                       |
--------------------- | --------------------- | 
Cooling Capacity            | 28.2 (W)                   | 


Title 1 | Title 2 | Title 3 | Title 4
--- | --- | --- | ---
lorem | lorem ipsum | lorem ipsum dolor | lorem ipsum dolor sit
lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur | lorem ipsum dolor sit amet | lorem ipsum dolor sit
lorem ipsum dolor | lorem ipsum | lorem | lorem ipsum
lorem ipsum dolor | lorem ipsum dolor sit | lorem ipsum dolor sit amet | lorem ipsum dolor sit amet consectetur
