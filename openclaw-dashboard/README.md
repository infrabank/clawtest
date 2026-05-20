# OpenClaw Dashboard Screenshot

Captured from the VPS-local OpenClaw Control UI on 2026-05-20T09:38:28.591Z.

Sensitive tokens/IDs/emails were redacted before committing.

## Files

- `dashboard-overview-redacted.png`

## Redacted text snapshot

```text
Title: OpenClaw Control

OpenClaw
›
main
›
Overview
Search
⌘K
CONTROL
OpenClaw
CHAT
Chat
CONTROL
Overview
Channels
Instances
Sessions
Usage
Cron Jobs
AGENT
Agents
Skills
Nodes
Dreaming
SETTINGS
Config
Communications
Appearance
Automation
Infrastructure
AI & Agents
Debug
Logs
Docs
VERSION
v2026.5.7
Update available: v2026.5.18 (running v2026.5.7). Update now 
Overview
Status, entry points, health.
Gateway Access
Where the dashboard connects and how it authenticates.
WebSocket URL
Gateway Token
Password (not stored)
Default Session Key
Language
English
简体中文 (Simplified Chinese)
繁體中文 (Traditional Chinese)
Português (Brazilian Portuguese)
Deutsch (German)
Español (Spanish)
日本語 (Japanese)
한국어 (Korean)
Français (French)
العربية (Arabic)
Italiano (Italian)
Türkçe (Turkish)
Українська (Ukrainian)
Bahasa Indonesia (Indonesian)
Polski (Polish)
ไทย (Thai)
Tiếng Việt (Vietnamese)
Nederlands (Dutch)
فارسی (Persian)
Connect
Refresh
Click Connect to apply connection changes.
Snapshot
Latest gateway handshake information.
STATUS
OK
UPTIME
3d
TICK INTERVAL
30s
LAST CHANNELS REFRESH
just now
Use Channels to link WhatsApp, Telegram, Discord, Signal, or iMessage.
Attention
1 cron job failed
daily-worklog-23-kst
Event Log
24
9:38:25 AM
control-ui.refresh
{ "tab": "overview", "phase": "end", "status": "ok", "durationMs": 952 }
9:38:25 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "cron.list", "ok": true, "durationMs": 942, "slow":
9:38:25 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "channels.status", "ok": true, "durationMs": 925, "s
9:38:25 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "cron.status", "ok": true, "durationMs": 920, "slow"
9:38:25 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "system-presence", "ok": true, "durationMs": 883, "s
9:38:24 AM
***REDACTED***
{ "tab": "overview", "name": "long-animation-frame", "startTimeMs": 6313, "durationMs": 75, "blockingDurationM
9:38:24 AM
control-ui.tab.visible
{ "previousTab": "chat", "tab": "overview", "durationMs": 72 }
9:38:24 AM
control-ui.refresh
{ "tab": "overview", "phase": "start" }
9:38:23 AM
***REDACTED***
{ "tab": "chat", "name": "long-animation-frame", "startTimeMs": 4939, "durationMs": 379, "blockingDurationMs":
9:38:22 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "chat.history", "ok": true, "durationMs": 4564, "slo
9:38:22 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "device.pair.list", "ok": true, "durationMs": 4527,
9:38:22 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "node.list", "ok": true, "durationMs": 4523, "slow":
9:38:21 AM
***REDACTED***
{ "tab": "chat", "name": "long-animation-frame", "startTimeMs": 2768, "durationMs": 650, "blockingDurationMs":
9:38:21 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "models.list", "ok": true, "durationMs": 3022, "slow
9:38:21 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "commands.list", "ok": true, "durationMs": 3018, "sl
9:38:21 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "health", "ok": true, "durationMs": 3019, "slow": tr
9:38:21 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "agents.list", "ok": true, "durationMs": 2791, "slow
9:38:18 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "agent.identity.get", "ok": true, "durationMs": 270,
9:38:18 AM
control-ui.rpc
{ "id": "***REDACTED***", "method": "sessions.subscribe", "ok": true, "durationMs": 269,
9:38:18 AM
***REDACTED***
{ "tab": "chat", "name": "long-animation-frame", "startTimeMs": 379, "durationMs": 136, "blockingDurationMs":
```

## Additional dashboard tabs

Latest Usage capture refreshed on 2026-05-20T10:26:28Z. Sensitive tokens/IDs/emails were redacted before committing.

- `dashboard-sessions-redacted.png`
- `dashboard-usage-redacted.png`
- `dashboard-agents-redacted.png`

