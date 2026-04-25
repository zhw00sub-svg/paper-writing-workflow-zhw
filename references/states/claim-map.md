# State: CLAIM_MAP

## Purpose

Turn evidence and data interpretation into a bounded argument map.

## Primary Agents

- `claim-planner-agent`

## Required Inputs

- `evidence pack`
- `analysis brief`
- target manuscript scope

## Required Outputs

- `claim map`
- section outline
- figure and table mapping

## Hooks

- `after_agent_return`

## Failure Routing

Return to `EVIDENCE_PACK` if claims are unsupported or underspecified.
