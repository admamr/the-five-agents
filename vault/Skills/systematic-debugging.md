---
title: Systematic Debugging
tags:
  - skill
  - superpowers
  - debugging
---

# Systematic Debugging

## Overview

Skill לדיבוג שיטתי: מחייב ניתוח וזיהוי root cause לפני הצעת תיקון. כולל כלים להמתנה מבוססת-תנאי, מציאת test polluters, ועקרונות defense-in-depth. מונע תיקונים ניחושיים.

## קבצים משויכים

| קובץ | תפקיד |
|---|---|
| `SKILL.md` | פרוטוקול דיבוג שיטתי |
| `CREATION-LOG.md` | לוג יצירת ה-skill |
| `condition-based-waiting.md` | תבנית המתנה מבוססת-תנאי |
| `condition-based-waiting-example.ts` | דוגמת TypeScript לתבנית |
| `defense-in-depth.md` | עקרון שכבות הגנה בדיבוג |
| `root-cause-tracing.md` | מתודולוגיית מעקב root cause |
| `find-polluter.sh` | סקריפט מציאת test polluter |
| `test-academic.md` | טסט אקדמי של ה-skill |
| `test-pressure-1/2/3.md` | טסטי לחץ בתרחישים שונים |

## מתי להשתמש

כאשר נתקלים ב-bug, כישלון טסט, או התנהגות לא צפויה — לפני הצעת כל תיקון.

## Open Questions

- none

## Related

[[test-driven-development]] | [[verification-before-completion]] | [[receiving-code-review]]
