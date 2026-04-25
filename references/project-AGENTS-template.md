# Project Rule Template

Use this as the target project's `AGENTS.md` when the paper workflow should be the default behavior.

## Default Workflow

This project uses the `paper-writing-workflow-zhw` skill as its default manuscript workflow.

## Default Interaction

- The user talks to `master-agent` by default.
- The user may write informally; `master-agent` handles intake convergence.
- `master-agent` owns state transitions and final reporting.

## Subagent Authorization

Default policy:

- `master-agent` may use bounded subagents when the user explicitly allows subagents in the thread.
- If the user says "default allow subagents", then `EVIDENCE_PACK`, `DRAFTING`, `VISUAL_DRAFT`, and QC stages may use subagents as needed.

## Startup

When the user starts a paper task:

1. use conversational, template, or material-driven startup
2. create or update `task brief`
3. identify the active workflow state
4. report status using the standard master status format

## Required Skill

- `paper-writing-workflow-zhw`
