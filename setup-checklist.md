# Setup Checklist

Use this checklist when setting up `paper-writing-workflow-zhw` on another computer.

## Install Workflow Skill

Clone this repository into the Codex skills directory:

```bash
mkdir -p ~/.codex/skills
git clone <repo-url> ~/.codex/skills/paper-writing-workflow-zhw
```

## Check Required Skills

Confirm these skills exist on the target computer:

- `scientific-writing`
- `literature-review`
- `research-lookup`
- `citation-management`
- `scientific-critical-thinking`
- `peer-review`
- `venue-templates`
- `clinical-reports`
- `statistical-analysis`
- `statsmodels`
- `seaborn`
- `spreadsheet`

Install any missing required skills before relying on full workflow behavior.

## Add Project Rule

For each paper-writing project, place the content from:

```text
references/project-AGENTS-template.md
```

into the project root `AGENTS.md`, then adjust project-specific notes if needed.

## Smoke Test Prompt

Use this prompt in the target project:

```text
启动论文工作流：按当前项目开始，先进入 INTAKE，判断当前状态和材料缺口。默认允许按需调用 subagents。
```

Expected behavior:

- `master-agent` treats the conversation as the main channel
- `INTAKE` is performed by `master-agent`
- a draft or executable `task brief` is produced
- missing required materials or missing skills are reported
