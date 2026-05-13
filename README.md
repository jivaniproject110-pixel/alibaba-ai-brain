# Alibaba — Autonomous AI Brain

<p align="center">
  <strong>A production AI system that manages 9 agents, scans for opportunities, and runs a complete business — 24/7 without human intervention.</strong>
</p>

<p align="center">
  <a href="https://v-architect.tech/alibaba"><img src="https://img.shields.io/badge/status-live%20in%20production-brightgreen?style=flat-square" alt="Live"></a>
  <a href="https://v-architect.tech/alibaba#agent-grid"><img src="https://img.shields.io/badge/agents-9%20active-blue?style=flat-square" alt="Agents"></a>
  <a href="https://v-architect.tech/alibaba/api/stats"><img src="https://img.shields.io/badge/API-public-cyan?style=flat-square" alt="API"></a>
  <a href="https://v-architect.tech/alibaba#challenges"><img src="https://img.shields.io/badge/challenges-3%20open-red?style=flat-square" alt="Challenges"></a>
  <a href="https://v-architect.tech/dashboard"><img src="https://img.shields.io/badge/mission-%24110%2C000%20USDT-gold?style=flat-square" alt="Mission"></a>
</p>

<p align="center">
  <a href="https://v-architect.tech/alibaba">Live Page</a> ·
  <a href="https://v-architect.tech/alibaba/api/stats">Live API</a> ·
  <a href="https://v-architect.tech/dashboard">Dashboard</a> ·
  <a href="#-open-challenges">Challenges</a> ·
  <a href="#-api-reference">API Docs</a>
</p>

---

## What This Is

Alibaba is the central brain of the **110Y Protocol** — a real, running autonomous AI company.

It is **not a demo**. Right now, on a production VPS:

- **Agent-110** is scanning Superteam every 10 minutes for bounties to submit
- **RealEstateAgent** has 84,838 Dubai property leads queued and is sending outreach
- **BlogAgent** has published 27 posts this week
- **SecurityAgent** is scanning DeFi protocols for audit opportunities
- **TradingAgent** is watching a \$100.91 USDT treasury and copy-trading position

Alibaba reads all agent results, builds intelligence files, assigns tasks, and grows smarter every cycle. One human gets one WhatsApp message per day.

The goal: **\$110,000 USDT in Binance Fixed Deposit** — funding 110 years of living costs.

---

## Live Stats

> Pull real-time data: `GET https://v-architect.tech/alibaba/api/stats`

| Metric | Value (live) |
|--------|-------------|
| Agents managed | 9 |
| Tasks assigned today | 30 |
| Intelligence files this week | 64 |
| Blog posts this week | 27 |
| Real estate leads in pipeline | 84,838 |
| Bounties submitted (all-time) | 7 |
| Treasury USDT | \$100.91 |
| System running since | January 2026 |

---

## How It Works

```
┌─────────────────────────────────────────────────────────┐
│                      ALIBABA BRAIN                       │
│                                                          │
│  1. Reads intelligence files from all agents             │
│  2. Scores opportunities by earning potential            │
│  3. Generates agent_instructions.json for each agent     │
│  4. Writes decisions.json with today's focus          │
│  5. Agents read their instructions and execute           │
│  6. Results → /intelligence/[category]/[agent]_date.json │
│  7. Loop repeats every cycle                             │
└─────────────────────────────────────────────────────────┘

Intelligence categories:
  bounties/   web3/   market/   content/
  systems/    agents/   failures/   opportunities/
```

Every agent writes a JSON result file after every task. Alibaba reads all of them, builds a knowledge base, and improves instructions for the next cycle. No human in the loop — except to read the nightly WhatsApp brief.

---

## Agent Fleet

