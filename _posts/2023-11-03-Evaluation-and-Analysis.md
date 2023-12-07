---
layout: post

---

## Assumptions

To tackle designing this system we needed to reduce its complexity by providing assumptions and justifications. The main assumptions we made are below:

- Steady heat in from the flame:
- Leakage from the piston is negligible
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

{: .subtext}
Figure (3): Equations for ODE45




![A2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/PvA.png){: .center-image width="600" }

{: .subtext}
Figure (4): Graph of Pressure Vs Angle

Another step of our analysis was to understand the pressure our system was experiencing. The Cylinder Assembly is made from glass, so the limiting working pressure of the system is --. The graph above displays that we will experience a max pressure of 0.7 MPa, delivering a factor of safety of ---.


![A3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/TLC.png){: .center-image width="600" }

{: .subtext}
Figure (5): Load over Time

The pressure in the system can then be translated to a force on the piston. Since Pressure = Force/Area, we can take the pressure in the system x the surface area of our Piston to extract a force shown in Figure (5).


![A4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Goodman.png){: .center-image width="600" }

{: .subtext}
Figure (1): Time-Varying load Curve

After finding the force that created the pressure in our system we need to analyze if our shaft will yield due to fatigue. For this, we use a Goodman Diagram that displays our mean stress against amplitude stress. Since we are well beneath the Goodman line we expect this loading condition to be good.

## Evaluation

## Finite Element Analysis

For this project, there were three main areas of concern we wanted to address with FEA. This includes the pressure in our fuel tank, clamping force on our flextures, and steady state response of our system.

### Clamping Force

#### Shaft Clamp Flexure

![CF1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/mesh_overall_flexure.jpg){: .center-image width="400" }

{: .subtext}
Figure (7): Shaft Clamp Flexure Mesh

To analyze the flexure shaft clamp, we did a static FEA study to find the clamping force for which the shaft cannot slip and the clamp does not break. To do this, a contact interaction with friction (coefficient of friction = 0.6 for steel on aluminum from https://www.engineeringtoolbox.com/friction-coefficients-d_778.html) was specified between the clamp and the shaft, one end of the flexure was fixed, and the bolt clamping force was applied to a split-surface on the flexure (corresponding to the area where the head of the bolt makes contact). A torque of 0.478 Nm was also applied to the shaft, as this is an upper bound estimate for the torque applied to the shaft in a worst-case scenario. If the shaft does not slip, its displacement is the same as the displacement of the clamp holding it. If the shaft slips, it will have a non-zero displacement relative to the surrounding clamp.

To get sufficiently accurate results without a prohibitive run time, the mesh used was coarse overall with refinement regions in areas of high stress. The mesh included several refinement zones utilizing increasingly smaller minimum mesh size. The filet near the bolt head mount was of particular concern, so was refined to a very fine mesh.


![CF2](https://eliaswheatfall.github.io/StirlingEngineOne/assets/800N_FOS_Min.jpg){: .center-image width="400" }

{: .subtext}
Figure (8): Shaft Clamp Flexure Analysis

Under 625N of clamping force, the displacement of the shaft is non-zero relative to the rest of the flexure, meaning that the rod slipped and 625N is insufficient clamping force. Under 800N of clamping force, the rod had the same displacement as the surrounding flexure, meaning that it did not slip, and 800N is sufficient force. 800N is less than the 6-32 bolt’s proof strength. Using the equation for bolt clamping force to torque, 
T=F*D*K
with K = 0.2, and diameter corresponding to a 6-32 machine screw, we calculate a torque on the bolt of 0.478 N*m is required to get 800N of clamping force.

The FOS for yielding is above 1.0 throughout the flexure for an 800N clamping force, so the flexure will not fail due to excessive clamping force.

#### Cylinder Clamp Flexure
![CF3](https://eliaswheatfall.github.io/StirlingEngineOne/assets/coldclamp_mesxh.jpg){: .center-image width="400" }

{: .subtext}
Figure (9): Cylinder Clamp Flexure Mesh
![CF4](https://eliaswheatfall.github.io/StirlingEngineOne/assets/x550N_FOS_sus_coldclamp.jpg){: .center-image width="400" }

{: .subtext}
Figure (10): Cylinder Clamp Flexure Analysis

The flexure clamp used to mount the cylinders was analyzed with a similar FEA study. Like the other flexure FEA, the mesh was refined in areas of high stress, particularly the filet near the bolt head. With 550N of clamping force, the FOS for yielding is above 1.0 throughout the flexure for an 800N clamping force, so the flexure will not fail due to excessive clamping force.


#### Pillow Block Flexure

![CF5](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_625N_FOS.jpg){: .center-image width="400" }

{: .subtext}
Figure (11): Pillow Block Flexure FOS

![CF6](https://eliaswheatfall.github.io/StirlingEngineOne/assets/Pillow_Disp_625N.jpg){: .center-image width="400" }

{: .subtext}
Figure (12): Cylinder Clamp Flexure Deformation

The flexure for the pillow block was similarly analyzed. With the 625N bolt force, the FOS is above 3.0 throughout most of the part. There are some stress concentrations in the bolt hole itself that are primarily due to the coarseness of the mesh and the boundary conditions, but even in these concentrations the FOS is always above 1.0

### Steady State Response
![SS1](https://eliaswheatfall.github.io/StirlingEngineOne/assets/thermal_nocut.jpg){: .center-image width="600" }

{: .subtext}
Figure (13): Cylinder Steady State Temperature

To ensure that no part of the heated cylinder exceeds its melting temperature, a thermal FEA study was conducted. The hot end had a convection boundary condition with h=25 for forced convection and ambient temperature = 1647 Kelvin (temperature of denatured alcohol flame), the rest of the assembly has a surface convection boundary condition with ambient temperature of 293.15 Kelvin (room temperature). All bonded components have a thermal resistance of 0 to represent good thermal contact.


Ethanol Burner       |                       |
--------------------- | --------------------- | 
Air Fuel Ratio        | 9:1                   | 
Max Flame Temperature | 1,920 (C)              | 
Boiling Temperature   | 78.4 (C)               | 
Specific Heat         | 8.46E+05 J/kg         | 
Density               | 2460 J/kg             |
Energy Density        | 3.00E+07 J/kg         |

{: .subtext}
Table (2): Burner Variables

Burner       |                       |
--------------------- | --------------------- | 
Heat Input            | 500 (W)                   | 
Burner Efficiency      | 0.5                      |
Fuel Mass Flow Rate   | 0.0333(g/s)               | 

{: .subtext}
Table (3): Burner Charachteristics

Regenerative Cooling      |                       |
--------------------- | --------------------- | 
Cooling Capacity            | 28.2 (W)                   | 

{: .subtext}
Table (4): Cooling Capacity


