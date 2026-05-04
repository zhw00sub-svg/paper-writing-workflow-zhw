# State: POLISH

## Purpose

Improve readability, flow, concision, and human academic style without changing scientific meaning.

## Primary Agents

- `polish-agent`

## Required Inputs

- scientifically approved draft
- visually approved figure package

## Required Outputs

- `polished draft`
- `meaning preservation notes`
- `style changes`
- `remaining ai-like risks`

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `DRAFTING` if meaning changes or unsupported claims are introduced.

Return to `POLISH` if the text still shows obvious generic AI-like phrasing, translationese Chinese, or over-smoothed English template prose.
