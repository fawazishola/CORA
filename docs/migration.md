# CORA Migration Notes

This repository is in the middle of a naming and structure normalization pass.

## Naming

The project now uses `CORA` as the primary name:

- `CORA` = Core Operating & Reasoning Appliance

The older name `SIERRA` still appears in some legacy files:

- `SIERRA` = Symbolic Intelligence Engine for Reasoning & Recursive Architecture

Those references are historical, not a sign of a separate project.

## Structure

The repo is now organized into:

- `docs/`
- `hardware/`
- `renders/`
- `sim/`

## Legacy Files

Some filenames still use the older `SIERRA_*` prefix. That is intentional for now to avoid breaking continuity while the repo is still being cleaned up.

The current approach is:

- keep legacy names where they preserve history
- make `CORA` the public-facing name in README and product framing
- rename lower-level artifacts gradually when the structure is stable
