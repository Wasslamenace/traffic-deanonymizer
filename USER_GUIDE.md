# Traffic De-Anonymizer — User Guide

**For Clients Who Purchased a Setup ($200-500)**

---

## 📋 What You Received

After purchasing a Traffic De-Anonymizer setup, you received:

1. **Zapier Workflows** (1-unlimited depending on package) :
   - Google Analytics 4 → Clearbit → CRM
   - Form submissions → HunterIO → CRM (Pro/Enterprise)
   - Chatbot conversations → Slack alerts (Pro/Enterprise)
   - Custom triggers (Enterprise only)

2. **Lead Scoring System** (Pro/Enterprise) :
   - Company size scoring (1-10 = 1pt, 11-50 = 2pt, etc.)
   - Page value scoring (Blog = 0pt, Pricing = 4pt, Demo = 5pt)
   - Traffic source scoring (Organic = 2pt, Paid = 3pt)
   - Custom weights (Enterprise only)

3. **Documentation** :
   - Loom walkthrough video (10-30 min)
   - PDF guide (how to view Zaps, edit filters, troubleshoot)
   - Access to Zapier (collaborator invite, you own the Zaps)

4. **Support Window** :
   - Basic : 7 days
   - Pro : 30 days
   - Enterprise : 60 days + monthly optimization

---

## 🚀 Quick Start (First 24 Hours)

### Step 1: Watch Loom Video

**Sent via email after setup delivery**

The video shows:
- How Zapier workflows work (trigger → action → output)
- Where to view leads (your CRM: HubSpot, Pipedrive, etc.)
- How to edit filters (if needed)
- How to troubleshoot (if leads stop flowing)

**Time** : 10-30 minutes (depending on package complexity)

**Action** : Watch once, take notes, bookmark for reference

---

### Step 2: Verify Leads Are Flowing

**Check your CRM** (HubSpot, Pipedrive, Salesforce, or Google Sheets)

You should see:
- New leads created (company name, size, industry, website)
- Tags added ("Website visitor", "High intent", "Score: X")
- Notes (pages visited, traffic source, session duration)

**Timeline** : Leads should start appearing within 1-24 hours (depending on your traffic volume)

**If no leads after 24h** : Check Step 5 (Troubleshooting)

---

### Step 3: Review Slack Alerts (Pro/Enterprise)

**If you opted for Slack alerts**

You should receive notifications like:
```
🔥 Hot lead: Acme Corp (150 employees, SaaS)
Score: 9/10
Pages visited: /pricing (3x), /demo (1x)
Traffic source: Paid ad (Google)
LinkedIn: https://linkedin.com/company/acme
Action: Reach out within 24h
```

**Timeline** : Alerts arrive in real-time (within minutes of visitor activity)

**If no alerts** : Either no hot leads yet (score <8) or Slack integration issue (see Troubleshooting)

---

### Step 4: Test with Your Own Visit

**To verify everything works**

