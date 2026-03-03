# Traffic De-Anonymizer - Zapier Workflow Template (Enterprise)

**Package**: Enterprise Setup ($500)  
**Delivery Time**: 6-10h (custom workflows)  
**Client Pays**: Zapier Professional ($50/mo) + APIs + tools

---

## Workflow Overview (Fully Custom)

**Unlimited Trigger Sources** → **Advanced Scoring** → **Multi-CRM** → **Real-Time Alerts** → **Attribution**

```
[Website Visits] ──┐
[Form Submissions]─┤
[Chatbot Convos] ──┤
[Webinar Signups] ─├─→ Identify → Advanced Score → Route 3+ CRMs → Alerts → Attribution
[Demo Requests] ───┤
[Email Opens] ─────┤
[Custom Events] ───┘
```

---

## Enhanced Features vs Pro

**Pro ($350)**:
- 3 triggers (GA4 + forms + chat)
- 2 CRMs
- Basic scoring
- Slack alerts

**Enterprise ($500)**:
- **Unlimited triggers** (all visitor touchpoints)
- **3+ CRM integrations** (HubSpot + Pipedrive + Salesforce)
- **Advanced scoring rules** (custom weighting, industry-specific)
- **Multi-touch attribution** (first touch → last touch tracking)
- **Dedicated Slack channel** (team notifications)
- **60-day support + monthly optimization**

---

## Workflow 1: Website Visits (High-Intent Pages)

Same as Pro setup (see `zapier-workflow-pro.md`), but with:

### Enhanced Filters

**Trigger conditions** (more granular):
- URL contains `/pricing` OR `/demo` OR `/case-studies` OR `/customers` OR `/enterprise`
- Session duration >5 minutes (vs 3 min Pro)
- Pages viewed >7 (vs 5 Pro)
- Returning visitor (cookie tracking)

**Lead scoring** (more sophisticated):
- Company size: 1-10 = 1pt, 11-50 = 2pt, 51-200 = 3pt, 201+ = 4pt
- Page value: Blog = 0pt, Product = 2pt, Pricing = 4pt, Demo = 5pt, Contact = 6pt
- Traffic source: Direct = 1pt, Organic = 2pt, Referral = 2pt, Paid = 3pt
- Engagement: <2 min = 0pt, 2-5 min = 1pt, 5-10 min = 2pt, >10 min = 3pt
- Returning: First visit = 0pt, 2nd visit = 1pt, 3rd+ visit = 2pt

**Total score**: 0-15 (vs 0-10 Pro)

**Lead tiers**:
- 0-4: Cold (nurture campaign)
- 5-8: Warm (follow up 48h)
- 9-12: Hot (follow up 24h)
- 13-15: Burning (immediate outreach)

---

## Workflow 2: Form Submissions (Explicit Interest)

Same as Pro, but with:

### Form Field Analysis

**Extract additional data**:
- Company size (if provided in form)
- Industry (if provided)
- Use case (if multiple choice form)
- Budget range (if qualification question)

**Auto-tagging**:
- Tag in CRM based on use case (e.g., "Enterprise Trial", "SMB Self-Serve")
- Lifecycle stage: Form submit = MQL (Marketing Qualified Lead)

---

## Workflow 3: Chatbot Conversations (Live Engagement)

Same as Pro, but with:

### Sentiment Analysis

**Zapier + Claude API**:
- Extract chat transcript
- Analyze sentiment (positive/neutral/negative)
- Extract intent (pricing question, support, sales, technical)
- Score urgency (low/medium/high)

**Auto-routing**:
- High urgency + positive sentiment → Sales team (immediate)
- Technical questions → Support team (30 min SLA)
- Negative sentiment → Account manager (damage control)

---

## Workflow 4: Webinar Signups (High-Intent Event)

**Trigger**: Webinar registration (Zoom, Demio, Livestorm)

**Data captured**:
- Name, email, company
- Webinar topic (indicates pain point)
- Questions submitted (shows engagement)

**Actions**:
- Identify company (email domain → Clearbit)
- Enrich (company size, industry, tech stack)
- Score (webinar signup = 7 points automatically, high intent)
- Create deal in CRM (stage: "Webinar Registered")
- Add to nurture sequence (pre-webinar emails)
- Alert sales rep (if company size >50)

**Post-webinar workflow**:
- Trigger: Webinar attendance (Zoom webhook)
- If attended → Score +3, move deal stage "Webinar Attended"
- If no-show → Score -2, move to "Nurture" campaign

---

## Workflow 5: Demo Requests (Highest Intent)

**Trigger**: Demo form submission or Calendly booking

