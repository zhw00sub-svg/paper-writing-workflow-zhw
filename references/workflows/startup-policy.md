# Startup Policy

## Purpose

Define how a private manuscript workflow starts when the user input is natural, informal, incomplete, or fragmented.

## Core Assumption

Human startup input may be conversational, generalized, casual, discontinuous, and incomplete. The `master-agent` must turn that input into an executable `task brief` through progressive convergence.

## Startup Modes

| Mode | When Used | Master-Agent Behavior |
|---|---|---|
| conversational startup | user describes the task naturally | capture intent, ask only blocking questions, draft a task brief |
| template startup | user provides structured fields | validate fields, fill gaps, start faster |
| material-driven startup | user points to files or folders | inspect materials, infer current state, ask for missing boundaries |

## Intake Substates

`INTAKE` remains one workflow state, but the `master-agent` should internally run three substages.

| Substate | Purpose | Output |
|---|---|---|
| `INTAKE_CAPTURE` | receive raw oral or informal input | raw intent notes |
| `INTAKE_CONVERGE` | extract goal, materials, gaps, and priority | draft task brief |
| `INTAKE_CONFIRM` | confirm enough information exists to start | executable task brief |

## Minimum Startup Threshold

The workflow may start once these five items are sufficiently known:

1. overall manuscript goal
2. current priority
3. approximate available materials
4. major known gaps
5. likely next agent or workflow state

Information does not need to be perfect. Non-blocking details can be resolved in later states.

## Question Policy

The `master-agent` should ask only questions that block state advancement.

Good questions:

- What is the current priority: manuscript drafting, data interpretation, figure planning, or revision?
- Which materials are already available?
- Is there a target journal or should we proceed journal-neutral?

Avoid:

- long questionnaires before any useful summary
- asking for details that can be inferred from files
- forcing the user to rewrite a casual request into a formal template

## Draft Brief Policy

During multi-turn intake, the `master-agent` may maintain a `draft task brief`. Each new user answer updates the draft until the minimum startup threshold is reached.

## Launch Decision

When the threshold is met, the `master-agent` must:

1. present the executable `task brief`
2. identify the next workflow state
3. list the first subagents to dispatch
4. state any residual assumptions
