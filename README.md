# Alibaba Brain — an autonomous cognitive architecture

A brain-inspired decision-making system that runs on a schedule, reflects on its
own state, remembers what it tried, and proposes its own next actions. It is the
"central brain" of a solo-built project (the 110Y Protocol).

**Status: pre-revenue. Built in public, honestly.** This is a real running system
on a production VPS, but it has not yet earned money — $0 in the fixed deposit it
is aiming at. What follows describes what genuinely exists today, not a pitch.

---

## What this actually is

The core is **Cortex** — a cognitive architecture loosely modelled on how a brain
processes information, rather than a flat "agent that calls an LLM in a loop."

It runs on a schedule (via cron) and does the following each cycle:

1. **Sensory intake** (every 30 min) — reads the current state of the system into a
   sensory buffer: what's running, recent outcomes, queued work.
2. **Reflection** (nightly + midday) — two phases:
   - *Divergent:* an LLM generates many raw candidate ideas by forcing connections
     between unrelated data points.
   - *Convergent:* a second pass scores those ideas, filters them against the
     project's **operating principles**, and selects at most one action.
3. **Memory** — every cycle updates **episodic** memory (what was tried + what
   happened) and **semantic** memory (lessons, hypotheses, principles).
4. **Gating layers** — a set of small modulators inspired by brain regions
   (a thalamic attention gate, an OFC-style valuation pass, reward-prediction-error
   scoring, safety/threat checks, circadian/idle gating, etc.) shape what gets
   attention and what gets suppressed before anything executes.

A human makes the final call on architecture, deletions, scope, and pricing. The
brain proposes and prioritises; it does not act autonomously on those.

### Operating principles the brain weighs

The convergent phase rejects or down-ranks ideas that violate hard lines learned
the expensive way — for example: **warm human channels over cold automated
outreach** (cold blasting is banned here after it cost a messaging-channel
restriction), **honesty over hype** (no fabricated metrics), **protect the core
assets**, and **compliance is not optional** (no scraping personal data, no
autonomous spend, no terms-violating automation).

---

## What runs today

This is the honest, current list — not an aspirational fleet.

| Component | What it does | Cadence |
|-----------|-------------|---------|
| **Cortex** | The cognitive architecture above — sensory + reflection + memory | every 30 min / nightly / midday / weekly |
| **NEURON** | Weekly research pass that grounds the brain in fresh external research before it reasons | weekly |
| **Blog + SEO automation** | Generates and maintains long-form articles and keeps the sites' SEO/sitemaps healthy | daily |
| Supporting services | A finance/coordination service, a small shop, WhatsApp bot infrastructure, and a host-health monitor | continuous |

An earlier version of this project ran a fleet of named "earning agents"
(bounty-hunting, outreach, etc.). Those were **deliberately retired** — several
relied on cold outreach that didn't work and created risk. The system today is
centred on the cognitive architecture and a few genuinely-useful scheduled
processes, not on that fleet.

---

## Tech

- **LLMs:** a config-driven failover chain — **Groq (primary, free) → Gemini
  (secondary) → rule-based degrade**. No dependency on any paid frontier provider
  to keep running.
- **Runtime:** Python 3.12 on an Ubuntu VPS, cron-scheduled, with a small Flask
  surface for internal use.

---

## Why it's interesting

Most "autonomous agent" projects are a prompt in a `while` loop. This one is an
attempt at something more structured: separate divergent/convergent reasoning,
real episodic + semantic memory across runs, explicit operating principles the
system is held to, and brain-inspired gating so it doesn't act on every impulse.

It is early and pre-revenue. It's shared as an honest write-up of the
architecture, not as a finished product or a tool you can `pip install` today.

---

## Contact

Built solo. Questions or ideas: **jivani.project110@gmail.com**

*Building in public — honestly, including the parts that don't work yet.*
