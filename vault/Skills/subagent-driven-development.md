---
title: Subagent-Driven Development
tags:
  - skill
  - superpowers
  - agents
---

# Subagent-Driven Development

## Overview

Skill לביצוע תכניות מימוש באמצעות sub-agents בסשן הנוכחי. כולל שלושה פרומפטים נפרדים: `spec-reviewer`, `implementer`, `code-quality-reviewer` — כל אחד מבצע תפקיד מוגדר. מיועד לביצוע מקביל של משימות עצמאיות מתוך תכנית.

## קבצים משויכים

| קובץ | תפקיד |
|---|---|
| `SKILL.md` | פרוטוקול פיתוח מונע sub-agents |
| `spec-reviewer-prompt.md` | פרומפט לסקירת מפרט |
| `implementer-prompt.md` | פרומפט למימוש |
| `code-quality-reviewer-prompt.md` | פרומפט לבדיקת איכות קוד |

## מתי להשתמש

כאשר יש תכנית מימוש עם משימות עצמאיות שאפשר לבצע במקביל בסשן הנוכחי.

## Open Questions

- none

## Related

[[dispatching-parallel-agents]] | [[executing-plans]] | [[requesting-code-review]] | [[using-git-worktrees]]
