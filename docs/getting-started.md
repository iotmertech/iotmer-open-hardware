# Getting started

## Repository structure

| Path | Purpose |
| --- | --- |
| `boards/` | One subdirectory per board product; each contains `hardware/`, `docs/`, and board-level `README.md` |
| `boards/<name>/hardware/` | Schematics, PCB sources, BOM, and mechanical exports |
| `boards/<name>/docs/` | Pinout, specifications, and figures |
| `docs/` | Repository-wide guides (this file, manufacturing) |
| `tools/` | Scripts and utilities shared across boards (TBD) |
| `.github/` | Issue forms and pull request template |

## How to find a board

1. Open the root [README.md](../README.md) table for a summary of published boards.
2. Enter the board folder under `boards/<board-name>/` for the board `README.md`, hardware paths, and changelog.

## How to order PCBs

1. Locate or generate Gerber and drill archives for the target revision in `boards/<board-name>/hardware/pcb/` (or linked release artifacts).
2. Follow [manufacturing-guide.md](manufacturing-guide.md) for JLCPCB and PCBWay-oriented checks.
3. Cross-check the BOM in `hardware/bom/` against the schematic revision before assembly.

## How to contribute

Read [CONTRIBUTING.md](../CONTRIBUTING.md) for branch names, commit message format, Gerber naming, BOM columns, and the required-files checklist for pull requests.
