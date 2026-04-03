# OpenClaw Mission Control Dashboard

Created by **Komputer Mechanic** — <https://komputermechanic.com/>

> Watch the full video tutorial on YouTube: <https://www.youtube.com/watch?v=2udlMLtEdcg>

Build a fully operational AI agent system with a premium SaaS-style dashboard — 5 specialized agents, real-time activity monitoring, a drag-and-drop Kanban board, and a Content CRM, all running on your own VPS.

---

## What You Will Build

| Feature | Description |
|---------|-------------|
| 5 Specialized AI Agents | Research, content, marketing, development, and social media |
| Agent Activity Monitor | Real-time agent status, model usage, and task logs from Supabase |
| Kanban Task Board | Drag and drop with productivity charts and Supabase persistence |
| Content CRM | Connected to Supabase |
| Content Feed | Connected to Notion |

> Throughout this tutorial the example uses a fictional brand called **Agent OS** and five fictional agents. Replace the brand name, agent names, niches, and descriptions with whatever fits your own project.

---

## What You Will Need

- A VPS with OpenClaw installed — [grab one here](https://komputermechanic.com/go/openclaw-vps)
- A Supabase account (free tier works)
- A Discord server
- A Telegram account
- A Perplexity API key (optional but recommended)

---

## Tutorial Phases

| Phase | File | Description |
|-------|------|-------------|
| 1 | [01-agents.md](tutorial/01-agents.md) | Create 5 agents, set up memory, router, and content pipeline |
| 2 | [02-discord.md](tutorial/02-discord.md) | Connect each agent to a dedicated Discord channel |
| 3 | [03-telegram.md](tutorial/03-telegram.md) | Set up Telegram as your main orchestrator |
| 4 | [04-perplexity.md](tutorial/04-perplexity.md) | Add real-time web search via Perplexity |
| 5 | [05-supabase.md](tutorial/05-supabase.md) | Create the Supabase tables that power the dashboard |
| 6 | [06-logging.md](tutorial/06-logging.md) | Make agents log their activity to Supabase |
| 7 | [07-dashboard-server.md](tutorial/07-dashboard-server.md) | Set up the dashboard web server on your VPS |
| 8 | [08-dashboard-shell.md](tutorial/08-dashboard-shell.md) | Build the base dashboard shell |
| 9 | [09-agent-monitor.md](tutorial/09-agent-monitor.md) | Build the Agent Monitor page |
| 10 | [10-kanban.md](tutorial/10-kanban.md) | Build the Kanban Tasks page |
| — | [troubleshooting.md](tutorial/troubleshooting.md) | Common issues and fixes |

---

## Quick Start

Work through the phases in order. Each phase builds on the previous one.

1. Complete all 10 phases in sequence
2. Test each phase before moving to the next
3. Replace all placeholder values (`YOUR_VPS_IP`, `YOUR_SUPABASE_URL`, etc.) with your own

---

## Tech Stack

| Layer | Technology |
|-------|-----------|
| Agents | OpenClaw |
| Database | Supabase (PostgreSQL) |
| Messaging | Discord + Telegram |
| Search | Perplexity API |
| Dashboard | Single HTML file — Tailwind CSS, Chart.js, Supabase JS SDK (all via CDN) |
| Server | Python HTTP server on VPS via systemd |
| Access | SSH tunnel + one-click desktop launcher |
