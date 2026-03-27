# Contributing

Thank you for contributing to IOTMER Hardware. This document describes how to submit hardware files, branches, commits, and pull requests in a consistent way.

## Hardware files

### Gerber archive naming

- Use a single ZIP archive per board revision.
- Name the archive using lowercase, hyphen-separated tokens: `gerber-<board-name>-v<version>.zip` (example: `gerber-smart-dual-power-control-v0.1.zip`).
- Include all layers and drill files required by your fabricator (typically copper, soldermask, silkscreen, drill, and outline as applicable).

### Bill of materials (BOM)

- Provide BOM as CSV with UTF-8 encoding.
- Required columns: `Reference`, `Value`, `Footprint`, `Quantity`, `Manufacturer`, `Part Number`, `LCSC Part #`, `Notes`.
- One logical line per part or reference group; use `Notes` for alternates, DNP, or assembly instructions.
- Match the schematic reference designators and revision in the PR description.

## Branch naming

Use:

`board/<board-name>/v<version>`

Examples:

- `board/smart-dual-power-control/v0.2`

## Commit messages

Format:

`[<board-name>] <short description>`

Examples:

- `[smart-dual-power-control] add BOM for v0.1`
- `[smart-dual-power-control] update schematic PDF`

Use imperative mood in the description (e.g., “add”, “fix”, “update”).

## File naming

- Use lowercase letters, digits, and hyphens only (`kebab-case`).
- Avoid spaces and special characters in file and directory names.

## Pull request checklist (required files)

Before opening a PR that changes a released revision, ensure the following are included or linked as release artifacts as agreed in the PR:

| Item | Requirement |
| --- | --- |
| Schematic PDF | Exported from the design tool for the same revision as the PR |
| Gerber ZIP | Complete set for fabrication, named per convention above |
| BOM CSV | Matches schematic and uses the column layout in this document |

If any item is intentionally omitted (e.g., documentation-only change), state that explicitly in the PR description.

## Questions

Open an issue using the hardware question template, or refer to [docs/getting-started.md](docs/getting-started.md).
