# Phase 9 — Building the Agent Monitor Page

[← Phase 8](08-dashboard-shell.md) | [Next: Phase 10 — Kanban →](10-kanban.md)

> 🎬 **Video tutorial available:** Watch the full walkthrough on YouTube — https://youtu.be/2udlMLtEdcg

Build the Agents tab — a real-time view of all 5 agents pulling live data from the `agent_logs` Supabase table.

---

## Build the Agent Monitor

```
I need you to build the Agents tab in the dashboard. This page will show real-time information about all 5 agents by reading from our Supabase agent_logs table.

Context: We have a Supabase table called agent_logs where every agent writes an entry after completing a task. The columns are: agent_name, task_description, model_used, status, created_at.

The page should have no hardcoded fake data anywhere.

AGENT CARDS (one per agent: Alex, Maya, Jordan, Dev, Sam):
- Agent emoji + name bold
- Role subtitle: Alex "Research Analyst", Maya "Content Writer", Jordan "Marketing Strategist", Dev "Full Stack Developer", Sam "Social Media Manager"
- Status: "Connected" with green dot
- Model: read from most recent agent_logs entry
- Last task: most recent task_description
- Last active: timestamp of most recent log entry
- Tasks today: count of today's entries
- Unique glow color per agent: Alex blue, Maya purple, Jordan amber, Dev green, Sam pink

RECENT ACTIVITY FEED:
- Fetch last 50 entries from agent_logs ordered by created_at descending
- Each row: colored agent badge, timestamp, task description, model used, status badge

TASK STATISTICS: Total tasks today, this week, most active agent, success rate

MODEL USAGE TRACKER: Table with Agent, Model, Tasks Today — all from agent_logs

Please update index.html and confirm when done.
```

---

[← Phase 8](08-dashboard-shell.md) | [Next: Phase 10 — Kanban →](10-kanban.md)