**Immediate actions**:
- Score = 10 (automatic, very high intent)
- Create deal CRM (stage: "Demo Scheduled")
- Assign sales rep (round-robin or territory-based)
- Send calendar invite + reminder sequence
- Slack alert: "🔥 Demo booked: [Company] ([Size] employees, [Industry])"

**Pre-demo enrichment**:
- Pull LinkedIn company page (followers, recent posts)
- Check tech stack (BuiltWith, Wappalyzer)
- Pull recent funding news (Crunchbase)
- Compile "demo prep sheet" → Google Docs (shared with sales rep)

---

## Workflow 6: Email Opens/Clicks (Nurture Engagement)

**Trigger**: Email opened or link clicked (via marketing tool: HubSpot, Mailchimp, Sendinblue)

**Actions**:
- Increment engagement score (+1 per open, +2 per click)
- Tag in CRM ("Engaged: [Campaign Name]")
- If score threshold reached (e.g., 5 opens + 2 clicks) → Alert sales rep
- Move to "Sales Ready" list

**Use case**: Someone not ready to buy now, but engaged with nurture emails → alert sales when hot.

---

## Workflow 7: Custom Events (Client-Specific)

**Examples**:
- PDF download (e-book, whitepaper)
- Video watch >50% (Wistia, Vimeo)
- Free trial signup
- Feature usage (in-app events via webhook)

**Custom triggers** (built per client):
- Client defines events that indicate buying intent
- We build webhooks/Zapier triggers
- Score accordingly

**Example** (SaaS client):
```
Event: User invited 3+ team members (in free trial)
  → Score +5 (high intent, team adoption)
  → Alert sales rep immediately
  → Move deal stage "High Intent Trial"
```

---

## Advanced Lead Scoring (Industry-Specific)

### SaaS Client Example

**Weighting**:
- Company size: 30% (larger companies = higher value)
- Product fit: 40% (tech stack match = priority)
- Engagement: 20% (active prospects = ready to buy)
- Traffic source: 10% (paid > organic for immediate intent)

**Custom rules**:
- Uses Stripe (competitor to Paddle) → Score +3 (easy switch)
- HubSpot CRM → Score +2 (integration available)
- 50-200 employees → Score +4 (sweet spot)
- Visited pricing 3+ times → Score +5 (high intent)

**Result**: Hyper-accurate scoring tailored to client's ICP.

---

### E-commerce Client Example

**Weighting**:
- Order volume: 40% (high-volume merchants = priority)
- Cart abandonment: 30% (pain point match)
- Platform: 20% (Shopify/WooCommerce integration)
- Geography: 10% (target markets only)

**Custom rules**:
- Shopify store → Score +3 (native integration)
- >1,000 orders/month → Score +5 (high-volume)
- Visited "Cart Abandonment" page → Score +4 (pain point)

---

## Multi-CRM Integration (3+ Systems)

**Why 3+ CRMs?**
- Marketing owns HubSpot (nurture campaigns)
- Sales owns Pipedrive (deal pipeline)
- Finance/CS owns Salesforce (post-sale, invoicing)

**Workflow**:
```
Visitor identified
  ↓
Push to HubSpot (lifecycle: Lead → MQL → SQL)
  ↓ (if SQL)
Push to Pipedrive (create deal, assign rep)
  ↓ (if closed-won)
Push to Salesforce (onboarding, invoicing)
```

**Data sync**:
- All CRMs see same company record (Zapier keeps in sync)
- Tags/notes replicate across systems
- No duplication (domain = primary key)

---

## Multi-Touch Attribution (First → Last)

**Problem**: Which touchpoint closed the deal?

**Solution**: Track full journey.

**Example journey**:
1. **First touch**: Organic search → Blog post (awareness)
2. Visit 2: LinkedIn ad → Pricing page (consideration)
3. Visit 3: Email campaign → Case study (evaluation)
4. Visit 4: Direct → Demo request (decision)

**Attribution**:
- **First touch**: Blog post (credit 40%, awareness channel)
- **Last touch**: Demo request (credit 40%, conversion channel)
- **Middle touches**: 20% split (assisted conversion)

**Zapier tracking**:
- Custom field in CRM: "Touch 1 Source", "Touch 2 Source", etc.
- Update on each visit (append to journey log)
- Report monthly: "Which channels drive most pipeline?"

**Use case**: Marketing proves ROI (content drove awareness, paid ads closed deals).

---

## Dedicated Slack Channel (Team Notifications)

