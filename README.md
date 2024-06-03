# Audio-Amp.-
FigTroniX - 4 Ohm - 108 Watt Audio Amp. 48 Volts DC

# FigTroniX Class AB Audio Amplifier

Welcome to the FigTroniX Class AB Audio Amplifier project! This repository contains all the information and files you need to build, test, and optimize a high-quality Class AB audio amplifier.

## Introduction

The FigTroniX Class AB Audio Amplifier is designed to provide high-quality audio amplification with a balanced frequency response and minimal distortion. This guide provides a detailed explanation of the circuit, a comprehensive parts list, and instructions for building, testing, and setting up the amplifier.

## Circuit Explanation

The amplifier circuit consists of several key sections:
- **Input Stage:** Sets input impedance and stabilizes the input signal.
- **Voltage Amplification Stage:** Amplifies the small input signal voltage.
- **Driver and Output Stage:** Provides necessary current to drive the load (speaker).
- **Power Supply Filtering:** Ensures stable DC voltage and reduces noise.
- **Feedback Network:** Ensures stability and sets the overall gain.
- **Adjustment Potentiometer:** Fine-tunes the biasing and gain.
- **Output Stabilization Networks:** Prevents oscillations and stabilizes high-frequency response.

## Parts List

### Resistors
- **R1, R17, R2, R3, R4, R6, R8, R9, R11, R12, R18:** 10kΩ, 1/4W, metal film
- **R5, R7:** 4.7Ω, 1/4W, carbon film
- **R14, R15:** 0.5Ω, 5W, wire-wound
- **R19:** 10Ω, 1/4W, metal film
- **R13:** 4Ω, 1/4W, carbon film
- **R20:** 5kΩ, 1/4W, metal film

### Capacitors
- **C1:** 15nF, film
- **C10:** 100pF, film
- **C3:** 22pF, film
- **C12:** 560pF, film
- **C13:** 100pF, film
- **C2:** 47µF, 80V, electrolytic
- **C4, C5:** 220µF, 80V, electrolytic
- **C7:** 4700µF, electrolytic
- **C8, C16, C17, C18, C19, C20, C21, C22, C23:** 0.1µF, ceramic
- **C9:** 2µF, polyester film
- **C15:** 0.1µF, ceramic

### Transistors
- **Q1, Q4:** 2N3904, NPN
- **Q2:** 2N3906, PNP
- **Q3, Q5:** 2STW100, NPN

### Diodes
- **D1, D2:** 1N4148
- **D3, D4:** 1N5408 - These diodes are used for protecting the output transistors from voltage spikes and ensuring stable operation.

### Inductor
- **L1:** 2-10µH, suitable for the output current

### Miscellaneous
- **JMP1:** Jumper wire
- **SP1:** 4-ohm speaker

## Building and Testing

### Initial Setup:
- Assemble the circuit on a breadboard or PCB, ensuring all connections are secure.
- Double-check the polarity of electrolytic capacitors (C2, C4, C5, C7).
- Ensure proper heat sinking for power transistors Q3 and Q5 to prevent overheating.

### Power Supply:
- Connect the amplifier to a stable power supply providing 48V DC.
- Verify that the power supply provides clean and stable voltage without significant ripple.

### Testing Procedure:
- **No Signal Test:** Power up the amplifier without an input signal. Measure the DC offset at the output to ensure it is close to zero.
- **Signal Test:** Apply a known audio signal (e.g., 1 kHz sine wave) to the input and measure the output using an oscilloscope. Verify that the output is a clean amplified version of the input.
- **Frequency Response Test:** Sweep the input frequency from 20 Hz to 20 kHz and observe the output. Ensure the amplitude remains consistent across the frequency range.
- **Load Test:** Connect the speaker (SP1) and test the amplifier with various audio signals, adjusting the input level to observe performance under load.

### Adjustment of Potentiometer (R16):
- **Initial Setting:** Start with R16 (10kΩ) set to its mid-point.
- **Bias Adjustment:** Monitor the quiescent current through the output transistors (Q3, Q5). Adjust R16 to achieve the desired bias current, ensuring minimal crossover distortion while avoiding excessive idle current that can lead to overheating.
- **Fine-Tuning:** Once the initial bias is set, make small adjustments to R16 while monitoring the output signal for any signs of distortion. The goal is to find the optimal balance between low distortion and thermal stability.

### Fine-Tuning Capacitors (C12 and C13):
- **Purpose of C12:** The 560pF capacitor (C12) is part of the feedback network. It helps stabilize the amplifier by reducing high-frequency gain, preventing oscillations and ensuring a smooth response across the audio spectrum.
- **Purpose of C13:** The 100pF capacitor (C13) is used to stabilize the voltage amplification stage. It acts to prevent high-frequency oscillations and ensures the amplifier operates smoothly at high frequencies.
- **Recommended Values:** C12 is typically between 470pF and 1nF, while C13 can be between 68pF and 150pF. Start with the values provided (560pF for C12 and 100pF for C13) and adjust if necessary.
- **What to Look For:** During testing, if you observe high-frequency oscillations or instability, slightly increase the value of C12 or C13. If the amplifier's high-frequency response is overly damped, consider slightly decreasing these values. Adjust in small increments and re-test the frequency response to find the optimal values.

## Maximum Output Power Calculation

### Supply Voltage (V_CC): 48V
### Load Impedance (R_L): 4Ω
### Efficiency (η) of Class AB Amplifier: Typically around 50% to 70%. For calculation purposes, we’ll use an average efficiency of 60%.

### Step-by-Step Calculation:

1. **Peak Output Voltage (V_peak):**
   - The peak output voltage is ideally the supply voltage minus some headroom for the transistors. For simplicity, let's assume a headroom of 5V on each side (for positive and negative swings).
   - \( V_{peak} = V_{CC} - 2 \times 5V = 48V - 10V = 38V \)

2. **Peak Output Current (I_peak):**
   - \( I_{peak} = \frac{V_{peak}}{R_L} = \frac{38V}{4Ω} = 9.5A \)

3. **RMS Values:**
   - The RMS value of the output voltage is \( V_{RMS} = \frac{V_{peak}}{\sqrt{2}} = \frac{38V}{\sqrt{2}} \approx 26.87V \)
   - The RMS value of the output current is \( I_{RMS} = \frac{I_{peak}}{\sqrt{2}} = \frac{9.5A}{\sqrt{2}} \approx 6.71A \)

4. **Output Power:**
   - The output power \( P_{out} \) in RMS terms is \( P_{out} = V_{RMS} \times I_{RMS} = 26.87V \times 6.71A \approx 180W \)

5. **Considering Efficiency:**
   - The actual output power considering efficiency \( P_{actual} \) is \( P_{actual} = P_{out} \times \eta \)
   - Assuming 60% efficiency: \( P_{actual} = 180W \times 0.60 \approx 108W \)

## Open Hardware License

This project is licensed under the CERN Open Hardware Licence v1.2.

You may redistribute and modify this documentation and design files under the terms of the CERN OHL v.1.2. This documentation and design files are distributed WITHOUT ANY EXPRESS OR IMPLIED WARRANTY, INCLUDING OF MERCHANTABILITY, SATISFACTORY QUALITY AND FITNESS FOR A PARTICULAR PURPOSE. Please see the CERN OHL v.1.2 for applicable conditions.

For more information about the CERN OHL, please visit: [CERN OHL](https://www.ohwr.org/documents/294)

---

Happy building! If you encounter any issues or need further assistance, feel free to reach out for support.
