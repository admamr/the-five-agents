---
title: Environment Config (.env / .env.example)
tags:
  - project-file
  - config
  - secrets
---

# Environment Config

## Overview

שני קבצים מנהלים את משתני הסביבה של הפרויקט:
- **`.env`** — ערכים אמיתיים, **לא עולה ל-git** (מוגן ב-`.gitignore`)
- **`.env.example`** — תבנית ציבורית עם ערכים placeholder, עולה ל-git

### משתנים נוכחיים

| משתנה | תיאור |
|---|---|
| `ANTHROPIC_API_KEY` | מפתח ה-API לשירותי Anthropic/Claude |
| `DEFAULT_MODEL` | מודל Claude ברירת-מחדל (`claude-opus-4-7`) |

## מיקום

- `/.env` — מקומי בלבד
- `/.env.example` — ב-git

## Open Questions

- להוסיף משתנים נוספים כאשר יוגדרו agents עם כלים חיצוניים

## Related

[[gitignore]] | [[claude-md]] | [[claude-directory]]
