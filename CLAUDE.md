# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**The Five Agents** is a content creation system built around a multi-agent architecture.
A CEO agent acts as the primary orchestrator, managing a team of specialized sub-agents.
The team composition and each agent's role will be defined as the project evolves.

## Project Structure

```
.claude/
├── agents/    # Agent definitions and configurations
├── skills/    # Reusable skills available to agents
└── commands/  # Custom slash commands for this project
```

All agent logic, skills, and custom commands live under `.claude/` and are loaded automatically by Claude Code.

## ניתוב דרך ראובן

**כל משימה חייבת לעבור דרך ראובן (סוכן המנכ"ל). אל תבצע משימות ישירות.**
ראובן מוגדר ב-`.claude/agents/reuven.md` ומנהל את כל הפייפליין (Agent 1 → 2 → 3 → 4).

## Vault (Long-Term Memory)

The project vault at `vault/` is Claude's persistent memory. **Use the `obsidian-vault-workflow` skill at the start and end of every task.**

- `vault/Meeting Notes/` — session logs, architecture decisions, code work
- `vault/Skills/` — documentation for every installed skill
- `vault/Project Files/` — documentation for every config/root file
- `vault/Content Briefs/` — editorial briefs and campaign specs
- `vault/Publishing Log/` — publish runs and post-mortems
- `vault/Brand Guidelines/` — voice, visuals, tone

Start every session: read `vault/Meeting Notes/_index.md` → find the relevant topic file → read it fully before doing any work.
