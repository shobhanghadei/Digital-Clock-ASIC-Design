# 24-Hour Digital Clock ASIC RTL Project

**Faculty Guide:** Prof. Ajaykumar Devarapalli  
**Institution:** BMS College of Engineering, Bengaluru  
**HDL:** Verilog HDL (IEEE 1364-2001 style)

## Directory structure
- `01_Documentation/` — project report and professor-provided reference PDF
- `02_RTL/` — six synthesizable RTL modules
- `03_Testbenches/` — six matching simulation testbenches
- `04_Simulation_Results/` — place simulator logs and VCD files here
- `05_ASIC_Flow/` — place synthesis, timing and physical-design outputs here

## RTL module order
1. `tick_gen.v` — creates a one-clock-cycle one-second enable pulse.
2. `seconds_counter.v` — counts 0–59 and generates `min_tick`.
3. `minutes_counter.v` — counts 0–59 and generates `hour_tick`.
4. `hours_counter.v` — counts 0–23 and wraps to zero.
5. `display_ctrl.v` — converts binary counters into six decimal digit outputs.
6. `digital_clock_top.v` — connects all modules into the complete clock.

## Testbench pairing
Each testbench in `03_Testbenches/` corresponds to the RTL module with the same function. For the integrated test, compile all six RTL files with `tb_digital_clock_top.v`.

## Run using Icarus Verilog
Example for the seconds counter:
```bash
iverilog -g2005 -s tb_seconds_counter -o simv 02_RTL/seconds_counter.v 03_Testbenches/tb_seconds_counter.v
vvp simv
```
Integrated design:
```bash
iverilog -g2005 -s tb_digital_clock_top -o simv 02_RTL/*.v 03_Testbenches/tb_digital_clock_top.v
vvp simv
```
Do not include testbench files in synthesis.

## Important implementation note
The design uses a common clock and active-low asynchronous reset. `tick_1s`, `min_tick`, and `hour_tick` are clock-enable pulses, not separate clocks. The testbenches use reduced divider parameters to make simulation practical.

## ASIC-flow status
RTL and testbench files alone do not establish completed ASIC implementation. Synthesis, static timing analysis, and physical design require a target PDK, standard-cell libraries, timing constraints (SDC), and platform configuration. Add actual tool reports before claiming those stages are complete.

## Reference
`Digital_Clock_ASIC_RTL_Verification_Package.pdf`, supplied as the professor's reference document.
