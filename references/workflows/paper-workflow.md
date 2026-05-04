# Paper Workflow Specification

## Architecture

- Pattern: `master-agent + subagents`
- Governance: workflow-driven, not hook-only and not free-form swarm
- State ownership: only `master-agent` may advance or rollback workflow state
- Delivery model: subagent -> master-agent -> user
- Intake model: `INTAKE` is handled directly by the `master-agent`
- Startup model: conversational by default, with template and material-driven alternatives

## Startup Modes

| Mode | Description |
|---|---|
| conversational startup | user starts naturally; master-agent converges over one or more turns |
| template startup | user provides structured startup fields |
| material-driven startup | user points to files or folders and the master-agent infers current state |

## Workflow States

1. `INTAKE`
2. `EVIDENCE_PACK`
3. `CLAIM_MAP`
4. `DRAFTING`
5. `VISUAL_DRAFT`
6. `SCIENTIFIC_QC`
7. `VISUAL_QC`
8. `POLISH`
9. `FINAL_QC`
10. `DELIVERED`

## State Goals

| State | Goal | Main Output |
|---|---|---|
| `INTAKE` | scope the task and define boundaries | `task brief` |
| `EVIDENCE_PACK` | collect literature, data context, and evidence | `evidence pack`, `analysis brief` |
| `CLAIM_MAP` | map claims to evidence and figures | `claim map` |
| `DRAFTING` | produce section drafts | `manuscript draft` |
| `VISUAL_DRAFT` | produce draft visuals and plotting handoff | `draft visuals`, `figure-ready data` |
| `SCIENTIFIC_QC` | test scientific correctness | `scientific qc report` |
| `VISUAL_QC` | test visual clarity and consistency | `visual qc report` |
| `POLISH` | improve expression without changing meaning and reduce generic AI-like language | `polished draft`, `style changes`, `remaining ai-like risks` |
| `FINAL_QC` | final integrated review including language authenticity check | `final qc report` |
| `DELIVERED` | package and hand off artifacts | delivery bundle |

## Parallelism Policy

- Allowed inside `EVIDENCE_PACK`, `DRAFTING`, `VISUAL_DRAFT`, and parts of QC
- Not allowed across final state transitions
- Never allow two subagents to own the same final artifact at the same time

## High-Risk Failure Modes

- claim drift across sections
- unsupported conclusions from clinical data
- citation metadata mismatch
- figure-text inconsistency
- over-polishing that changes scientific meaning
- generic AI-like prose, translationese Chinese, or over-smoothed English academic boilerplate

## Hard Gates

- `SCIENTIFIC_QC`: must verify claims, numbers, citations, and methods
- `VISUAL_QC`: must verify figure-text alignment and readability
- `FINAL_QC`: must verify integrated submission quality and language authenticity using `language-style-policy.md`
