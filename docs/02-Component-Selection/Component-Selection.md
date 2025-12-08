---
title: Component Selection
---

## Component Selection

This section outlines the major components chosen for the Audio and Alert subsystem and summarizes the design decisions behind each choice. The final major components are listed in the summary table below, followed by detailed evaluations of alternatives considered during development.
<br>

---

## 1. Speaker Signal Conditioning (Transistor Driver Options)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|---------|---------|
| **2N3904 (NPN) + 2N3906 (PNP) (already in kit)** | Complementary BJT pair forms a simple push-pull stage. Very low cost and works well with PIC PWM output. Easy to integrate and compact. | Limited current capability (around 200–300 mA). Not suitable for high-volume audio. | ~$0.10 combined | [2N3904](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3904/22116349)<br>[2N3906](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3906/22116343) | ![2N3906](https://github.com/user-attachments/assets/fa75cb63-4de4-4150-b3bc-0b110ac82301) |
| Single NPN Driver (2N2222 or 2N3904) | Very simple circuit suitable for low-side switching. Works well for short, simple tone bursts. | Lower output volume. Not a true push-pull stage. Limited to pulling current in one direction. | ~$0.05 | [2N2222](https://www.digikey.com/en/products/detail/onsemi/2N2222/33077) | ![2N2222](https://github.com/user-attachments/assets/69ea7552-7565-4d7f-a179-7653fd5d176a) |
| Logic-Level MOSFET (Si2302) | Higher current capability, low conduction losses, and efficient for PWM audio. | Not included in kit and more sensitive to wiring and grounding. | ~$0.30 | [Si2302](https://www.digikey.com/en/products/detail/mcc-micro-commercial-components/SI2302-TP/1793243) | ![Si2302](https://github.com/user-attachments/assets/244a0dfa-d4ad-462e-ae66-8da078ac7b3c) |

**Final Choice: 2N3904 + 2N3906**  
**Rationale:**  
This complementary pair forms an efficient, low-cost push-pull driver compatible with the PIC’s PWM signal. Both transistors are provided in the kit, easy to solder, and offer enough current handling for short audio bursts. The resulting circuit is compact, reliable, and requires minimal external components.

---

## 2. Speaker/Buzzer (Audio Output Device)

| Solution | Pros | Cons | Cost | Datasheet/DigiKey | Picture |
|----------|------|------|------:|--------------------|-----------|
| **8 Ω Mylar Mini Speaker (already in kit)** | Small, lightweight, and produces clear tones. Convenient and already available. | Moderate loudness (~85 dB). Not suited for high-power audio. | $0.85 | [CE-2808B36 Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) | <img src="https://github.com/user-attachments/assets/24a6eb60-09d2-4d6f-b6c7-82f5fd910cd7" width="120" /> |
| WT-1205 Buzzer | Louder (~90 dB) and has a simple two-pin interface. Great for fixed alerts. | Not included in kit. Only supports fixed-frequency tones. | $0.59 | [WT-1205 DigiKey](https://www.digikey.com/en/products/detail/soberton-inc/WT-1205/479674) | <img src="https://github.com/user-attachments/assets/ca3dbe7e-1671-4284-ba8d-99634466c295" width="120" /> |
| CUI CDS-25148-L100 | Robust construction and loud (~95 dB). Suitable for noisy environments. | Not included in kit. Larger physical size. | $2.46 | [CDS-25148-L100 DigiKey](https://www.digikey.ca/en/products/detail/same-sky-formerly-cui-devices/CDS-25148-L100/5355540) | <img src="https://github.com/user-attachments/assets/5f8edc63-4071-42bb-97db-7a784e2491be" width="120" /> |

**Final Choice: 8 Ω Mylar Mini Speaker**  
**Rationale:**  
This speaker is already available in the kit, easy to mount, and produces clear enough tones for alerting purposes. It integrates well with the transistor driver and does not require additional amplification or specialized circuitry. Its size and power rating are appropriate for a lightweight subsystem.

---

## 3. Voltage Regulation (5 V Supply)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|-----------|-----------|
| **LM7805 Linear Regulator (already in kit)** | Stable 5 V output, low noise, and extremely simple to integrate. Requires very few external components. | Low efficiency when stepping down from higher voltages. Can produce heat at higher loads. | $0.43 | [LM7805 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) | <img src="https://github.com/user-attachments/assets/eddfdf8e-9196-4929-8f94-2821147ae6c7" width="120" /> |
| LM2940 Low Dropout Regulator | Lower dropout voltage and more efficient over moderate loads. Designed for unstable power environments. | Not included in kit and requires specific output capacitors for stability. | $1.00 | [LM2940 DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM2940CT-5-0-NOPB/32575) | <img src="https://github.com/user-attachments/assets/189cf4cb-28ce-4b4e-9072-73f90d5db23d" width="120" /> |
| LM2596S-5.0 Switching Regulator | High efficiency and capable of supplying higher currents with very little heat. | More complex layout and requires additional passive components. | $3.50 | [LM2596S-5.0](https://www.digikey.com/en/products/detail/umw/LM2596S-5-0/16705901) | <img src="https://github.com/user-attachments/assets/e440cd1d-b4ff-4d56-aba8-00aee270d8fc" width="120" /> |

**Final Choice: LM7805**  
**Rationale:**  
The LM7805 is stable, low-noise, and straightforward to use, which makes it ideal for powering both the PIC microcontroller and the audio circuitry. Because the subsystem draws relatively little current, heat is not a concern, and the regulator provides a clean 5 V rail with minimal external components. Its availability in the kit further simplifies the design.

---
## Summary of Major Components

| Component | Part Number | Function | Rationale for Selection | Cost | Link |
|-----------|-------------|----------|--------------------------|------:|-------|
| **PIC18F57Q43 Curiosity Nano** | EV18F57Q43 | Microcontroller for PWM generation and subsystem control | Already provided in the kit, strong peripheral set, consistent with team’s chosen MCU | Included in kit | [Product Page](https://www.microchip.com/en-us/development-tool/EV18F57Q43) |
| **2N3904 NPN Transistor** | 2N3904 | Push-pull driver (high-side switching) | Readily available, reliable, and supports the required current for alert tones | ~$0.05 | [DigiKey](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3904/22116349) |
| **2N3906 PNP Transistor** | 2N3906 | Push-pull driver (low-side switching) | Complements 2N3904 to create a simple and effective audio drive stage | ~$0.05 | [DigiKey](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3906/22116343) |
| **8 Ω Mini Mylar Speaker** | CE-2808B36 | Produces audible alert tones | Already available, compact, and sufficiently loud for subsystem needs | ~$0.85 | [Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) |
| **LM7805 Linear Regulator** | LM7805CT | Provides regulated 5 V supply | Stable, low-noise, easy to use, and included in the kit | ~$0.43 | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) |
| **5 V / 2 A Wall Adapter** | Generic | Primary subsystem power source | Reliable and provides significant current overhead | ~$6.00 | — |

<br>
