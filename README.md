Digital Clock – ASIC RTL Design

A Modular 24-Hour Digital Clock Implementation Using Verilog HDL

---

1. Project Overview

This project implements a 24-hour Digital Clock using Verilog HDL, following a modular Register Transfer Level (RTL) design approach.

The design is divided into six synthesizable RTL modules, each responsible for a specific function in the digital clock system. These modules are integrated through a top-level module to produce a complete clock with hours, minutes, and seconds in "HH:MM:SS" format.

The project covers RTL development, module-level and top-level functional verification, waveform analysis, RTL synthesis, gate-level representation, and preliminary Power, Performance, and Area (PPA) analysis.

2. Faculty Guidance

Faculty Guide: Prof. Ajaykumar Devarapalli
Institution: BMS College of Engineering, Bengaluru
HDL: Verilog HDL (IEEE 1364-2001 style)

This project was developed under the academic guidance of Prof. Ajaykumar Devarapalli. We sincerely acknowledge his technical guidance, support, and the RTL interface specifications provided for the Digital Clock ASIC design.

3. Project Contributors

3.1 Archit Jain

USN: 1BF24EC028

Contributions:

- Collaborated on the design and development of RTL Modules 1–3.
- Contributed to the implementation of the initial functional blocks.
- Assisted in assembling and organizing the initial RTL modules.
- Participated in discussions regarding modular design and signal interfacing.

3.2 Shobhan Ghadei

USN: 1BF24EC144

Contributions:

- Worked on the design and implementation of the remaining RTL modules.
- Contributed to the top-level integration of the Digital Clock.
- Worked on testbench development and functional verification.
- Contributed to simulation execution and waveform analysis.
- Worked on RTL synthesis, gate-level representation, and preliminary PPA analysis.
- Organized project documentation and ASIC flow outputs.

4. Design Specifications

Parameter| Specification
Project| 24-Hour Digital Clock
HDL| Verilog HDL
Coding Standard| IEEE 1364-2001 style
Design Approach| Modular RTL
Time Format| HH:MM:SS
Seconds Range| 00–59
Minutes Range| 00–59
Hours Range| 00–23
Reset| Active-low asynchronous reset
Clocking| Single clock domain
Output Format| Six 4-bit BCD digits

5. RTL Module Description

The Digital Clock consists of six RTL modules.

No.| Module Name| Function
1| "tick_gen"| Generates a one-second enable pulse from the input clock.
2| "seconds_counter"| Counts seconds from 00 to 59 and generates a minute enable pulse.
3| "minutes_counter"| Counts minutes from 00 to 59 and generates an hour enable pulse.
4| "hours_counter"| Counts hours from 00 to 23 and resets after 23.
5| "display_ctrl"| Converts binary counter values into individual BCD digits.
6| "digital_clock_top"| Integrates all modules into the complete Digital Clock system.

5.1 Design Operation

1. The tick generator produces a one-second enable pulse.
2. The seconds counter increments whenever the enable pulse is asserted.
3. When seconds reach 59, the counter resets to 00 and generates a minute enable pulse.
4. The minutes counter increments on the minute enable pulse.
5. When minutes reach 59, it resets to 00 and generates an hour enable pulse.
6. The hours counter increments on the hour enable pulse.
7. When hours reach 23, the next increment resets the hour count to 00.
8. The display controller converts the internal binary counts into six BCD digits.

The final output represents the time in "HH:MM:SS" format.

6. Directory Structure

The repository is organized to make the RTL design, verification files, simulation results, and ASIC implementation outputs easy to navigate.

Digital-Clock-ASIC-RTL-Design/
│
├── README.md
│
├── 01_Documentation/
│   ├── Project_Report.pdf
│   └── RTL_Interface_Agreement.pdf
│
├── 02_RTL/
│   ├── tick_gen.v
│   ├── seconds_counter.v
│   ├── minutes_counter.v
│   ├── hours_counter.v
│   ├── display_ctrl.v
│   └── digital_clock_top.v
│
├── 03_Testbenches/
│   ├── tb_tick_gen.v
│   ├── tb_seconds_counter.v
│   ├── tb_minutes_counter.v
│   ├── tb_hours_counter.v
│   ├── tb_display_ctrl.v
│   └── tb_digital_clock_top.v
│
├── 04_Simulation_Results/
│   ├── simulator_logs/
│   └── waveforms/
│
└── 05_ASIC_Flow/
    ├── README.md
    ├── 01_RTL_Synthesis/
    ├── 02_PPA_Analysis/
    ├── 03_Timing_Constraints/
    └── 04_Physical_Design/

