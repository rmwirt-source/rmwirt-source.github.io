---
title: Component Selection
---

## Component Selection

---

### 1. Speaker Signal Conditioning (Transistor Options)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|---------|---------|
| **2N3904 (NPN) + 2N3906 (PNP) (already in kit)** | - Complementary BJT pair for push-pull output<br>- Very low cost<br>- Works well with PIC PWM<br>- Simple design | - Limited current (≈200–300 mA)<br>- Not suitable for loud/high-power audio | ~$0.10 combined | [2N3904](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3904/22116349)<br>[2N3906](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3906/22116343) |![2N3906](https://github.com/user-attachments/assets/fa75cb63-4de4-4150-b3bc-0b110ac82301)|
| Single NPN Driver (2N2222 or 2N3904) | - Simplest design<br>- Easy low-side switching<br>- Good for short beeps | - Lower volume<br>- Not push-pull<br>- Only pulls to ground | ~$0.05 | [2N2222](https://www.digikey.com/en/products/detail/onsemi/2N2222/33077) |![2N2222](https://github.com/user-attachments/assets/69ea7552-7565-4d7f-a179-7653fd5d176a)|
| Logic-Level MOSFET (N-Channel, Si2302) | - Higher current capability<br>- Low heat / low Rds(on)<br>- Efficient for PWM tones | - Not in kit<br>- More sensitive to wiring/layout | ~$0.30 | [Si2302](https://www.digikey.com/en/products/detail/mcc-micro-commercial-components/SI2302-TP/1793243) | ![Si2302](https://github.com/user-attachments/assets/244a0dfa-d4ad-462e-ae66-8da078ac7b3c)|

**Choice:** 2N3904 + 2N3906  
**Rationale:**  
Provides a simple, low-cost push-pull transistor driver compatible with the PIC’s PWM output. It supplies enough current for the 8 Ω speaker while keeping the circuit compact and easy to implement.


---

### 2. Speaker/Buzzer (Audio Alert)

| Solution | Pros | Cons | Cost | Datasheet/DigiKey | Picture |
|----------|------|------|------:|--------------------|-----------|
| **8 Ω Mylar Mini Speaker (already in kit)** | - Already available<br>- Compact<br>- Works with small-signal amplifiers | - Limited sound pressure level (≈ 85 dB)<br>- Not high-fidelity | $0.85 | [CE-2808B36 Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) | <img src="https://github.com/user-attachments/assets/24a6eb60-09d2-4d6f-b6c7-82f5fd910cd7" alt="8Ω Mylar Mini Speaker" width="120" /> |
| WT-1205 Buzzer | - Small and easy to wire<br>- Louder than basic speakers (~90 dB)<br>- Reliable brand<br>- Simple two-pin connection | - Not in kit<br>- Slightly higher cost | $0.59 | [WT-1205 DigiKey](https://www.digikey.com/en/products/detail/soberton-inc/WT-1205/479674) | <img src="https://github.com/user-attachments/assets/ca3dbe7e-1671-4284-ba8d-99634466c295" alt="WT-1205 Buzzer" width="120" /> |
| CUI Devices CDS-25148-L100 | - Robust design<br>- High sound output (≈ 95 dB)<br>- Durable housing | - Not in kit<br>- Larger footprint | $2.46 | [CUI Devices CDS-25148-L100 DigiKey](https://www.digikey.ca/en/products/detail/same-sky-formerly-cui-devices/CDS-25148-L100/5355540) | <img src="https://github.com/user-attachments/assets/5f8edc63-4071-42bb-97db-7a784e2491be" alt="CUI Devices CDS-25148-L100" width="120" /> |

**Choice:** 8 Ω Mylar Mini Speaker
**Rationale:**  
Already in kit, works well with system, creates a loud enough noise for the purpose.

---

### 3. Voltage Regulator (5 V Supply)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|-----------|-----------|
| **LM7805 Linear Regulator (already in kit)** | - Already available<br>- Simple to use<br>- Stable 5 V output<br>- Low noise | - Inefficient for large voltage drops<br>- Heat generation above 1 A load | $0.43 | [LM7805 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) | <img src="https://github.com/user-attachments/assets/eddfdf8e-9196-4929-8f94-2821147ae6c7" alt="LM7805 Linear Regulator" width="120" /> |
| LM2940 Low Dropout 5 V Regulator | - Low dropout voltage (0.5 V)<br>- Better efficiency than 7805<br>- Stable with automotive inputs | - Not in kit<br>- Requires larger output capacitor for stability | $1.00 | [LM2940 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM2940CT-5-0-NOPB/32575) | <img src="https://github.com/user-attachments/assets/189cf4cb-28ce-4b4e-9072-73f90d5db23d" alt="LM2940 LDO Regulator" width="120" /> |
| LM2596S-5.0 Switching Regulator | - High efficiency (~85–90%)<br>- Supplies up to 3 A<br>- Minimal heat dissipation | - Requires inductor and diode<br>- More complex PCB layout | $3.50 | [LM2596S-5.0 Switching Regulator DigiKey](https://www.digikey.com/en/products/detail/umw/LM2596S-5-0/16705901) | <img src="https://github.com/user-attachments/assets/e440cd1d-b4ff-4d56-aba8-00aee270d8fc" alt="LM2596S Switching Regulator" width="120" /> |

**Choice:** LM7805  
**Rationale:**  
Provides a simple and proven 5 V source for the PIC and sensors with minimal external components. While less efficient than switching regulators, its low noise and stability make it well-suited for mixed analog/digital systems.

---
