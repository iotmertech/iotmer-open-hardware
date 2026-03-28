# Smart Dual Power Control

Dual-channel AC relay module with energy measurement, intended for integration with the IOTMER cloud platform.

## Overview

IoT power control board for remote switching and energy monitoring over WiFi. Designed for smart plugs and home appliances.

## Specifications

| Parameter | Value |
|---|---|
| MCU | ESP32-C3-MINI-1 (WiFi + BLE) |
| Energy Metering IC | STPM32TR (SPI interface) |
| AC Input | 220V single phase |
| Max Load Current | 16A |
| Relay | 1x 16A with RC snubber |
| Power Supply | Hi-Link HLK-PM01 (5V isolated AC/DC) |
| LDO | AMS1117-3.3 (5V → 3.3V) |
| Board Size | ~80 x 60 mm |
| Layers | 2-layer, FR4 1.6mm |
| Design Tool | EasyEDA |

## Features

- STPM32TR energy metering: voltage, current, power, energy (kWh)
- 16A relay with transistor driver and flyback protection
- RC snubber for inductive load switching
- AC/DC isolation via Hi-Link module
- Kelvin (4-wire) sensing for accurate shunt measurement
- WiFi connectivity via ESP32-C3
- UART programming header (4-pin: 3V3, GND, TX, RX)
- Boot and Reset buttons for firmware flashing
- MOV surge protection + X2 safety capacitor
- Status LED

## Pinout (ESP32-C3)

| GPIO | Function |
|---|---|
| GPIO4 | SPI MISO (STPM32) |
| GPIO5 | SPI MOSI (STPM32) |
| GPIO6 | SPI CLK (STPM32) |
| GPIO7 | SPI CS (STPM32) |
| GPIO8 | STPM32 EN |
| GPIO0 | STPM32 SYN |
| GPIO10 | Relay control |
| GPIO3 | Status LED |
| GPIO9 | Boot button |

## Energy Measurement

- Voltage sensing: 3x 270kΩ resistive divider from PHASE line
- Current sensing: 4mΩ shunt resistor with Kelvin connection
- Measurement accuracy: < 0.1% over 5000:1 dynamic range (STPM32 spec)
- Supports: RMS voltage, RMS current, active/reactive/apparent power, energy

## AC Safety

- Fuse: 16A 250V slow-blow
- MOV varistor: 275V surge protection
- X2 safety capacitor: 220nF 275VAC
- RC snubber: 100nF 275VAC + 100Ω 1W across relay contacts
- Creepage/clearance: designed per IEC 62368-1 requirements
- AC/DC isolation via Hi-Link module (3kV isolation)

## Directory Structure

```
hardware/
├── schematics/    # Schematic PDF and EasyEDA source
├── pcb/           # Gerber files for manufacturing
├── bom/           # Bill of materials
└── 3d/            # 3D renders of the board
docs/              # Assembly guide and documentation
```

## Manufacturing

- PCB: 2-layer, 1.6mm FR4, HASL or ENIG
- Solder mask: Blue
- Silkscreen: White
- Compatible with JLCPCB / PCBWay assembly

## Status

- [x] Schematic design (v1.1)
- [x] PCB layout
- [x] Gerber files generated
- [ ] Prototype testing
- [ ] Firmware development
- [ ] CE/UKCA compliance testing

## License

See [LICENSE](../../LICENSE) for details.

## Contributing

See [CONTRIBUTING.md](../../CONTRIBUTING.md) for guidelines.
