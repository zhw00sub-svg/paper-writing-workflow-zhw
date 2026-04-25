# Dependency Manifest

This personal workflow skill is an orchestrator. It does not bundle the professional domain skills it calls during manuscript work. Install the dependencies on each Codex machine where this workflow will be used.

## Required Skills

| Skill | Used For |
|---|---|
| `scientific-writing` | manuscript structure, drafting, polish, figure captions |
| `literature-review` | evidence packs and literature synthesis |
| `research-lookup` | targeted paper lookup and evidence completion |
| `citation-management` | DOI, BibTeX, reference metadata, citation checks |
| `scientific-critical-thinking` | claim strength, overstatement checks, method-risk reasoning |
| `peer-review` | reviewer-style critique and final scientific review |
| `venue-templates` | target journal or venue format constraints |
| `clinical-reports` | clinical framing, endpoint wording, medical context |
| `statistical-analysis` | test selection, statistical reporting logic |
| `statsmodels` | regression and statistical model implementation |
| `seaborn` | draft statistical figures and exploratory visuals |
| `spreadsheet` | figure-ready tables, CSV/XLSX-style handoff data |

## Conditional Skills

| Skill | Trigger |
|---|---|
| `scikit-survival` | survival outcomes such as OS, PFS, DFS, time-to-event endpoints |
| `pydeseq2` | bulk RNA-seq differential expression tasks |
| `scanpy` | single-cell RNA-seq analysis tasks |
| `anndata` | `.h5ad` files or scverse data handling |
| `scikit-learn` | ML pipelines, classifiers, regressors, clustering |

## Degraded Mode

If a required skill is missing, the workflow may still run, but that stage should be marked `PARTIAL` and the `master-agent` should report the missing skill in `risks_or_gaps`.

## Recommended Install Order

1. install `paper-writing-workflow-zhw`
2. install required scientific writing and literature skills
3. install clinical and statistical skills
4. install figure and spreadsheet skills
5. install conditional skills only when a project needs them
