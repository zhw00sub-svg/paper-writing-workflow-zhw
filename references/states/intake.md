# State: INTAKE

## Purpose

Define manuscript scope, target, available materials, and missing dependencies.

`INTAKE` is a convergence process, not a one-shot form. User input may be informal, incomplete, or discontinuous.

## Primary Agents

- `master-agent`

## Entry Criteria

- a new manuscript task is proposed conversationally, through a template, or by pointing to materials

## Required Inputs

- research objective
- target venue if known
- available materials
- known data boundaries

## Required Outputs

- `task brief`
- missing materials list
- delivery goal

## Internal Substates

- `INTAKE_CAPTURE`
- `INTAKE_CONVERGE`
- `INTAKE_CONFIRM`

## Minimum Startup Threshold

- overall manuscript goal is known
- current priority is known
- approximate available materials are known
- major known gaps are known
- likely next agent or state is known

## Hooks

- `on_state_enter`
- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Do not advance until the task brief is complete.
