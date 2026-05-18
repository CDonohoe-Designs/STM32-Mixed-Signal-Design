# STM32 Mixed‑Signal Design

A single‑document design note covering a compact mixed‑signal board built around an STM32 microcontroller. It summarizes rationale and trade‑offs for analog front‑end (ADC/DAC paths), power (buck + LDO), PCB considerations (Altium), interfaces (SPI/I²C/UART, USB FS), and basic EMC/bring‑up practices.

- [View PDF design note](./STM32-Mixed-Signal-Design.pdf)
- [Download editable DOCX source](./STM32%20Mixed%20Signal%20Design.docx)

## What’s inside the DOCX
- Requirements and system overview (20 Hz–20 kHz analog path, ≥40 kS/s sampling; USB FS throughput).  
- AFE notes: input protection, biasing, Sallen‑Key anti‑aliasing, DAC reconstruction.  
- Power strategy: USB 5 V → buck (3V3_D) → LDO (3V3_A); noise/PSRR considerations.  
- PCB/layout pointers (Altium): return paths, test points, split rails (not grounds), bring‑up checklist.  
- Interfaces: SPI/I²C/UART patterns; USB FS with ESD/CMC.  
- Quick verification checklist and back‑of‑the‑envelope calcs.

## Keywords 
Schematic & PCB layout · I²C/SPI/UART · Prototype bring‑up/rework · Low‑power DC‑DC & battery charging · EMC/EMI · STM32 · V&V (DV/DVT)


## Contact
**Caoilte Donohoe** · Dublin, Ireland  
Email: caoiltedonohoe@gmail.com · LinkedIn: https://www.linkedin.com/in/caoilte-donohoe-69601a40a/ · GitHub: github.com/CDonohoe-Designs

---
© 2025 Caoilte Donohoe. All rights reserved.
