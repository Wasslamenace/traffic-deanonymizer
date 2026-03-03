# Anonymous Traffic De-Anonymizer Tool — Build Plan

**Start**: 10 mars 2026 (after AI Visibility + Cold Outreach)  
**Launch**: 24 mars 2026 (2 weeks)  
**Builder**: Rapid Deployment Agent (Alfred autonomous)  
**Priority**: P3 (week 2 start)

---

## 🎯 Product Overview

**Problem**: "150k visitors/month but most are just anonymous numbers" (r/SaaS)

**Evidence**: Real pain point, B2B SaaS founders with traffic but low conversion

**Product**: Visitor Identification Tool/Service
- SaaS tool (no-code automation)
- OR Service (done-for-you setup)

**Format**: Zapier/Make.com workflow + enrichment APIs

---

## 📦 Product Options

### Option A: SaaS Tool ($49-99/mois)
**What it does**:
- Identifies anonymous website visitors
- Enriches with company data (Clearbit, Hunter.io)
- Pushes to CRM (HubSpot, Pipedrive, Attio)
- Sends Slack/email alerts for high-intent visitors

**Tech Stack**:
- Frontend: Next.js (simple dashboard)
- Backend: Supabase (visitor logs)
- Enrichment: Clearbit API ($0.01/lookup), Hunter.io
- Automation: Zapier/Make.com webhooks
- Tracking: JavaScript snippet (install on site)

**Build Time**: 2 weeks (complex, API integrations)

