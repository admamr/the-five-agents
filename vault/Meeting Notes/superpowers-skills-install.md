# Superpowers Skills Install

## Overview

התקנה ידנית של Superpowers v5.1.0 מ-`https://github.com/obra/superpowers` — clone לתיקייה זמנית, העתקת 14 skills ל-`.claude/skills/`. אין `commands/` או `agents/` במאגר המקור.

## Open Questions

- לשקול עדכון אוטומטי כאשר יוצא גרסה חדשה

## Session Log

### 2026-05-06 — Install Superpowers v5.1.0 [shipped]

- **What was done:** Clone של `obra/superpowers` ל-`/tmp/superpowers`, העתקת 14 skill directories ל-`.claude/skills/` ללא דריסת קבצים קיימים. Commit hash `5ceeff6`.
- **Decisions:** התקנה ידנית (לא `/plugin`) כי מערכת ה-plugins לא זמינה. `cp -r` רק לתיקיות שאינן קיימות.
- **Notes / Caveats:** המאגר לא כולל `commands/` או `agents/` — skills בלבד.
- **Related:** [[claude-directory]], [[using-superpowers]], [[writing-skills]]
