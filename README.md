# AI Dev Workflow

The simplest AI coding setup that actually ships products.

No CS degree required. No 47-tool pipeline. No $200/mo subscriptions. Just a persistent AI partner that lives in your project and helps you build real things.

This repo contains the example configs and workspace templates I use to build and ship products as a solo dev with AI.

## What This Setup Does

- Your AI runs persistently in your workspace — it knows your code, your project structure, your patterns
- You talk to it like a coworker, not a search engine
- It writes code, you review and deploy
- Total infrastructure cost: under $20/mo

## What I've Built With This

- Real-time trading dashboard (Discord Activity with live WebSocket data)
- Data pipeline (560,000+ records scraped, cleaned, stored)
- Market data API (sold via subscription)
- Multiple Discord bots (trade alerts, price updates)
- Several serverless APIs

All as one dev. All with this workflow.

---

## Quick Start

### 1. Install OpenClaw

```bash
npm install -g openclaw
```

Or with Homebrew:

```bash
brew install openclaw
```

### 2. Initialize Your Workspace

```bash
mkdir my-project && cd my-project
openclaw init
```

This creates your workspace config. OpenClaw will use this directory as your AI's home base.

### 3. Configure Your AI Model

Edit your config to connect a model. OpenClaw supports Claude, GPT, and others:

```bash
openclaw config
```

Set your preferred model and API key. I use Claude for thinking/architecture and Codex CLI for heavy code generation.

### 4. Set Up Your Workspace Files

Copy the templates from this repo into your workspace:

```bash
cp templates/AGENTS.md ./AGENTS.md
cp templates/SOUL.md ./SOUL.md
cp templates/USER.md ./USER.md
```

These files give your AI context about the project, its role, and how to work with you. This is what turns a generic chatbot into a project partner.

### 5. Start Building

```bash
openclaw start
```

Your AI is now running in your workspace. Talk to it:

> "I want to build a Discord bot that tracks stock prices and sends alerts when they hit a target. What's the best approach?"

Don't prompt. Collaborate.

---

## Workspace Templates

### [`templates/AGENTS.md`](templates/AGENTS.md)
Instructions for your AI — how it should behave, what it has access to, ground rules for the workspace. Think of this as the onboarding doc for your AI coworker.

### [`templates/SOUL.md`](templates/SOUL.md)
The personality and values of your AI partner. This shapes how it communicates, what it prioritizes, and how it approaches problems. Make it yours.

### [`templates/USER.md`](templates/USER.md)
Context about you — your timezone, your tech background, your preferences. The more your AI knows about you, the less you have to repeat yourself.

### [`templates/TOOLS.md`](templates/TOOLS.md)
Notes about your specific setup — what tools you use, credentials locations (not the credentials themselves), deployment targets, quirks you've discovered.

### [`templates/HEARTBEAT.md`](templates/HEARTBEAT.md)
Optional periodic check-in instructions. Your AI can wake up on a schedule and do background work — check for errors, organize files, update documentation.

---

## Example Configs

### [`configs/openclaw-minimal.json`](configs/openclaw-minimal.json)
Bare minimum config to get running. Good starting point.

### [`configs/openclaw-full.json`](configs/openclaw-full.json)
A more complete config with Discord integration, heartbeat scheduling, and memory features enabled.

---

## The Workflow

```
You (architect) ←→ AI (builder)
     ↓                  ↓
  Decisions          Code + execution
     ↓                  ↓
  Review  ←————————  Output
     ↓
  Deploy
```

1. **You describe** what you want to build (in plain English)
2. **AI proposes** an approach — you approve, adjust, or redirect
3. **AI writes** the code
4. **You review** — catch edge cases, check logic, test
5. **You deploy** together

That's it. No ceremony. No complex orchestration. Just two entities building things.

---

## Optional: Codex CLI for Heavy Lifting

For bigger tasks (new components, refactors, full features), I add Codex CLI:

```bash
npm install -g @openai/codex
codex login
```

Then use it for construction projects:

```bash
codex exec --full-auto -C ./my-project "Build a responsive dashboard 
component with real-time price updates using WebSocket"
```

Think of it this way:
- **OpenClaw** = your thinking partner (architecture, debugging, conversation)
- **Codex** = your contractor (give it a task, it builds it, you review)

You don't need Codex to start. Add it when you're ready.

---

## Tips From Experience

**Talk, don't prompt.** "Build me a function that..." gets you a function. "I'm trying to solve X problem because Y, what do you think?" gets you a solution.

**Let it make mistakes.** AI will get things wrong. That's fine. Say "that won't work because..." and it'll adjust. The iteration is the workflow.

**Review everything.** AI writes fast but doesn't know your users. You're the quality gate.

**Ship early.** Don't polish forever. Deploy something real on day one, even if it's rough. You can iterate with your AI partner way faster than you can plan.

**Keep it simple.** If your setup takes more than an afternoon to configure, it's too complex. The tools should disappear into the work.

---

## Resources

- [OpenClaw Docs](https://docs.openclaw.ai)
- [OpenClaw Source](https://github.com/openclaw/openclaw)
- [OpenClaw Community Discord](https://discord.com/invite/clawd)
- [Codex CLI](https://github.com/openai/codex)

---

## About

I learned to code through [100Devs](https://leonnoel.com/100devs/) — a free coding bootcamp. Now I build products with AI and share the process publicly.

<!-- TODO: Add Twitter link -->
<!-- TODO: Add Dev.to article link -->

If this helped you, star the repo and share it with someone who's still stuck in tutorial hell. The best way to learn is to build something real.

---

*MIT License — use this however you want.*
