# Quad-Band Anti-Jamming Communication System for NavIC

## Overview

This project focuses on the design and simulation of a **Quad-Band Anti-Jamming Communication System for NavIC (Navigation with Indian Constellation)** using a **microstrip patch antenna and antenna array architecture**.

Satellite navigation signals are received at very low power levels and are highly vulnerable to intentional jamming and unintentional radio-frequency interference. Such interference can degrade positioning accuracy, reduce signal availability, or cause complete loss of navigation services.

The objective of this project is to investigate a multi-band antenna architecture capable of supporting navigation-related frequency bands and to improve antenna gain and directivity using an antenna array. The antenna system is designed and simulated using **ANSYS HFSS**.

The current development begins with a single microstrip patch antenna operating near **2.4 GHz as an initial S-band-oriented prototype**. The design is progressively extended toward an **8-element antenna array** and a future quad-band architecture targeting the **L1, L2, L5, and S frequency bands**.

---

## Problem Statement

NavIC and other Global Navigation Satellite Systems (GNSS) depend on weak satellite signals for Positioning, Navigation, and Timing (PNT) services.

Due to the low received signal power, navigation receivers are vulnerable to:

- Narrowband interference
- Broadband interference
- Continuous-wave jamming
- Intentional RF jamming
- Multipath effects
- Signal degradation in complex environments

A strong interfering signal can increase the receiver noise floor and prevent the receiver from correctly detecting navigation signals.

Therefore, there is a need for an antenna system that provides:

- Multi-band signal reception
- Improved antenna gain
- Higher directivity
- Better interference rejection capability
- Support for future adaptive beamforming and null steering

This project investigates a **quad-band antenna array architecture for improved NavIC communication reliability and anti-jamming applications**.

---

## Project Objectives

The major objectives of this project are:

1. Design a microstrip patch antenna using ANSYS HFSS.
2. Simulate and analyze the antenna at the selected operating frequency.
3. Study antenna parameters such as return loss, gain, directivity, and radiation pattern.
4. Convert the single antenna element into a multi-element antenna array.
5. Develop an 8-element antenna array for improved gain and directivity.
6. Design an appropriate feed network for equal power distribution.
7. Extend the antenna architecture toward quad-band operation.
8. Target the L1, L2, L5, and S frequency bands.
9. Investigate antenna array techniques for interference and jamming mitigation.
10. Provide a platform for future beamforming and adaptive null-steering implementation.

---

## Target Frequency Bands

The proposed quad-band architecture considers the following navigation and satellite communication frequency bands:

| Band | Frequency | Primary Application |
|------|-----------|---------------------|
| L1 | 1575.42 MHz | Civil navigation and positioning |
| L2 | 1227.60 MHz | Precision navigation and dual-frequency correction |
| L5 | 1176.45 MHz | High-accuracy and safety-related navigation |
| S Band | 2492.028 MHz | NavIC regional navigation signal |

The use of multiple frequency bands can improve signal availability and provide frequency diversity when interference affects a particular band.

> Note: L2 is considered in this project as an additional GNSS-oriented frequency band for quad-band research. The primary NavIC-focused bands are L1, L5, and S-band.

---

## Why Microstrip Patch Antenna?

A microstrip patch antenna was selected because of its advantages in satellite and wireless communication systems.

The major advantages include:

- Compact size
- Low profile
- Lightweight structure
- Low fabrication cost
- Easy PCB fabrication
- Simple integration with RF circuits
- Suitable for microwave frequency applications
- Easy implementation of antenna arrays
- Possibility of multi-band operation using slots and geometric modifications
- Capability of circular polarization design

These characteristics make microstrip antennas suitable for navigation receiver and antenna array applications.

---

## Initial Antenna Design

The first stage of the project involves the design of a **single rectangular microstrip patch antenna operating near 2.4 GHz**.

### Initial Design Parameters

| Parameter | Value |
|-----------|-------|
| Operating Frequency | 2.4 GHz |
| Patch Width | 29.4 mm |
| Patch Length | 38 mm |
| Substrate | FR4 |
| Substrate Thickness | 1.6 mm |
| Simulation Software | ANSYS HFSS |

The 2.4 GHz antenna acts as the initial prototype for understanding antenna modeling, excitation, impedance matching, and radiation characteristics before extending the design to a multi-element and multi-band configuration.

---

## Antenna Design Procedure

The antenna development procedure is divided into multiple stages.

### Stage 1: Single Patch Antenna Design

A rectangular microstrip patch antenna is designed in ANSYS HFSS.

The main design steps are:

1. Create the dielectric substrate.
2. Assign the FR4 material.
3. Create the ground plane.
4. Design the rectangular radiating patch.
5. Create the microstrip feed line.
6. Assign the metallic conductor properties.
7. Create an air box around the antenna.
8. Assign a radiation boundary.
9. Assign the appropriate excitation port.
10. Configure the HFSS solution setup.
11. Add a frequency sweep.
12. Simulate the antenna.
13. Analyze S11, gain, directivity, and radiation pattern.

---

### Stage 2: Antenna Array Development

After validating the single antenna element, the design is extended into an antenna array.

The development sequence is:

- Single element
- 2-element array
- 4-element array
- 8-element array

The progressive design approach helps identify impedance matching, mutual coupling, and feed network problems at each stage.

For an ideal antenna array, doubling the number of equally excited elements can provide an approximate **3 dB increase in array gain**, although practical gain depends on feed loss, mutual coupling, antenna efficiency, and element radiation characteristics.

---

### Stage 3: Eight-Element Antenna Array

The proposed array consists of eight microstrip patch antenna elements.

The elements are arranged with appropriate center-to-center spacing to control mutual coupling and prevent unwanted grating lobes.

An initial spacing close to half of the free-space wavelength is considered:

\[
d \approx \frac{\lambda_0}{2}
\]

At 2.4 GHz:

\[
\lambda_0 = \frac{c}{f}
\]

\[
\lambda_0 \approx 125\ mm
\]

Therefore:

\[
d \approx 62.5\ mm
\]

The exact spacing is optimized through HFSS simulation based on S-parameters and radiation characteristics.

---

## Corporate Feed Network

A corporate feed network is considered for distributing input power to all eight antenna elements.

The power division architecture follows:

```text
                 Input
                   |
                 1-to-2
                /      \
             1-to-2    1-to-2
             /   \      /   \
           Split Split Split Split
           / \   / \   / \   / \
          P1 P2 P3 P4 P5 P6 P7 P8
