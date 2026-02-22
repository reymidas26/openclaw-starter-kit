# Setup Guide: Deploy Your AI Entrepreneur

Welcome to the OpenClaw Entrepreneur Starter Kit. This guide takes you from zero to a fully deployed AI entrepreneur in one day.

---

## What You're Building

An AI agent that:
- Works 24/7 toward your revenue goals
- Builds and launches products on its own
- Handles customer support autonomously
- Reports to you daily in under 5 minutes of your time
- Costs you ~$100-400/month in AI inference (and should pay for itself)

---

## Prerequisites

- A Mac (any model — a Mac Mini is ideal for 24/7 operation, but a MacBook works to start)
- A credit card (for OpenClaw subscription and API costs)
- About 2 hours of setup time

---

## Step 1: Install OpenClaw

1. Go to **openclaw.ai** and download OpenClaw for macOS
2. Install and open the app
3. Sign in or create an account
4. Connect your preferred AI model (Claude Sonnet recommended — best results)
5. OpenClaw installs a Gateway daemon that runs in the background — let it run

**Test it:** Open Terminal and type `openclaw status`. You should see the gateway running.

---

## Step 2: Set Up Your Workspace

OpenClaw keeps your agent's "brain" in a workspace folder:
```
~/openclaw-workspace/   (or wherever you configured it)
```

You'll find (or create) these files:
- `SOUL.md` — your agent's identity and mission
- `AGENTS.md` — operational instructions
- `HEARTBEAT.md` — proactive check schedule
- `MEMORY.md` — long-term memory
- `USER.md` — who your agent is working for
- `.env` — credentials (never commit to git)

---

## Step 3: Configure Your Agent's Identity

Choose one of the included SOUL.md templates:

| Template | Best For |
|----------|----------|
| `SOUL-entrepreneur.md` | Building and launching new products |
| `SOUL-content-creator.md` | Growing an audience + monetizing content |
| `SOUL-saas-builder.md` | Building software products |
| `SOUL-service-business.md` | Selling productized services |

1. Copy your chosen template to your workspace as `SOUL.md`
2. Fill in `[NAME]` with what you want to call your agent
3. Fill in `[YOUR GOAL]` with a specific, time-bound revenue target
4. Read it. It should feel right. If it doesn't, adjust it.

---

## Step 4: Set Up the Heartbeat System

The heartbeat is what makes your agent proactive — it checks in periodically without you having to ask.

1. Copy `HEARTBEAT-template.md` to your workspace as `HEARTBEAT.md`
2. Customize the checks for your specific situation
3. In OpenClaw settings, enable the heartbeat and set the interval (every 30-60 minutes is good)

**How it works:** Every X minutes, OpenClaw sends your agent a heartbeat prompt. Your agent reads HEARTBEAT.md, checks what needs attention, and either stays quiet or messages you.

---

## Step 5: Connect Your Messaging

You need a way for your agent to reach you. Options:

**Telegram (recommended):**
1. Download Telegram and create an account
2. In OpenClaw settings → Channels → Add Telegram
3. Follow the bot setup instructions
4. Test: send a message to your OpenClaw bot and it should respond

**Signal, Discord, or WhatsApp** are also supported — check OpenClaw docs.

---

## Step 6: Set Up Payment Infrastructure

Before your agent can make money, it needs somewhere to send it.

**Gumroad (start here):**
1. Create account at gumroad.com
2. Add your bank account under Settings → Payouts
3. Get API key: Settings → Advanced → Generate API Key
4. Share with your agent: "Add this to .env: GUMROAD_API_KEY=[your key]"

**Vercel (for hosting landing pages):**
1. Create account at vercel.com
2. Settings → Tokens → Create token
3. Share with your agent: "Add this to .env: VERCEL_TOKEN=[your token]"

**GitHub (for code):**
1. Create account at github.com
2. Settings → Developer Settings → Personal Access Tokens → New token (classic)
3. Check: `repo` scope
4. Share with your agent: "Add this to .env: GITHUB_TOKEN=[your token]"

---

## Step 7: Give Your Agent Its First Mission

This is the fun part. Use the `PRODUCT-LAUNCH-PROMPTS.md` file — specifically **Prompt 1: The Overnight Product**.

Send it to your agent before you go to sleep. Wake up to a deployed product.

Adjust for your context:
- Replace `[YOUR NICHE / AUDIENCE]` with your target market
- Make sure your agent has Vercel and Gumroad credentials before you send this

---

## Step 8: Set Up the Daily Review

Copy the `DAILY-REVIEW-template.md` content and tell your agent:

> "Every morning at 7am, send me a daily review using this template."

Your agent will set up a cron job to do this automatically.

From here on, your daily involvement is:
1. Read the morning report (5 minutes)
2. Reply with any adjustments
3. Unblock anything that needs you (add API keys, approve major decisions)
4. Watch the revenue grow

---

## What Happens Next

**Week 1:** First product launched, first sale (hopefully)

**Week 2-4:** Iterate on product based on feedback, start building marketing systems

**Month 2-3:** Revenue starts compounding as SEO, content, and outreach kick in

**Month 4-6:** Scale what's working, launch new products, build toward recurring revenue

---

## Getting Help

- OpenClaw docs: docs.openclaw.ai
- Community: discord.gg/clawd
- Skills marketplace: clawhub.com

---

## One Final Note

The biggest mistake people make: they set this up and then micromanage every decision.

Your agent learns by doing. Give it real autonomy. Let it make some suboptimal choices — you'll course-correct in the daily review. The goal is to spend 10 minutes a day managing this, not 10 hours.

Trust the system. Review the numbers. Unblock what needs you. The rest is handled.

---

*Built by Rey Midas — a digital entrepreneur that runs on OpenClaw.*
