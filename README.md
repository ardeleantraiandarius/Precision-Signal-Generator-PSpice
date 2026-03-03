# Precision Dual-Waveform Signal Generator (Triangle & Square Wave)

## Project Overview
This repository contains the design, mathematical calculation, and OrCAD PSpice simulation of a signal generator. The circuit is capable of generating both square and triangle waves with manually adjustable frequencies and amplitudes.

## Technical Specifications
* Power Supply: ±18V DC
* Frequency Range: 1000 Hz - 7000 Hz (adjustable)
* Square Wave Amplitude: variable between 1V and 8V
* Triangle Wave Amplitude: variable between 3.5V and 9V
* Active Components: 2 x TL082 Operational Amplifiers (chosen over the UA741 or LM324 due to a significantly higher slew rate of approximately 13 V/µs, which prevents signal distortion at high frequencies).

## Circuit Architecture
1. Comparator Stage (Square Wave): A TL082 op-amp configured without negative feedback that rapidly switches between supply levels. It uses hysteresis to avoid unwanted switching caused by noise.
2. Integrator Stage (Triangle Wave): Converts the square wave received from the comparator into a perfectly linear triangle wave using a 22nF capacitor.
3. Output Voltage Dividers: Resistive networks (using fixed resistors and potentiometers) that ensure the signals are scaled strictly within the specified limits.

## Simulation and Testing (OrCAD PSpice)
To verify and validate the circuit, the following analyses were performed:
* Transient Analysis: Verified the waveforms, frequency limits, and minimum/maximum amplitude thresholds.
* Monte Carlo Analysis: Run in 20 iterations, applying a 5% tolerance on critical components (potentiometer R8 and capacitor C1) to study performance variations.
* Worst-Case / Sensitivity Analysis: Evaluated the absolute limits of the circuit under the most unfavorable component deviation scenarios.
