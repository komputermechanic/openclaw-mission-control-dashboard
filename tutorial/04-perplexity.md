# Phase 4 — Adding Perplexity Search

[← Phase 3](03-telegram.md) | [Next: Phase 5 — Supabase →](05-supabase.md)

> 🎬 **Video tutorial available:** Watch the full walkthrough on YouTube — https://youtu.be/2udlMLtEdcg

Perplexity gives all your agents access to real-time web search. Without this, agents can only use their training data which gets outdated quickly. This is especially important for Alex who relies on current news and information.

> This phase is optional but strongly recommended.

---

## Configure Perplexity

```
Please set up global Perplexity search using the sonar model. Here is the config:

{
  "tools": {
    "web": {
      "search": {
        "provider": "perplexity",
        "perplexity": {
          "apiKey": "YOUR_PERPLEXITY_API_KEY",
          "baseUrl": "https://api.perplexity.ai",
          "model": "perplexity/sonar"
        }
      }
    }
  }
}

Please confirm when updated and run a connection test.
```

Replace `YOUR_PERPLEXITY_API_KEY` with your actual key from the Perplexity dashboard.

---

[← Phase 3](03-telegram.md) | [Next: Phase 5 — Supabase →](05-supabase.md)
