# State: VISUAL_DRAFT

## Purpose

Create figure and table drafts early enough to shape interpretation and writing.

## Primary Agents

- `figure-table-agent`

## Required Inputs

- `claim map`
- `manuscript draft`
- data summaries
- target figure list

## Required Outputs

- `draft visuals`
- `figure-ready data`
- `plot spec`
- `caption package`

## Hooks

- `on_state_enter`
- `after_agent_return`

## Failure Routing

Stay in `VISUAL_DRAFT` until the figure bundle is complete.
