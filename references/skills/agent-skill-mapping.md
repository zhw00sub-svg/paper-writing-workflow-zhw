# Agent-Skill Mapping

| Agent | Required Skills | Conditional Skills |
|---|---|---|
| `research-agent` | `literature-review`, `research-lookup` | `citation-management` |
| `clinical-analysis-agent` | `clinical-reports`, `statistical-analysis` | `statsmodels`, `scikit-survival` |
| `statistical-analysis-agent` | `statistical-analysis`, `statsmodels` | `scikit-survival` |
| `claim-planner-agent` | `scientific-writing`, `scientific-critical-thinking` | `venue-templates` |
| `writer-agent` | `scientific-writing` | `venue-templates` |
| `citation-factcheck-agent` | `citation-management`, `scientific-critical-thinking` | `peer-review` |
| `figure-table-agent` | `seaborn`, `spreadsheet` | `scientific-writing`, `venue-templates` |
| `standardization-agent` | `scientific-writing`, `venue-templates` | `citation-management` |
| `reviewer-agent` | `peer-review`, `scientific-critical-thinking` | `venue-templates` |
| `polish-agent` | `scientific-writing` | `venue-templates` |

## Policy

- required skills must be checked before dispatch
- conditional skills must be activated when trigger conditions are present
- a workflow state may add mandatory skills on top of agent bindings

## ZHW writing overrides — 2026-11-07

When using `scientific-writing` or `nature-writing-review`, read [the personal argument and language policy](../../language-style-policy.md) first. Its 2026-11-07 requirements govern central claims, paragraph progression, evidence integration and necessary qualifications in Chinese and English. They supersede generic fixed sentence-length targets, vocabulary bans and compulsory transition patterns when those impair complete reasoning. Preserve contrary findings, inferential limits, reporting completeness and verified journal requirements. These are writing preferences, not authorization to dispatch agents.
