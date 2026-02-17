# Discrete BJT-Based Two-Stage Audio Distortion Amplifier

## Overview
This project is a 9V single-supply discrete BJT-based audio distortion amplifier designed using Autodesk Fusion Electronics.

The circuit processes a small AC input signal (typically 100–500 mV peak-to-peak from a guitar pickup) and produces a clipped AC output waveform of approximately 100 mV to 2 V peak-to-peak. The output is intended to drive a high-impedance amplifier input.

---

## Circuit Operation

### Input Stage
The input signal first passes through a potentiometer connected as a voltage divider, which controls the signal amplitude entering the circuit.

A coupling capacitor blocks DC and allows only the AC signal to pass. Together with the input resistance, this forms a high-pass filter that removes very low-frequency components and protects the biasing of the transistor stage.

---

### First Amplifier Stage (T1 – 2N3904)
The first transistor is a 2N3904 NPN BJT configured in common-emitter mode.

- The base is DC biased to set the operating point in the active region.
- The stage provides linear voltage amplification.
- The small input signal is boosted to a higher amplitude while remaining mostly clean.

This stage prepares the signal for the distortion stage.

---

### Drive Control
A 500k potentiometer is placed between the first and second stages and acts as a variable voltage divider.

It controls how much of the amplified signal from T1 reaches the base of T2:

- Lower resistance → stronger drive into T2 → heavier clipping.
- Higher resistance → weaker drive → softer distortion.

---

### Second Amplifier Stage (T2 – 2N3904)
The second stage also uses a 2N3904 in common-emitter configuration.

Because it receives an already amplified signal, this stage operates at higher effective gain. When driven strongly, the transistor enters saturation and cutoff, resulting in non-linear waveform clipping.

This clipping produces the distortion effect.

---

### Tone Control Network
After clipping, the signal contains strong high-frequency components and can sound harsh.

A passive RC tone control network shapes the frequency response by adjusting the balance between low and high frequencies. This allows control over how bright or dark the distorted sound becomes.

---

### Output Stage
A master volume potentiometer is used as a voltage divider to control the final output amplitude.

The output is an instrument-level distorted AC signal suitable for feeding a high-impedance power amplifier input. This circuit is not designed to drive a speaker directly.

---

## Power Section
- 9V DC supply
- Reverse polarity protection diode
- Bulk supply filtering capacitor
- LED power indicator
- Two-layer PCB with ground and +9V copper pours

---

## Summary
This project demonstrates:
- DC biasing of BJTs in common-emitter configuration
- Linear vs non-linear transistor operation
- Cascaded voltage gain
- Controlled waveform clipping
- Passive frequency shaping
- Practical two-layer PCB implementation of an analog audio circuit

## Author
Girish Halavagalu
