<p align="center">
  <img src="https://github.com/user-attachments/assets/412c1fa2-660c-4b2a-a2ad-588ef438be32" alt="LoRa Project Screenshot" width="600" />
</p>

# STM32F103 RFID Relay Controller
 
RFID-based access control system built around the STM32F103 (Blue Pill). Reads RFID tags via RC522 over SPI and controls a relay output through a BC547 transistor driver. Schematic designed in KiCad.
 
---
 
### Hardware
 
| Module | Component | Notes |
|---|---|---|
| MCU | STM32F103C8T6 | 2× 20-pin headers (STM1, STM2) |
| RFID | RC522 | SPI — SS, SCK, MOSI, MISO, RST, INT |
| Regulator | LM2596 | 12V → 5V buck, 3.3V tapped for RFID |
| Relay | JQC-3FF-005-1Z | Driven by BC547 NPN + flyback diode |
| Output | J2 Screw Terminal | 3-pin load connection |
 
---
 
### Schematic overview
 
- **Source:** 12V DC input
- **Regulator:** LM2596 steps down to 5V; 3.3V rail for RC522
- **MCU:** STM32F103 reads RC522 tag data over SPI
- **Relay driver:** GPIO `relayControl` → BC547 base → relay coil switches J2 output
 
---
## Schematic Diagram

![Schematic](./Images/schematic.png)

