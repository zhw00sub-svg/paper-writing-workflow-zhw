# State: FINAL_QC

## Purpose

Perform final integrated validation before delivery.

## Primary Agents

- `reviewer-agent`
- `standardization-agent`

## Required Inputs

- `polished draft`
- final figure bundle
- citation set
- prior QC history

## Required Outputs

- `final qc report`

## Hooks

- `before_gate`
- `on_gate_fail`
- `before_handoff`

## Failure Routing

- minor failure -> `DRAFTING`
- major failure -> `CLAIM_MAP`
