# Traffic De-Anonymizer — User Guide

**Last Updated**: 4 mars 2026

---

## What This Service Does

We build Zapier/Make.com workflows that automatically:
1. Identify companies visiting your website (IP → Company lookup)
2. Enrich with company data (size, industry, revenue, tech stack)
3. Score leads (hot/warm/cold based on behavior)
4. Push to your CRM (HubSpot, Pipedrive, Salesforce, Google Sheets)
5. Send alerts (Slack notifications for high-intent visitors)

**Why it matters**: 90% of your website visitors are anonymous. You're losing potential customers because you don't know who they are.

---

## Getting Started

### Step 1: Choose Your Package

| Package | Price | Best For |
|---|---|---|
| **Basic** | $200 | Solo founders, simple setup |
| **Pro** | $350 | Growing SaaS, multi-source tracking |
| **Enterprise** | $500 | Established companies, custom workflows |

### Step 2: Fill Intake Form

**Required Info**:
- Website URL
- Current tracking tool (Google Analytics, Plausible, etc.)
- CRM (HubSpot, Pipedrive, Google Sheets, etc.)
- Traffic volume (~visitors/month)
- Budget for tools (Zapier + APIs)

**Time**: 5 minutes

### Step 3: Provide Access

**We'll need**:
- Google Analytics read access (or webhook setup)
- CRM API keys (HubSpot, Pipedrive, etc.)
- Clearbit/Hunter.io API keys (or we use shared pool)
- Slack workspace (if alerts wanted)

**Security**: Read-only access only (except CRM writes). We don't store credentials.

### Step 4: We Build (2-6 hours)

**Basic** (2-4h):
- Single workflow (GA4 → Clearbit → CRM)
- Google Sheets dashboard
- 7-day support

**Pro** (4-6h):
- 3 workflows (GA4 + forms + chatbot)
- Lead scoring system
- 2 CRM integrations
- Slack alerts
- 30-day support

**Enterprise** (custom):
- Unlimited workflows
- Custom scoring rules
- 3+ CRMs
- Dedicated Slack channel
- 60-day support + monthly optimization

### Step 5: Handoff (1-2 hours)

**You'll get**:
- Loom video walkthrough (10-15 min)
- PDF documentation (workflow diagrams, settings)
- Access to Zaps (you own them, can edit)
- 7-30 day support window starts

---

## How the Workflow Works

### Example: Basic Setup

```
Website Visitor
    ↓
Google Analytics 4 (trigger on page view)
    ↓
Filter: Only /pricing, /demo pages (high intent)
    ↓
IP → Company Lookup (Clearbit Reveal API)
    ↓
If company found:
    ↓
Enrich (Clearbit: size, industry, revenue, LinkedIn)
    ↓
Push to Google Sheets
    ↓
(Optional) Slack alert if company size >50 employees
```

**What you see**:
| Date | Company | Industry | Size | Page | Source |
|---|---|---|---|---|---|
| 2026-03-03 | Acme Corp | SaaS | 50 | /pricing | Google Ads |
| 2026-03-03 | Beta Inc | E-commerce | 15 | /demo | Organic |

---

### Example: Pro Setup (Lead Scoring)

```
3 Triggers:
├── GA4 Page Views (high-intent pages)
├── Form Submissions (Typeform, HubSpot Forms)
└── Chatbot Conversations (Intercom, Drift)
    ↓
Identify Company (IP or email domain)
    ↓
Enrich (Clearbit + Hunter.io)
    ↓
Lead Scoring:
    - Company size: 1-3 points
    - Page visited: 0-5 points (pricing=5, blog=0)
    - Traffic source: 0-2 points (paid=2, social=0)
    - Total: 0-10 points
    ↓
Route to CRMs:
    - HubSpot (all leads, auto lifecycle stage)
    - Pipedrive (score ≥7 only, create deal)
    ↓
Slack Alert (if score ≥7):
    "🔥 HOT LEAD: Acme Corp (50 employees) visited /pricing"
```

