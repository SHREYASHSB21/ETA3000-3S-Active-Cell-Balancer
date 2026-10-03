\# ETA3000 3S Active Cell Balancer



A compact 3-cell (3S) inductive active cell-balancing module designed using the ETA3000 active cell-balancing IC.



!\[3D View](Images/3d\_view.png)



\## Project Overview



This project was developed as part of an Electronics Systems task to design and develop a compact active cell-balancing module for a 3S battery system intended for drone applications.



In conventional passive cell balancing, excess energy from a higher-voltage cell is dissipated as heat through a balancing resistor. This results in energy loss and additional thermal stress.



The ETA3000-based design uses \*\*inductive active cell balancing\*\*, where energy is transferred between cells instead of simply being dissipated as heat.



The target balancing current for this design is \*\*up to 1.2 A\*\*.



\---



\## Specifications



| Parameter                | Specification              |

| ------------------------ | -------------------------- |

| Battery configuration    | 3S                         |

| Number of cells          | 3                          |

| Balancing method         | Inductive active balancing |

| Balancing IC             | ETA3000                    |

| Target balancing current | Up to 1.2 A                |

| PCB design software      | KiCad                      |

| PCB type                 | Custom 2-layer PCB         |

| Main design objective    | Compact form factor        |

| Application              | Drone battery system       |



\---



\## Design Architecture



The three battery cells are connected to the active-balancing circuit through the cell input connections.



The ETA3000 controls the inductive energy-transfer process between the cells. When a voltage imbalance exists, energy can be transferred from a higher-voltage cell toward a lower-voltage cell.



Unlike passive balancing, the energy is not intentionally converted into heat through a large balancing resistor.



\### Basic concept



```text

&#x20;Higher-voltage cell

&#x20;       │

&#x20;       ▼

&#x20;  ETA3000 Control

&#x20;       │

&#x20;       ▼

&#x20;  Inductive Energy

&#x20;     Transfer

&#x20;       │

&#x20;       ▼

&#x20;Lower-voltage cell

```



The actual switching and energy-transfer behaviour is determined by the ETA3000 architecture and its external components.



\---



\## Schematic



!\[Schematic](Images/schematic.png)



The schematic was designed according to the ETA3000 datasheet/application information and the requirements of the 3S battery configuration.



Important design considerations include:



\* Correct cell connections

\* ETA3000 power connections

\* Inductive energy-transfer components

\* Local bypass/decoupling capacitors

\* Appropriate component voltage ratings

\* High-current balancing paths

\* Correct grounding and return paths



\---



\## PCB Layout



!\[PCB Layout](Images/pcb\_layout.png)



The PCB layout was designed with compactness as one of the primary objectives.



Since the intended application is a drone battery system, reducing PCB area and unnecessary wiring is important.



The layout therefore considers:



\* Short high-current paths

\* Compact placement of the balancing components

\* Inductor placement

\* Decoupling capacitor placement

\* Practical routing

\* Copper width for balancing-current paths

\* Component accessibility

\* Clearance between different electrical nodes



\---



\## Compact Layout Considerations



A major challenge of the project was fitting the complete balancing circuit into a small PCB area.



The placement was performed with the following priorities:



1\. Keep the main energy-transfer paths short.

2\. Keep relevant passive components close to the ETA3000.

3\. Minimize unnecessary routing.

4\. Maintain suitable electrical clearances.

5\. Provide sufficiently wide copper for higher-current paths.

6\. Keep the overall board compact.



The final PCB layout was then checked using KiCad's Design Rules Checker.



\---



\## Current Handling



The target balancing current is approximately:



\*\*1.2 A\*\*



PCB trace width cannot be selected only from the nominal current. The actual design should also consider:



\* Copper thickness

\* Trace width

\* Trace length

\* Allowable temperature rise

\* PCB layer

\* Ambient temperature

\* Current duty cycle



The higher-current balancing paths were therefore given greater consideration during PCB routing than low-current signal connections.



\### Trace-width calculation



The final trace width should be justified using a PCB trace-width calculation based on the actual copper thickness and acceptable temperature rise.



> Note: The numerical trace-width value should be added here based on the actual PCB copper thickness and the calculation used for this design.



\---



\## ETA3000 Custom Footprint



The ETA3000 footprint was not available directly in the default KiCad library used during the project.



A custom KiCad footprint was therefore created/imported for the ETA3000 package.



The custom footprint is included in:



```text

ETA3000D2I.pretty/

└── ETA3000D2I.kicad\_mod

```



The footprint dimensions should be verified against the manufacturer's package drawing before fabrication.



\---



\## Component Selection



Component selection was performed with consideration for:



\* ETA3000 recommended operating conditions

\* Voltage ratings

\* Current capability

\* Package size

\* PCB availability

\* Compact placement

\* Suitable footprints



For future fabrication, components should be checked against their latest manufacturer datasheets before ordering.



\---



\## PCB Manufacturing Files



The `Gerbers/` directory contains the generated manufacturing files for the PCB.



These files can be used to inspect or manufacture the PCB using a PCB fabrication service.



Typical manufacturing outputs include:



\* Front copper

\* Back copper

\* Solder masks

\* Silkscreens

\* Board outline

\* Drill files



\---



\## Repository Structure



```text

ETA3000-3S-Active-Cell-Balancer/

│

├── ACB\_BMS.kicad\_pro

├── ACB\_BMS.kicad\_sch

├── ACB\_BMS.kicad\_pcb

│

├── ETA3000D2I.pretty/

│   └── ETA3000D2I.kicad\_mod

│

├── Images/

│   ├── schematic.png

│   ├── pcb\_layout.png

│   └── 3d\_view.png

│

├── Gerbers/

│   └── PCB manufacturing files

│

├── .gitignore

└── README.md

```



\---



\## Tools Used



\* KiCad

\* ETA3000 datasheet

\* ETA3000 application/reference information

\* PCB Design Rules Checker

\* PCB trace-width calculations



\---



\## Project Status



\*\*PCB design completed.\*\*



The current repository contains the KiCad schematic, PCB layout, custom ETA3000 footprint and manufacturing outputs.



Further validation would include:



\* PCB fabrication

\* Component assembly

\* Power-up testing

\* Cell-voltage measurement

\* Balancing-current measurement

\* Thermal testing

\* Verification of balancing behaviour under different cell-voltage conditions



\---



\## Learning Outcomes



This project involved practical work in:



\* Reading an IC datasheet

\* Understanding active cell balancing

\* Inductive energy transfer

\* Component selection

\* Custom KiCad footprint handling

\* Schematic design

\* PCB placement

\* High-current PCB routing

\* PCB trace-width considerations

\* Design Rule Checking

\* Gerber generation

\* Git/GitHub version control



\---



\## Author



\*\*Shreyash Birdawade\*\*



Electronics \& Telecommunication Engineering



GitHub: \[@SHREYASHSB21](https://github.com/SHREYASHSB21)



