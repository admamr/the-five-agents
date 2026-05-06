# Project Structure

## Overview

הקמת מבנה הפרויקט הראשוני: אתחול git, יצירת CLAUDE.md, קבצי env, gitignore, וספריית `.claude/` עם תת-ספריות `agents/`, `skills/`, `commands/`.

## Open Questions

- none

## Session Log

### 2026-05-06 — Project bootstrap [shipped]

- **What was done:** אתחול git repo, יצירת CLAUDE.md עם תיאור הפרויקט, `.env` ו-`.env.example` עם `ANTHROPIC_API_KEY` ו-`DEFAULT_MODEL`, `.gitignore` להחרגת `.env`, מבנה `.claude/agents|skills|commands/` עם `.gitkeep`. Push ל-GitHub `admamr/the-five-agents`.
- **Decisions:** `.gitkeep` בתיקיות ריקות כדי שיישמרו ב-git. `.env` מוחרג, `.env.example` ציבורי.
- **Notes / Caveats:** הפרויקט ריק מקוד — רק תשתית.
- **Related:** [[env-config]], [[claude-md]], [[gitignore]], [[claude-directory]]
