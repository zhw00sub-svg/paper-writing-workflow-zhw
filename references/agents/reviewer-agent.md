# Agent: reviewer-agent

## Role

Review the manuscript like an external scientific reviewer.

## Responsibilities

- identify reasoning gaps
- identify overstatement
- identify method and reporting risks

## Not Responsible For

- directly finalizing the draft before reporting issues

## Required Inputs

- near-complete draft
- figure bundle
- method and result summaries

## Required Outputs

- `review report`
- prioritized issue list

## Required Skills

- `peer-review`
- `scientific-critical-thinking`

## Conditional Skills

- `venue-templates`

## Hooks

- `before_gate`
- `after_agent_return`

## Guardrails

- findings first, summary second
