---
title: Individual Block Diagram
---

## Overview
This block diagram represents my Audio and Alert subsystem for Team 201: The Irri-Gators Garden Buddy project. The Microchip PIC18F57Q43 Curiosity Nano receives sensor signals from the 8-pin ribbon connector and processes them to determine when audio alerts should be generated. The microcontroller outputs a PWM signal that feeds a complementary transistor driver stage (2N3904 + 2N3906), which provides the necessary current to drive an 8 Ω speaker. A regulated +5 V supply powers the entire subsystem, and an LM7805 footprint is included on the PCB for compatibility with unregulated inputs, though it is bypassed when using a regulated 5 V adapter.

The subsystem also includes a local LED indicator and a pushbutton for testing and debugging without requiring connection to the main hub. This diagram shows how signals flow through the system, how the power architecture supports the components, and how the subsystem integrates with the overall Garden Buddy design.

## Block Diagram

![BlockDiagram](BlockDiagramRW.png)
<br><br>

A downloadable PDF of the block diagram is available [here](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/01-Block-Diagram/BlockDiagramRW.pdf).
<br>

A downloadable .zip of the block diagram is available [here](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/01-Block-Diagram/SpeakerBlockDiagramRW.zip).
