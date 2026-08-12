# STM32 Mixed-Signal Signal Generator & Analyser

I designed this project as a mixed-signal signal generation and acquisition platform based on the **STM32F103**. The system is designed to generate and analyse analogue signals over approximately **20 Hz–20 kHz** using external ADC and DAC signal paths.

The project focuses on the complete signal chain rather than the MCU alone: analogue input protection and conditioning, anti-alias filtering, ADC acquisition, DAC reconstruction filtering, analogue output buffering, bias generation, separate analogue/digital power supplies, USB-C and EMC/ESD considerations.

A major part of the work was understanding and documenting the engineering decisions behind each stage, including sampling requirements, filter design, signal biasing, noise, impedance and mixed-signal PCB architecture.

---

## Design Documentation

**[View Complete Mixed-Signal Design Report (PDF)](STM32-Mixed-Signal-Design.pdf)**

The design report is the main engineering document for this project and covers:

- System architecture and requirements
- Sampling-rate and ADC/DAC considerations
- Analogue front-end design
- Input protection and RF filtering
- Anti-alias filtering
- DAC reconstruction filtering
- Sallen-Key filter design
- Mid-supply analogue bias generation
- Separate analogue and digital power architecture
- USB-C, ESD and EMC considerations
- STM32F103 implementation
- STM32CubeIDE configuration
- Schematic design and component selection

---

## System Architecture

The system combines signal generation and signal acquisition around the STM32F103:

**Analogue Input → Protection / Filtering → Analogue Front End → ADC → STM32F103**

**STM32F103 → DAC → Reconstruction Filter / Buffer → Analogue Output**

The power architecture uses separate supplies for the analogue and digital sections, with a switching regulator used for the digital circuitry and a low-noise LDO used for the analogue circuitry.

---

## Key Design Areas

### Analogue Front End

The input signal chain includes protection, filtering, buffering and signal conditioning before the ADC.

The analogue input is biased around a mid-supply reference to allow bipolar AC signals to be processed by the single-supply analogue circuitry.

### ADC / DAC

External ADC and DAC devices provide the analogue acquisition and signal-generation paths.

The design considers:

- ADC resolution and sampling rate
- Nyquist requirements
- Input impedance
- ADC drive requirements
- Anti-alias filtering
- DAC reconstruction filtering
- Output buffering

### Power

The power architecture separates the requirements of the digital and analogue circuitry:

- Switching regulation for the digital section
- Low-noise LDO regulation for the analogue section
- Input filtering
- Decoupling
- Mid-supply analogue bias generation

### USB-C

USB-C provides the external power/interface connection.

The design includes:

- USB-C connection
- ESD protection
- Data-line filtering
- Common-mode filtering
- Power-input filtering

---

## Development Tools

- **Altium Designer** — schematic and PCB design
- **STM32CubeIDE** — STM32 configuration and embedded development
- **LTspice** — analogue and filter analysis
- **Git / GitHub** — project documentation and version control

---

## What This Project Demonstrates

This project demonstrates my approach to **mixed-signal hardware design**, particularly the interaction between analogue signal conditioning, ADC/DAC conversion, embedded processing and power architecture.

The main engineering focus is on understanding the complete signal path:

**input protection → analogue conditioning → filtering → conversion → processing → signal generation → analogue output**

rather than treating the MCU, ADC, DAC and analogue circuitry as independent blocks.
