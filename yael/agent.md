# Yael — Content Writer Agent

**Canonical definition:** `.claude/agents/yael.md`

## How to use

יעל משכתבת מאמרי גלם מ-`Content/` לסגנון הפרויקט. ראובן (CEO) מפעיל אותה עם path מפורש למאמר. יעל לא בוחרת קבצים בעצמה ולא יכולה להפעיל סוכנים אחרים.

## Tools

`Read, Write, Edit, Glob, Grep` — סוכנת LLM-only. אין Bash, אין WebSearch, אין Task.

## Directory structure

```
yael/
├── style-guide.md     ← מדריך הסגנון (חובה לקרוא בתחילת סשן)
├── reference/         ← דוגמאות לטקסטים בסגנון הפרויקט
└── agent.md           ← הקובץ הזה

Content/               ← מאמרי גלם (input)
└── Ready/             ← ארכיון מאמרים שעובדו

Output/                ← תוצרים משוכתבים (לאחר השלמת תמונות בידי ראובן)
```

## Style context

- `style-guide.md` — מדריך הסגנון (חובה)
- `reference/` — דוגמאות בסגנון הפרויקט (אופציונלי)

יעל טוענת את שניהם פעם אחת בכל סשן.

## Image placeholders

יעל לא יכולה להפעיל את יובל ישירות (סאב-אייג'נטים ב-Claude Code לא מפעילים סאב-אייג'נטים אחרים). כשהיא מזהה צורך בתמונה היא משאירה:

```
{{IMAGE_NEEDED: "<English description, prompt-ready for Yuval>"}}
```

ראובן הוא זה שעובר על ה-placeholders, מפעיל את יובל לכל אחד, ומחליף אותם ב-markdown image references בגרסה הסופית ב-`Output/`.

## Flow summary

1. ראובן מעביר ל-יעל path ב-`Content/<name>.md`
2. יעל קוראת style-guide + reference (פעם בסשן)
3. יעל משכתבת ושומרת ב-`Output/<name>.md` (עם IMAGE_NEEDED placeholders)
4. יעל מעתיקה את המקור ל-`Content/Ready/<name>.md` (ראובן ימחק את המקור)
5. יעל מחזירה לראובן דוח עם רשימת ה-placeholders
6. ראובן מפעיל את יובל לכל placeholder ומחליף בגרסה הסופית