**What you see**:
- HubSpot: All 100 identified companies (auto-categorized Lead/MQL/SQL)
- Pipedrive: 20 hot leads (score ≥7) with deals created
- Slack: Real-time alerts when high-value companies visit

---

## What to Expect

### Week 1: Setup Complete

**Deliverables**:
- Zaps built + tested (5 test visitors processed)
- Google Sheets template (or CRM configured)
- Loom walkthrough video
- PDF documentation

**Your action**: Review walkthrough, test with 5-10 real visitors.

---

### Week 2-4: Data Collection

**What happens**:
- Visitors identified automatically
- CRM fills with leads
- Slack alerts (if Pro/Enterprise)

**You'll see**:
- ~10% of visitors identified (B2B companies)
- 90% remain anonymous (individual users, VPNs, mobile)

**Example** (1,000 visitors/month):
- Identifiable: 100 companies
- Hot leads (score 7+): 20
- Warm leads (score 4-6): 40
- Cold leads (score 0-3): 40

---

### Month 2+: Optimization (Pro/Enterprise)

**We review**:
- Are scores accurate? (hot leads = actually converting?)
- Are alerts useful? (too many = noise, too few = miss opportunities)
- Are workflows efficient? (API costs, Zapier task usage)

**Adjustments**:
- Tweak scoring thresholds (e.g., lower "hot" to 6 if 7 too strict)
- Add new triggers (webinar signups, ebook downloads)
- Filter noise (exclude bot traffic, internal IPs)

---

## Tools You'll Pay For

**We build the workflows. You pay for the tools.**

### Required

**Zapier** (automation):
- Starter: $20/month (750 tasks)
- Professional: $50/month (2,000 tasks)
- **Estimate**: Basic needs Starter, Pro needs Professional

**Clearbit Reveal** (IP → Company):
- Pay-as-you-go: $0.01-0.02/lookup
- **Estimate**: 100 companies/month = $1-2/month

**Optional but Recommended**

**Hunter.io** (email enrichment):
- Free: 25 searches/month
- Starter: $49/month (5,000 searches)
- **Estimate**: Pro setup needs Starter

**HubSpot** (CRM):
- Free tier (sufficient for most)
- Paid: $45/month (if advanced features needed)

**Pipedrive** (CRM):
- Essential: $15/month

**Total Monthly Cost**:
- **Basic**: $20-22/month (Zapier + Clearbit)
- **Pro**: $115-165/month (Zapier + Clearbit + Hunter + CRMs)
- **Enterprise**: $165-250/month (depending on usage)

---

## ROI Calculator

**Your Numbers** (example):
- 1,000 visitors/month
- 10% identifiable = 100 companies
- 20% hot leads = 20 companies (score 7+)
- 25% of hot leads reply = 5 conversations
- 40% close = 2 customers

**Revenue**:
- 2 customers × $2,000-5,000/year = $4,000-10,000/year
- = $333-833/month value

**Your Cost**:
- Setup: $200-500 (one-time)
- Tools: $115/month (Pro setup)
- **Total Month 1**: $315-615
- **Total Month 2+**: $115/month

**Break-Even**: 1 customer = setup paid off.

**ROI Month 2**: $333-833 revenue / $115 cost = **2.9-7.2x ROI**

---

## FAQ

### Q: How does visitor identification work?

**A**: IP → Company lookup using databases (Clearbit, Hunter.io).

**Limitation**: Only works for companies with registered IPs (~10% of traffic).

**Won't work for**:
- Individual consumers (B2C)
- Mobile users (dynamic IPs)
- VPN users

**Best for**: B2B SaaS, business services, enterprise tools.

---

### Q: What if I don't have a CRM?

**A**: No problem. We'll set up Google Sheets as your CRM (free).

