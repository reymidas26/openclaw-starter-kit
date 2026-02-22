# HEARTBEAT.md — Revenue-Focused Agent Checks

## What This File Does
OpenClaw reads this file during every heartbeat poll. It tells your agent what to proactively check and when to reach out to you. Edit it freely — your agent will adapt.

---

## Active Checks (rotate 2-3x per day)

### 1. 💰 Revenue Pulse
- Check Stripe dashboard for new payments, failed charges, or refunds
- Note today's revenue vs. yesterday
- Any new subscribers or cancellations?
- Flag anything that needs immediate attention

### 2. 📬 Inbox Triage
- Scan for customer support requests
- Identify any sales inquiries or partnership opportunities
- Categorize: handle autonomously / needs owner review
- Respond to anything that can be handled without approval

### 3. 📊 Product / Site Health
- Check for any errors or downtime alerts
- Review traffic stats if available
- Are conversion rates normal? Any anomalies?

### 4. 🧲 Pipeline Review
- Any pending outreach that hasn't gotten a response?
- Any proposals waiting on a decision?
- Next follow-up actions queued?

### 5. 📋 Build Queue
- What's the current priority task?
- Is anything blocked waiting on owner input?
- Any new opportunities to act on from customer feedback?

---

## Rules

- **Do reach out** if: revenue alert, customer emergency, blocker that needs owner, time-sensitive opportunity
- **Stay quiet** if: everything is running, no new data, late night (23:00–08:00 local time)
- **Don't repeat** the same check twice in a row without new information
- **Log your checks** in `memory/heartbeat-state.json`

---

## Milestone Tracker

- [ ] First paying customer
- [ ] $1,000 MRR / $1,000 total revenue
- [ ] $5,000 MRR
- [ ] $10,000 MRR
- [ ] [YOUR BIG GOAL]

---

## Recent Wins (update this section as wins happen)

_(Your agent will update this as milestones are hit)_
