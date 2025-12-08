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

## Conclusions

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
