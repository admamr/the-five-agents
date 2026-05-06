# yuval-agent-creation

## Overview

סשן זה הוסיף ליכולות הפרויקט: ייצור תמונות באמצעות OpenAI Images API, עם עקביות ויזואלית מבוססת reference images.

## מה נוצר

### סקיל: gpt-image-gen
- **קובץ:** `.claude/skills/gpt-image-gen/SKILL.md`
- **תפקיד:** מעטפת לקריאת OpenAI Images API (gpt-image-2)
- **קלט:** prompt טקסטואלי + output path
- **פלט:** קובץ PNG ב-1024×1024 (ברירת מחדל medium quality)
- **fallbacks:** curl+jq (ראשי), Python 3 urllib (גיבוי ל-Git Bash)

### סוכן: יובל
- **קובץ:** `.claude/agents/yuval.md`
- **תפקיד:** Creative Agent — ייצור תמונות עם עקביות ויזואלית
- **Workflow 7 שלבים:** scan reference → extract style → build prompt → call API → save PNG+TXT → validate → report
- **תיקיית עבודה:** `yuval/` (reference/, outputs/)

### עדכון ראובן
- נוסף section "סוכנים מיוחדים (On-Demand)" ל-`.claude/agents/reuven.md`
- yuval רשום עם trigger keywords בעברית ואנגלית

### משתני סביבה
- `OPENAI_API_KEY=` נוסף ל-`.env` ול-`.env.example`

## Session Log

**2026-05-06** — יצירת כל הקבצים לעיל, commit + push לענף main.

## החלטות ארכיטקטורה

- `yuval.md` flat ב-`.claude/agents/` (Claude Code מגלה רק flat files)
- `yuval/` בשורש — תיקיית עבודה עם reference/ ו-outputs/
- outputs לא מוגדרים ב-gitignore — committed כברירת מחדל
- Prompt log (sibling .txt) לכל תמונה — לאיטרציה
