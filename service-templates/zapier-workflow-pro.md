# Traffic De-Anonymizer - Zapier Workflow Template (Pro)

**Package**: Pro Setup ($350)  
**Delivery Time**: 4-6h  
**Client Pays**: Zapier Pro ($50/month) + Clearbit + Hunter.io

---

## Workflow Overview (Multi-Source)

**3 Trigger Sources** → **Identify** → **Score** → **Route** → **Alert**

```
[GA4 Page Views] ──┐
                    ├──→ Identify → Score → Route to CRM(s) → Slack Alert
[Form Submissions] ─┤
                    │
[Chatbot Visitors] ─┘
```

---

## Enhanced Features vs Basic

**Basic ($200)**:
- Single trigger (GA4 only)
- 1 CRM integration
- Basic enrichment

**Pro ($350)**:
- 3 triggers (GA4 + forms + chat)
- 2 CRM integrations (HubSpot + Pipedrive)
- Lead scoring (hot/warm/cold)
- Slack alerts (customizable rules)
- 30-day support + optimization

---

## Workflow 1: GA4 Page Views (High-Intent)

### Trigger: GA4 Page View Events

**Filter**: Only trigger when:
- Page location contains `/pricing`, `/demo`, `/case-studies`, `/customers`
- OR session duration > 3 minutes
- OR pages viewed > 5

**Rationale**: Focus on high-intent visitors (not blog readers)

---

### Step 1: IP → Company Lookup (Clearbit Reveal)

Same as Basic workflow (see `zapier-workflow-basic.md`)

---

### Step 2: Lead Scoring Logic

**Zapier Filter**: Calculate score (0-10)

**Score Components**:
1. **Company Size** (0-3 points):
   - 1-10 employees: 1 point
   - 11-50 employees: 2 points
   - 51+ employees: 3 points

2. **Page Visited** (0-5 points):
   - Blog/resources: 0 points
   - Product pages: 2 points
   - Pricing: 4 points
   - Demo/contact: 5 points

3. **Traffic Source** (0-2 points):
   - Direct: 1 point
   - Organic search: 1 point
   - Paid ads (Google/LinkedIn): 2 points
   - Social: 0 points (usually low intent)

**Total Score**: 0-10 (sum of above)

**Lead Tier**:
- 0-3: Cold (low priority)
- 4-6: Warm (follow up within 48h)
- 7-10: Hot (immediate alert)

---

### Step 3: Route to Primary CRM (HubSpot)

**Zapier Action**: HubSpot - Create or Update Company

**Fields**:
- Domain (primary key)
- Company Name
- Industry
- Size (employees)
- Lead Score (custom property)
- Last Visit Date
- Last Page Visited
- Traffic Source
- Lifecycle Stage (auto-set based on score):
  - 0-3: Lead
  - 4-6: Marketing Qualified Lead (MQL)
  - 7-10: Sales Qualified Lead (SQL)

**HubSpot Workflow** (set up by client):
- If Lifecycle = SQL → Auto-assign to sales rep
- If Lifecycle = MQL → Add to nurture sequence

---

### Step 4: Route to Secondary CRM (Pipedrive)

**Zapier Action**: Pipedrive - Create or Update Organization

**Why Two CRMs?**:
- HubSpot: Marketing owns (nurture, email campaigns)
- Pipedrive: Sales owns (direct outreach, deals)

**Fields**:
- Organization Name
- Website
- Custom Field: Lead Score
- Custom Field: Last Visit URL
- Custom Field: Visit Count (increment if org exists)

**Pipedrive Auto-Actions** (set up by client):
- If Score >= 7 → Create Deal (stage: "New Lead")
- If Score >= 7 → Assign to sales rep via round-robin

---

### Step 5: Slack Alert (Hot Leads Only)

**Zapier Filter**: Only continue if Lead Score >= 7

**Zapier Action**: Slack - Send Channel Message

**Message**:
```
🔥 HOT LEAD DETECTED! (Score: {{lead_score}}/10)

🏢 Company: {{company_name}}
📊 Size: {{company_size}} employees
🏭 Industry: {{industry}}
📍 Location: {{company_location}}

🔗 Page Visited: {{page_url}}
📈 Traffic Source: {{traffic_source}}
⏱️ Session Duration: {{session_duration}} min

💼 LinkedIn: {{linkedin_url}}
📧 Suggested Contact: {{hunter_io_email}}

➡️ Next Action: Reach out within 1 hour
```

**Channel**: #hot-leads (client creates, sales team monitors)

---

## Workflow 2: Form Submissions (Explicit Interest)

### Trigger: Typeform/Google Forms/HubSpot Forms Submission

**Fields Captured**:
- Name
- Email
- Company (if provided)
- Message/question

---

### Step 1: Email → Company Lookup (Hunter.io)

**Zapier Action**: Hunter.io - Domain Search by Email

**Input**: Form email (e.g., john@acmecorp.com)  
**Output**: Company domain, size, industry (from Hunter.io database)

---

### Step 2: Enrich Company (Clearbit)

Same as Workflow 1, Step 2

---

### Step 3: Auto-Create Deal in Pipedrive

**Zapier Action**: Pipedrive - Create Deal

**Fields**:
- Deal Title: "Inbound Lead - {{company_name}}"
- Value: $0 (to be qualified)
- Stage: "New Inbound"
- Person: {{name}} (form submitter)
- Organization: {{company_name}}
- Custom Field: Form Message ({{message}})

