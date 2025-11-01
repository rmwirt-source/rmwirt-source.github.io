---
title: Component Selection
---

## Component Selection

---

### 1. Rail-to-Rail Op-Amp (Signal Conditioning)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|---------|--------|
| **MCP6004-I/P (already in kit)** | - Already available<br>- Rail-to-rail I/O<br>- Compatible with 5 V PIC supply | - Limited bandwidth (1 MHz)<br>- Low output current drive (~0.6 mA typical) | $0.44 | [MCP6004 DigiKey](https://www.digikey.com/en/products/detail/microchip-technology/MCP6004-I-P/523060) | <img src="https://github.com/user-attachments/assets/f6fecd63-522c-47dc-affc-7346e519ad36" alt="MCP6004" width="120" /> |
| LM358 Dual Op-Amp | - Low cost<br>- Widely available<br>- Can handle dual-signal inputs | - Not rail-to-rail<br>- Slightly higher offset voltage (~2 mV)<br>- Lower output swing near ground | $0.25 | [LM358 DigiKey](https://www.digikey.com/en/products/detail/stmicroelectronics/LM358DT/591693) | <img src="https://github.com/user-attachments/assets/8139f031-292d-494d-ae0a-b5134d419061" alt="LM358" width="120" /> |
| TLV2372 Rail-to-Rail Op-Amp | - Rail-to-rail input/output<br>- Low noise (8 nV/√Hz)<br>- Higher bandwidth (3 MHz)<br>- Small footprint | - Slightly more expensive | $0.85 | [TLV2372 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/TLV2372IDR/381216) | <img src="https://github.com/user-attachments/assets/d1e9d01a-b685-4323-860b-a36365ad96ae" alt="TLV2372" width="120" /> |

**Choice:** MCP6004-I/P  
**Rationale:**  
Selected for its rail-to-rail operation and 5 V compatibility, enabling accurate low-level signal amplification without output clipping. It provides sufficient bandwidth for sensor signals while maintaining simplicity and low cost compared to higher-performance options.

---

### 2. Push Buttons (User Input)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|-----------|-----------|
| **Tactile Push Button (already in kit)** | - Already available<br>- Easy to wire<br>- Very inexpensive | - Small actuation area<br>- Limited mechanical lifespan (~100k cycles) | $0.10 | [Tactile Switch DigiKey](https://www.digikey.com/en/products/detail/same-sky-formerly-cui-devices/TS02-66-60-BK-160-LCR-D/15634268?s=N4IgTCBcDaICoGUAMYC0A2dGmoEIGlUBGdHAGQGEAlVAERAF0BfIA) | <img src="https://github.com/user-attachments/assets/2508181f-b9f1-4dc4-8268-5cfe5b284e4c" alt="Tactile Switch" width="120" /> |
| Omron B3F-4050 | - Long lifespan (~1 M cycles)<br>- Good tactile feedback<br>- Compact | - Slightly more expensive<br>- Requires more precise mounting | $0.50 | [Omron B3F-4050 DigiKey](https://www.digikey.com/en/products/detail/omron-electronics-inc-emc-div/B3F-4050/95200?s=N4IgTCBcDaIPIFsBOB7AdgAgEIGYBiAtACwAMArCSALoC%2BQA) | <img src="https://github.com/user-attachments/assets/748d65d9-3ac8-4643-ad7d-6be7b74a3403" alt="Omron B3F-4050" width="120" /> |
| C&K PTS645SM43SMTR92LFS | - Long lifespan<br>- Crisp tactile response<br>- Compact SMD package | - Not in kit<br>- SMD form factor makes soldering harder | $0.28 | [C&K PTS645SM43SMTR92LFS DigiKey](https://www.digikey.com/en/products/detail/c-k/PTS645SM43SMTR92-LFS/10071777) | <img src="https://github.com/user-attachments/assets/dd81ab68-0fbb-4b96-a69a-aaa120e653d3" alt="C&K PTS645" width="120" /> |

**Choice:** Kit Push Button  
**Rationale:**  
Provides the necessary tactile input with minimal integration effort. Other options offered higher durability but unnecessary complexity for the project’s limited mechanical usage.

---

### 3. Red LED (Visual Alert)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|-----------|-----------|
| **Red LED (already in kit)** | - Already available<br>- Easy to interface<br>- Compact | - Low brightness in direct sunlight<br>- Requires series resistor | $0.05 | [Red LED DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP710A10SRD14V/25610483) | <img src="https://github.com/user-attachments/assets/4712c179-c5b8-49c6-8c86-a8148871bd27" alt="Red LED" width="120" /> |
| Kingbright WP7113ID | - High brightness (8000 mcd)<br>- Wide viewing angle (40°) | - Not in kit<br>- Slightly higher cost | $0.20 | [WP7113 DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP7113ID/1747663) | <img src="https://github.com/user-attachments/assets/182ed7ff-567b-4f90-b8ff-128127207bb3" alt="Kingbright WP7113ID" width="120" /> |
| Kingbright WP710A10SRD/J4 | - Extremely bright (10 000 mcd)<br>- Wide angle<br>- Low cost | - Not in kit<br>- Slightly higher forward voltage (2.1 V) | $0.12 | [Kingbright WP710A10SRD/J4 DigiKey](https://www.digikey.com/en/products/detail/kingbright/WP710A10SRD-J4/4098608?s=N4IgTCBcDaIOoAUDsBGADAQXQZQEoBEB6AKQBYQBdAXyA) | <img src="https://github.com/user-attachments/assets/1fd41189-617d-4d37-8f09-3cfeee184a2c" alt="Kingbright WP710A10SRD/J4" width="120" /> |

**Choice:** Kit LED  
**Rationale:**  
Provides reliable visibility in indoor environments at minimal cost. Higher-intensity options were unnecessary for the application’s lighting conditions.

---

### 4. Speaker/Buzzer (Audio Alert)

| Solution | Pros | Cons | Cost | Datasheet/DigiKey | Picture |
|----------|------|------|------:|--------------------|-----------|
| 8 Ω Mylar Mini Speaker (already in kit) | - Already available<br>- Compact<br>- Works with small-signal amplifiers | - Limited sound pressure level (≈ 85 dB)<br>- Not high-fidelity | $0.85 | [CE-2808B36 Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) | <img src="https://github.com/user-attachments/assets/24a6eb60-09d2-4d6f-b6c7-82f5fd910cd7" alt="8Ω Mylar Mini Speaker" width="120" /> |
| **WT-1205 Buzzer** | - Small and easy to wire<br>- Louder than basic speakers (~90 dB)<br>- Reliable brand<br>- Simple two-pin connection | - Not in kit<br>- Slightly higher cost | $0.59 | [WT-1205 DigiKey](https://www.digikey.com/en/products/detail/soberton-inc/WT-1205/479674) | <img src="https://github.com/user-attachments/assets/ca3dbe7e-1671-4284-ba8d-99634466c295" alt="WT-1205 Buzzer" width="120" /> |
| CUI Devices CDS-25148-L100 | - Robust design<br>- High sound output (≈ 95 dB)<br>- Durable housing | - Not in kit<br>- Larger footprint | $2.46 | [CUI Devices CDS-25148-L100 DigiKey](https://www.digikey.ca/en/products/detail/same-sky-formerly-cui-devices/CDS-25148-L100/5355540) | <img src="https://github.com/user-attachments/assets/5f8edc63-4071-42bb-97db-7a784e2491be" alt="CUI Devices CDS-25148-L100" width="120" /> |

**Choice:** WT-1205 Buzzer  
**Rationale:**  
Offers a stronger and clearer tone than the kit speaker while requiring simpler drive circuitry. Balances loudness, reliability, and ease of integration for short alert signals.

---

### 5. Voltage Regulator (5 V Supply)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|-----------|-----------|
| **LM7805 Linear Regulator (already in kit)** | - Already available<br>- Simple to use<br>- Stable 5 V output<br>- Low noise | - Inefficient for large voltage drops<br>- Heat generation above 1 A load | $0.43 | [LM7805 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) | <img src="https://github.com/user-attachments/assets/eddfdf8e-9196-4929-8f94-2821147ae6c7" alt="LM7805 Linear Regulator" width="120" /> |
| LM2940 Low Dropout 5 V Regulator | - Low dropout voltage (0.5 V)<br>- Better efficiency than 7805<br>- Stable with automotive inputs | - Not in kit<br>- Requires larger output capacitor for stability | $1.00 | [LM2940 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM2940CT-5-0-NOPB/32575) | <img src="https://github.com/user-attachments/assets/189cf4cb-28ce-4b4e-9072-73f90d5db23d" alt="LM2940 LDO Regulator" width="120" /> |
| LM2596S-5.0 Switching Regulator | - High efficiency (~85–90%)<br>- Supplies up to 3 A<br>- Minimal heat dissipation | - Requires inductor and diode<br>- More complex PCB layout | $3.50 | [LM2596S-5.0 Switching Regulator DigiKey](https://www.digikey.com/en/products/detail/umw/LM2596S-5-0/16705901) | <img src="https://github.com/user-attachments/assets/e440cd1d-b4ff-4d56-aba8-00aee270d8fc" alt="LM2596S Switching Regulator" width="120" /> |

**Choice:** LM7805  
**Rationale:**  
Provides a simple and proven 5 V source for the PIC and sensors with minimal external components. While less efficient than switching regulators, its low noise and stability make it well-suited for mixed analog/digital systems.

---
