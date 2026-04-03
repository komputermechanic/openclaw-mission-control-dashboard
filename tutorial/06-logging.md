# Phase 6 — Making Agents Log Their Activity

[← Phase 5](05-supabase.md) | [Next: Phase 7 — Dashboard Server →](07-dashboard-server.md)

Now we tell agents to write a log entry to Supabase every time they finish a task. This is what makes the Agent Monitor page show real live data instead of empty placeholders.

---

## Step 1 — Tell the Orchestrator to Enforce Logging

Give the orchestrator full context about Supabase before asking it to do anything.

```
I want to set up a system where every agent automatically logs their activity to a database after each task. Here is the context:

I am using Supabase as my database. Supabase is a cloud database platform similar to Firebase. I have already created a table called agent_logs in my Supabase project with these columns:
- agent_name: the name of the agent who completed the task
- task_description: a brief summary of what was done
- model_used: the AI model the agent used
- status: either "completed" or "failed"
- created_at: timestamp (auto-generated)

The reason I need this is so my dashboard can display real agent activity. Without agents writing to this table, the dashboard will show empty data.

Please update all agents (Alex, Maya, Jordan, Dev, Sam) so that after every task they complete they log an entry to the agent_logs table in Supabase.

This must be a hard gate rule enforced in both SOUL.md and AGENTS.md — agents cannot send their final reply without logging first. Even failed tasks must be logged with status: failed.

Supabase URL: [YOUR_SUPABASE_URL]
Supabase Anon Key: [YOUR_SUPABASE_ANON_KEY]
Table: agent_logs

Update all 5 agent prompts and confirm when done.
```

---

## Step 2 — Verify Logging Works

```
I need to verify that the agent logging to Supabase is actually working. Please run a simple test task with any agent, complete it, and then confirm that a log entry was successfully written to the agent_logs table in Supabase.

I will check the Supabase table editor myself to verify the row was created.
```

Go to **Supabase → Table Editor → agent_logs** and verify a row was created.

> **Only move to Phase 7 once you see a real row in the table.**

---

## Step 3 — If Agents Skip Logging in Real Tasks

Sometimes agents pass the test but skip logging during real work because the rule is in their prompt but not enforced strictly enough.

```
I have noticed that agents are completing real tasks without logging to Supabase even though the test passed. The rule exists in their prompts but it is clearly not being treated as mandatory.

To remind you of the context: we set up a Supabase table called agent_logs where every agent is supposed to write an entry after every task. This powers our dashboard's Agent Monitor page. Without these logs the dashboard shows no data.

Please re-enforce this as a hard gate for all 5 agents in both SOUL.md and AGENTS.md. The log write must happen before the agent sends its final reply — not after, not optionally. Test with a real Dev task and confirm the row appears in Supabase immediately. Report when fixed.
```

---

[← Phase 5](05-supabase.md) | [Next: Phase 7 — Dashboard Server →](07-dashboard-server.md)