**Why immediate deal?**: Form submission = explicit interest (higher intent than anonymous visit)

---

### Step 4: Send Internal Notification (Email + Slack)

**Zapier Action 1**: Gmail - Send Email

**To**: sales@clientdomain.com  
**Subject**: New Inbound Lead - {{company_name}}  
**Body**:
```
New form submission:

Name: {{name}}
Email: {{email}}
Company: {{company_name}} ({{company_size}} employees)
Message: {{message}}

[Link to Pipedrive Deal]
```

**Zapier Action 2**: Slack - Send Direct Message

**To**: @sales-rep (round-robin assignment)  
**Message**: Same as Workflow 1 Slack alert format

---

## Workflow 3: Chatbot Visitors (Live Engagement)

### Trigger: Intercom/Drift/Crisp - New Conversation Started

**Fields Captured**:
- Visitor IP
- Pages visited (chat widget tracks)
- Questions asked (chat transcript)

---

### Step 1: IP → Company Lookup

Same as Workflow 1

---

### Step 2: Real-Time Alert to Sales Rep

**Zapier Action**: Slack - Send Direct Message

**To**: @on-call-sales-rep (rotation schedule)  
**Message**:
```
💬 LIVE CHAT IN PROGRESS

Company: {{company_name}} ({{company_size}} employees)
Pages: {{pages_visited}}
Question: "{{first_message}}"

🔗 Jump to chat: {{intercom_conversation_url}}

⚡ Respond NOW (visitor is waiting)
```

**Why real-time?**: Chatbot = highest intent (visitor actively seeking help)

---

### Step 3: Auto-Log in CRM (Post-Chat)

**Trigger**: Intercom - Conversation Closed

**Zapier Action**: HubSpot - Create Note

**Associated With**: Company (matched by domain)  
**Note Content**:
```
Chat Transcript ({{conversation_date}}):

{{full_transcript}}

Outcome: {{conversation_tag}} (e.g., "Demo Requested", "Pricing Question", "Not Qualified")
```

---

## Lead Scoring Dashboard (Google Sheets)

**Purpose**: Real-time visibility into identified visitors (for clients without HubSpot/Pipedrive)

### Auto-Generated Sheet Structure

| Date | Company | Industry | Size | Score | Page | Source | Action Taken |
|---|---|---|---|---|---|---|---|
| 2026-03-03 | Acme Corp | SaaS | 50 | 8 | /pricing | Google Ads | Outreach sent |
| 2026-03-03 | Beta Inc | E-commerce | 15 | 5 | /features | Organic | Added to nurture |

**Zapier Action**: Google Sheets - Append Row

**Conditional Formatting** (client sets up):
- Score 7-10: Red (hot leads)
- Score 4-6: Orange (warm)
- Score 0-3: Green (cold)

**Auto-Refresh**: Connects to Data Studio (free) → Live dashboard for team

---

## Cost Breakdown (Client)

**Tools**:
- Zapier Pro: $50/month (2,000 tasks)
- Clearbit: $50/month (1,500 lookups)
- Hunter.io: $49/month (5,000 emails)
- HubSpot: Free tier (or existing subscription)
- Pipedrive: $15/month (or existing)
- Slack: Free (or existing workspace)

**Total**: $115-165/month

**ROI Example** (B2B SaaS):
- 1,000 visitors/month
- 10% identifiable (100 companies)
- 20% hot leads (20 companies scored 7+)
- 10% convert (2 customers)
- Average deal: $2,000/year
- **Annual value**: $4,000 (24x ROI on $165/month)

---

## Delivery Checklist (4-6h)

**Setup**:
- [ ] Zapier Pro account (client or shared)
- [ ] Connect GA4, forms, chatbot (3 triggers)
- [ ] Configure Clearbit + Hunter.io (API keys)
- [ ] Map fields to HubSpot + Pipedrive (2 CRMs)
- [ ] Build lead scoring logic (Zapier filters)
- [ ] Create Slack channels (#hot-leads, #all-leads)
- [ ] Test end-to-end (5 mock visitors, verify CRM + Slack)
- [ ] Google Sheets dashboard (if opted)
- [ ] Documentation (Loom video + PDF guide)

**Handoff**:
- [ ] Client can view/edit all Zaps
- [ ] Client understands scoring logic (can tweak thresholds)
- [ ] Sales team trained on Slack alerts
- [ ] 30-day support starts

---

## Upsells (Post-Delivery)

**Week 2**: Custom Scoring Model (+$100)
- Industry-specific scoring (SaaS vs E-commerce weighting)
- Tech stack scoring (uses Stripe = +2 points)
- Geographic scoring (target markets only)

**Week 4**: Multi-Touch Attribution (+$150)
- Track visitor journey (first touch → last touch)
- Attribute conversions to traffic sources
- Google Analytics integration (UTM tracking)

**Month 2**: Monthly Optimization Retainer (+$200/month)
- Review lead quality (are scores accurate?)
- Adjust scoring thresholds
- Add new triggers (e.g., webinar signups)
- Monthly report (identified → converted pipeline)

---

_Template v1.0 - Pro Setup - 3 mars 2026, 22:40_  
_Next: Enterprise template (custom API, webhooks, Salesforce)_
