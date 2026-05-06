# gpt-image-gen Skill

**Canonical definition:** `.claude/skills/gpt-image-gen/SKILL.md`

Calls OpenAI Images API (gpt-image-2). Returns a base64-encoded PNG decoded to a file.

## Requirements

- `OPENAI_API_KEY` set in `.env` at project root
- `curl` + `jq` (or Python 3 as fallback)

## Default parameters

| model | size | quality | format |
|---|---|---|---|
| gpt-image-2 | 1024x1024 | medium | png |
