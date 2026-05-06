# yael-agent-creation

## Overview

סשן זה הוסיף ליכולות הפרויקט: סוכנת LLM-only לשכתוב מאמרי גלם בסגנון הפרויקט, עם תמיכה בזיהוי צורך בתמונות דרך IMAGE_NEEDED placeholders. ראובן עודכן לטפל ב-handoff בין יעל ליובל (כי סאב-אייג'נטים ב-Claude Code לא מפעילים סאב-אייג'נטים אחרים).

## מה נוצר

### סוכנת: יעל
- **קובץ:** `.claude/agents/yael.md`
- **תפקיד:** Content Writer — שכתוב/עריכת מאמרים בסגנון הפרויקט
- **Tools:** `Read, Write, Edit, Glob, Grep` בלבד — סוכנת LLM-only (אין Bash, אין Task, אין WebSearch/Fetch)
- **Workflow 7 שלבים:** קבלת path → טעינת style context (פעם בסשן) → קריאת המקור → שכתוב → IMAGE_NEEDED placeholders → שמירה ב-Output → העתקה ל-Ready
- **תיקיית עבודה:** `yael/` (style-guide.md, reference/, agent.md)

### תיקיות שורש חדשות
- `Content/` — input של מאמרי גלם
- `Content/Ready/` — ארכיון מאמרים שעובדו
- `Output/` — תוצרים סופיים (לאחר השלמת תמונות בידי ראובן)

### עדכון ראובן
- שורה חדשה ל-yael בטבלת "סוכנים מיוחדים (On-Demand)" ב-`.claude/agents/reuven.md`
- פרוטוקול חדש: "כשלקוח מבקש שכתוב/עריכת מאמר" — כולל הטיפול ב-IMAGE_NEEDED placeholders (ראובן מפעיל את יובל לכל placeholder ומחליף ב-markdown image refs ב-Output/)
- מחיקת המקור מ-`Content/` היא באחריות ראובן (יעל לא יכולה — אין לה Bash)

## Session Log

**2026-05-06** — יצירת כל הקבצים לעיל, עדכון ראובן, commit + push לענף main.

## החלטות ארכיטקטורה

### למה יעל היא LLM-only
החלטה מודעת לצמצם את הסוכנת רק לפעולות טקסט מקומיות. בלי Bash/Task/Web — מצמצם attack surface ומונע מצב שבו הסוכנת מנסה לעשות משהו שהיא לא צריכה (למשל לחפש מידע באינטרנט במקום להישאר נאמנה למקור).

### למה IMAGE_NEEDED placeholders ולא קריאה ישירה ליובל
ב-Claude Code סאב-אייג'נטים לא יכולים להפעיל סאב-אייג'נטים אחרים — רק ראובן (Top-level orchestrator) יכול. הפתרון: יעל מתעדת את ה-prompt בתוך המאמר, ראובן עובר עליהם בשלב נפרד ומפעיל את יובל. זה גם נותן לראובן ביקורת על איכות ה-prompts לפני יצירת תמונות.

### למה יעל לא מוחקת את המקור מ-Content/
אין לה Bash. הפתרון: יעל יוצרת עותק ב-`Content/Ready/<name>.md`, ראובן מוחק את `Content/<name>.md` בשלב הסיום של הפרוטוקול שלו (אחרי שכל התמונות הוחלפו בהצלחה). זה גם משאיר את המחיקה כפעולה "סיום עסקה" — רק אם הכל הצליח.

### למה Output/ ב-overwrite ולא בקובץ נפרד
התשובה הפשוטה: רק תוצר אחד באמת רלוונטי — הסופי. הגרסה עם placeholders היא אחת ביניים שלא צריך לשמור. אם תהיה בעיה — git history נותן את ההיסטוריה.

### דפוסים שעקבנו אחריהם
- YAML frontmatter תואם בדיוק את `.claude/agents/yuval.md:1-6`
- מבנה סעיפים תואם yuval.md (הזהות → חוקי ברזל → Workflow מנומר → דוח → גבולות → מבנה תיקיות)
- פורמט הטבלה ב-reuven.md תואם בדיוק (4 עמודות, אותו seperator)
- pointer doc ב-`yael/agent.md` תואם פורמט `yuval/agent.md`
