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
