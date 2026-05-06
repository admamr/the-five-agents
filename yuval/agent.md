# Yuval — Creative Image Agent

**Canonical definition:** `.claude/agents/yuval.md`
**Skill used:** `.claude/skills/gpt-image-gen/SKILL.md`

## How to use

Place reference images (PNG/JPG) in `reference/` — Yuval will analyze their style,
color palette, and composition before generating anything.

Generated images land in `outputs/` as `YYYY-MM-DD-<slug>.png`,
with a sibling `.txt` file containing the exact prompt used (for iteration).

## Directory structure

```
yuval/
├── reference/   ← drop style reference images here
├── outputs/     ← generated images + prompt logs
├── agent.md     ← this file
└── skill.md     ← notes on the gpt-image-gen skill
```
