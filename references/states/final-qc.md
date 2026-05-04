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
- language authenticity check

## Hooks

- `before_gate`
- `on_gate_fail`
- `before_handoff`

## Failure Routing

- minor failure -> `DRAFTING`
- major failure -> `CLAIM_MAP`

## Language Gate

Before delivery, verify that `references/workflows/language-style-policy.md` has been applied. If the manuscript still contains obvious AI-like boilerplate, inflated claims, translationese Chinese, or generic English academic phrasing, return to `POLISH`.
