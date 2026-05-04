# Language Style Policy

## Purpose

Reduce generic AI-like writing patterns and improve manuscript language so it reads like careful human academic writing. This policy improves style quality; it does not promise or optimize for any detector score.

## Scope

Apply this policy during:

- `DRAFTING`
- `POLISH`
- `FINAL_QC`
- any user-requested rewrite, translation, or bilingual polishing task

## Core Principles

- Preserve scientific meaning, uncertainty, and evidence boundaries.
- Prefer specific, concrete language over broad evaluative phrasing.
- Vary sentence rhythm naturally without adding decorative complexity.
- Keep claims proportionate to the data.
- Remove boilerplate transitions and generic academic filler.
- Make Chinese prose idiomatic, direct, and discipline-appropriate.
- Make English prose precise, restrained, and journal-compatible.

## Common AI-Like Patterns To Remove

| Pattern | Why It Fails | Preferred Direction |
|---|---|---|
| overuse of "important", "significant", "crucial", "notably" | sounds inflated and generic | describe the actual finding or limitation |
| formulaic transitions such as "In conclusion", "It is worth noting that" | creates template-like rhythm | use section-specific transitions only when needed |
| repeated sentence frames | makes prose mechanical | vary clause order and emphasis based on content |
| excessive parallelism | reads like generated text | use natural paragraph flow |
| vague value judgments | weakens scientific authority | anchor judgment to data, method, or comparison |
| inflated certainty | overstates evidence | add appropriate qualifiers and limitations |

## English Manuscript Polish Rules

- Prefer active analytical verbs when they clarify the actor or mechanism.
- Avoid stacking abstract nouns when a direct verb is possible.
- Use cautious verbs for observational clinical data: `was associated with`, `may reflect`, `suggests`, `is consistent with`.
- Avoid repeated high-level openings such as `This study demonstrates`.
- Do not overuse `underscore`, `highlight`, `robust`, `comprehensive`, `novel`, `important`, or `significant` unless statistically or conceptually justified.
- Keep paragraph topic sentences specific to the manuscript, not generic to the field.
- Preserve journal-appropriate concision.

## Chinese Academic Polish Rules

- Avoid translationese and empty connective phrases.
- Avoid overusing: `值得注意的是`, `综上所述`, `进一步`, `显著`, `重要意义`, `提供了新的见解`, `具有重要临床价值`.
- Prefer concise subject-verb-object structure when possible.
- Keep clinical and statistical terms stable across the manuscript.
- Do not use promotional or policy-report style language.
- When translating from English, rewrite into natural Chinese academic prose instead of preserving English sentence order.

## Required Output For Polish Tasks

When the `polish-agent` edits text, it should return:

- `polished_text`
- `meaning_preservation_notes`
- `style_changes`
- `remaining_ai_like_risks`
- `terms_or_claims_not_changed`

## Final QC Language Check

Before delivery, `FINAL_QC` must check:

- repeated template phrases
- inflated claims
- inconsistent terminology
- Chinese translationese if Chinese text is present
- English generic AI-like academic phrasing if English text is present
- whether polishing changed scientific meaning
