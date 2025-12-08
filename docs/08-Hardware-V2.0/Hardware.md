---
title: Hardware V2.0
---

## Overview
This page describes the improvements that would be made if the Audio and Alert Subsystem were redesigned for a Version 2.0 release. Because the physical PCBs arrived late in the semester I was not able to complete full assembly or hardware testing. The recommendations below are based on what I learned from schematic design, layout planning, firmware development, and reviewing the PCB before assembly. These improvements focus on making the subsystem easier to assemble, easier to debug, and more robust when integrated with the full Garden Buddy system.

---

## Improvement 1: Using an Integrated Audio Driver Instead of Discrete Transistors

The Version 1 design uses a 2N3904 and 2N3906 pair as a simple push pull stage for the PWM audio signal. While this works on paper and on breadboard prototypes, an integrated audio driver IC would provide more predictable sound output and reduce the number of discrete parts. It would also simplify routing and reduce the chance of incorrect assembly once the PCB is built.

A small audio driver IC would improve consistency and make the subsystem easier to support in Version 2.0.

---

## Improvement 2: Adding a Small Low Pass Filter for Cleaner Audio

The existing design sends raw PWM to the transistor stage. This is acceptable for simple alert tones, but it can sometimes create noticeable switching harmonics. A Version 2 design could include a simple RC low pass filter to smooth the PWM into a cleaner audio waveform. This would improve tone quality and reduce noise without increasing complexity.

---

## Improvement 3: Updating the Board Layout for Easier Assembly

Since I did not get to solder the board, I was able to look at the layout with a focus on usability. In Version 2.0 I would adjust part spacing to make soldering easier, especially around the transistor pair and the barrel jack footprint. Moving connectors closer to the edge of the board would also make cable routing easier when integrating the subsystem into the full Garden Buddy enclosure.

These updates would make the board more user friendly and reduce the chance of assembly errors.

---

## Improvement 4: Clearer Silkscreen Labels

A future revision should include clearer silkscreen labels for the power input, speaker terminals, and the ribbon connector orientation. This is especially important when a team member is assembling the board for the first time. Adding labels such as “PWM IN” or “LED” near the associated pads would make Version 2.0 easier and safer to assemble.

---

## Improvement 5: Adding Test Pads for Debugging

During firmware development I often needed to monitor the PWM output or measure the supply voltage. Adding small test pads in Version 2.0 would make these measurements much easier once the board is assembled. This is helpful even without a full test cycle on Version 1 since it makes future debugging more predictable.

---

## Improvement 6: Optional Support for a More Efficient Regulator

The PCB currently includes an LM7805 footprint for compatibility, even though the subsystem is powered by a regulated 5 V supply. A Version 2 design could replace this footprint with a more compact buck converter footprint or remove it entirely to save board space. This would simplify routing and reduce unnecessary components.

---

## Improvement 7: Reducing Board Size and Optimizing Routing

The Version 1 board intentionally used generous spacing for clarity and educational value. A Version 2 layout could reduce the footprint by tightening routing and grouping related components more efficiently. This would lower manufacturing cost and make the board easier to fit inside the Garden Buddy enclosure.

---

## Summary

Although the physical Version 1 PCB was not fully assembled due to late arrival, the design process still revealed a number of improvements that would benefit a Version 2 release. These changes focus on simplifying assembly, improving sound quality, making debugging easier, and creating a cleaner and more efficient PCB layout. The insights gained during schematic design and layout review directly informed these recommendations and will guide any future revision of the subsystem.