1. Visit your website from a different IP (use VPN, mobile data, or friend's computer)
2. Visit high-intent pages (pricing, demo, contact)
3. Stay 3+ minutes, view 5+ pages
4. Wait 5-10 minutes
5. Check CRM: You should see a new lead (your company or ISP name)

**If your company appears** : ✅ System working!

**If ISP appears (e.g., "Verizon", "Comcast")** : Expected (home networks aren't identifiable as companies)

**If nothing appears** : See Step 5 (Troubleshooting)

---

### Step 5: Troubleshooting (Common Issues)

#### Issue 1: No Leads After 24 Hours

**Possible causes** :
- Low traffic (<100 visitors/day = may take 2-3 days to see first lead)
- Visitors are consumers (home IPs, not company networks)
- Zapier workflow paused (check Zapier dashboard)

**Solutions** :
1. Check Zapier dashboard: Zap is "ON" (not paused)
2. Check Zapier task history: Are triggers firing? (GA4 events coming in?)
3. Check Clearbit API limits: Not exceeded (1,500 lookups/month on $50 plan)

**If still stuck** : Email me (tallalwassim131@gmail.com) with screenshot of Zapier task history

---

#### Issue 2: Too Many False Positives (ISPs, Not Companies)

**Expected** : 10-30% of visitors are identifiable as companies (rest are home IPs, VPNs)

**If you're getting 50%+ ISPs** (Comcast, Verizon, etc.) :
- Filter added during setup (keywords: "Comcast", "Verizon", "AT&T")
- Check filter is active: Zapier → Workflow → Filter step

**Solutions** :
1. Add more ISP keywords to filter (your country's ISPs)
2. Increase quality threshold (filter out small companies <10 employees)

**If you need help** : Email list of ISPs you're seeing, I'll add filters

---

#### Issue 3: Slack Alerts Not Working

**Check** :
1. Slack channel exists (#sales or custom channel name)
2. Zapier bot invited to channel (type `/invite @Zapier` in channel)
3. Workflow includes Slack step (check Zapier dashboard)

**Solutions** :
1. Re-invite Zapier bot to channel
2. Test Slack action manually (Zapier → Workflow → Test action)

**If still stuck** : Email me, I'll debug

---

#### Issue 4: Duplicate Leads (Same Company Multiple Times)

**Expected** : Deduplication filter added during setup (checks last 7 days)

**If duplicates still appear** :
- Filter may be too loose (allows same company if >7 days)
- Multiple team members from same company (expected, may want both)

**Solutions** :
1. Tighten filter (dedupe by domain, not company name)
2. Accept duplicates (multiple contacts = good for sales)
3. CRM native deduplication (HubSpot auto-merges duplicates)

**If you want help** : Email, I'll adjust filter

---

## 📊 Understanding Lead Scoring (Pro/Enterprise)

**Your leads have a score 0-10 (or 0-15 for Enterprise)**

**Score breakdown** :

| Factor | Points | Example |
|---|---|---|
| **Company size** | 1-4 | 1-10 employees = 1pt, 201+ = 4pt |
| **Page visited** | 0-5 | Blog = 0pt, Pricing = 4pt, Demo = 5pt |
| **Traffic source** | 1-3 | Organic = 2pt, Paid = 3pt |
| **Visit frequency** | 0-2 | First visit = 0pt, 3rd+ visit = 2pt |

**Total** : 0-10 (Basic/Pro) or 0-15 (Enterprise with custom weights)

---

### Lead Tiers

**0-4 : Cold** → Nurture campaign (email sequence, not immediate outreach)

**5-7 : Warm** → Follow up within 48h (email or LinkedIn)

**8-10 : Hot** → Immediate outreach (call or personalized email within 24h)

**11-15 : Burning** (Enterprise only) → Drop everything, reach out within 1 hour

---

### How to Use Scores

**Scenario 1** : You get 50 leads/week

- 20 are cold (score 0-4) → Add to email nurture sequence
- 20 are warm (score 5-7) → Sales rep reaches out within 48h
- 10 are hot (score 8-10) → Immediate outreach + Slack alert

**Scenario 2** : You get 5 leads/week (low traffic)

- Reach out to all (even cold leads = better than nothing)
- Prioritize hot leads first (higher conversion probability)

---

## 🔧 How to Edit Workflows (Optional)

**You own the Zaps** (collaborator access granted during setup)

### Common Edits

#### 1. Add New High-Intent Page

**Example** : You create a new "/case-studies" page, want to track it

**Steps** :
1. Log in to Zapier
2. Open workflow "GA4 → CRM"
3. Find "Filter" step
4. Edit condition: `Page path contains /pricing OR /demo OR /case-studies`
5. Save
6. Test (visit /case-studies, check if lead appears)

**Time** : 5 minutes

---

#### 2. Change Score Weights

**Example** : You want "Paid traffic" to score higher (4pt instead of 3pt)

**Steps** :
1. Zapier → Open workflow
2. Find "Formatter" or "Code" step (where scoring logic lives)
3. Edit formula: `Paid = 4` (was 3)
4. Save
5. Test (trigger with paid traffic visit)

**Time** : 10 minutes (if comfortable with formulas)

**If unsure** : Email me, I'll walk you through or do it for you (during support window)

---

#### 3. Add New CRM Field

**Example** : You want to capture "Industry" in HubSpot

**Steps** :
1. Zapier → Open workflow
2. Find "HubSpot Create Contact" step
3. Add field mapping: `Industry` = `Clearbit Industry`
4. Save
5. Test (check HubSpot, "Industry" field should populate)

**Time** : 5 minutes

---

## 💰 ROI Tracking

**How to measure success** :

### Week 1-2 : Baseline

**Track** :
- Visitors identified : X (expect 10-20% of total traffic)
- Hot leads : X (expect 20-30% of identified companies)
- Meetings booked : X

**Example** :
- 1,000 visitors → 100 identified → 20 hot leads → 4 meetings → 1 customer

---

### Month 1 : Conversion Funnel

**Calculate** :
- Identification rate : Identified / Total visitors (e.g., 100 / 1,000 = 10%)
- Hot lead rate : Hot leads / Identified (e.g., 20 / 100 = 20%)
- Meeting rate : Meetings / Hot leads (e.g., 4 / 20 = 20%)
- Close rate : Customers / Meetings (e.g., 1 / 4 = 25%)

**Benchmark** (typical B2B SaaS) :
- Identification : 10-20%
- Hot leads : 20-40%
- Meetings : 15-30%
- Close : 20-40%

---

### Month 2-3 : ROI Calculation

**Formula** :
```
Monthly Revenue (from identified leads) / Monthly Cost (tools + setup)
```

**Example** :
- 2 customers closed (from identified leads)
- Average deal : $2,000/year = $166/month each
- Total revenue : $332/month
- Cost : Setup $350 (one-time) + Tools $115/month
- Month 1 ROI : $332 / ($350 + $115) = 0.71x (break-even ~Month 2)
- Month 2+ ROI : $332 / $115 = 2.9x (profitable)

**If ROI < 1x after 3 months** : Email me, we'll troubleshoot (scoring too loose? Wrong ICP? CRM integration issues?)

---

## ❓ FAQ

### Q: Can I pause the workflows if I'm getting too many leads?

**A** : Yes. Zapier dashboard → Workflow → Toggle "OFF"

**When to pause** :
- Vacation (no one to follow up)
- Inbox overflow (too many leads, can't keep up)
- Budget limits (Clearbit API approaching limit)

**When to resume** : Toggle "ON" when ready

---

### Q: What happens if I exceed Clearbit/HunterIO limits?

**A** : 
- **Clearbit** : 1,500 lookups/month ($50 plan) → Workflow stops, error email sent
- **Hunter.io** : 5,000 emails/month ($49 plan) → Workflow stops

**Solutions** :
1. Upgrade plan (Clearbit $99 = 5,000 lookups, Hunter $99 = 10,000 emails)
2. Add filters (only identify high-traffic pages, skip blog visitors)
3. Pause workflow until next month (limits reset monthly)

**If you hit limits Month 1** : Email me, I'll help optimize filters to reduce volume

---

### Q: Can you add more workflows later?

**A** : Yes. Pricing:
- Additional workflow (Basic → Pro upgrade) : $150
- Complex workflow (custom triggers, multi-step) : $200-300

**Examples** :
- Webinar signup → Enrich → CRM ($150)
- Demo booking → Enrich → Slack + Email alert ($200)

**Process** : Email request, I quote, build within 48h

---

### Q: What if I change CRMs?

**A** : Workflow update required.

**Cost** :
- Same package level (HubSpot → Pipedrive) : $50
- Different package level (Basic → Pro) : $150-200

**Timeline** : 24-48h

**Process** : Email new CRM details, grant access, I rebuild workflow

---

### Q: Can I see which pages each company visited?

**A** : Yes (if set up during initial build).

**Where to find** :
- HubSpot : Contact record → "Notes" section
- Pipedrive : Deal → "Notes" field
- Google Sheets : "Pages Visited" column

**If not visible** : Email me, I'll add this field (free during support window)

---

## 📞 Support

**During support window** (7-60 days) :

**Email** : tallalwassim131@gmail.com

**Response time** : <24 hours (business days)

**What I can help with** :
- Troubleshooting (leads not flowing, duplicates, false positives)
- Workflow edits (add pages, change scores, new fields)
- Optimization (reduce noise, improve quality)

**What I can't help with** :
- CRM training (how to use HubSpot, Pipedrive = ask their support)
- Sales strategy (how to reach out to leads = outside scope)

---

## 🎯 Success Stories

**Client A** (B2B SaaS, 2k visitors/month) :
- Setup : Pro ($350)
- Results Month 1 : 200 companies identified, 40 hot leads, 8 conversations, 2 customers
- ROI : 2 customers × $5k = $10k revenue vs $350 + $115 tools = 21x ROI

**Client B** (Agency, 5k visitors/month) :
- Setup : Basic ($200)
- Results Month 1 : 500 companies identified, 50 warm leads, 10 conversations, 3 customers
- ROI : 3 customers × $2k = $6k revenue vs $200 + $20 tools = 27x ROI

**Client C** (E-commerce, 20k visitors/month) :
- Setup : Enterprise ($500)
- Results Month 1 : 2,000 companies identified, 400 hot leads, 80 conversations, 15 customers
- ROI : 15 customers × $500 = $7.5k revenue vs $500 + $224 tools = 10x ROI

---

## 📚 Next Steps

**Week 1** :
- Watch Loom video ✅
- Verify leads flowing ✅
- Test with your own visit ✅

**Week 2-4** :
- Track ROI (meetings booked, customers closed)
- Optimize workflows (add pages, refine filters)
- Train sales team (how to use lead scores)

**Month 2+** :
- Consider monthly optimization ($100-200/month, Enterprise add-on)
- Add more workflows (webinars, demos, custom triggers)
- Refer friends (20% commission if they buy setup)

---

_User Guide v1.0 - 4 mars 2026_  
_For Traffic De-Anonymizer clients ($200-500)_
