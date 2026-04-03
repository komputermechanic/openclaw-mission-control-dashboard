# Phase 5 — Setting Up Supabase

[← Phase 4](04-perplexity.md) | [Next: Phase 6 — Logging →](06-logging.md)

Supabase is the database that powers the dashboard. We use it to store agent activity logs (Agent Monitor page) and tasks (Kanban board). Setting it up now means the dashboard will have real data from day one.

Go to **Supabase → SQL Editor** and run each script below.

---

## agent_logs table — powers the Agent Monitor page

```sql
CREATE TABLE agent_logs (
  id uuid DEFAULT gen_random_uuid() PRIMARY KEY,
  agent_name text,
  task_description text,
  model_used text,
  status text,
  created_at timestamptz DEFAULT now()
);

ALTER TABLE agent_logs ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Allow all operations" ON agent_logs FOR ALL USING (true);
```

---

## todos table — powers the Kanban Tasks page

```sql
CREATE TABLE IF NOT EXISTS public.todos (
  id uuid PRIMARY KEY DEFAULT gen_random_uuid(),
  title text NOT NULL,
  category text NOT NULL CHECK (category IN ('Work', 'Marketing', 'Development', 'Personal')),
  priority text NOT NULL CHECK (priority IN ('Urgent', 'Normal', 'Someday')),
  due_date date NULL,
  completed boolean NOT NULL DEFAULT false,
  status text NOT NULL DEFAULT 'todo' CHECK (status IN ('todo', 'in_progress', 'done')),
  track_status text DEFAULT 'On Track' CHECK (track_status IN ('On Track', 'At Risk', 'Off Track')),
  created_at timestamptz NOT NULL DEFAULT now()
);

ALTER TABLE public.todos ENABLE ROW LEVEL SECURITY;
CREATE POLICY "Allow all" ON public.todos FOR ALL USING (true);
```

---

> **Tip:** Any time a new Supabase table shows "UNRESTRICTED" in the table list, it has no security rules. Fix it immediately:
> ```sql
> ALTER TABLE public.TABLE_NAME ENABLE ROW LEVEL SECURITY;
> CREATE POLICY "Allow all" ON public.TABLE_NAME FOR ALL USING (true);
> ```

---

[← Phase 4](04-perplexity.md) | [Next: Phase 6 — Logging →](06-logging.md)
