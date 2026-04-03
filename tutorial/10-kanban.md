# Phase 10 — Building the Kanban Tasks Page

[← Phase 9](09-agent-monitor.md) | [Troubleshooting →](troubleshooting.md)

> 🎬 **Video tutorial available:** Watch the full walkthrough on YouTube — https://youtu.be/2udlMLtEdcg

Build the Tasks tab — a full Kanban board with drag and drop, powered by the `todos` Supabase table.

---

## Build the Kanban Board

```
I need you to build the Tasks tab as a full dedicated Kanban board page.

Context: Supabase table "todos" with columns: id, title, category, priority, due_date, completed, status (todo/in_progress/done), track_status (On Track/At Risk/Off Track), created_at.

PRODUCTIVITY OVERVIEW BAR at the top with a donut chart, stat cards, and motivational message.

KANBAN BOARD: Three columns — To Do, Doing, Done — with full drag and drop between columns. Status updates to Supabase immediately on drop.

CARD DESIGN: Dark background, checkbox, bold title, colored pill badges for category/priority/track status, due date, three dot menu for Edit and Delete.

ADD TASK: Inline form in each column with title, category, priority, track status, and due date fields.

EDIT TASK: Modal pre-filled with current values, saves to Supabase on confirm.

Please update index.html and confirm when done.
```

---

[← Phase 9](09-agent-monitor.md) | [Troubleshooting →](troubleshooting.md)
