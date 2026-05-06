---
title: Brainstorming Skill
tags:
  - skill
  - superpowers
aliases:
  - visual-brainstorming
---

# Brainstorming

## Overview

Skill לסיעור מוחות ויזואלי שפותח חלון דפדפן נלווה (`localhost`) לצד שיחת Claude. מאפשר ויזואליזציה של רעיונות, דיאגרמות ומפות מחשבה בזמן אמת תוך כדי שיחה. מכיל שרת Node.js מקומי (`scripts/server.cjs`) שמנהל את חלון הדפדפן.

## קבצים משויכים

| קובץ | תפקיד |
|---|---|
| `SKILL.md` | הגדרת ה-skill וההוראות לפעלתו |
| `scripts/server.cjs` | שרת WebSocket מקומי לתקשורת עם הדפדפן |
| `scripts/start-server.sh` | הפעלת השרת |
| `scripts/stop-server.sh` | עצירת השרת |
| `scripts/helper.js` | פונקציות עזר |
| `scripts/frame-template.html` | תבנית HTML לחלון הדפדפן |
| `visual-companion.md` | הוראות שימוש בחלון הנלווה |
| `spec-document-reviewer-prompt.md` | פרומפט לסקירת מסמכי spec |

## מתי להשתמש

כאשר צריך לחקור רעיונות, להמחיש ארכיטקטורה, או לייצר דיאגרמות תוך כדי שיחה.

## Open Questions

- none

## Related

[[dispatching-parallel-agents]] | [[writing-plans]] | [[using-superpowers]]
