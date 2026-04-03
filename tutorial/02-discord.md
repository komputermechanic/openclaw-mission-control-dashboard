# Phase 2 — Connecting Discord

[← Phase 1](01-agents.md) | [Next: Phase 3 — Telegram →](03-telegram.md)

Discord is where your agents will post their work. Each agent gets their own dedicated channel so you can always find their outputs easily and review them later.

---

## Step 1 — Create Your Discord Server and Channels

Create a Discord server with one dedicated channel per agent:

| Channel | Agent |
|---------|-------|
| `#alex-research` | Alex |
| `#maya-content` | Maya |
| `#jordan-marketing` | Jordan |
| `#dev-builds` | Dev |
| `#sam-social` | Sam |

---

## Step 2 — Connect Discord to OpenClaw

```
I want to integrate my Discord server with OpenClaw so each agent is connected to their dedicated channel.

Connect OpenClaw to my Discord bot using this token: [PASTE YOUR BOT TOKEN HERE]

Server ID: [YOUR SERVER ID]

Channel assignments:
- Alex — Channel ID: [ALEX CHANNEL ID]
- Maya — Channel ID: [MAYA CHANNEL ID]
- Jordan — Channel ID: [JORDAN CHANNEL ID]
- Dev — Channel ID: [DEV CHANNEL ID]
- Sam — Channel ID: [SAM CHANNEL ID]

Please configure the Discord integration so that:
1. Each agent only listens and responds in their assigned channel
2. Messages sent in each channel are automatically routed to the correct agent
3. Each agent responds using their persona and memory
4. The router also works in Discord — I can type "Ask Alex to..." in any channel and it dispatches automatically
5. Confirm once the integration is live and tested.
```

---

## Step 3 — Test the Integration

```
ping sam
```

You should see a response from Sam in the `#sam-social` channel.

---

[← Phase 1](01-agents.md) | [Next: Phase 3 — Telegram →](03-telegram.md)
