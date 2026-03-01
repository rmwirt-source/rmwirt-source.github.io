---
Welcome
---
<center>
<font size= "6">Rylee Wirt Datasheet</font><br>
as part of<br>
<font size= "8"> Garden Buddy</font><br>
for<br>
<font size= "5"> Team 201 </font><br>

**Submission: October 26, 2025**
</center>

## Introduction

This datasheet documents the Audio and Alert subsystem I designed for Team 201’s Garden Buddy project. The subsystem provides audible and visual feedback to indicate system status, alerts, and fault conditions. It uses a Microchip PIC18F57Q43 Curiosity Nano to process sensor inputs received through an 8-pin ribbon connector, and a complementary transistor push-pull driver (2N3904 + 2N3906) to drive an 8 Ω speaker using PWM. Power is supplied by a regulated +5 V rail. An LM7805 footprint is included on the PCB for compatibility with unregulated inputs but is bypassed when a regulated 5 V adapter is used.

This datasheet contains the BOM, schematic, power budget, PCB images, and code used in the subsystem, along with design rationale and testing information. For the full system documentation, see the team website.

### Project Summary

Team 201: The Irri-Gators is developing an irrigation control system that monitors plant moisture conditions and activates watering when needed. The overall system integrates sensors, actuators, and microcontroller-based logic. My portion of the project focuses on the Audio and Alert subsystem, which generates sound-based notifications to indicate system activity, warnings, and possible errors.

The subsystem uses a PIC18F57Q43 Curiosity Nano to interpret sensor signals sent over an 8-pin ribbon connector. The microcontroller then produces PWM output that is amplified by a complementary 2N3904 / 2N3906 transistor stage and sent to an 8 Ω speaker for audible alerts. The subsystem is powered from a regulated 5 V supply to maintain consistent and stable operation.

This datasheet represents one part of our complete project documentation. To explore the full system, visit the team report at:
https://asu-egr304-2025-f-201.github.io

### My Contribution

My contribution to Team 201 involves designing, testing, and documenting the speaker subsystem. This subsystem provides a dependable method for generating audio alerts that help users understand system behavior or detect errors. I worked with my teammates to define electrical interfaces, ensure power compatibility, and integrate the subsystem cleanly with the overall Garden Buddy architecture.

This datasheet guides readers through the technical aspects of my subsystem. The “BOM” section lists the major components used in the design. The schematic, power budget, PCB layout, and testing sections provide further detail on the electrical performance and design decisions. Together, these sections explain how the speaker subsystem supports Team 201’s Garden Buddy project.

To review the materials used in this design, see the [BOM](https://rmwirt-source.github.io/03-BOM/BOM) section of the datasheet.
