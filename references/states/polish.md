# State: POLISH

## Purpose

Improve readability, flow, concision, and human academic style without changing scientific meaning.

Apply Chinese and English requirements equally. For bilingual manuscripts or translation tasks, both Chinese and English must be checked against `language-style-policy.md`.

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
- `needs source or user confirmation`

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `DRAFTING` if meaning changes or unsupported claims are introduced.

Return to `POLISH` if the text still shows obvious generic AI-like phrasing, translationese Chinese, or over-smoothed English template prose.

Return to `POLISH` if paragraph-level checks are incomplete or if Chinese requirements are treated as secondary to English requirements.
