# STM32 Mixed-Signal Signal Generator and Signal Analyser

This is my STM32-based mixed-signal design for a compact signal generator and signal analyser.

I designed this board to show how a small embedded system can generate analogue test signals, capture external analogue signals, and handle the practical mixed-signal design issues that come with ADCs, DACs, USB power, filtering, biasing, EMC protection and PCB layout.

My design uses an STM32 microcontroller as the main controller, with a DAC output path for signal generation and an ADC input path for signal measurement. The DAC side is used to generate low-frequency analogue waveforms, while the ADC side allows an external signal to be conditioned, filtered and sampled for analysis.

The target signal range is approximately 20 Hz to 20 kHz, so the project is aimed at low-frequency / audio-band signal work rather than high-speed RF. I included analogue front-end circuitry, anti-aliasing and reconstruction filtering, bias generation for single-supply operation, USB-C power input, ESD protection, and separate analogue/digital supply filtering.

At a high level, my design works as:

- **Signal generator:** the STM32 controls the DAC, creating an analogue output signal through a filtered output stage.
- **Signal analyser:** an external analogue signal enters through the input connector, passes through protection and analogue conditioning, and is then sampled by the ADC.
- **Mixed-signal PCB example:** the board brings together digital control, analogue signal paths, power regulation, USB, filtering, grounding and EMC considerations in one small design.

I created this project as a portfolio piece to demonstrate practical mixed-signal hardware design, from system requirements and schematic capture through to converter selection, analogue filtering, power-supply design and PCB implementation.

## Contents

- [View the full design note PDF](./STM32-Mixed-Signal-Design.pdf)
- [Download editable DOCX source](./Source/STM32-Mixed-Signal-Design.docx)

## What’s inside the DOCX
- Requirements and system overview (20 Hz–20 kHz analog path, ≥40 kS/s sampling; USB FS throughput).  
- AFE notes: input protection, biasing, Sallen‑Key anti‑aliasing, DAC reconstruction.  
- Power strategy: USB 5 V → buck (3V3_D) → LDO (3V3_A); noise/PSRR considerations.  
- PCB/layout pointers : return paths, test points, split rails (not grounds), bring‑up checklist.  
- Interfaces: SPI/I²C/UART patterns; USB FS with ESD/CMC.  
- Quick verification checklist and back‑of‑the‑envelope calcs.


## Contact
**Caoilte Donohoe** · Dublin, Ireland  
Email: caoiltedonohoe@gmail.com · LinkedIn: https://www.linkedin.com/in/caoilte-donohoe-69601a40a/ · GitHub: github.com/CDonohoe-Designs

---
© 2025 Caoilte Donohoe. All rights reserved.
