---
title: Schematic
---

## Overview

This schematic supports the Audio and Alert subsystem for Team 201’s Irri-Gators project. The subsystem provides both audible and visual feedback to indicate system status, alerts, or potential faults within the irrigation system. The design includes a regulated 5 V power input, a Microchip PIC18F57Q43 microcontroller, an MCP6004 operational amplifier configured for audio buffering and amplification, and a WT-1205 active buzzer for sound output. Local testing components such as an LED and pushbutton are also included to verify operation without requiring connection to the main hub.
<br><br>
Power enters the circuit through a 5 V DC barrel jack and passes through a 200–250 mA fuse for overcurrent protection. The LM7805 voltage regulator footprint is included for future compatibility with unregulated supplies but is bypassed when using a regulated 5 V input. Capacitors at the input and output of the power section filter noise and stabilize the supply, ensuring consistent voltage for the microcontroller and op-amp. Test points are provided for the 5 V rail and ground to simplify debugging and measurement.
<br><br>
The microcontroller receives the regulated 5 V power and handles input, output, and communication with the main hub through an 8-pin ribbon connector. The PIC generates a PWM signal on RB3 that is buffered by the MCP6004 op-amp before driving the buzzer. This configuration isolates the microcontroller from higher current loads and satisfies the project requirement to incorporate an op-amp. An LED connected to RC4 provides a local visual indicator, while a pushbutton on RB0 allows for manual testing. The design also includes analog I/O connections through the ribbon connector, with RA0 serving as an analog input and RA2 as an analog or DAC output to the hub.
<br><br>
The op-amp output is AC-coupled to the buzzer through a capacitor to block any DC offset and ensure a clean audible signal. The MCP6004 operates from the 5 V rail with local decoupling for stability. The ribbon connector provides all required signal interfaces with the hub, including the digital alert output, analog feedback input, and analog output. Only the ground line is shared across boards; no 5 V power is distributed through the ribbon.
<br><br>
This subsystem meets the user and team requirements by providing reliable audio and visual feedback while maintaining electrical isolation between subsystems. The regulated 5 V design ensures stable operation and compatibility with the other Irri-Gators components. The schematic supports future expansion through labeled unused pins and additional op-amp channels that can be configured for new features or signal conditioning as the system evolves.
<br><br>


![Schematic](SchematicScreenshot.png)




## Resouces

The schematic as a PDF download is available [*here*](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/04-Schematic/SchematicDesign_RW.pdf).


