# State: EVIDENCE_PACK

## Purpose

Assemble literature, clinical data context, and citation-ready evidence.

## Primary Agents

- `research-agent`
- `clinical-analysis-agent`

## Required Inputs

- `task brief`
- source papers
- available clinical data context

## Required Outputs

- `evidence pack`
- `analysis brief`
- candidate citation list

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `INTAKE` if evidence is not traceable or materials are missing.
