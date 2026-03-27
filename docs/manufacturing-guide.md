# Manufacturing guide

This document summarizes generic ordering steps for two common fabricators and lists typical fabrication outputs for 2-layer boards in this repository.

## Ordering from JLCPCB

| Step | Action |
| --- | --- |
| 1 | Upload the Gerber ZIP for the board revision (see [CONTRIBUTING.md](../CONTRIBUTING.md) for naming). |
| 2 | Confirm layer mapping (signal, mask, silk, outline, drill) in the online preview. |
| 3 | Select board quantity, thickness (typically 1.6 mm unless the design states otherwise), surface finish, and copper weight. |
| 4 | Verify impedance-controlled requirements: not applicable for simple 2-layer digital boards unless noted TBD in the board docs. |
| 5 | Download the fabrication checklist from the board `README.md` or issue tracker if provided. |

Always verify design rules against [JLCPCB capabilities](https://jlcpcb.com/capabilities/pcb-capabilities) before release.

## Ordering from PCBWay

| Step | Action |
| --- | --- |
| 1 | Upload the same Gerber ZIP and any README notes supplied with the release. |
| 2 | Match stackup and finish to the values assumed in the board documentation (TBD if not yet specified). |
| 3 | Review DRC reports from your CAD tool against [PCBWay design rules](https://www.pcbway.com/pcb_prototype.aspx) for the selected service tier. |

## Required Gerber files list

Typical 2-layer set (exact names depend on the CAD exporter):

| File / layer | Role |
| --- | --- |
| Copper top / bottom | Etch layers |
| Soldermask top / bottom | Mask openings |
| Silkscreen top / bottom | Legend |
| Board outline / profile | Routing contour |
| Drill file(s) | Plated holes (Excellon or similar) |
| Optional: paste top / bottom | Stencil generation for SMT assembly |

Include a drill map or netlist only if the fabricator requests it.

## Recommended stackup for 2-layer boards

| Layer | Thickness (typical) | Material | Notes |
| --- | --- | --- | --- |
| L1 (top copper) | TBD | Copper (1 oz default) | <!-- TODO per design --> |
| Core / prepreg | TBD | FR-4 | Standard Tg unless high-temperature operation is specified |
| L2 (bottom copper) | TBD | Copper (1 oz default) | Ground or signal as per design |

Exact stackup should be confirmed in the board fabrication notes when values are no longer TBD.
