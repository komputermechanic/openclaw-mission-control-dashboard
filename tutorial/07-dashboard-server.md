# Phase 7 — Setting Up the Dashboard Server

[← Phase 6](06-logging.md) | [Next: Phase 8 — Dashboard Shell →](08-dashboard-shell.md)

The dashboard runs as a lightweight web server on your VPS. You access it securely through an SSH tunnel from your browser — it is never exposed to the public internet.

---

## Step 1 — Ask Dev to Set Up the Server

```
I need you to set up a lightweight web server on the VPS that will serve our dashboard. Here is what I need:

1. Create a folder at: /root/.openclaw/workspace/agent-dashboard/
2. Start a simple Python HTTP server that serves that folder on port 45680, but only accessible from localhost (127.0.0.1:45680) — not from the public internet
3. Create a systemd service called agent-dashboard.service so the server starts automatically every time the VPS reboots and restarts itself if it ever crashes

The reason we use localhost only is for security — we will access it through an encrypted SSH tunnel from our own computer, so it never needs to be exposed publicly.

Confirm when the server is live on port 45680.
```

---

## Step 2 — Test the Connection Manually

Before setting up any automation, confirm the server works. Open your terminal and run:

```bash
ssh -N -L 45680:127.0.0.1:45680 root@YOUR_VPS_IP
```

Then open your browser and go to `http://localhost:45680`

If you see any page load — even a blank one or a directory listing — the server is working.

> **Why test manually first?** If you skip straight to automation and something is broken, it becomes very hard to isolate whether the problem is the server, the SSH key, or the automation script. Test manually first, then automate.

Press `Ctrl + C` in the terminal to stop the tunnel when done testing.

---

## Step 3 — Set Up SSH Keys

Set up SSH key authentication so you never have to type a password again.

**Mac / Linux:**

```bash
# Check if you already have an SSH key
ls ~/.ssh/id_ed25519

# If not found, generate one:
ssh-keygen -t ed25519 -C "agent-dashboard"
# Press Enter for all prompts — no passphrase needed for automation

# Copy your key to the VPS (enter your VPS password one last time)
ssh-copy-id root@YOUR_VPS_IP

# Test — you should connect with no password prompt
ssh root@YOUR_VPS_IP
```

**Windows PowerShell:**

```powershell
# Check if you already have an SSH key
Test-Path "$env:USERPROFILE\.ssh\id_ed25519"

# If False, generate one:
ssh-keygen -t ed25519 -C "agent-dashboard"

# Copy your key to the VPS
$pubKey = Get-Content "$env:USERPROFILE\.ssh\id_ed25519.pub"
ssh root@YOUR_VPS_IP "mkdir -p ~/.ssh && echo '$pubKey' >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"

# Test the connection
ssh root@YOUR_VPS_IP
```

---

## Step 4 — Create a One-Click Desktop Launcher

Create a file you can double-click on your desktop to open the dashboard automatically.

**Mac — save as `AgentOS.command`:**

```bash
#!/bin/bash
pkill -f "45680:127.0.0.1:45680" 2>/dev/null
sleep 1
ssh -o StrictHostKeyChecking=no -N -L 45680:127.0.0.1:45680 root@YOUR_VPS_IP &
sleep 2
open "http://localhost:45680"
```

Then make it executable:

```bash
chmod +x /path/to/AgentOS.command
```

**Windows — save as `AgentOS.ps1`:**

```powershell
Get-Process | Where-Object {$_.ProcessName -match "ssh"} | Stop-Process -Force -ErrorAction SilentlyContinue 2>$null
Write-Host "Starting SSH tunnel to AgentOS..."
ssh -o StrictHostKeyChecking=no -N -L 45680:127.0.0.1:45680 root@YOUR_VPS_IP
```

Double-click **AgentOS** on your desktop from now on. The tunnel opens and your browser goes straight to the dashboard.

---

[← Phase 6](06-logging.md) | [Next: Phase 8 — Dashboard Shell →](08-dashboard-shell.md)
