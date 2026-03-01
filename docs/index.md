---
title: Welcome
---

<center>
<font size="6">Rylee Wirt – Controller Module Datasheet</font><br>
as part of<br>
<font size="8">EGR 314 Rover Project</font><br>
for<br>
<font size="5">Team 301</font><br>

**Submission: May 4, 2026**
</center>

---

## Introduction

This datasheet documents the design of the Controller Module for Team 301’s EGR 314 rover system. The controller module is responsible for receiving user input, processing control logic, and transmitting structured command messages to other subsystems within the rover architecture.

The module is built around an ESP32 microcontroller operating at 3.3 V logic. It communicates with other team modules over the defined system bus and manages command generation, message formatting, and control coordination. Stable 3.3 V regulation is used to ensure reliable digital communication and consistent system behavior.

This document provides the technical details of the controller module, including requirements, block diagram, component selection, bill of materials, schematic, and power budget.

---

## System Context

The rover system consists of multiple distributed modules connected through a shared communication structure. Each module has a defined role and address within the architecture.

The controller module functions as the primary command source. It interprets control inputs and transmits properly formatted packets to motor, sensor, and support modules. Clear signal routing, defined voltage levels, and reliable communication are critical to ensure predictable rover operation.

---

## My Contribution

My responsibility on Team 301 includes:

- Defining controller module requirements  
- Designing the block diagram and communication interface  
- Selecting and justifying hardware components  
- Developing the schematic  
- Creating and analyzing the power budget  
- Documenting the complete electrical design  

This datasheet explains how the controller module satisfies functional requirements and integrates with the overall rover system architecture.

 ---
 
For complete system level documentation, visit the Team 301 website:  
https://asu-egr314-301-s-2026.github.io/EGR314-Team301/
