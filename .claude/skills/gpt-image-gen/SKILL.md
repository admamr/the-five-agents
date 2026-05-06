---
name: gpt-image-gen
description: Use when any agent needs to generate an image via OpenAI Images API (gpt-image-2). Triggers when image generation, visual creation, or picture output is required.
---

# gpt-image-gen

## Overview

Wrapper for OpenAI Images API (`gpt-image-2`). Accepts a text prompt, returns a PNG file saved to a given output path.

## Requirements

- `OPENAI_API_KEY` set in `.env` at project root
- `curl` available (standard on macOS/Linux)
- `jq` for primary decode path, or Python 3 as fallback

## Usage

### Primary path (curl + jq)

```bash
set -a && source .env && set +a
curl -s -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d "{
    \"model\": \"gpt-image-2\",
    \"prompt\": \"<THE PROMPT>\",
    \"size\": \"1024x1024\",
    \"quality\": \"medium\",
    \"output_format\": \"png\"
  }" | jq -r '.data[0].b64_json' | base64 --decode > <OUTPUT_PATH>.png
```

### Python fallback (Git Bash / no jq)

```python
#!/usr/bin/env python3
# Usage: python3 gen.py "prompt text" output.png
import json, base64, os, subprocess, sys

prompt, out_path = sys.argv[1], sys.argv[2]

from dotenv import dotenv_values
env = dotenv_values(".env")
api_key = env.get("OPENAI_API_KEY") or os.environ.get("OPENAI_API_KEY")

import urllib.request
req = urllib.request.Request(
    "https://api.openai.com/v1/images/generations",
    data=json.dumps({
        "model": "gpt-image-2",
        "prompt": prompt,
        "size": "1024x1024",
        "quality": "medium",
        "output_format": "png"
    }).encode(),
    headers={"Authorization": f"Bearer {api_key}", "Content-Type": "application/json"},
    method="POST"
)
resp = json.loads(urllib.request.urlopen(req).read())
with open(out_path, "wb") as f:
    f.write(base64.b64decode(resp["data"][0]["b64_json"]))
print(f"Saved: {out_path}")
```

## Quick Reference

| Parameter | Default | Options |
|---|---|---|
| `model` | `gpt-image-2` | fixed |
| `size` | `1024x1024` | `1024x1024`, `1536x1024`, `1024x1536` |
| `quality` | `medium` | `low`, `medium`, `high` |
| `output_format` | `png` | `png`, `jpeg`, `webp` |

## Common Errors

| Error | Cause | Fix |
|---|---|---|
| `401 Unauthorized` | Missing or invalid API key | Check `OPENAI_API_KEY` in `.env` |
| `400 invalid size` | Unsupported size string | Use values from table above |
| `429 Too Many Requests` | Rate limit / quota exceeded | Wait or check billing |
| Empty file (0 bytes) | `jq` not found, pipe failed silently | Use Python fallback |

## Verification

After generation, always verify:
```bash
test -s <OUTPUT_PATH>.png && echo "OK" || echo "FAILED: file missing or empty"
```