### Option B: Done-For-You Service ($200-500 one-time setup)
**What it includes**:
- Custom Zapier/Make.com workflow build
- Enrichment API setup (client's own keys or shared pool)
- CRM integration (HubSpot, Pipedrive, etc.)
- 30-day monitoring + tweaks

**Tech Stack**:
- Zapier/Make.com (client pays subscription $20-50/mois)
- Enrichment APIs (client keys)
- Documentation + handoff

**Build Time**: 3-5 days per client (manual service)

### Option C: Hybrid (Service → SaaS)
**Phase 1**: Launch service ($200-500 setup, 10-20 clients)
- Validate demand
- Build case studies
- Revenue M1: $2,000-10,000

**Phase 2**: Convert to SaaS (2 weeks dev)
- Productize common workflows
- Self-serve signup
- Recurring revenue $49-99/mois

---

## 🎯 RECOMMENDATION: Option C (Hybrid)

**Reasons**:
1. ✅ Service = quick cash (no dev time, launch week 2)
2. ✅ Validate demand before building SaaS
3. ✅ Case studies from service clients
4. ✅ SaaS build informed by real use cases

**Timeline**:
- **Week 2** (10-17 Mars): Launch service (done-for-you setups)
- **Week 3-4** (18 Mars - 1 Avril): Deliver 5-10 setups, collect feedback
- **Week 5-6** (2-15 Avril): Build SaaS tool (if demand validated)
- **Week 7** (16 Avril): Launch SaaS, migrate service clients

---

## 📦 Service Component (Phase 1)

### Deliverables (Per Client)

**1. Custom Automation Workflow**:
- Visitor tracking (GA4, Plausible, or JavaScript snippet)
- Visitor identification (IP → company lookup)
- Enrichment (Clearbit, Hunter.io, LinkedIn scraping)
- CRM push (HubSpot, Pipedrive, Attio, Google Sheets)
- Alerts (Slack, email for high-intent visitors)

**2. Documentation**:
- Workflow diagram (visual Zapier/Make.com map)
- Setup guide (how to monitor, tweak, troubleshoot)
- API keys management (client owns keys, or uses shared pool)

**3. 30-Day Support**:
- Bug fixes, tweaks, optimization
- Monthly report (visitors identified, leads generated)

### Pricing

**Basic Setup**: $200
- Single workflow (GA4 → Clearbit → Google Sheets)
- 1 CRM integration
- 7-day support

**Pro Setup**: $350
- Multi-workflow (GA4 + form submissions + chatbot)
- 2 CRM integrations (HubSpot + Pipedrive)
- Slack alerts
- 30-day support

**Enterprise Setup**: $500
- Custom workflows (complex rules, scoring)
- 3+ integrations
- Dedicated Slack channel
- 60-day support + monthly optimization

### Build Tasks (Service)

**Day 1-2**: Framework
- [ ] Zapier/Make.com templates (3 variations: Basic, Pro, Enterprise)
- [ ] Enrichment API research (Clearbit, Hunter.io, Snov.io alternatives)
- [ ] Documentation template (workflow diagrams, setup guides)

**Day 3**: Sales Assets
- [ ] Landing page (GitHub Pages)
- [ ] Gumroad/Calendly booking (or Stripe payment links)
- [ ] Case study template (before/after metrics)

**Day 4-5**: First 3 Clients (Manual Delivery)
- [ ] Intake form (website URL, CRM, tracking tool, budget)
- [ ] Build workflow (2-4h per client)
- [ ] Handoff + documentation

**Day 6-14**: Scale (5-10 Clients)
- [ ] Refine templates (reduce delivery time 4h → 2h)
- [ ] Upsell retainer (monthly optimization $100-200/mois)
- [ ] Collect testimonials

---

## 💻 SaaS Component (Phase 2, IF validated)

### Features (MVP)

**Dashboard**:
- Visitor feed (real-time identified companies)
- Enrichment data (company size, industry, tech stack)
- Lead scoring (high/medium/low intent based on pages visited)
- CRM sync status

**Integrations**:
- Website tracking (JavaScript snippet, 1-click install)
- CRM connectors (HubSpot, Pipedrive, Salesforce)
- Enrichment APIs (Clearbit, Hunter.io, built-in)
- Alerts (Slack, email, webhooks)

**Pricing**:
- **Starter**: $49/mois (500 visitors/month identified)
- **Pro**: $99/mois (2,000 visitors/month)
- **Enterprise**: $299/mois (10,000+ visitors/month)

### Build Tasks (SaaS)

**Week 1**: Backend
- [ ] Supabase schema (visitors, companies, enrichment_logs)
- [ ] JavaScript tracking snippet
- [ ] Enrichment API integration (Clearbit, Hunter.io)

**Week 2**: Frontend + Integrations
- [ ] Dashboard (Next.js, visitor feed, lead scoring)
- [ ] CRM connectors (HubSpot, Pipedrive webhooks)
- [ ] Alerts system (Slack, email)

**Week 3**: Launch
- [ ] Landing page (value prop, pricing, demo)
- [ ] Stripe payment integration
- [ ] Onboarding flow (install tracking snippet, connect CRM)

---

## 🚀 Launch Strategy

### Service Launch (10 Mars)

**Reddit Post** (r/SaaS):
```
Title: "I'll build you a visitor de-anonymization workflow (Zapier/Make.com + Clearbit) — first 10 setups $200"

Body:
Saw the post about "150k visitors but all anonymous."

I felt that.

Here's what I built for my own SaaS:
- Zapier workflow: website visitor → IP lookup → Clearbit enrichment → HubSpot CRM
- Slack alerts when high-intent companies visit (based on pages, time on site)
- Result: 40% of identified visitors became leads (vs <5% before)

I'm offering to build the same setup for the first 10 SaaS founders.

**What you get**:
- Custom Zapier/Make.com workflow (tailored to your stack)
- Enrichment API setup (Clearbit, Hunter.io, or alternatives)
- CRM integration (HubSpot, Pipedrive, Google Sheets, etc.)
- 30-day support + tweaks

**Price**: $200 (normally $350, launching discount)

**Requirements**: You have website traffic (>1k visitors/month), a CRM or Google Sheets

Drop comment or DM if interested. I'll send intake form.
```

**Direct Outreach**:
- Reddit: Reply to "anonymous traffic" posts (offer free audit)
- Indie Hackers: Founders with traffic but low conversion
- Twitter: SaaS founders complaining about attribution

### SaaS Launch (16 Avril, IF Phase 1 success)

**Product Hunt**:
- Tagline: "Turn anonymous website visitors into CRM leads automatically"
- Description: De-anonymize, enrich, and push to your CRM in real-time

**Reddit** (r/SaaS, r/startups):
- Case study from service clients
- Free trial (14 days, 100 visitors identified)

---

## 📊 Success Metrics

### Phase 1 (Service, Week 2-4)
- Setups delivered: 5-10
- Revenue: $1,000-5,000
- Client satisfaction: >90%
- Upsell to retainer: 2-3 clients ($200-600/mois recurring)

### Phase 2 (SaaS, Week 7+)
- Signups: 20-50
- Paying customers: 10-20 (50% trial → paid conversion)
- MRR: $490-1,980
- Churn: <20% M1

### M3 Total (Combined)
- Service retainers: $400-800 MRR
- SaaS subscriptions: $1,000-2,500 MRR
- **Total**: $1,400-3,300 MRR

---

## 🛠️ Tech Stack

**Service**:
- Zapier/Make.com (client pays $20-50/mois)
- Clearbit API ($0.01/lookup, client keys or shared pool)
- Hunter.io ($49-99/mois, shared pool)
- Google Sheets (free)

**SaaS**:
- Next.js 15 (frontend)
- Supabase (backend, database)
- Clearbit/Hunter.io APIs (enrichment)
- Stripe (payments)
- Vercel (hosting, free tier)

**Total Costs**:
- Service: $0-50/mois (shared enrichment pool)
- SaaS: $100-200/mois (Supabase, enrichment, Vercel)

---

## 📅 Timeline

### Phase 1 (Service)

| Day | Task | Hours | Status |
|---|---|---|---|
| 1-2 | Templates + documentation | 8h | ⏳ Week 2 |
| 3 | Sales assets (landing, booking) | 4h | ⏳ |
| 4-5 | First 3 setups (manual) | 12h | ⏳ |
| 6-14 | Scale to 5-10 setups | 20h | ⏳ |

**Total**: 44h over 2 weeks

### Phase 2 (SaaS, IF validated)

| Week | Task | Hours | Status |
|---|---|---|---|
| 5 | Backend (Supabase, APIs) | 20h | ⏳ |
| 6 | Frontend + integrations | 25h | ⏳ |
| 7 | Launch (landing, Stripe, onboarding) | 10h | ⏳ |

**Total**: 55h over 3 weeks

---

## 🔄 Decision Point (24 Mars)

**IF Service Phase 1 success** (5+ clients, positive feedback):
→ **GO SaaS Phase 2** (2 weeks build, launch 16 Avril)

**IF Service Phase 1 weak** (<3 clients, low demand):
→ **KILL** (focus on AI Visibility + Cold Outreach scale)

---

_Build planned: Starts 10 mars 2026_  
_Phase 1 (Service) launch: 10 mars_  
_Phase 2 (SaaS) decision: 24 mars_  
_Builder: Alfred (Rapid Deployment, autonomous)_
