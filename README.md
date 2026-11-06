# Motion and Vibration Sensor — Hardware Design

Compact motion-sensing PCB concept combining an Arduino Nano ESP32 and an MPU-6050 six-axis IMU.

> **Status: design under review.** Source schematics, PCB files, renders and manufacturing exports are available. Firmware is not published in this repository, and no measurement results are supplied. The current design has unresolved electrical issues and must not be treated as ready for fabrication.

![PCB design render](Release/Wearable%20B%C3%A1sico%203.png)

## Objective and intended architecture

The intended application is acquiring motion data from an object and exploring wireless monitoring. The design includes:

- Arduino Nano ESP32 module for processing and intended Wi-Fi/Bluetooth connectivity.
- MPU-6050 accelerometer and gyroscope connected over I²C, with an interrupt signal.
- A battery input labelled `+7.4_BATT` connected to the Nano VIN input.
- A 3.3 V rail supplied by the Nano module to the IMU.
- External reset circuitry.

The carrier does not contain a separately populated 3.3 V regulator in the published netlist. The battery range, module input limits and power budget require verification.

## Important design-review findings

- C1 and C2 are assigned **2.2 µF** and connected between 3.3 V and SCL/SDA in the published netlist. This is not a substitute for I²C pull-up resistors and requires correction before fabrication.
- The reset resistor R1 has an unspecified value (`R`).
- The legacy source filenames say “Wearable Básico”; these are retained so existing links remain valid.

See [DESIGN_REVIEW.md](DESIGN_REVIEW.md) for evidence, proposed remediation and verification criteria. These findings are not marked as resolved.

## What is not demonstrated

No firmware, alerting service, wireless dashboard, logging implementation, calibrated vibration measurements, predictive-maintenance performance or measured battery life is provided. Those are possible future developments, not current capabilities.

## Repository contents

| Directory | Contents |
|---|---|
| [Kicad Files](Kicad%20Files/) | Editable schematics, PCB, project and exported netlist |
| [Schematic](Schematic/) | PDF schematic |
| [Manufacturing](Manufacturing/) | Historical BOM, placement and fabrication exports; review before reuse |
| [Release](Release/) | PCB renders and enclosure illustration |
| [Firmware](Firmware/) | Availability note; no implementation |

## Next development steps

Resolve the documented electrical findings, synchronize schematic and PCB, run ERC/DRC, regenerate outputs, then build and test a prototype. Define the measurement bandwidth, sampling rate, mechanical mounting and acceptance criteria before claiming vibration-monitoring performance.

## License

MIT. See [LICENSE](LICENSE).