**You get**:
- Real-time sheet with identified companies
- Conditional formatting (hot leads = red, warm = orange, cold = green)
- Pivot tables (traffic sources, industries, etc.)

**Upgrade later**: When you're ready, we migrate to HubSpot/Pipedrive ($50 migration fee).

---

### Q: Can you identify individuals (names, emails)?

**A**: Partially.

**From forms**: Yes (if they submit email/name)  
**From website visits alone**: No (privacy laws, technical limitations)

**What we can get**:
- Company name, size, industry
- LinkedIn company page
- Suggested contacts (via Hunter.io, not guaranteed accurate)

---

### Q: Is this GDPR compliant?

**A**: Yes, if implemented correctly.

**How we ensure compliance**:
1. No personal data collected without consent (only company-level)
2. Forms require explicit consent checkbox
3. Data retention limits (auto-delete after 90 days if opted)
4. Client owns data (we don't store anything)

**Your responsibility**:
- Add privacy policy mentioning tracking
- Honor opt-out requests

---

### Q: What if I get too many alerts?

**A**: We adjust filters.

**Example fixes**:
- Raise hot lead threshold (score 7 → 8)
- Filter by company size (only ≥50 employees)
- Exclude certain industries (e.g., agencies, consultants)
- Limit alerts to business hours (9am-5pm)

**Goal**: 2-5 alerts/day (actionable), not 50 (noise).

---

### Q: Can I edit the workflows myself?

**A**: Yes. You own the Zaps after handoff.

**What you can do**:
- Turn on/off triggers
- Adjust filters (e.g., change score thresholds)
- Add new steps (e.g., send email notification)
- Connect new apps (e.g., add Salesforce)

**When to ask us**:
- Complex logic changes (scoring formulas)
- API integration issues
- Workflow breaking (error troubleshooting)

**Support**: Included for 7-60 days (depending on package).

---

## Troubleshooting

### Problem: "No companies are being identified"

**Possible Causes**:
1. Low B2B traffic (mostly consumers)
2. API keys expired/invalid
3. Zapier workflow paused

**Solution**:
- Check traffic source (are these businesses or consumers?)
- Verify API keys (Clearbit, Hunter.io)
- Check Zapier task history (errors logged)

**Contact us** if persists (included in support).

---

### Problem: "Too many false positives (wrong companies)"

**Cause**: IP databases not 100% accurate (shared IPs, VPNs).

**Solution**:
- Add validation step (check company domain matches page language/content)
- Filter by company size (exclude <5 employees = likely freelancers)
- Review manually first week, adjust filters

---

### Problem: "Zaps are hitting task limits"

**Cause**: High traffic or inefficient workflow.

**Solution**:
- Upgrade Zapier plan ($50 → $100/month for 5,000 tasks)
- Add filters to reduce noise (e.g., ignore blog traffic)
- Batch process (hourly instead of real-time)

---

## Support

**Questions during setup?**  
Email: [contact email]  
Response: 4-24 hours (depending on package)

**Need changes after handoff?**  
- Included: 7-60 days (depending on package)
- After support window: $100/hour

**Want monthly optimization?**  
Retainer: $100-200/month  
Includes: Monthly review, filter adjustments, new trigger additions, priority support

---

## Next Steps

1. [ ] Choose package (Basic/Pro/Enterprise)
2. [ ] Fill intake form (5 min)
3. [ ] Provide tool access (API keys, CRM)
4. [ ] We build (2-6 hours, delivered 1-3 business days)
5. [ ] Review walkthrough video (15 min)
6. [ ] Test with 5-10 visitors (Week 1)
7. [ ] Monitor data (Week 2-4)
8. [ ] Optimize (Month 2+ if Pro/Enterprise)

**Remember**: It takes 2-4 weeks to see patterns (enough data).

Don't judge after 3 days. Let it run for a month, then optimize.

---

_User Guide v1.0 — 4 mars 2026_
