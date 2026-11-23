Digital Clock – ASIC RTL Design

24-Hour Digital Clock Implementation Using Verilog HDL

1. Project Overview

A modular 24-hour Digital Clock designed using Verilog HDL. The project includes six synthesizable RTL modules, individual testbenches, top-level integration, functional simulation, waveform verification, RTL synthesis, and preliminary PPA analysis.

2. Faculty Guide

- Name: Prof. Ajaykumar Devarapalli
- Institution: BMS College of Engineering, Bengaluru
- HDL: Verilog HDL (IEEE 1364-2001 style)

We sincerely acknowledge our faculty guide for his technical guidance, support, and RTL interface specifications.

3. Project Contributors

Archit Jain — 1BF24EC028

- Collaborated on the design, development, and assembly of RTL Modules 1–3.

Shobhan Ghadei — 1BF24EC144

- Contributed to the remaining RTL modules, top-level integration, verification, simulation, synthesis, PPA analysis, and project documentation.

4. Design Specifications

Parameter| Specification
Design| 24-Hour Digital Clock
HDL| Verilog
Coding Standard| IEEE 1364-2001
Time Format| HH:MM:SS
Hours| 00–23
Minutes| 00–59
Seconds| 00–59
Reset| Active-low asynchronous
Outputs| Six 4-bit BCD digits

5. RTL Modules

No.| Module| Function
1| "tick_gen"| One-second pulse generation
2| "seconds_counter"| Seconds counting
3| "minutes_counter"| Minutes counting
4| "hours_counter"| 24-hour counting
5| "display_ctrl"| Binary-to-BCD conversion
6| "digital_clock_top"| Top-level integration

6. Repository Structure

Root Directory: "Digital-Clock-ASIC-RTL-Design/"

README.md

- Main project overview and documentation.

01_Documentation/

- Project_Report.pdf
- RTL_Interface_Agreement.pdf

02_RTL/

- tick_gen.v
- seconds_counter.v
- minutes_counter.v
- hours_counter.v
- display_ctrl.v
- digital_clock_top.v

03_Testbenches/

- tb_tick_gen.v
- tb_seconds_counter.v
- tb_minutes_counter.v
- tb_hours_counter.v
- tb_display_ctrl.v
- tb_digital_clock_top.v

04_Simulation_Results/

- simulator_logs/
- waveforms/

05_ASIC_Flow/

- README.md
- 01_RTL_Synthesis/
- 02_PPA_Analysis/
- 03_Timing_Constraints/
- 04_Physical_Design/

7. Tools and Software

Tool| Purpose
EDA Playground| RTL simulation environment
Icarus Verilog| Verilog compilation and simulation
EPWave| Waveform visualization
ChipVerify Lab| ASIC synthesis and PPA analysis
Standard Cell Library| Technology library for synthesis

Software Acknowledgements: We acknowledge EDA Playground for providing the online RTL simulation environment and ChipVerify Lab for supporting the synthesis and preliminary ASIC analysis workflow.

8. Verification

Functional verification covers:

- Reset operation.
- Seconds and minutes incrementing.
- Minute and hour rollover.
- 24-hour rollover from "23:59:59" to "00:00:00".
- Correct BCD output generation.

Simulation waveforms and logs are maintained in "04_Simulation_Results/".

9. ASIC Flow Status

Stage| Status
RTL Design| Completed
Functional Simulation| Completed
Waveform Generation| Completed
RTL Synthesis| Completed
Gate-Level Diagram| Generated
PPA Analysis| Completed

10. Acknowledgements

We thank Prof. Ajaykumar Devarapalli for his academic guidance and technical support.

We acknowledge Archit Jain for his collaborative contributions to the initial RTL modules and Shobhan Ghadei for the remaining RTL development, integration, and implementation activities.

We also acknowledge EDA Playground and ChipVerify Lab for providing the tools used during simulation, synthesis, and preliminary ASIC analysis.

---

Institution: BMS College of Engineering, Bengaluru
Project: Digital Clock – ASIC RTL Design
HDL: Verilog (IEEE 1364-2001 style)
