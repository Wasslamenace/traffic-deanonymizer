# Traffic De-Anonymizer - Zapier Workflow Template (Basic)

**Package**: Basic Setup ($200)  
**Delivery Time**: 2-4h  
**Client Pays**: Zapier ($20/month) + Clearbit API (pay-as-you-go)

---

## Workflow Overview

**Trigger** → **Identify** → **Enrich** → **Deliver**

```
Website Visitor
    ↓
Google Analytics 4 (trigger on page view)
    ↓
IP → Company Lookup (Clearbit Reveal API)
    ↓
Enrich Company Data (Clearbit Enrichment)
    ↓
Push to Google Sheets (CRM)
    ↓
(Optional) Slack Alert for high-intent visitors
```

---

## Step-by-Step Setup

### Step 1: Trigger (GA4 Integration)

**Zapier Trigger**: Google Analytics 4 - New Event

**Configuration**:
- Event Name: `page_view`
- Filter: Only trigger when `user_properties.user_type = "new"` OR `session_count = 1`
- Fields to capture:
  - `client_ip` (visitor IP address)
  - `page_location` (URL visited)
  - `page_title`
  - `traffic_source` (where they came from)
  - `timestamp`

**Alternative Triggers** (if no GA4):
- Webhook (custom JavaScript snippet on site)
- Plausible Analytics webhook
- Matomo webhook

---

### Step 2: IP → Company Lookup (Clearbit Reveal)

**Zapier Action**: Clearbit - Reveal Company by IP

**API Endpoint**: `https://reveal.clearbit.com/v1/companies/find?ip={client_ip}`

**Configuration**:
- Input: `{{client_ip}}` from Step 1
- Output fields:
  - `company_name`
  - `company_domain`
  - `company_size` (employees)
  - `company_industry`
  - `company_location`
  - `company_tech_stack` (if available)

**Cost**: $0.01/lookup (Clearbit pricing)

**Fallback**: If no company found (B2C visitor or VPN), skip to end (don't waste enrichment credits).

---

### Step 3: Enrich Company Data (Clearbit Enrichment)

**Zapier Action**: Clearbit - Enrich Company

**API Endpoint**: `https://company.clearbit.com/v2/companies/find?domain={company_domain}`

**Configuration**:
- Input: `{{company_domain}}` from Step 2
- Output fields:
  - `company_description`
  - `company_linkedin_url`
  - `company_twitter_url`
  - `company_estimated_revenue`
  - `company_funding_raised`
  - `company_tags` (SaaS, E-commerce, etc.)

**Cost**: $0.01-0.02/lookup

**Note**: Only run if Step 2 returned a company (filter condition).

---

### Step 4: Push to Google Sheets (CRM)

**Zapier Action**: Google Sheets - Create Spreadsheet Row

**Spreadsheet Structure**:
| Column | Data Source |
|---|---|
| Timestamp | Step 1 timestamp |
| Company Name | Step 2 company_name |
| Domain | Step 2 company_domain |
| Industry | Step 2 company_industry |
| Size | Step 2 company_size |
| Page Visited | Step 1 page_location |
| Traffic Source | Step 1 traffic_source |
| LinkedIn | Step 3 company_linkedin_url |
| Revenue | Step 3 company_estimated_revenue |
| Tags | Step 3 company_tags |

**Configuration**:
- Spreadsheet: Client creates "Visitor Tracking" sheet
- Tab: "Identified Companies"
- Action: Append new row

---

### Step 5 (Optional): Slack Alert for High-Intent Visitors

**Zapier Filter**: Only Continue If...
- `company_size > 50` (mid-market or larger)
- OR `page_location` contains `/pricing` (high intent)
- OR `page_location` contains `/demo` (very high intent)

**Zapier Action**: Slack - Send Channel Message

**Message Template**:
```
🔥 High-Intent Visitor Detected!

Company: {{company_name}}
Industry: {{company_industry}}
Size: {{company_size}} employees
Page: {{page_location}}
Source: {{traffic_source}}

LinkedIn: {{company_linkedin_url}}
```

**Configuration**:
- Channel: #sales-alerts (client creates)
- Notification: Desktop + mobile

---

## Alternative: HubSpot Integration (Instead of Google Sheets)

**Step 4 Alternative**: HubSpot - Create/Update Company

**Zapier Action**: HubSpot - Create or Update Company

**Mapping**:
- Company Domain → `domain` (primary key, deduplicates)
- Company Name → `name`
- Industry → `industry`
- Size → `numberofemployees`
- LinkedIn → `linkedin_company_page`
- Custom Field: `last_visit_date` → Step 1 timestamp
- Custom Field: `last_page_visited` → Step 1 page_location

**Benefit**: Auto-deduplication (if company visits multiple times, updates record instead of duplicates).

---

## Cost Breakdown (Client)

**Tools**:
- Zapier: $20/month (Starter plan, 750 tasks)
- Clearbit: ~$0.02/visitor identified
- Google Sheets: Free
- Slack: Free (or existing workspace)

**Monthly Example** (1,000 visitors, 10% identifiable):
- Zapier: $20
- Clearbit: 100 companies × $0.02 = $2
- **Total**: $22/month

**ROI**: If 1 lead converts (B2B SaaS $500-5,000 value) → 20-200x ROI.

---

## Delivery Checklist

**Setup (2-4h)**:
- [ ] Zapier account setup (client or shared)
- [ ] GA4 connection (or webhook setup)
- [ ] Clearbit API key (client provides or shared pool)
- [ ] Google Sheets template created
- [ ] Zap configured + tested (5 test visitors)
- [ ] Slack channel created (if opted in)
- [ ] Documentation delivered (PDF + Loom video)

**Handoff**:
- [ ] Client can view Google Sheets
- [ ] Client can edit Zap (ownership transferred)
- [ ] 7-day support window starts

---

## Upsells (Post-Delivery)

**Week 2**: Lead Scoring Add-On (+$100)
- Score visitors based on:
  - Company size (1-10 employees = 1, 50+ = 5)
  - Pages visited (pricing = 5, blog = 1)
  - Traffic source (organic = 3, paid = 5)
- Push high-score leads to separate Slack channel or CRM list

**Week 4**: Monthly Optimization Retainer (+$100-200/month)
- Review data monthly
- Optimize filters (reduce noise)
- Add new triggers (form submissions, demo requests)
- Report on identified → converted pipeline

---

_Template v1.0 - Basic Setup - 3 mars 2026, 21:30_  
_Next: Create Pro + Enterprise templates (multi-CRM, custom scoring, API integrations)_
