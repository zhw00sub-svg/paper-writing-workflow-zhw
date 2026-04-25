# State: SCIENTIFIC_QC

## Purpose

Test whether claims, numbers, methods, and citations are scientifically defensible.

## Primary Agents

- `citation-factcheck-agent`
- `reviewer-agent`

## Required Inputs

- `manuscript draft`
- citation set
- data-derived summaries
- `draft visuals`

## Required Outputs

- `scientific qc report`

## Hooks

- `before_gate`
- `on_gate_fail`

## Failure Routing

Return to `DRAFTING`.
