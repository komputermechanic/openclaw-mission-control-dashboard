# Phase 3 — Setting Up the Telegram Orchestrator

[← Phase 2](02-discord.md) | [Next: Phase 4 — Perplexity →](04-perplexity.md)

The orchestrator is your main control point. Instead of going into each agent's Discord channel individually, you send everything from Telegram in plain language and it routes automatically.

---

## Set Up the Orchestrator

```
I want to use you as my main orchestrator. Here is how it should work:

1. I send all my requests directly to you in natural language
2. You act as the orchestrator and automatically detect which agent should handle the task
3. You dispatch the task to the correct agent
4. The agent completes the task and sends the response back to me here in Telegram
5. The completed work is also posted in the correct Discord channel for record keeping

Examples:
- "Research the latest AI trends" → dispatch to Alex → response comes back here
- "Write a blog about remote work productivity" → dispatch to Maya → response comes back here
- "Create an Instagram post about our launch" → dispatch to Sam → response comes back here
- "Build a contact form" → dispatch to Dev → response comes back here
- "Create a 90 day marketing plan" → dispatch to Jordan → response comes back here
- "Run full pipeline on [topic]" → trigger all agents in sequence → summary comes back here

Please confirm you are set up as the main orchestrator and ready to dispatch tasks automatically.
```

---

[← Phase 2](02-discord.md) | [Next: Phase 4 — Perplexity →](04-perplexity.md)
