# gpt-image-gen

## תיאור

מעטפת לקריאת OpenAI Images API (gpt-image-2). מקבל prompt טקסטואלי ומייצר קובץ PNG.

## קובץ

`.claude/skills/gpt-image-gen/SKILL.md`

## דרישות

- `OPENAI_API_KEY` ב-`.env`
- `curl` + `jq` (או Python 3 כ-fallback)

## פרמטרים ברירת מחדל

| פרמטר | ערך |
|---|---|
| model | gpt-image-2 |
| size | 1024x1024 |
| quality | medium |
| output_format | png |

## סוכנים שמשתמשים בסקיל

- **יובל** (`.claude/agents/yuval.md`) — creative agent לייצור תמונות עקביות ויזואלית

## הערות

נוצר: 2026-05-06
