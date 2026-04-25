# State: DELIVERED

## Purpose

Package and hand off the approved manuscript outputs.

## Primary Agents

- `master-agent`

## Required Inputs

- all approved outputs
- `final qc report`

## Required Outputs

- delivery bundle
- final status report

## Hooks

- `before_handoff`

## Failure Routing

No forward transition. If delivery bundle is incomplete, return to `FINAL_QC`.