7. Tools and Technologies Used

Tool / Technology| Purpose
Verilog HDL| RTL design and implementation
EDA Playground| Online RTL simulation environment
Icarus Verilog| Verilog compilation and simulation
EPWave| Simulation waveform visualization
ChipVerify Lab| RTL synthesis and PPA analysis
Standard Cell Library| Technology library used for synthesis

8. Functional Verification

Functional verification was performed using Icarus Verilog through EDA Playground.

The testbenches are intended to verify individual module operation and complete top-level integration.

8.1 Verification Scenarios

No.| Test Scenario| Expected Behaviour
1| Reset check| All counters reset to zero.
2| Seconds increment| Seconds increase by one.
3| Seconds rollover| 00:00:59 changes to 00:01:00.
4| Minutes rollover| 00:59:00 changes to 01:00:00.
5| Hour progression| Hours increment correctly.
6| 24-hour rollover| 23:59:59 changes to 00:00:00.
7| BCD conversion| Binary values are represented as correct BCD digits.

8.2 Waveform Analysis

Waveforms generated through EDA Playground using Icarus Verilog are maintained in the "04_Simulation_Results/" directory.

The waveform files help inspect:

- Clock and reset transitions.
- One-second enable pulse generation.
- Seconds, minutes, and hours counter progression.
- Carry/enable signal propagation.
- Final BCD output transitions.

9. ASIC Design Flow

The project follows an introductory ASIC implementation workflow.

9.1 Completed Stages

1. RTL Design

Development of six modular synthesizable Verilog RTL blocks.

2. Functional Simulation

Simulation using Icarus Verilog to verify module behaviour and top-level integration.

3. Waveform Generation

Generation and inspection of VCD waveforms to observe signal transitions.

4. RTL Synthesis

Synthesis of the Digital Clock RTL using ChipVerify Lab.

5. Gate-Level Representation

Generation of the synthesized gate-level representation of the design.

6. PPA Analysis

Preliminary Power, Performance, and Area analysis using the selected standard-cell library.

9.2 Physical Design – Planned

The following physical-design stages are planned but have not yet been completed:

- Floorplanning.
- Standard-cell placement.
- Clock Tree Synthesis (CTS).
- Routing.
- Post-route timing analysis.
- Final GDSII generation.

The "05_ASIC_Flow/04_Physical_Design/" directory is reserved for these future outputs.

10. ASIC Flow Output Organization

Directory| Contents
"01_RTL_Synthesis/"| Synthesized gate-level netlist, gate-level diagram, synthesis reports, and cell statistics.
"02_PPA_Analysis/"| Available area, timing, power, and PPA reports.
"03_Timing_Constraints/"| SDC timing constraint file and related documentation.
"04_Physical_Design/"| Reserved for future physical-design outputs.

11. Project Status

Project Stage| Status
RTL Module Development| Completed
Top-Level Integration| Completed
Module-Level Testbenches| Prepared
Top-Level Functional Simulation| Completed
Waveform Generation| Completed
RTL Synthesis| Completed
Gate-Level Diagram| Generated
PPA Analysis| Completed
Floorplanning| Pending
Placement| Pending
Clock Tree Synthesis| Pending
Routing| Pending
Final GDSII Generation| Pending

12. Acknowledgements

We express our sincere gratitude to our Faculty Guide, Prof. Ajaykumar Devarapalli, BMS College of Engineering, Bengaluru, for his guidance, technical support, and valuable direction throughout the project.

We also acknowledge the collaborative contributions of Archit Jain and Shobhan Ghadei in the design, development, assembly, integration, and verification of the Digital Clock RTL system.

This project has provided valuable practical exposure to modular digital design, Verilog RTL development, functional verification, synthesis, and preliminary ASIC implementation workflows.

---

Project Information

Project Title: Digital Clock – ASIC RTL Design
Institution: BMS College of Engineering, Bengaluru
Faculty Guide: Prof. Ajaykumar Devarapalli
Contributors:

- Archit Jain – 1BF24EC028
- Shobhan Ghadei – 1BF24EC144

Hardware Description Language: Verilog HDL
Coding Standard: IEEE 1364-2001 style
Design Category: Digital Design / ASIC RTL Implementation

---

This repository is maintained for academic learning, design documentation, and demonstration of the RTL-to-synthesis workflow. Physical design and fabrication are not claimed as completed.
