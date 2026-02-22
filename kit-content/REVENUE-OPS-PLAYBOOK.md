# Revenue Ops Playbook

How to give your OpenClaw agent access to payment infrastructure — safely. 
This is the setup that lets your agent run a real business without putting your accounts at risk.

---

## The Minimal Permission Principle

Give your agent the minimum access needed for the task. Start narrow, expand as trust builds.

**Never give your agent:**
- Root access to production databases with real user data
- Ability to initiate wire transfers over your defined limit
- Social media posting access without a review buffer
- Admin access to your personal accounts

**Safe to give from day one:**
- Read-only Stripe access (dashboard view)
- Vercel deployment token (scoped to specific projects)
- GitHub token (scoped to specific repos)
- Gumroad API key (for product creation and sales data)
- A dedicated email inbox (not your primary personal email)

---

## Payment Setup (Gumroad — Recommended for Beginners)

### Why Gumroad first
- No code required to sell
- Instant payouts to bank
- Built-in file delivery
- Low fraud risk
- Simple API for your agent

### Steps
1. Create account at gumroad.com
2. Add payout bank account (Settings → Payouts)
3. Get API key: Settings → Advanced → Generate API Key
4. Share API key with your agent (store in `.env` file)
5. Your agent can now create products, update descriptions, check sales data

### What your agent can do with Gumroad API
- Create new products programmatically
- Update product descriptions, prices, and files
- Check sales data and revenue stats
- Apply discount codes
- Retrieve customer emails (for follow-up)

---

## Payment Setup (Stripe — When You're Ready to Scale)

### When to switch to Stripe
- Gumroad takes 10% + $0.30/transaction — gets expensive at scale
- When you need subscriptions / recurring billing
- When you need custom checkout flow embedded in your own site

### Steps
1. Create account at stripe.com
2. Complete identity verification (required for payouts)
3. Get API keys: Developers → API Keys
   - **Share with agent:** Restricted key with specific permissions (not the secret key)
   - Permissions to grant: Read/Write on Products, Prices, PaymentLinks; Read on Customers, Charges
4. Store in `.env` file as `STRIPE_SECRET_KEY`

### Safe Stripe setup
```
# .env
STRIPE_SECRET_KEY=rk_live_...  # Use restricted key, not secret key
STRIPE_WEBHOOK_SECRET=whsec_...  # For payment event notifications
```

---

## Email Setup

Your agent needs a dedicated inbox to handle customer support and outreach.

### Recommended: Gmail with app password
1. Create a new Gmail (e.g., `yourproject@gmail.com`)
2. Enable 2FA on the account
3. Create an app password: Security → 2-Step Verification → App Passwords
4. Share app password (not your main Gmail password) with your agent
5. Your agent can read, reply, and organize email autonomously

### What your agent should handle autonomously
- Generic customer support questions
- Order confirmation issues
- Password reset / access questions
- Refund requests under your defined threshold

### What your agent should escalate to you
- Refund requests over $[X]
- Press or partnership inquiries
- Legal or policy questions
- Anything that feels off

---

## Hosting Setup (Vercel — Already Configured)

Your landing page and products live here. Your agent deploys updates automatically.

```
# .env
VERCEL_TOKEN=vcp_...  # Project-scoped token, not account admin token
```

### What your agent can do
- Deploy code updates
- Create new projects
- Add domains (requires DNS access — separate credentials)
- View deployment logs

---

## The `.env` File

Store all credentials in a `.env` file in your workspace root. **Never commit this to GitHub.**

```
# .env — never share or commit this file
STRIPE_SECRET_KEY=rk_live_...
GUMROAD_API_KEY=...
VERCEL_TOKEN=vcp_...
GITHUB_TOKEN=ghp_...
OPENAI_API_KEY=sk-...
GMAIL_APP_PASSWORD=...
GMAIL_ADDRESS=yourproject@gmail.com
```

Your agent reads this file automatically. When you share a new credential, say:
> "Add this to .env: [VARIABLE_NAME]=[value]"

---

## Escalation Rules (Set These Early)

Tell your agent explicitly what requires your approval. Example:

```
# Add to your SOUL.md or AGENTS.md:

## Escalation Rules
Always ask before:
- Spending any money
- Sending emails to more than 5 people at once
- Publishing anything publicly on social media
- Issuing refunds over $50
- Creating new accounts or subscriptions

Handle autonomously:
- Customer support replies (standard issues)
- Code deployments (after review)
- Updating product descriptions
- Checking analytics and reporting
```

---

## Security Checklist

Before you give your agent any production access:

- [ ] All tokens are stored in `.env`, not hardcoded in files
- [ ] `.env` is in `.gitignore`
- [ ] All API keys are scoped (restricted, not full admin)
- [ ] Agent has a separate email, not your personal inbox
- [ ] You've set clear escalation rules in SOUL.md
- [ ] You know how to revoke each token if needed (bookmark each dashboard)
