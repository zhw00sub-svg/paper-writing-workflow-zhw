---
name: paper-writing-workflow-zhw
description: Use this personal skill for ZHW's scientific manuscript writing projects that need the established private master-agent workflow: conversational intake, master-agent plus bounded subagents, clinical/statistical analysis, literature evidence packs, claim maps, drafting, figure/table draft visuals, scientific QC, visual QC, polish, and final delivery. Trigger when the user asks to start, continue, structure, review, or standardize a research paper, clinical manuscript, figure package, or paper-writing project using this personal workflow.
---

# Paper Writing Workflow ZHW

Use this skill to run ZHW's private manuscript workflow.

## Default Interaction

- Treat the current conversation as the `master-agent` channel.
- The user talks to the `master-agent` by default; do not require `@master-agent`.
- Use subagents only when the user explicitly allows subagents or when the active project rules already authorize them.
- When subagents are used, route all outputs back through the `master-agent`.

## Startup

Read `references/workflows/startup-policy.md` when starting a new manuscript task.

Default startup is conversational:

1. accept informal, fragmented, or oral-style user input
2. run `INTAKE_CAPTURE`, `INTAKE_CONVERGE`, then `INTAKE_CONFIRM`
3. ask only questions that block workflow progress
4. create an executable `task brief`
5. identify the next workflow state

Also support:

- template startup when the user provides structured fields
- material-driven startup when the user points to files or folders

## Core Workflow

Read these files when needed:

- `references/workflows/paper-workflow.md` for the overall workflow
- `references/workflows/state-machine.md` for state transitions and rollbacks
- `references/workflows/hooks-spec.md` for hooks and QC gates
- `references/workflows/handoff-contract.md` for subagent and user-facing report formats
- `references/skills/agent-skill-mapping.md` for required and conditional skills

The main states are:

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

## Agent Contracts

Read only the relevant agent contract from `references/agents/` before dispatching or simulating that role.

Key contracts:

- `master-agent.md`
- `research-agent.md`
- `clinical-analysis-agent.md`
- `statistical-analysis-agent.md`
- `claim-planner-agent.md`
- `writer-agent.md`
- `citation-factcheck-agent.md`
- `figure-table-agent.md`
- `standardization-agent.md`
- `reviewer-agent.md`
- `polish-agent.md`

## Figure Policy

Figures and tables are first-class scientific artifacts.

When a task enters `VISUAL_DRAFT`, require:

- draft visuals
- figure-ready data
- plot specification
- caption package
- notes for final human plotting in SPSS, R, or Prism

Do not treat figure work as an end-of-project decoration step.

## Reporting Format

When reporting workflow status to the user, use this shape unless the user asks otherwise:

```text
current_state:
completed:
key_findings:
risks_or_gaps:
next_action:
need_user_decision:
```

## Guardrails

- `master-agent` is the only state owner.
- `INTAKE` is executed by `master-agent`, not a separate intake agent.
- `SCIENTIFIC_QC`, `VISUAL_QC`, and `FINAL_QC` are hard gates.
- Do not skip `VISUAL_DRAFT` or `VISUAL_QC` when figures matter to the manuscript.
- Do not let a writing agent invent unsupported claims.
- Clinical data interpretation belongs to `clinical-analysis-agent`; formal statistical logic belongs to `statistical-analysis-agent`.
