# State: POLISH

## Purpose

Improve readability, flow, and concision without changing scientific meaning.

## Primary Agents

- `polish-agent`

## Required Inputs

- scientifically approved draft
- visually approved figure package

## Required Outputs

- `polished draft`

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `DRAFTING` if meaning changes or unsupported claims are introduced.
