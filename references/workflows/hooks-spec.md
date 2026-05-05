# Hooks Specification

## Hook Layers

1. workflow-state hooks
2. agent-level hooks
3. gate hooks

## Standard Hooks

| Hook | Layer | Type | Purpose |
|---|---|---|---|
| `on_state_enter` | workflow | soft/hard | prepare context and validate readiness |
| `before_agent_dispatch` | workflow/agent | hard | validate inputs and required skills |
| `after_agent_return` | workflow/agent | hard | validate output bundle and route next action |
| `before_gate` | workflow | hard | gather artifacts before QC |
| `on_gate_fail` | workflow | hard | route to rollback state |
| `before_handoff` | workflow | hard | validate final delivery bundle |
| `on_manual_override` | workflow | soft/hard | record human decision and adjust state |

## State Hook Matrix

| State | Required Hooks |
|---|---|
| `INTAKE` | `on_state_enter`, `before_agent_dispatch`, `after_agent_return` |
| `EVIDENCE_PACK` | `before_agent_dispatch`, `after_agent_return` |
| `CLAIM_MAP` | `after_agent_return` |
| `DRAFTING` | `before_agent_dispatch`, `after_agent_return` |
| `VISUAL_DRAFT` | `on_state_enter`, `after_agent_return` |
| `SCIENTIFIC_QC` | `before_gate`, `on_gate_fail` |
| `VISUAL_QC` | `before_gate`, `on_gate_fail` |
| `POLISH` | `before_agent_dispatch`, `after_agent_return` |
| `FINAL_QC` | `before_gate`, `on_gate_fail`, `before_handoff` |

## Language-Specific Hooks

- `before_agent_dispatch(POLISH)`: load `language-style-policy.md`
- `after_agent_return(polish-agent)`: require `meaning preservation notes`, `style changes`, `remaining ai-like risks`, and `needs source or user confirmation`
- `before_gate(FINAL_QC)`: check generic AI-like phrasing, inflated claims, translationese Chinese, and over-smoothed English template prose
- `before_gate(FINAL_QC)`: when bilingual text is present, check that Chinese and English requirements were applied equally
- `on_gate_fail(FINAL_QC)`: route language failures to `POLISH`

## Figure-Specific Hooks

- `on_state_enter(VISUAL_DRAFT)`: require draft visuals
- `after_agent_return(figure-table-agent)`: require `draft visuals`, `figure-ready data`, `plot spec`, `caption package`
- `before_gate(VISUAL_QC)`: verify figure-text mapping, readability, numbering, and legends
- `on_gate_fail(VISUAL_QC)`: route only to `VISUAL_DRAFT`
