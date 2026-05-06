---
title: .gitignore
tags:
  - project-file
  - git
---

# .gitignore

## Overview

מגדיר קבצים שלא יועלו ל-git. כרגע מכיל רק שורה אחת: `.env` — למניעת דליפת API keys וסודות לרפוזיטורי הציבורי.

## מיקום

`/.gitignore` — שורש הפרויקט

## תוכן נוכחי

```
.env
```

## Open Questions

- להרחיב כאשר יתווסף קוד (node_modules, __pycache__, dist, וכו')

## Related

[[env-config]] | [[claude-md]]
