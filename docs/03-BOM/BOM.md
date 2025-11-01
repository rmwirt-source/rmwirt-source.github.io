---
title: Bill of Materials
tags:
- electronics
- irriga-tors
---

## Overview
A table showing all of the products for my specific part of the Irri-Gators project. This subsystem provides visual, audio, and input feedback to alert the user to errors and assist with system interaction.

## Bill of Materials

| **Part Name / Description** | **Qty** | **Unit Cost** | **Total Cost** | **Manufacturer** | **Manufacturer Part #** | **Vendor** | **Vendor Part #** | **Vendor Link** | **Datasheet Link** | **# Ordered** | **Date Ordered** | **# Received** | **Schematic Reference Designators** |
|-----------------------------|---------|---------------|----------------|-----------------|-----------------------|------------|-----------------|----------------|-----------------|-------------|----------------|----------------|-----------------------------------|
| Microchip PIC18F57Q43 Curiosity Nano Dev Kit | 1 | $9.99 | $9.99 | Microchip | DM164150 | Microchip Direct | DM164150 | [Link](https://www.microchipdirect.com/dev-tools/DM164150?productLoaded=true&allDevTools=true) | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/40001742F.pdf) | 1 | 2025-08-25 | 1 | U1 |
| MCP6004-I/P Rail-to-Rail Op-Amp | 1 | $0.44 | $0.44 | Microchip | MCP6004-I/P | DigiKey | 523060 | [Link](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | [Datasheet](https://ww1.microchip.com/downloads/en/DeviceDoc/22090e.pdf) | 1 | 2025-08-25 | 1 | U2 |
| LM7805 Voltage Regulator | 1 | $0.43 | $0.43 | Texas Instruments | LM7805CT-NOPB | DigiKey | 3901929 | [Link](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) | [Datasheet](https://www.ti.com/lit/ds/symlink/lm7805.pdf) | 1 | 2025-08-25 | 1 | U3 |
| Red LED | 2 | $0.05 | $0.10 | Kingbright | WP710A10SRD14V | DigiKey | 25610483 | [Link](https://www.digikey.com/en/products/detail/kingbright/WP710A10SRD14V/25610483) | [Datasheet](https://www.kingbrightusa.com/images/catalog/spec/WP710A10SRD14V.pdf) | 2 | 2025-08-25 | 2 | D1, D2 |
| Tactile Push Button (kit) | 2 | $0.10 | $0.20 | CUI Devices | TS02-66-60-BK-160-LCR-D | DigiKey | 15634268 | [Link](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/TS02-66-60-BK-160-LCR-D/15634268) | [Datasheet](https://www.cuidevices.com/product/resource/ts02-series.pdf) | 2 | 2025-08-25 | 2 | SW1, SW2 |
| WT-1205 Buzzer | 1 | $0.59 | $0.59 | Soberton | WT-1205 | DigiKey | 479674 | [Link](https://www.digikey.com/en/products/detail/soberton-inc/WT-1205/479674) | [Datasheet](https://www.soberton.com/datasheets/WT-1205.pdf) | 1 | 2025-08-25 | 1 | BZ1 |
| Resistors (various for pull-ups / current limiting) | 5 | $0.01 | $0.05 | Yageo | RC0603FR-0710KL | DigiKey | 732301 | [Link](https://www.digikey.com/en/products/detail/yageo/RC0603FR-0710KL/732301) | [Datasheet](https://www.yageo.com/upload/media/product/product_2042.pdf) | 5 | 2025-08-25 | 5 | R1-R5 |
| Capacitors (10µF, 1µF, 0.1µF) | 3 | $0.10 | $0.30 | KEMET | C0805C106K5RACTU | DigiKey | 386308 | [Link](https://www.digikey.com/en/products/detail/kemet/C0805C106K5RACTU/386308) | [Datasheet](https://content.kemet.com/datasheets/KEM_C0805C106K5RACTU.pdf) | 3 | 2025-08-25 | 3 | C1-C3 |

---

### ✅ Summary
This finalized BOM includes all components used in the alert and input subsystem:
- Power regulation (LM7805)
- Signal conditioning (MCP6004)
- User inputs (Tactile Push Buttons)
- Indicators (Red LEDs)
- Audio alert (WT-1205 Buzzer)
- Passive support components (Resistors and Capacitors)
- PIC18F57Q43 microcontroller board

Total estimated subsystem cost: **≈ $12.10**