### Current Usage summary from refreshed capture

- Total: 7.1M tokens / $7.72 / 3 sessions
- Top agents:
  - hyeonwoobot: $6.19 / 6.4M tokens
  - jinhobot: $1.53 / 631.1K tokens
- Session rows:
  - hyeonwoobot direct Telegram: 5.6M tokens, 114 messages, 87 tools, 0 errors
  - jinhobot direct Telegram: 631.1K tokens, 45 messages, 19 tools, 0 errors
  - hyeonwoobot cron job: 820.3K tokens, 28 messages, 27 tools, 0 errors

Note: the dashboard still displayed a cache rebuilding/loading indicator (`partial: 1 pending, 1 stale, 38 cached`), but the usage metrics and session rows were populated.

### Redacted Usage text snapshot

```text
Captured: 2026-05-20T10:26:28.268Z

OpenClaw
›
main
›
Usage
Search
⌘K
CONTROL
OpenClaw
CHAT
Chat
CONTROL
Overview
Channels
Instances
Sessions
Usage
Cron Jobs
AGENT
Agents
Skills
Nodes
Dreaming
SETTINGS
Config
Communications
Appearance
Automation
Infrastructure
AI & Agents
Debug
Logs
Docs
VERSION
v2026.5.7
Update available: v2026.5.18 (running v2026.5.7). Update now 
Usage
API usage and costs.
Usage
See where tokens go, when sessions spike, and what drives cost.
Filters
Loading
7.1M
Tokens
$7.72
Cost
3
sessions
Pin
Export ▾
Today
7d
30d
to
Local
UTC
Tokens
Cost
Refresh
Filter (client-side)
3 sessions in range
Agent
All
Channel
All
Provider
All
Model
All
Tool
All
Tip: use filters or click bars to refine days.
Usage cache is rebuilding in the background. Displayed totals may be stale. partial: 1 pending, 1 stale, 38 cached
Usage Overview
MESSAGES ?
187
28 user · 159 assistant
THROUGHPUT ?
18.1K tok/min
$0.0197 / min
TOOL CALLS ?
133
11 tools used
AVG TOKENS / MSG ?
37.8K
Across 187 messages
CACHE HIT RATE ?
91.3%
6.4M cached · 7.0M prompt
ERROR RATE ?
0.00%
0 errors · 2h 10m avg session
AVG COST / MSG ?
$0.0413
$7.72 total
SESSIONS ?
3
of 3 in range
ERRORS ?
0
0 tool results
TOP MODELS
gpt-5.5
$7.72
7.1M · 159 msgs
TOP PROVIDERS
openai-codex
$7.72
7.1M · 159 msgs
TOP TOOLS
exec
81
calls
process
17
calls
update_plan
7
calls
memory_search
7
calls
read
6
calls
image_generate
4
calls
TOP AGENTS
hyeonwoobot
$6.19
6.4M
jinhobot
$1.53
631.1K
TOP CHANNELS
telegram
$6.87
6.3M
PEAK ERROR DAYS
No error data
PEAK ERROR HOURS
No error data
Activity by Time
Estimated from session spans (first/last activity). Time zone: Local.
7.1M tokens
DAY OF WEEK
Sun
0
Mon
0
Tue
0
Wed
7.1M
Thu
0
Fri
0
Sat
0
HOURS
0 → 23
Midnight
4am
8am
Noon
4pm
8pm
Low → High token density
Daily Usage
No data
TOKENS BY TYPE
Output 49.2K
Input 607.9K
Cache Write 0
Cache Read 6.4M
Total: 7.1M
Sessions
3 shown
2.4M avg
0 errors
All
Recently viewed
SORT
Cost
Errors
Messages
Recent
Tokens
↓
agent:hyeonwoobot:telegram:direct:***
channel:telegram · agent:hyeonwoobot · provider:openai-codex · model:gpt-5.5 · msgs:114 · tools:87 · errors:0 · dur:5h 30m
Copy
5.6M
agent:jinhobot:telegram:direct:***
channel:telegram · agent:jinhobot · provider:openai-codex · model:gpt-5.5 · msgs:45 · tools:19 · errors:0 · dur:57m 41s
Copy
631.1K
Cron: ***REDACTED***
agent:hyeonwoobot · provider:openai-codex · model:gpt-5.5 · msgs:28 · tools:27 · errors:0 · dur:3m 31s
Copy
820.3K

```
