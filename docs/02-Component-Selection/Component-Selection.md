---
title: Component Selection
---

## Component Selection

### 1. Light Sensor (Ambient Light Detection)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **TEMT6000 (already in kit)** | - Already available in kit <br> - Small and easy to interface with PIC <br> - Meets project spec | - Limited spectral sensitivity <br> - Not waterproof | $0.75 | [Vishay TEMT6000 Datasheet](https://cdn.sparkfun.com/assets/a/7/2/7/8/TEMT6000.pdf) |
| TSL2561 Digital Light Sensor | - I2C digital output <br> - High dynamic range <br> - Built-in lux calculation | - Needs I2C support on PIC <br> - Slightly larger footprint | $3.95 | [TSL2561 Datasheet](https://cdn-shop.adafruit.com/datasheets/TSL2561.pdf) |
| BH1750 Ambient Light Sensor | - Digital I2C interface <br> - High accuracy <br> - Compact | - Requires extra library for PIC <br> - Needs external pull-ups | $2.50 | [BH1750 Datasheet](https://www.mouser.com/datasheet/2/348/bh1750fvi-e-186247.pdf) |

**Choice:** TEMT6000  
**Rationale:** Already in kit, easy to integrate with PIC ADC, meets project light detection requirement without additional setup.

---

### 2. Rail-to-Rail Op-Amp (Signal Conditioning)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **MCP6004-I/P (already in kit)** | - Already available <br> - Rail-to-rail I/O <br> - Compatible with 5 V PIC supply | - Limited bandwidth <br> - Low current drive | $0.44 | [MCP6004 Datasheet](https://www.microchip.com/en-us/product/mcp6004) |
| LM358 Dual Op-Amp | - Low cost <br> - Widely available <br> - Can handle multiple signals | - Not rail-to-rail <br> - Slightly higher offset voltage | $0.25 | [LM358 Datasheet](https://www.ti.com/product/LM358) |
| TLV2372 Rail-to-Rail Op-Amp | - Rail-to-rail input/output <br> - Low noise <br> - Small footprint | - Slightly more expensive <br> - Not in kit | $0.85 | [TLV2372 Datasheet](https://www.ti.com/lit/ds/symlink/tlv2372.pdf) |

**Choice:** MCP6004-I/P  
**Rationale:** Already in kit, rail-to-rail, sufficient for amplifying sensor signals. Minimizes cost and time.

---

### 3. Push Buttons (User Input)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **Tactile Push Button (already in kit)** | - Already available <br> - Easy to wire <br> - Inexpensive | - Small size <br> - Limited lifespan | $0.10 | [Tactile Switch Datasheet](https://www.e-switch.com/catalog/tactile-switches) |
| Omron B3F-4050 | - Longer lifespan <br> - Tactile feedback <br> - Compact | - Slightly larger <br> - More expensive | $0.50 | [Omron B3F-4050 Datasheet](https://omronfs.omron.com/en_US/ecb/products/pdf/en-b3f.pdf) |
| Alps SKQGAAE010 | - Smooth tactile feel <br> - High durability | - Not in kit <br> - Requires careful PCB layout | $0.75 | [Alps SKQGAAE010 Datasheet](https://www.alps.com/prod/info/E_SKQG.pdf) |

**Choice:** Kit Push Button  
**Rationale:** Already available, meets mechanical and electrical requirements, minimal effort needed.

---

### 4. Red LED (Visual Alert)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **5 mm Red LED (already in kit)** | - Already available <br> - Easy to interface <br> - Compact | - Low brightness in sunlight <br> - Requires series resistor | $0.05 | [Vishay 5mm Red LED Datasheet](https://www.vishay.com/docs/85030/85030.pdf) |
| Kingbright WP7113ID | - High brightness <br> - Wide viewing angle | - Not in kit <br> - Slightly higher cost | $0.20 | [WP7113 Datasheet](https://www.kingbrightusa.com/images/catalog/spec/WP7113.pdf) |
| Cree CLM2F-RRD-CT | - Extremely bright <br> - Long life | - Not in kit <br> - Expensive | $1.50 | [CLM2F Datasheet](https://www.cree.com/led-components/media/documents/CLM2F.pdf) |

**Choice:** Kit LED  
**Rationale:** Already available, sufficient brightness indoors, easy to integrate.

---

### 5. Speaker (Audio Alert)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **8 Ω Mylar Mini Speaker (already in kit)** | - Already available <br> - Compact <br> - Works with small signal amplifiers | - Limited sound output <br> - Not high-fidelity | $0.85 | [CE-2808B36 Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) |
| Adafruit Mini Speaker 8 Ω 0.5 W | - Small and easy to wire <br> - Moderate volume | - Not in kit <br> - Slightly higher cost | $2.95 | [Adafruit Mini Speaker Datasheet](https://www.adafruit.com/product/1890) |
| CUI CDM-10008 | - Compact <br> - Decent volume | - Not in kit <br> - Needs amplifier | $1.25 | [CDM-10008 Datasheet](https://www.cui.com/product/resource/cdm-10008.pdf) |

**Choice:** Kit Mini Speaker  
**Rationale:** Already in kit, small size, functional, and meets project audio alert needs.

---

### 6. Voltage Regulator (5 V Supply)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **LM7805 Linear Regulator (already in kit)** | - Already available <br> - Simple to use <br> - Stable 5 V output | - Inefficient at high currents <br> - Heat dissipation for >1 A | $0.43 | [LM7805 Datasheet](https://www.st.com/resource/en/datasheet/l7805.pdf) |
| LM2940 Low Dropout 5 V Regulator | - Low dropout <br> - Better efficiency than 7805 | - Not in kit <br> - Needs input capacitor | $1.00 | [LM2940 Datasheet](https://www.ti.com/lit/ds/symlink/lm2940.pdf) |
| Switching Buck Converter 5 V Module | - High efficiency <br> - Can provide more current | - Needs careful layout <br> - EMI possible | $3.50 | [16060 Datasheet](https://cdn.sparkfun.com//assets/parts/1/1/1/2/5/16060-01.jpg) |

**Choice:** LM7805  
**Rationale:** Already in kit, provides reliable 5 V output for the system, simple implementation, and requires no additional components beyond standard input/output capacitors.

---

### 7. Potentiometer (Adjustable Threshold)

| Solution | Pros | Cons | Cost | Datasheet |
|----------|------|------|------|-----------|
| **10 kΩ Trim Pot (already in kit)** | - Already available <br> - Adjustable light threshold <br> - Easy to interface | - Small size <br> - Limited adjustment range | $0.15 | [65040 Datasheet](https://www.vishay.com/docs/65040/65040.pdf) |
| Bourns 3296W Multi-Turn Pot | - High precision <br> - Multi-turn adjustment | - Not in kit <br> - Slightly larger | $1.00 | [3296W Datasheet](https://www.bourns.com/docs/Product-Datasheets/3296W.pdf) |
| Alps RK09 Potentiometer | - Smooth adjustment <br> - Compact | - Not in kit <br> - Higher cost | $1.25 | [RK09 Datasheet](https://www.alps.com/prod/info/E_RK09.pdf) |

**Choice:** Kit 10 kΩ Trim Pot  
**Rationale:** Already available, meets project threshold adjustment needs, minimal assembly time.
