---
title: Component Selection
---

## Component Selection

This section outlines the major components chosen for the Audio and Alert subsystem and summarizes the design decisions behind each choice. The final major components are listed in the summary table below followed by detailed evaluations of alternatives considered during development.

---

## Summary of Final Major Components

The table below lists the primary components used in the Audio and Alert subsystem in a compact format that improves readability on the webpage.

| Component | Part Number | Function | Rationale | Cost | Link |
|-----------|-------------|----------|-----------|------:|------|
| PIC18F57Q43 Curiosity Nano | EV18F57Q43 | Microcontroller for PWM and control | Provided in kit. Matches team MCU. Reliable timers for tone generation | Included | [Microchip](https://www.microchip.com/en-us/development-tool/EV18F57Q43) |
| 2N3904 NPN Transistor | 2N3904 | Part of driver stage | Simple, available, and supports required current | $0.05 | [DigiKey](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3904/22116349) |
| 2N3906 PNP Transistor | 2N3906 | Completes push pull driver | Works with 2N3904 to create a clean audio output stage | $0.05 | [DigiKey](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3906/22116343) |
| 8 Ω Mini Mylar Speaker | CE 2808B36 | Outputs audible tones | Already in kit and produces clear alerts | $0.85 | [Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) |
| LM7805 Linear Regulator | LM7805CT | Regulates 5 V supply | Simple, stable, and included in kit | $0.43 | [DigiKey](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) |
| 5 V 2 A Wall Adapter | Generic | External power supply | Reliable source with ample current overhead | $6.00 | — |
| LED Indicator | Generic | Alert and debug indicator | Helps confirm tone output during testing | $0.05 | — |
| Momentary Pushbutton | Generic | Local trigger for test tones | Allows testing without main hub connection | $0.10 | — |
| Barrel Jack Connector | PJ 002AH | Main power input connector | Standard and secure power interface | $0.60 | [DigiKey](https://www.digikey.com/en/products/detail/cui-devices/PJ-002AH/474819) |

---

## 1. Speaker Signal Conditioning (Transistor Driver Options)

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|---------|---------|
| **2N3904 and 2N3906 pair (already in kit)** | Complementary BJT pair forms a simple push pull stage. Very low cost and works well with PIC PWM output. Easy to integrate and compact. | Limited current capability around 200 to 300 mA. Not suited for loud audio output. | ~$0.10 combined | [2N3904](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3904/22116349)<br>[2N3906](https://www.digikey.com/en/products/detail/lumimax-optoelectronic-technology/2N3906/22116343) | ![2N3906](https://github.com/user-attachments/assets/fa75cb63-4de4-4150-b3bc-0b110ac82301) |
| Single NPN Driver | Very simple circuit suitable for low side switching. Works well for short simple tone bursts. | Lower output volume. Not a true push pull stage. Limited to one direction of current flow. | ~$0.05 | [2N2222](https://www.digikey.com/en/products/detail/onsemi/2N2222/33077) | ![2N2222](https://github.com/user-attachments/assets/69ea7552-7565-4d7f-a179-7653fd5d176a) |
| Logic Level MOSFET | Higher current capability, low conduction losses, and efficient for PWM audio. | Not included in kit and more sensitive to wiring and grounding. | ~$0.30 | [Si2302](https://www.digikey.com/en/products/detail/mcc-micro-commercial-components/SI2302-TP/1793243) | ![Si2302](https://github.com/user-attachments/assets/244a0dfa-d4ad-462e-ae66-8da078ac7b3c) |

**Final Choice: 2N3904 and 2N3906**  
**Rationale:**  
This complementary pair forms an efficient and low cost driver that works well with the PIC PWM output. Both transistors are included in the kit and provide enough current for alert tones. The circuit is compact and easy to assemble.

---

## 2. Speaker or Buzzer

| Solution | Pros | Cons | Cost | Datasheet or Seller | Picture |
|----------|------|------|------:|----------------------|-----------|
| **8 Ω Mini Mylar Speaker (in kit)** | Small, lightweight, and produces clear tones. Very convenient. | Moderate loudness and not designed for high power audio. | $0.85 | [Datasheet](https://www.jameco.com/z/CE-2808B36-James-Electronics-Micro-Round-8-Ohm-Mylar-Speaker-92-dB-2-Wires_2302983.html) | <img src="https://github.com/user-attachments/assets/24a6eb60-09d2-4d6f-b6c7-82f5fd910cd7" width="120" /> |
| WT 1205 Buzzer | Loud and easy to use with a simple two pin design. | Only fixed frequency tones and not included in kit. | $0.59 | [DigiKey](https://www.digikey.com/en/products/detail/soberton-inc/WT-1205/479674) | <img src="https://github.com/user-attachments/assets/ca3dbe7e-1671-4284-ba8d-99634466c295" width="120" /> |
| CUI CDS 25148 Speaker | Very loud and durable. | Not in kit and physically larger. | $2.46 | [DigiKey](https://www.digikey.ca/en/products/detail/same-sky-formerly-cui-devices/CDS-25148-L100/5355540) | <img src="https://github.com/user-attachments/assets/5f8edc63-4071-42bb-97db-7a784e2491be" width="120" /> |

**Final Choice: 8 Ω Mini Mylar Speaker**  
**Rationale:**  
Already available in the kit and produces clear alert tones. It integrates well with the driver stage and requires no additional amplifier.

---

## 3. Voltage Regulation

| Solution | Pros | Cons | Cost | DigiKey | Picture |
|----------|------|------|------:|---------|---------|
| **LM7805 Linear Regulator (in kit)** | Stable 5 V output with low noise. Requires very few external parts. | Lower efficiency when stepping down from higher voltages. Can create noticeable heat under heavy load. | $0.43 | [LM7805](https://www.digikey.com/en/products/detail/texas-instruments/LM7805CT-NOPB/3901929) | <img src="https://github.com/user-attachments/assets/eddfdf8e-9196-4929-8f94-2821147ae6c7" width="120" /> |
| LM2940 LDO Regulator | Low dropout voltage and better efficiency at moderate loads. | Requires specific capacitors for stability and not included in kit. | $1.00 | [LM2940](https://www.digikey.com/en/products/detail/texas-instruments/LM2940CT-5-0-NOPB/32575) | <img src="https://github.com/user-attachments/assets/189cf4cb-28ce-4b4e-9072-73f90d5db23d" width="120" /> |
| LM2596 Switching Regulator | Highly efficient and handles high currents with little heat. | More complex layout and requires additional passive parts. | $3.50 | [LM2596](https://www.digikey.com/en/products/detail/umw/LM2596S-5-0/16705901) | <img src="https://github.com/user-attachments/assets/e440cd1d-b4ff-4d56-aba8-00aee270d8fc" width="120" /> |

**Final Choice: LM7805**  
**Rationale:**  
It provides a clean and stable 5 V rail with very little design effort. The subsystem current draw is low enough that heat is not a concern. Its presence in the kit simplifies the design.
