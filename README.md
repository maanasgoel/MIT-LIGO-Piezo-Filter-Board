# Slip-Stick Piezo Motor Filter Selector Board

A 12-channel filter and switching board for the slip-stick piezo motors in the Coating Thermal Noise (CTN) experiment at the MIT LIGO Laboratory, designed during a hardware engineering internship in Summer 2025.

Slip-stick piezo motors behave like capacitors at low frequency. This board lets each channel's drive signal take one of two paths, chosen by a microcontroller:

- **Filtered:** a three-stage RC low-pass (about 10 Hz corner) that smooths noisy signals and steps before they reach the motor
- **Direct:** a fixed 30 kΩ path for calibration or when more bandwidth is needed

Both paths present the same 30 kΩ of series resistance, so switching between them doesn't cause gain jumps.

## What's in the design

- Filter design: component sizing for cascaded RC sections, settling time, tolerances, and alternative 5 Hz and 1 Hz corners
- Motor measurements: capacitance and leakage measured on the bench
- MOSFET SPDT switching per channel, with an LED that shows when a channel is filtered
- Microcontroller control: a SAMD21 (uChip) running a USB serial command protocol and state machine, with reference firmware
- Altium schematics and PCB layout, connector pin mapping, bring-up and test plan, and bill of materials

## Report

[MIT_LIGO_2025_Piezo_Filter_Board_Report.pdf](MIT_LIGO_2025_Piezo_Filter_Board_Report.pdf)
