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
- `discussion structure notes` when polishing an English `Discussion`

## Hooks

- `before_agent_dispatch`
- `after_agent_return`

## Failure Routing

Return to `DRAFTING` if meaning changes or unsupported claims are introduced.

Return to `POLISH` if the text still shows obvious generic AI-like phrasing, translationese Chinese, or over-smoothed English template prose.

Return to `POLISH` if paragraph-level checks are incomplete or if Chinese requirements are treated as secondary to English requirements.

Return to `POLISH` if an English `Discussion` does not open with the central interpretation, fails to converge evidence and limitations toward a concise final point, or relies on mechanical paragraph templates.

## Language Review Standard (2026-10-22)

Apply [the bilingual language policy](../../language-style-policy.md) and [English Academic Prose](../english-academic-prose.md). Review each language as continuous prose before checking factual equivalence. Do not infer readability from factual correctness, force equal paragraph structures, or replace necessary explanations with shorter wording. Report the actual sections reviewed; a sample check does not establish full-manuscript approval. Preserve necessary uncertainty while removing repeated paraphrases of the same finding or limitation.
