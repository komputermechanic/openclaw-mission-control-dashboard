# Phase 8 — Building the Dashboard Shell

[← Phase 7](07-dashboard-server.md) | [Next: Phase 9 — Agent Monitor →](09-agent-monitor.md)

With the server running and the connection confirmed, build the actual dashboard shell. This creates the navigation and layout — individual pages are built in the next phases.

---

## Build the Base Dashboard Shell

```
I need you to build a premium single-file dashboard for our Agent OS system.

Save the file as index.html at: /root/.openclaw/workspace/agent-dashboard/

TECH STACK (important — use CDN only, no NPM, no build tools, no framework installation):
- Single HTML file
- Tailwind CSS via CDN
- Chart.js via CDN
- Google Fonts (Inter) via CDN
- Vanilla JavaScript
- Supabase JS SDK via CDN

DESIGN:
- Dark premium SaaS aesthetic (#0A0F1E background)
- Glassmorphism cards with glowing colored gradient borders
- Top navigation bar with pill-shaped active tab indicator
- Page load animations: cards stagger in one by one
- Tab switching with smooth fade transition
- Color scheme: purple to pink gradients (#7C3AED to #EC4899), electric cyan (#06B6D4), amber (#F59E0B)

NAVIGATION TABS:
- Dashboard
- Content
- Agents
- Tasks
- Settings

Supabase URL: YOUR_SUPABASE_URL
Supabase Anon Key: YOUR_SUPABASE_ANON_KEY

Build the full shell with all tabs present but empty content first. Confirm when done.
```

Replace `YOUR_SUPABASE_URL` and `YOUR_SUPABASE_ANON_KEY` with your actual Supabase project values.

---

[← Phase 7](07-dashboard-server.md) | [Next: Phase 9 — Agent Monitor →](09-agent-monitor.md)
