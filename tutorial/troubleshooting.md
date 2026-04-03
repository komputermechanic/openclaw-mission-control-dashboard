# Troubleshooting

[← Phase 10](10-kanban.md) | [← README](../README.md)

> 🎬 **Video tutorial available:** Watch the full walkthrough on YouTube — https://youtu.be/2udlMLtEdcg

---

## Dashboard not loading after running the tunnel

Check whether the server is actually running on the VPS:

```bash
ssh root@YOUR_VPS_IP "systemctl status agent-dashboard.service"
```

---

## Dashboard not updating after Dev makes changes

Hard reload the browser: `Cmd + Shift + R`

If it still shows the old version, send this to Dev:

```
Please verify that your changes were actually saved to /root/.openclaw/workspace/agent-dashboard/index.html and then restart the server: systemctl restart agent-dashboard.service
```

---

## Agent page showing hardcoded fake data

```
The Agents page is displaying hardcoded fake data instead of reading from Supabase. Please remove all hardcoded values completely. If agent_logs has no entries yet for an agent, show "N/A" or "No data yet". Every value on this page must come from a real Supabase query.
```

---

## Agents not logging in real tasks after passing the test

```
Agents are still skipping the Supabase log in real tasks even though the test passed. Please re-enforce the hard gate logging rule for all 5 agents in both SOUL.md and AGENTS.md. The log entry must be written before the agent sends its final reply. Run a real task with Dev and confirm the row appears in Supabase immediately.
```

---

[← Phase 10](10-kanban.md) | [← README](../README.md)
