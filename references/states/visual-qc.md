# State: VISUAL_QC

## Purpose

Test whether figures and tables are readable, correctly labeled, and aligned with the text.

## Primary Agents

- `figure-table-agent`
- `standardization-agent`

## Required Inputs

- `draft visuals`
- `figure-ready data`
- `plot spec`
- `caption package`
- linked text sections

## Required Outputs

- `visual qc report`

## Hooks

- `before_gate`
- `on_gate_fail`

## Failure Routing

Return to `VISUAL_DRAFT`.
