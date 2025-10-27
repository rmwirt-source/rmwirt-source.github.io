---
title: Schematic
---

## Overview

This schematic is design to support the speaker subsystem for Team 201's Irri-gators project. This subsystem provides audio feedback to alert users of system events, watering status, or errors. The schemmatic includes a 5V power supply, the PIC18f57q43 microcontroller, an audio amplifier using the MCP6004 op amp and an 8 ohm speaker for sound output.
<br><br>
Using the barrel jack connector power enters the circuit and passes through a fuse, for protection, before reaching the LM7805 voltage regulator. The LM7805 outputs a steady 5 V DC supply used by the rest ofthe components. A pair of capacitors stabbilize the voltage and minimize noise on the power line.
<br><br>
From there the mircocontroller recieves the regulated 5 V and generates an audio PWM signal, which is fed into the MCP6004 operational amplifier configures as a non-inverting amplifier. The amplifier boosts the signal strength so the signal can reach the speaker effectively. From there a coupling capacitor filters the DC offset and ensures a clean sound output. The schematic also includes a status LED with a resistor so we have a visual indicator that the system is powered and active.
<br><br>
This subsystem means the user's needs by providiing a reliable audio feedback and improves the irrigation system's usability and accessibility. The regulated 5 V design ensures consistem operation and compatibility with my team's other subsystems. The schematic can be seen below, as well as a PDF of the design in the resources below.
<br>



![1761591332839-e21bd0b6-e113-4a6a-bef0-81fbec15be35_1](https://github.com/user-attachments/assets/0bc870ec-c6b7-42eb-b2fd-03b7d51a9028)




## Resouces

The schematic as a PDF download is available [*here*](https://github.com/user-attachments/files/23172034/SchematicDesign_RW.pdf)

