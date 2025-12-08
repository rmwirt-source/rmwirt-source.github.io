---
title: Reflections
---

## Reflections
This page contains my project reflections. Use the links below to jump to each section.

- [Lessons Learned](#lessons-learned)  
- [Recommendations for Future Students](#recommendations-for-future-students)

---

<a id="lessons-learned"></a>
## Lessons Learned

During this project I learned several technical and workflow lessons that improved my design and debugging approach. First, PWM frequency selection matters for perceived audio quality. On breadboard prototypes I found that using a PWM frequency that is too low produced audible switching artifacts. After increasing the frequency and testing several values I selected a PWM frequency that balances tone clarity and MCU timing overhead.

Second, the complementary transistor driver requires proper base resistors and layout attention. On breadboard tests I observed that missing base resistors allowed excessive base current and made the driver stage less reliable. Adding the correct resistors and keeping short traces in the layout reduced stress on the microcontroller pins and improved repeatability.

Third, planning probe points and test pads early saves time. While reviewing the PCB layout before assembly I added several test pads for PWM, 5 volt, and ground. Those points make it easier to validate signals when the boards are assembled. Even though the physical PCBs arrived late and I did not fully populate them, planning those pads paid off during firmware development on a breadboard.

Finally, clear documentation and version control for component choices reduces confusion during integration. Keeping a concise summary table of final components and a short rationale for each part helped the team avoid mismatches between the schematic and the BOM.

These lessons came from a mix of breadboard testing, schematic review, and layout checks and will directly improve any future iterations of this subsystem.

---

<a id="recommendations-for-future-students"></a>
## Recommendations for Future Students

Here are practical recommendations to help future teams complete this assignment efficiently and avoid common pitfalls.

1. Add test pads for PWM, 5 volt, and ground early in the layout process. They make debugging with an oscilloscope or meter simple and safe.  
2. Reserve space for probe access and for a small breadboard friendly jumper area. This allows quick testing of firmware without full board population.  
3. Choose a PWM frequency and test it on a breadboard with the actual speaker or buzzer you plan to use. Tone perception can change with the speaker and the frequency choice.  
4. Use short base resistor values for transistor drivers and verify base currents using simple calculations or measurements. This protects microcontroller pins and improves reliability.  
5. Keep a compact summary table of final components near the top of the component selection page. This speeds grading and prevents version mismatch errors.  
6. If you expect late PCBs, make a deliberate plan for what you will validate on breadboard first and what can wait until assembly.

Prioritize items in that order. These steps reduce rework and make integration with the full project smoother.

