# Smart Dual Power Control

Dual-channel AC relay module with energy measurement, intended for integration with the IOTMER cloud platform.

## Features

- Dual-channel AC relay outputs
- Energy metering with STMicro **STPM32TR** (shunt-based current sensing, AC voltage dividers)
- Wi-Fi via **Espressif ESP32-C3-MINI-1-H4**
- Isolated low-voltage supply via **HLK-5M05** module (confirm footprint matches the selected module in CAD)
- Design assumptions for IOTMER cloud connectivity are documented in firmware repositories when available (TBD)

## Specifications

| Parameter | Value | Notes |
| --- | --- | --- |
| Supply voltage | TBD | <!-- TODO --> |
| Relay rating (per channel) | TBD | <!-- TODO --> |
| Measurement accuracy | TBD | <!-- TODO --> |
| MCU | ESP32-C3-MINI-1-H4 | 2.4 GHz Wi-Fi |
| Energy metering IC | STPM32TR | VQFN-24; interface to MCU per ST datasheet |
| PCB dimensions | TBD | <!-- TODO --> |
| Operating temperature | TBD | See [docs/specifications.md](docs/specifications.md) |

## Hardware files

| Path | Contents |
| --- | --- |
| [hardware/schematics/schematic-smart-dual-power-control-2026-03-27.pdf](hardware/schematics/schematic-smart-dual-power-control-2026-03-27.pdf) | Schematic PDF |
| [hardware/bom/bom-smart-dual-power-control-2026-03-27.csv](hardware/bom/bom-smart-dual-power-control-2026-03-27.csv) | BOM export (tab-separated; supplier part columns) |
| [hardware/bom/BOM_TEMPLATE.csv](hardware/bom/BOM_TEMPLATE.csv) | Target column layout for future normalized BOMs |
| [hardware/pcb/](hardware/pcb/) | Layout sources and Gerber ZIP (TBD) |
| [hardware/3d/](hardware/3d/) | Mechanical STEP and enclosure references (TBD) |
| [docs/pinout.md](docs/pinout.md) | Connector and test point pinout |
| [docs/specifications.md](docs/specifications.md) | Electrical, mechanical, environmental placeholders |

## Manufacturing

Gerber and drill files produced from this design are intended to be compatible with common online PCB services such as [JLCPCB](https://jlcpcb.com/) and [PCBWay](https://www.pcbway.com/) when exported using standard 2-layer rules. Always verify layer stackup, copper weights, and board finish against the fabricator’s process limits before ordering.

## License

Covered hardware design materials in this directory are licensed under **CERN-OHL-S v2**. See the repository [LICENSE](../../LICENSE).
