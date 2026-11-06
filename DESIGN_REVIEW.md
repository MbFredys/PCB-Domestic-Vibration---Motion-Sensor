# Design review and release criteria

Status: open findings. This is a static review of published design files, not an ERC/DRC run or a laboratory validation. No electrical source or manufacturing file has been corrected by this documentation update.

## VIB-01 — I²C pull-up network

**Observed:** In `Kicad Files/Wearable Básico.net`, C1 and C2 are 2.2 µF. Each has one terminal on +3V3; the other terminals connect to I2C_SCL_IMU and I2C_SDA_IMU. The schematic assigns the same capacitance values.

**Consequence:** These are capacitors, not resistive pull-ups. Their capacitance is incompatible with the intended conventional I²C connection and cannot be accepted as a functional pull-up network.

**Remediation:** Confirm the intended circuit, replace the erroneous elements with correctly sized pull-up resistors if external pull-ups are required, and account for any pull-ups already on connected modules. Choose resistance from bus voltage, sink-current limits, rise time and estimated capacitance; do not select a value solely by habit.

**Close only after:** schematic/PCB synchronization, reviewed BOM, ERC/DRC and measured SCL/SDA voltage levels and rise times at the chosen clock rate.

## VIB-02 — Reset resistor

**Observed:** R1 is listed with the generic value `R`.

**Remediation:** Define its actual resistance, tolerance and reset timing in conjunction with the 2.2 µF capacitor C5 and the Nano reset circuitry.

**Close only after:** documented calculation and repeated power-on/manual-reset checks.

## VIB-03 — Power and battery claims

**Observed:** +7.4_BATT feeds Nano VIN. The IMU receives 3.3 V from the Nano. A separate carrier-board regulator is not listed.

**Remediation:** Verify the exact Nano revision and its complete VIN range against a fully charged battery pack, current consumption and thermal behavior. Define battery protection, charging and power switching outside the carrier if not provided on the board.

**Close only after:** electrical review plus rail, temperature and consumption measurements.

## VIB-04 — Function and measurement claims

Firmware is not available. Define sampling rate, bandwidth, filtering, orientation, mounting, calibration and the actual target use. Publish repeatable measurements before claiming abnormal-vibration detection or predictive maintenance.

## Documentation synchronization

After implementing approved circuit changes, update the PCB, PDF, netlist, BOM, positions, Gerbers and renders together. Historical fabrication exports are not a validated release.

## References

- [NXP — I²C-bus specification and user manual, UM10204](https://www.nxp.com/docs/en/user-guide/UM10204.pdf)
- [Arduino — Nano ESP32 documentation](https://docs.arduino.cc/hardware/nano-esp32/)
