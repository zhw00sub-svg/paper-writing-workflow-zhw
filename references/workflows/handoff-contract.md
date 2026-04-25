# Handoff Contract

## Subagent to Master-Agent

Each subagent must return a structured bundle.

### Required Fields

- `summary`
- `inputs_used`
- `outputs_created`
- `evidence`
- `open_questions`
- `risks_or_limits`
- `recommended_next_action`

### Optional Fields

- `commands_run`
- `files_touched`
- `verdict`

## Master-Agent to User

The `master-agent` reports only distilled status, not raw process logs.

### Required Fields

- `current_state`
- `completed`
- `key_findings`
- `risks_or_gaps`
- `next_action`
- `need_user_decision`

## Artifact Naming

- use kebab-case file names
- use one artifact per file where possible
- include date only when versioning is needed

## Escalation Rules

- if data cannot support a planned claim, escalate before writing stronger language
- if QC fails three times in a row, escalate for manual review
- if figure-text mismatch changes interpretation, escalate before polish