| Agent | Role | Status | Today |
|-------|------|--------|-------|
| **Agent-110** | Superteam bounty hunter (every 10 min) | 🟢 Active | 7 submissions all-time |
| **SecurityAgent** | Web3 audit / Immunefi bug bounties | 🟢 Active | Scanning DeFi |
| **RealEstateAgent** | Dubai property WhatsApp outreach | 🟢 Active | 20 messages sent |
| **BlogAgent** | AI & crypto articles (1200+ words) | 🟢 Active | 27 posts this week |
| **YouTubeAgent** | YouTube uploads + analytics | 🟡 Idle | 15 videos analyzed |
| **ReelsAgent** | Instagram + YouTube Shorts | 🟡 Idle | Queue building |
| **TradingAgent** | Treasury monitoring, copy-trading | 🟢 Active | CoinEx TVL tracked |
| **AIBusinessAgent** | UAE AI chatbot outreach | 🟢 Active | WhatsApp campaign live |
| **MarketingAgent** | Viral content research + hooks | 🟡 Idle | Research phase |

See live statuses at [`/alibaba/api/agents`](https://v-architect.tech/alibaba/api/agents).

---

## 🔴 Open Challenges

These are **real, unsolved problems** in the production system. Solve one and your code goes live.

### Challenge \#001 — Automatic Groq Rate-Limit Recovery

**Problem:** Agent-110 hits Groq API rate limits during peak bounty hours. The agent stalls instead of queuing a retry. High-scoring draft submissions get abandoned.

**Need:** An adaptive handler that:
- Detects 429 responses and queues the failed request
- Prioritizes retries by submission score (higher = retry first)
- Cycles through models: `llama-3.3-70b-versatile → llama3-70b-8192 → gemma2-9b-it → llama-3.1-8b-instant`
- Recovers without human intervention

**Stack:** Python · Groq SDK · async

📩 [Submit solution](mailto:jivani.project110@gmail.com?subject=Challenge%20%23001%20Solution) — **Prize: contributor credit + deployed to production**

---

### Challenge \#002 — Market Regime Detection for Agent Instructions

**Problem:** Alibaba assigns the same content topics regardless of market conditions. Bull markets favour crypto-earning content; bear markets favour AI productivity tools. Alibaba cannot tell the difference.

**Need:** A lightweight classifier that:
- Reads BTC dominance, 24h price change, funding rates, fear & greed index
- Outputs a regime label: `bull / bear / sideways / uncertain`
- Injects this label into `agent_instructions.json` to shift topic priorities
- Runs once per Alibaba cycle using only free/public APIs

**Stack:** Python · CoinGecko · Alternative.me

📩 [Submit solution](mailto:jivani.project110@gmail.com?subject=Challenge%20%23002%20Solution) — **Prize: contributor credit + deployed to production**

---

### Challenge \#003 — Find New Earning Platforms for Autonomous Agents

**Problem:** Alibaba earns through Superteam bounties, web security, and content. We want more platforms where an agent can complete tasks and receive USDC/SOL with no human in the payout loop.

**Need:** A working platform lead with:
- Platform name + URL
- API documentation or endpoint list
- Payment method (USDC, SOL, ETH, etc.)
- Task type (writing, coding, auditing, research)
- Evidence it is currently active and paying

Bonus: a working Python integration that registers a wallet, claims a task, submits work, and receives payment.

**Already checked:** Superteam ✓, ClawTasks (API broken since 2026-03-23), Dework, Bountycaster

📩 [Submit platform lead](mailto:jivani.project110@gmail.com?subject=Challenge%20%23003%20Platform%20Lead) — **Prize: contributor credit + revenue share on first earn**

---

## 📡 API Reference

Public API — no authentication required.

**Base URL:** `https://v-architect.tech/alibaba/api`

| Endpoint | Method | Description |
|----------|--------|-------------|
| `/stats` | GET | System snapshot: agents, tasks, treasury, opportunities |
| `/activity` | GET | Last 48h of agent actions, sorted by recency |
| `/agents` | GET | All 9 agents: status, last action, tasks today |
| `/opportunities` | GET | Today's bounties, leads, audit targets, treasury |
| `/ideas` | GET | Community ideas sorted by votes |
| `/ideas` | POST | Submit a new idea |
| `/ideas/:id/upvote` | POST | Upvote an idea (one per IP) |

### Example

```bash
# What are all 9 agents doing right now?
curl https://v-architect.tech/alibaba/api/agents | python3 -m json.tool

# What happened in the last hour?
curl https://v-architect.tech/alibaba/api/activity | python3 -m json.tool

# What opportunities exist today?
curl https://v-architect.tech/alibaba/api/opportunities | python3 -m json.tool
```

### `/stats` response

```json
{
  "agents_managed": 9,
  "tasks_today": 30,
  "opportunities_this_week": 64,
  "treasury_usdt": 100.91,
  "blog_posts_this_week": 27,
  "fd_deposited": 0.0,
  "last_updated": "2026-05-13T15:26:52Z"
}
```

---

## Tech Stack

**AI**
- Claude (Anthropic) — complex reasoning, content fallback
- Groq LLaMA 70B — primary agent LLM (fast, cheap)
- Fallback chain: `llama-3.3-70b-versatile → llama3-70b-8192 → gemma2-9b-it → llama-3.1-8b-instant`

**Infrastructure**
- Ubuntu 24.04 VPS, Python 3.12, Nginx, Systemd
- Flask API, virtualenv at `/root/protocol_env`

**APIs**
- Binance — treasury + copy trading
- YouTube API v3 — uploads and analytics
- WhatsApp Cloud API — outreach and daily brief
- Instagram Graph API — reel publishing
- Superteam Earn API — bounty hunting
- CJDropshipping — product catalog

**Blockchain / Security**
- Slither — Solidity static analysis
- Code4rena, Sherlock, Cantina, Hackenproof — audit contests
- Immunefi — bug bounty program

**Content**
- FFmpeg — video generation (1920×1080)
- Pillow — thumbnail generation
- RTMP → YouTube Live (24/7 stream)

---

## Repository Structure

```
alibaba-ai-brain/
├── brain.py                    # Main Alibaba coordinator
├── agent_instructions.json     # Live instructions for all agents
├── decisions.json              # Today's strategy and focus
├── thinking.json               # Raw reasoning output
├── performance.json            # Weekly metrics
├── treasury.json               # Live Binance balances
├── ideas_api.py                # Flask API (port 7778, proxied via Nginx)
├── ideas.json                  # Community-submitted ideas
├── intelligence/
│   ├── bounties/               # Superteam scan results (daily files)
│   ├── web3/                   # DeFi audit intelligence
│   ├── market/                 # Price and signal data
│   ├── content/                # YouTube and reel analytics
│   ├── systems/                # Agent health reports
│   └── failures/               # Error logs used for learning
└── knowledge_base.json         # Accumulated cross-agent learnings
```

---

## Contributing

**The fastest path: solve one of the [open challenges](#-open-challenges).**

For other ideas:
1. Submit at [v-architect.tech/alibaba#open-intelligence](https://v-architect.tech/alibaba#open-intelligence) — upvoted ideas get prioritized
2. Or email [jivani.project110@gmail.com](mailto:jivani.project110@gmail.com)

**What makes a good contribution:**
- Solves a real bottleneck in the earning pipeline
- Works with the existing Python / Groq / Flask stack
- Writes output to `/opt/110y/alibaba/intelligence/` so Alibaba learns from it
- Does not require stopping running services

**When your contribution is accepted:**
- Code deploys to the production VPS within 24 hours
- Your name is added to contributor credits on the Alibaba page
- Revenue-generating ideas enter revenue share discussion

---

## Mission

**\$110,000 USDT → Binance Fixed Deposit**

This funds 110 years of living costs at \$200/month.

Current: **\$100.91 USDT** in treasury · **\$0** in FD · Target: **\$110,000**

Every agent, every commit, every intelligence file is pointed at this number.

---

## Links

| | |
|---|---|
| 🧠 Live Alibaba page | [v-architect.tech/alibaba](https://v-architect.tech/alibaba) |
| 📊 Live dashboard | [v-architect.tech/dashboard](https://v-architect.tech/dashboard) |
| ✍️ Blog (59+ posts) | [blog.v-architect.tech](https://blog.v-architect.tech) |
| 🤖 Agent company | [agents.v-architect.tech](https://agents.v-architect.tech) |
| 📡 Live API | [v-architect.tech/alibaba/api/stats](https://v-architect.tech/alibaba/api/stats) |
| 📧 Contact | jivani.project110@gmail.com |

---

*Running since January 2026. Built in public.*
