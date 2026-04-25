# State: DRAFTING

## Purpose

Produce section-level manuscript drafts from the approved claim map.

## Primary Agents

- `writer-agent`

## Required Inputs

- `claim map`
- `evidence pack`
- `analysis brief`
- venue constraints if known

## Required Outputs

- `manuscript draft`

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `CLAIM_MAP` if the draft exceeds evidence boundaries.
