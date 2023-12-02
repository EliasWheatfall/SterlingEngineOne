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

![A1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/ODE.png){: .center-image :.width="250" }

{: .center-text .subtext}
Figure (1): Alpha-Type Stirling Engine

![A2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/PvA.png){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine

![A3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/TLC.png){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine

![A4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Goodman.png){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine



## Evaluation

## Finite Element Analysis

For this project, there were three main areas of concern we wanted to address with FEA. This includes the pressure in our fuel tank, clamping force on our flextures, and steady state response of our system.

### Fuel Tank Pressure

### Clamping Force
![CF1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/mesh_overall_flexure.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine

![CF2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/800N_FOS_Min.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine

![CF3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/coldclamp_mesxh.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine


![CF4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/x550N_FOS_sus_coldclamp.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine


![CF5](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_625N_FOS.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine


![CF6](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_Disp_625N.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine


### Steady State Response
![SS1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/thermal_nocut.jpg){: .center-image }
{: .center-text; .subtext}
Figure (1): Alpha-Type Stirling Engine

![SS2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/thermal_screenshot1.jpg){: .center-image }
{: .center-text; .subtext}
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
