# Reuven Agent Creation

## Overview

יצירת ראובן — סוכן המנכ"ל הראשי (CEO Orchestrator) של מערכת The Five Agents. ראובן הוא נקודת הכניסה היחידה למערכת: מקבל משימות מהמשתמש, מנתח, מבקש הבהרות, מאשר תוכנית, מפעיל 4 סוכני משנה בפייפליין טורי קבוע, מדווח בכל שלב, ומטפל בכשלים. לא מבצע משימות בעצמו.

## Open Questions

- להוסיף שמות ותפקידים ל-Agent 1–4 כאשר יוגדרו ב-PRDs נפרדים
- לשקול אם `model: claude-sonnet-4-6` הוא הנכון, או לשדרג ל-Opus להחלטות מורכבות

## Session Log

### 2026-05-06 — Reuven CEO agent v1.0 [shipped]

- **What was done:** יצירת `.claude/agents/reuven.md` לפי PRD v1.0. כולל frontmatter (name, description, tools, model), 5 פרוטוקולים (קבלת משימה, הפעלת סוכן, דיווח, טיפול בכשלים, גבולות תפקיד), מיפוי placeholder ל-agent-1 עד agent-4, 3 דוגמאות תרחישים. עדכון CLAUDE.md עם הוראת ניתוב חובה דרך ראובן.
- **Decisions:** `model: claude-sonnet-4-6` (איזון עלות/יכולת ל-orchestration). סוכני המשנה מוגדרים כ-pending — יוגדרו ב-PRDs נפרדים. שמירת context ב-session window (לא קבצים חיצוניים בשלב זה).
- **Notes / Caveats:** ראובן לא נבדק עדיין עם משימות אמיתיות — יש לבדוק עם mock tasks לפני הוספת הסוכנים. סדר הפייפליין קבוע (טורי) — multi-parallel מחוץ לסקופ.
- **Related:** [[claude-directory]], [[project-structure]], [[superpowers-skills-install]]
