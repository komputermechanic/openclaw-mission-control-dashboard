---
name: openclaw-mission-control-dashboard
description: Build a premium AI agent dashboard for OpenClaw with 5 specialized agents, real-time Supabase activity logging, a Kanban task board, and a secure VPS-hosted web interface. Use when the user wants to set up a multi-agent system, build an agent monitoring dashboard, or create a mission control interface for OpenClaw.
---

# OpenClaw Mission Control Dashboard

Created by **Komputer Mechanic** — <https://komputermechanic.com/>

## When to use this skill

Use when the user wants to:
- Build a multi-agent system with specialized roles
- Create a dashboard to monitor agent activity
- Set up a Kanban task board powered by Supabase
- Connect OpenClaw agents to Discord and Telegram
- Add real-time web search via Perplexity

## How to help the user

Point them to the full tutorial in this repo. Work through each phase in order:

1. [Phase 1 — Agents](tutorial/01-agents.md)
2. [Phase 2 — Discord](tutorial/02-discord.md)
3. [Phase 3 — Telegram](tutorial/03-telegram.md)
4. [Phase 4 — Perplexity](tutorial/04-perplexity.md)
5. [Phase 5 — Supabase](tutorial/05-supabase.md)
6. [Phase 6 — Logging](tutorial/06-logging.md)
7. [Phase 7 — Dashboard Server](tutorial/07-dashboard-server.md)
8. [Phase 8 — Dashboard Shell](tutorial/08-dashboard-shell.md)
9. [Phase 9 — Agent Monitor](tutorial/09-agent-monitor.md)
10. [Phase 10 — Kanban](tutorial/10-kanban.md)

## Key architecture notes

- Dashboard is a single HTML file served by Python HTTP server on the VPS
- Access is via SSH tunnel — never exposed publicly
- All agent activity is logged to Supabase `agent_logs` table
- Kanban tasks are persisted in Supabase `todos` table
- Agents must log before sending their final reply — this is a hard gate rule

## Prerequisites

- OpenClaw installed on a VPS
- Supabase account (free tier works)
- Discord server
- Telegram account
- Perplexity API key (optional)