**Enterprise clients get**:
- Private Slack channel: `#leads-[client-name]`
- Notifications by lead tier:
  - Burning leads (13-15 score) → `@here` (everyone notified)
  - Hot leads (9-12) → `@sales-team` (sales notified)
  - Warm leads (5-8) → Silent notification (logged only)

**Message format**:
```
🔥 BURNING LEAD (Score: 14/15)

Company: Acme Corp
Size: 150 employees
Industry: SaaS
Score breakdown:
  - Company size (51-200): 3pt
  - Pricing page visit: 4pt
  - Demo request: 6pt
  - Returning visitor: 1pt

Pages visited:
  - /pricing (3x)
  - /case-studies (1x)
  - /demo (1x)

LinkedIn: https://linkedin.com/company/acme
Contact suggestion: john@acme.com (CEO, via Hunter.io)

➡️ Action: Reach out within 1 hour
```

**Team collaboration**:
- Sales rep claims lead (emoji reaction 🙋)
- Updates thread with status ("Called, voicemail left")
- Logs outcome ("Meeting booked for Friday 2pm")

---

## Monthly Optimization (Included in Enterprise)

**What we do**:
- Review lead quality (are scores accurate? False positives?)
- Adjust scoring weights (if needed)
- Add new triggers (client requests: "Can we track X event?")
- Optimize filters (reduce noise, increase signal)
- Generate report (identified → converted pipeline)

**Report includes**:
- Total visitors identified (e.g., 500)
- Hot leads generated (e.g., 100)
- Meetings booked (e.g., 20)
- Customers closed (e.g., 5)
- Conversion rates (0.5% visitor → customer)
- ROI calculation (5 customers × $5k/year = $25k revenue vs $500 setup + $165/mo tools)

**Adjustments** (based on data):
- "We see 'Blog' visits score 0, but blog readers convert well. Let's increase blog score to 1pt."
- "'Paid ads' visitors have low close rate. Let's lower paid score from 3pt to 2pt."
- "'Returning visitors' close 3x more. Let's increase returning score from 2pt to 4pt."

---

## Cost Breakdown (Client)

**Tools**:
- Zapier Professional: $50/month (2,000 tasks)
- Clearbit: $50/month (1,500 lookups)
- Hunter.io: $49/month (5,000 emails)
- HubSpot: Free or existing
- Pipedrive: $15/month
- Salesforce: Existing enterprise license
- Slack: Free or existing workspace
- Claude API: $10-30/month (sentiment analysis, optional)

**Total**: $174-224/month

**ROI Example** (B2B SaaS):
- 2,000 visitors/month
- 200 identifiable (10%)
- 50 hot leads (25%)
- 10 meetings (20%)
- 3 customers (30%)
- Average deal: $5,000/year
- **Annual value**: $15,000
- **Monthly value**: $1,250
- **ROI**: $1,250 / $224 = **5.6x** monthly

---

## Delivery Checklist (6-10h)

**Setup**:
- [ ] Discovery call (understand client's ICP, scoring criteria, systems)
- [ ] Zapier Professional account (client or shared)
- [ ] Connect all triggers (GA4, forms, chat, webinars, demos, email, custom)
- [ ] Configure enrichment APIs (Clearbit, Hunter.io, client keys)
- [ ] Map fields to 3+ CRMs (HubSpot, Pipedrive, Salesforce, or custom)
- [ ] Build advanced scoring logic (industry-specific weighting)
- [ ] Set up multi-touch attribution (journey tracking)
- [ ] Create dedicated Slack channel + notifications
- [ ] Test end-to-end (10 mock visitors, verify all CRMs + Slack)
- [ ] Documentation (Loom video 20-30 min + PDF guide)

**Handoff**:
- [ ] Client can view/edit all Zaps
- [ ] Client team trained (Slack usage, CRM sync, scoring interpretation)
- [ ] 60-day support starts
- [ ] Monthly optimization scheduled (first call 30 days)

---

## Upsells (Post-Delivery)

**Month 2**: Predictive Lead Scoring (+$200/month)
- Machine learning model (predicts close probability)
- Trained on client's closed-won deals
- Auto-adjusts scoring weights monthly

**Month 3**: Competitor Intelligence (+$150/month)
- Alerts when competitors' customers visit your site (domain matching)
- "Company X (currently using Competitor Y) visited pricing 3x"
- Targeted outreach campaigns

**Month 6**: White-Label Dashboard (+$500 one-time + $100/month hosting)
- Branded real-time dashboard (client's logo, colors)
- Embed in client's internal tools
- API access for custom integrations

---

_Template v1.0 - Enterprise Setup - 4 mars 2026, 03h20_  
_Delivery: 6-10h custom workflow, unlimited triggers, 3+ CRMs, attribution_
