---
title: Power Budget
---

## Overview
This power budget identifies the amount of power that my subsystem requires and confirms that the selected power source safely meets the needs of the Audio and Alert subsystem. Each component in the design was reviewed to determine its maximum current draw, including the PIC18F57Q43 microcontroller, the 2N3904 and 2N3906 transistors used in the speaker driver, the indicator LED, and the support circuitry.
<br>

My subsystem operates entirely from a regulated +5 V rail and is powered by a 5 V, 2 A wall adapter. The tables shown below outline the current requirements for each part of the design. A 25 percent safety margin is applied to account for worst-case operating conditions. Based on these calculations, the total subsystem current remains well below the limits of the power supply.
<br>

The transistor-based speaker driver replaces the previous op-amp design and draws significantly less current in steady state. The speaker itself draws short bursts of higher current when generating alert tones, but these pulses remain within the safe limits of the supply and the wiring allowances included in the budget.


![budget1](PowerBudgetRW_V5_PG1.png)

![budget2](PowerBudgetRW_V5_PG2.png)

![budget3](PowerBudgetRW_V5_PG3.png)

## Power Budget Explanation

The purpose of the power budget is to verify that all components in the Speaker Subsystem can operate safely from the selected power source without exceeding the regulator’s current capability or causing thermal issues. To create the final power budget, I collected the maximum current values for each component from their datasheets and used worst-case estimates to ensure that the design remains reliable even under full load.
<br>

The PIC18F57Q43 microcontroller has a relatively small current draw, and its maximum active current was used to provide margin during operation. The audio amplifier and speaker load represent the largest portion of the subsystem’s power consumption, so their values were calculated based on the maximum output power and expected efficiency. I also included losses through the linear regulator, since linear regulators dissipate excess voltage as heat, which affects total system power requirements.
<br>

Once all currents were summed, I compared the total subsystem current to the 9V supply and to the maximum output capability of the linear regulator. From this comparison, I confirmed that the regulator provides sufficient headroom for safe operation, even at peak load. This analysis shows that the subsystem will not exceed the regulator's thermal or electrical limits, and no additional power components are required.
<br>
The conclusion from this power budget is that the Speaker Subsystem comfortably meets power requirements with adequate safety margin, and the chosen power architecture is appropriate for the final design.

## Conclusions

From the updated power budget, the subsystem’s current requirements remain far below the limits of the 5 V, 2 A wall adapter. The replacement of the op-amp with a 2N3904 and 2N3906 transistor driver does not significantly impact the overall power consumption, and the speaker load only draws short bursts of current during audible alerts. The total operating current, including a 25 percent safety margin, is approximately 200 mA, leaving substantial overhead for reliable operation.
<br>

Because the subsystem uses only a 5 V power rail and does not include any higher-voltage regulation stages, the design remains simple, efficient, and low risk for power faults. The calculated current draws confirm that all components receive sufficient power without overloading the supply, and the regulator and wiring allowances provide additional margin for real-world conditions.
<br>

This analysis increases confidence that the subsystem will remain stable during testing and full system integration, even under worst-case load conditions.
<br>

## Resouces

The power budget as a PDF download is available [*here*](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/05-Power-Budget/PowerBudgetRW_V5.pdf
)
, and a Microsoft Excel Sheet [*here*](https://raw.githubusercontent.com/rmwirt-source/rmwirt-source.github.io/main/docs/05-Power-Budget/PowerBudgetRW_V5.xlsx)
.
