---
title: Individual Block Diagram
---

## Overview
This block diagram represents my Audio and Alert subsystem for Team 201: The Irri Gators Garden Buddy project. The Microchip PIC18F57Q43 Curiosity Nano receives sensor signals from the 8 pin ribbon connector and processes them to determine when audio alerts should be generated. The microcontroller outputs a PWM signal that feeds a complementary transistor driver stage using a 2N3904 and a 2N3906. This stage provides the necessary current to drive an 8 Ω speaker. A regulated 5 V supply powers the entire subsystem and an LM7805 footprint is included on the PCB for compatibility with unregulated inputs although it is bypassed when a regulated 5 V adapter is used.

The subsystem also includes a local LED indicator and a pushbutton for testing and debugging without requiring connection to the main hub. This diagram shows how signals flow through the system, how the power architecture supports the components, and how the subsystem integrates with the overall Garden Buddy design.

## Block Diagram

![BlockDiagram](BlockDiagramRW.png)
<br><br>

A downloadable PDF of the block diagram is available [here](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/01-Block-Diagram/BlockDiagramRW.pdf).  
A downloadable zip of the block diagram is available [here](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/01-Block-Diagram/SpeakerBlockDiagramRW.zip).

---

## Block Explanations

The block diagram illustrates how the subsystem converts digital PWM signals into audible alerts while meeting the team’s product requirements for reliability, clarity, and controlled output volume. Each block contributes an essential function to the overall signal chain.

### PIC18F57Q43 Microcontroller
The microcontroller receives sensor data from the main hub through the ribbon cable and determines when audio alerts are required. It generates precise PWM signals using its onboard timers which allows clean and consistent tone output. By making alert decisions in firmware this block meets requirements for configurable behavior and reliable timing.

### PWM Signal Output
The PIC produces PWM because it cannot generate true analog outputs. The high speed switching creates an approximate audio waveform that can be shaped later in the circuit. PWM allows flexible tone generation with very low hardware cost while maintaining consistent control over frequency and patterns.

### Signal Conditioning and Complementary Transistor Driver
The 2N3904 and 2N3906 pair strengthens the PWM signal so that it can drive the next stage without harming the microcontroller. This stage isolates the PIC from higher current loads and improves signal clarity which directly affects the quality of the audio produced. It also ensures that the microcontroller pin operates safely within its current limits.

### Voltage Regulation using a 5 V Rail
The subsystem requires a stable 5 V supply for safe and predictable operation. A regulated 5 V adapter is used during normal operation and the LM7805 footprint exists for compatibility with unregulated sources when needed. The regulator maintains a clean supply voltage which prevents audio noise and protects sensitive components.

### Speaker Driver and Output Stage
This stage amplifies the conditioned PWM signal and supplies enough current to drive the 8 Ω speaker. It ensures that sound levels are high enough for outdoor or noisy environments which is important for the Garden Buddy system. The driver protects the earlier stages from excessive load while improving the clarity of the final audio output.

### Speaker
The speaker converts the amplified electrical signal into sound waves. It was chosen for its impedance and compatibility with the amplification stage. It fulfills the essential subsystem requirement of producing clear and audible tones that represent system alerts.

### Local LED Indicator
The LED provides a visual confirmation of alert activity. This feature is useful for debugging and makes it possible to test the subsystem without requiring the full Garden Buddy hub.

### Local Pushbutton
The pushbutton enables manual testing of the alert tone. It allows validation of the subsystem even when the main unit is disconnected which improves the debugging workflow and makes firmware testing easier.

---

## How These Blocks Work Together

1. The PIC18F57Q43 receives sensor data and decides when alerts should occur.  
2. It outputs a PWM waveform that represents the desired tone.  
3. The transistor pair conditions and strengthens this signal.  
4. The regulated 5 V supply powers all logic and audio circuitry.  
5. The driver stage amplifies the PWM waveform.  
6. The speaker outputs a clear and audible tone.  
7. The LED and pushbutton provide convenient tools for standalone debugging and validation.

Together these blocks create a reliable and efficient audio subsystem that integrates smoothly with the Garden Buddy system and meets all product level requirements.
