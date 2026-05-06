---
title: .claude/ Directory
tags:
  - project-file
  - config
  - claude-code
---

# .claude/ Directory

## Overview

ספריית התצורה של Claude Code לפרויקט. מכילה שלוש תת-ספריות שנטענות אוטומטית על-ידי Claude Code:

| תת-ספרייה | תוכן נוכחי | מטרה |
|---|---|---|
| `.claude/agents/` | ריק (`.gitkeep`) | הגדרות agent מותאמות לפרויקט |
| `.claude/skills/` | 17 skills | skills לשימוש Claude |
| `.claude/commands/` | ריק (`.gitkeep`) | slash commands מותאמים |

### Skills מותקנים (17)

**מ-Superpowers v5.1.0 (14):**
`brainstorming` · `dispatching-parallel-agents` · `executing-plans` · `finishing-a-development-branch` · `receiving-code-review` · `requesting-code-review` · `subagent-driven-development` · `systematic-debugging` · `test-driven-development` · `using-git-worktrees` · `using-superpowers` · `verification-before-completion` · `writing-plans` · `writing-skills`

**מותאמים לפרויקט (3):**
`obsidian-bases` · `obsidian-markdown` · `obsidian-vault-workflow`

## מיקום

`/.claude/` — שורש הפרויקט

## Open Questions

- להגדיר agents כאשר הצוות יאוייש
- להוסיף commands מותאמים לפרויקט

## Related

[[claude-md]] | [[obsidian-vault-workflow]] | [[using-superpowers]]
