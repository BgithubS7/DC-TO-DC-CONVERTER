# 12V to 24V DC-DC Converter

A high-efficiency **DC-DC boost converter** designed to step up a **12V input** to a regulated **24V output** for powering higher-voltage loads from a lower-voltage DC source. This project covers the converter design process from theory and simulation to hardware implementation and testing.

## Overview

This project focuses on the design and validation of a **boost converter** that converts **12V DC to 24V DC**. The converter can be used in applications such as:

- Battery-powered systems
- Embedded electronics
- Automotive auxiliary power
- Portable instrumentation
- Industrial control circuits

The project includes:
- Converter design calculations
- Schematic design
- Simulation results
- Component selection
- Performance testing
- Efficiency and ripple analysis

## Objectives

- Step up a 12V DC source to a stable 24V DC output
- Maintain good voltage regulation under load
- Achieve high conversion efficiency
- Minimize output voltage ripple
- Validate operation through simulation and/or hardware testing

## Converter Topology

This design uses a **boost converter topology**, which increases the input voltage by storing energy in an inductor during the switch ON time and transferring it to the load during the switch OFF time.

### Basic Principle of Operation

1. **Switch ON**  
   The inductor stores energy from the 12V source.

2. **Switch OFF**  
   The inductor releases energy through the diode to the output capacitor and load.

3. **Output Filtering**  
   The capacitor smooths the pulsating current to provide a stable 24V output.

## Design Specifications

| Parameter | Value |
|----------|-------|
| Input Voltage | 12V DC |
| Output Voltage | 24V DC |
| Converter Type | Boost Converter |
| Switching Method | PWM |
| Target Efficiency | 80–95% |
| Output Regulation | Regulated DC Output |
| Load Type | Resistive / DC Load |

## Key Components

- **PWM Controller / Gate Driver**
- **MOSFET Switch**
- **Boost Inductor**
- **Fast Recovery or Schottky Diode**
- **Output Capacitor**
- **Input Capacitor**
- **Feedback Network**
- **Load Resistor / Electronic Load**

## Design Equations

### Duty Cycle
For an ideal boost converter:

\[
V_{out} = \frac{V_{in}}{1-D}
\]

Solving for duty cycle:

\[
D = 1 - \frac{V_{in}}{V_{out}}
\]

For:

- \(V_{in} = 12V\)
- \(V_{out} = 24V\)

\[
D = 1 - \frac{12}{24} = 0.5
\]

So the ideal duty cycle is approximately **50%**.

### Inductor Selection
Inductor value can be estimated using:

\[
L = \frac{V_{in} \cdot D}{\Delta I_L \cdot f_s}
\]

Where:
- \(L\) = inductance
- \(D\) = duty cycle
- \(\Delta I_L\) = inductor ripple current
- \(f_s\) = switching frequency

### Output Capacitor Selection
The output capacitor can be estimated from:

\[
C_{out} = \frac{I_{out} \cdot D}{f_s \cdot \Delta V_{out}}
\]

Where:
- \(I_{out}\) = output current
- \(\Delta V_{out}\) = allowable output ripple voltage

## Simulation

The converter was simulated to verify:

- Output reaches 24V
- Switching waveform is correct
- Inductor current behaves as expected
- MOSFET gate drive is stable
- Output ripple is within acceptable range

### Typical Plots
- Output voltage vs. time
- Inductor current vs. time
- MOSFET gate pulse
- Switch node voltage
- Output ripple waveform

## Hardware Implementation

The hardware prototype includes:
- Breadboard or PCB implementation
- Power MOSFET switching stage
- Inductor and diode boost path
- PWM control circuitry
- Feedback for voltage regulation
- Load testing setup

## Testing and Validation

The following tests were performed or are planned:

- **No-load output voltage test**
- **Loaded output voltage test**
- **Efficiency measurement**
- **Output ripple measurement**
- **Switching waveform verification**
- **Thermal observation of switching components**

## Results

### Expected Performance
- Output voltage regulated near **24V**
- Stable switching operation
- Reduced ripple with proper capacitor sizing
- Improved efficiency with low-loss components

### Measured / Simulated Metrics
- Output Voltage: `24V`
- Input Voltage: `12V`
- Duty Cycle: `~50%`
- Efficiency: `TBD / Measured Value`
- Output Ripple: `TBD / Measured Value`

## Challenges

Some common design challenges in this project include:

- Incorrect duty cycle causing low output voltage
- High ripple due to insufficient output capacitance
- Inductor saturation
- Diode losses
- MOSFET switching losses
- Control loop instability
- Layout-related noise in hardware implementation

## Applications

This converter can be used in:

- 24V actuators powered from 12V systems
- Embedded power rails
- Automotive electronics
- Battery-powered field equipment
- Robotics and motor control support systems

## Tools Used

- **LTspice / PSpice** for simulation
- **Oscilloscope** for waveform capture
- **Digital Multimeter** for voltage/current checks
- **Power Supply** for input source
- **Electronic Load / Resistor Load** for testing

## Project Structure

```bash
12V-to-24V-DC-DC-Converter/
│── README.md
│── schematics/
│── simulations/
│── calculations/
│── pcb/
│── results/
│── images/
