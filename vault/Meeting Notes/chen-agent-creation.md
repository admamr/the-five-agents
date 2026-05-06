# Chen Agent Creation

## Overview

יצירת חן — סוכנת חוקרת רשת עם WebSearch+WebFetch. תפקידה לקבל בקשות מראובן, לחפש מקורות אמינים ברשת, לסנן לפי קריטריוני איכות קבועים, ולהשאיר את הממצאים ב-`Content/` כקלט ליעל (או להחזיר למשתמש בלי שכתוב, לפי הבקשה). כוללת מנגנון זיכרון (`chen/Memory/searches.md`) שמונע חיפושים כפולים תוך 30 יום.

הסוכנת נוספה כ-**on-demand agent** בראובן — לא חלק מהפייפליין הקבוע (Agent 1–4), אלא מופעלת לפי trigger keywords (חפש, מצא, מחקר, search, find, research, וכד').

## Open Questions

- האם להוסיף בעתיד פלטפורמות חיפוש ייעודיות (Google Scholar, arXiv, PubMed)?
- האם להגדיר רף איכות מינימלי שחן **אסור** לה לרדת ממנו גם אם ראובן מבקש?
- האם לאפשר לחן לאסוף כמה מקורות (multi-source) ולא רק primary אחד?

## Session Log

### 2026-05-06 — Chen v1.0 [shipped]

- **What was done:** נוצר `.claude/agents/chen.md` (frontmatter: `name: chen`, `tools: WebSearch, WebFetch, Read, Write, Edit, Glob, Grep`, `model: claude-sonnet-4-6`). כולל: 7 חוקי ברזל, Workflow בן 9 שלבים (עם בדיקת זיכרון בשלב 2-3), קריטריוני איכות מפורטים, פורמט קבוע לקובץ ב-Content/, פורמט Memory entry, 3 מצבי Handback (הצליח / hit בזיכרון / נכשל). נוצרה תיקיית `chen/` עם `Memory/searches.md` (seed עם הסבר פורמט) ו-`agent.md` (pointer doc). עודכן ראובן: שורה חדשה בטבלת on-demand + בלוק פרוטוקול עם ההחלטה "מחקר בלבד → עצור / מחקר + שכתוב → המשך ליעל אוטומטית".
- **Decisions:** `claude-sonnet-4-6` — עקביות עם yael/yuval ושיקול דעת מספיק לסינון איכות. מיקום on-demand (לא pipeline) — חן מופעלת לפי דרישה ספציפית, לא בכל פייפליין. פורמט Memory hit flow: חן עוצרת תמיד, ראובן מחליט ומעביר למשתמש.
- **Notes / Caveats:** חן לא יכולה להפעיל את יעל ישירות — ראובן הוא זה שמחליט ומחבר. אם WebFetch נחסם על מקור מסוים (paywall, captcha) — מדלגים ומנסים מקור אחר; אם כולם חסומים → מצב 3 (נכשל).
- **Related:** [[reuven-agent-creation]], [[yael-agent-creation]], [[yuval-agent-creation]]
