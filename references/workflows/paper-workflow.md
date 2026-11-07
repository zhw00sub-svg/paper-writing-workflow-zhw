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

## 2026-11-07 论证推进检查并入现有工作流

- CLAIM_MAP：用一句话记录研究问题和结果允许的中心回答；区分直接发现、解释与待验证方向，纳入相反结果和未解决问题，不另建状态机。
- DRAFTING：段落功能提纲同时标注新增认识、证据位置与前段关系。原始研究、综述和Methods采用各自适当结构，不为叙事牺牲报告完整性。
- POLISH：先连续检查中心论点和段落推进，再合并重复限定，最后复核推断强度。逐段问“这一段让读者比上一段多理解了什么”。没有新增认识时合并或重写，必要定义及可复现细节除外。
- SCIENTIFIC_QC/FINAL_QC：检查增强行文力度后是否隐去不利结果、放大因果或临床效用；任何证据与结论变化返回原有科学核验流程。此补充是现有gate的判据，不自动代表通过。
