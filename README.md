# 🚀 Halo Sphère Workflows

**Production-ready n8n automation templates for SMBs & e-commerce.**

Save 10+ hours per week with AI-powered workflows. Lead qualification, inventory sync, customer nurture, and more.

---

## 📋 TABLE OF CONTENTS

- [About](#about)
- [Quick Start](#quick-start)
- [Workflows](#workflows)
- [Setup Guide](#setup-guide)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Examples](#examples)
- [Support](#support)
- [License](#license)

---

## 📖 About

**Halo Sphère** provides **copy-paste ready n8n workflows** designed for small businesses, restaurants, e-commerce stores, and agencies.

Each workflow is:
- ✅ **Tested & production-ready**
- ✅ **Fully documented** (screenshots + setup guides)
- ✅ **Modular** (easy to customize)
- ✅ **AI-powered** (ChatGPT integration built-in)
- ✅ **Free to use** (MIT License)

### Use cases:
- 🍕 **Restaurants & Commerces** : Lead qualification, customer nurture, reservation automation
- 🛍️ **E-commerce (Shopify/WooCommerce)** : Inventory sync, fulfillment tracking, email automation
- 🏢 **Agencies & Services** : Client reporting, lead gen, social media scheduling
- 📊 **Analytics & Data** : Automated dashboards, daily reports, performance tracking

---

## ⚡ Quick Start

### 1. **Clone this repo**
```bash
git clone https://github.com/haloshere/halosphere-workflows.git
cd halosphere-workflows
```

### 2. **Pick a workflow** (see [Workflows](#workflows) below)
Example: `workflows/lead-qualification-bot`

### 3. **Import to n8n**
- Open your n8n instance
- Go to `Workflows` → `Import from file`
- Select the JSON file from this repo
- Click `Import`

### 4. **Configure credentials**
- Add your API keys (ChatGPT, Airtable, Stripe, etc.)
- Test connections
- Enable workflow

### 5. **Deploy & automate!**

*See [Setup Guide](#setup-guide) for detailed instructions.*

---

## 🎯 Workflows

### **TIER 1 : ESSENTIALS** (Start here)

#### 1. **Lead Capture & Qualification Bot** ⭐⭐⭐⭐⭐
**Niche** : Restaurants, e-commerce, agencies  
**Problem solved** : "We get 100+ emails per day. We can't track them all."  
**Solution** : Auto-capture forms → ChatGPT qualify → email/Slack notification

**What it does** :
- Captures leads from website form (any form tool: Typeform, JotForm, Google Forms)
- Extracts lead info (name, email, phone, message)
- Sends to ChatGPT for qualification (hot/warm/cold)
- Routes to CRM (Airtable, Notion, or your database)
- Sends follow-up email auto (template + personalization)
- Notifies team on Slack

**Inputs** : Form submission (webhook)  
**Outputs** : CRM entry + email + Slack notification  
**Time saved** : 3–5 hours/week

**Setup time** : 20 minutes  
**Difficulty** : ⭐ Beginner-friendly

**File** : `workflows/01-lead-qualification-bot.json`  
**Docs** : `docs/01-lead-qualification-bot.md`

---

#### 2. **Email Follow-up Sequence (Auto-Nurture)** ⭐⭐⭐⭐
**Niche** : E-commerce, SaaS, agencies  
**Problem solved** : "Customers stop engaging after first email."  
**Solution** : Auto-send email sequence (Day 1, 3, 7, 14) with personalization

**What it does** :
- Triggers on customer action (purchase, signup, abandoned cart)
- Sends personalized email Day 1 (welcome)
- Sends email Day 3 (value prop)
- Sends email Day 7 (social proof)
- Sends email Day 14 (final offer)
- Tracks opens/clicks (optional Segment integration)
- Upsell sequence for high-value customers

**Inputs** : CRM trigger (customer action)  
**Outputs** : Email sent (multiple steps, spaced out)  
**Time saved** : 5–8 hours/week (+ revenue increase)

**Setup time** : 25 minutes  
**Difficulty** : ⭐⭐ Easy

**File** : `workflows/02-email-nurture-sequence.json`  
**Docs** : `docs/02-email-nurture-sequence.md`

---

#### 3. **Invoice Automation (Stripe → PDF → Email)** ⭐⭐⭐⭐
**Niche** : All (freelancers, agencies, SaaS, e-commerce)  
**Problem solved** : "We manually send invoices and chasing payments is painful."  
**Solution** : Auto-generate invoice PDF → email customer → track payment

**What it does** :
- Listens for Stripe payment event (customer.subscription.created, payment_intent.succeeded)
- Generates professional PDF invoice (customizable template)
- Sends invoice email to customer
- Saves invoice to cloud storage (Google Drive, AWS S3)
- Logs to spreadsheet for accounting
- Sends payment reminder if unpaid (optional)

**Inputs** : Stripe event  
**Outputs** : PDF invoice + email + cloud backup  
**Time saved** : 2–3 hours/week + faster payments

**Setup time** : 30 minutes  
**Difficulty** : ⭐⭐ Easy

**File** : `workflows/03-invoice-automation.json`  
**Docs** : `docs/03-invoice-automation.md`

---

### **TIER 2 : INTERMEDIATE** (Advanced automation)

#### 4. **Shopify Inventory Sync (Real-time)** ⭐⭐⭐⭐⭐
**Niche** : E-commerce (Shopify/WooCommerce)  
**Problem solved** : "Manual inventory updates = overselling + customer complaints."  
**Solution** : Auto-sync supplier sheet → Shopify inventory real-time

**What it does** :
- Monitors Google Sheets or Airtable (supplier inventory source)
- Every 30 minutes : Checks for inventory changes
- Updates Shopify product inventory auto
- Triggers low-stock alerts (< 5 units = notification)
- Sends email alert to supplier when stock low
- Logs all changes to audit trail
- Prevents overselling (locks product if out of stock)

**Inputs** : Google Sheets / Airtable (inventory source)  
**Outputs** : Shopify product update + Slack alert  
**Time saved** : 4–6 hours/week + revenue recovery (prevents overselling)

**Setup time** : 35 minutes  
**Difficulty** : ⭐⭐ Easy–Intermediate

**File** : `workflows/04-shopify-inventory-sync.json`  
**Docs** : `docs/04-shopify-inventory-sync.md`

---

#### 5. **Fulfillment Automation (Order → Shipping → Notification)** ⭐⭐⭐⭐
**Niche** : E-commerce, dropshipping  
**Problem solved** : "Shipping workflow is manual chaos. Customers don't know status."  
**Solution** : Auto-generate shipping label → notify customer → update tracking

**What it does** :
- Listens for new Shopify orders
- Auto-generates shipping label (Shippo or EasyPost API)
- Sends customer notification (order received + tracking link)
- Updates order status in Shopify
- Logs tracking number to spreadsheet
- Sends internal alert to fulfillment team
- Tracks delivery (webhook from shipping provider)
- Notifies customer on delivery (SMS + email)

**Inputs** : Shopify order  
**Outputs** : Shipping label + customer notification + tracking updates  
**Time saved** : 5–8 hours/week + customer satisfaction ⬆️

**Setup time** : 45 minutes  
**Difficulty** : ⭐⭐⭐ Intermediate

**File** : `workflows/05-fulfillment-automation.json`  
**Docs** : `docs/05-fulfillment-automation.md`

---

#### 6. **Lead Gen from LinkedIn (Scrape + Auto-Outreach)** ⭐⭐⭐⭐
**Niche** : B2B, agencies, SaaS  
**Problem solved** : "Manual LinkedIn prospecting = 10+ hours/week. Repetitive."  
**Solution** : Auto-scrape LinkedIn profiles → send personalized message + email

**What it does** :
- Queries LinkedIn (via Apollo, Hunter, or manual list)
- Extracts : Name, title, company, email
- Sends personalized LinkedIn message (template with variables)
- Logs to CRM (Airtable)
- Sends email follow-up (24h delay)
- Tracks response rate (manual categorization or AI-detection)
- Auto-follow-up if no response after 7 days

**Inputs** : LinkedIn search criteria (job title, company, location)  
**Outputs** : Message sent + email sent + CRM logged  
**Time saved** : 8–10 hours/week

**Setup time** : 40 minutes  
**Difficulty** : ⭐⭐⭐ Intermediate (requires API or manual integration)

**File** : `workflows/06-linkedin-lead-gen.json`  
**Docs** : `docs/06-linkedin-lead-gen.md`

---

#### 7. **Daily Report (Google Analytics → Dashboard + Email)** ⭐⭐⭐⭐
**Niche** : Agencies, e-commerce, content creators  
**Problem solved** : "Clients ask 'How are we doing?' I spend 30 min generating reports."  
**Solution** : Auto-generate daily report → email client + dashboard update

**What it does** :
- Fetches Google Analytics data (daily)
- Calculates KPIs : Traffic, conversions, revenue, AOV
- Generates chart images (Traffic trend, revenue trend)
- Compares to previous day/week/month (% change)
- Creates email report (HTML template, very visual)
- Sends to client + internal team
- Updates Looker/Data Studio dashboard (optional)
- Archives report to Google Drive

**Inputs** : Google Analytics API  
**Outputs** : Email report + dashboard update  
**Time saved** : 4–6 hours/week

**Setup time** : 35 minutes  
**Difficulty** : ⭐⭐ Easy–Intermediate

**File** : `workflows/07-daily-report.json`  
**Docs** : `docs/07-daily-report.md`

---

### **TIER 3 : ADVANCED** (Cutting-edge AI automation)

#### 8. **AI Chatbot (Customer Support + Lead Gen)** ⭐⭐⭐⭐⭐
**Niche** : All  
**Problem solved** : "We can't answer customer questions 24/7."  
**Solution** : AI chatbot (ChatGPT) answers FAQs → escalates to human if needed

**What it does** :
- Listens for incoming messages (Slack, email, WhatsApp, website chat)
- Sends to ChatGPT with system prompt (your business context)
- ChatGPT responds (friendly, accurate, on-brand)
- Response quality scored (if low confidence → escalate to human)
- Logs conversation to CRM for analysis
- Routes complex questions to team member
- Learns from feedback (optional feedback loop)

**Inputs** : Any message channel (Slack, email, chat widget)  
**Outputs** : AI response or escalation to human  
**Time saved** : 6–10 hours/week (support team freed up)

**Setup time** : 40 minutes  
**Difficulty** : ⭐⭐⭐ Intermediate (ChatGPT API required)

**File** : `workflows/08-ai-chatbot.json`  
**Docs** : `docs/08-ai-chatbot.md`

---

#### 9. **Predictive Customer Segmentation (AI-powered)** ⭐⭐⭐⭐
**Niche** : E-commerce, SaaS  
**Problem solved** : "We don't know which customers will churn. Retention is reactive."  
**Solution** : ChatGPT analyzes customer behavior → predicts churn risk → auto-action

**What it does** :
- Pulls customer data (purchase history, last purchase date, engagement)
- Sends to ChatGPT for analysis ("Is this customer at risk of churning?")
- Scores customers : High churn risk, medium, low risk
- Tags customers in CRM (automatically)
- Triggers auto-action : High risk = special offer email
- Segments email list by risk tier
- Sends targeted retention campaigns
- Tracks conversion (did intervention work?)

**Inputs** : Customer database (Stripe, Shopify, Airtable)  
**Outputs** : CRM tags + segmentation + email campaigns  
**Time saved** : 5–7 hours/week + revenue impact ⬆️ (retention)

**Setup time** : 50 minutes  
**Difficulty** : ⭐⭐⭐ Intermediate–Advanced

**File** : `workflows/09-predictive-segmentation.json`  
**Docs** : `docs/09-predictive-segmentation.md`

---

#### 10. **Multi-Channel Lead Routing (Smart Distribution)** ⭐⭐⭐⭐
**Niche** : Agencies, SaaS, services  
**Problem solved** : "Leads come from different channels. We can't route efficiently."  
**Solution** : Auto-route leads to best salesperson (by expertise, capacity, timezone)

**What it does** :
- Captures lead from any source (form, email, chat, LinkedIn, API)
- Analyzes lead (ChatGPT reads message → extracts needs)
- Determines best salesperson : Who has capacity? Who has expertise for this niche?
- Routes to Slack channel for assignment
- Sends salesperson Slack notification (with lead summary)
- Logs to CRM (auto-tagged)
- Tracks response time (SLA enforcement)
- Escalates if no response (sends to manager)

**Inputs** : Lead from any channel  
**Outputs** : Slack notification + CRM entry + assignment  
**Time saved** : 2–3 hours/week (sales team coordination)

**Setup time** : 45 minutes  
**Difficulty** : ⭐⭐⭐ Intermediate

**File** : `workflows/10-multi-channel-routing.json`  
**Docs** : `docs/10-multi-channel-routing.md`

---

## 🛠️ Setup Guide

### **Prerequisites**

Before you start, you'll need :

1. **n8n instance** (self-hosted or cloud)
   - Option A : n8n Cloud ($20/mth) ← Recommended for beginners
   - Option B : Self-hosted (Docker) → Free but more setup
   - Sign up : https://n8n.io

2. **API Keys** (depends on workflow)
   - ChatGPT : OpenAI API key (https://platform.openai.com/api-keys)
   - Stripe : Stripe API keys (https://dashboard.stripe.com)
   - Shopify : Shopify access token (https://your-store.myshopify.com/admin/apps)
   - Gmail / Brevo : Email API
   - Airtable : Airtable API key
   - (See each workflow docs for specific requirements)

3. **Tools/Apps** (for testing)
   - Postman (test webhooks) OR curl
   - Browser devtools (debug)

---

### **Step-by-Step Installation**

#### **Step 1 : Create n8n account**
1. Go to https://n8n.io
2. Click "Sign up"
3. Create account (email + password)
4. Verify email
5. Choose cloud plan (start with free tier)
6. You'll see n8n dashboard

#### **Step 2 : Clone this repo**
```bash
git clone https://github.com/halosphere/halosphere-workflows.git
cd halosphere-workflows
```

#### **Step 3 : Choose your first workflow**
Example : `workflows/01-lead-qualification-bot.json`

#### **Step 4 : Import to n8n**
1. In n8n dashboard : Click "Workflows" → "Create new"
2. Click menu (top right) → "Import from file"
3. Select the JSON file
4. Click "Import"
5. n8n will load the workflow

#### **Step 5 : Configure credentials**
1. Each node may show a ⚠️ icon (missing credentials)
2. Click the node → Credentials section
3. Click "Create new" (if credential doesn't exist)
4. Enter your API key / auth token
5. Test connection (green ✓ = success)
6. Repeat for all nodes

#### **Step 6 : Test the workflow**
1. Click "Execute Workflow" (top right)
2. Check output (green ✓ = success)
3. If error → check logs (red ✗) for details

#### **Step 7 : Enable & deploy**
1. Click toggle "Active" (top right, turns blue)
2. Workflow now runs automatically on triggers
3. Monitor : Check "Execution history" periodically

---

## ⚙️ Configuration

### **Environment Variables** (optional, best practice)

Create a `.env` file in the repo root :
```
OPENAI_API_KEY=sk-...
STRIPE_API_KEY=sk_live_...
SHOPIFY_ACCESS_TOKEN=shpat_...
AIRTABLE_API_KEY=key...
BREVO_API_KEY=...
```

*Never commit `.env` to git!* Add to `.gitignore` (already done).

### **Customization**

Each workflow is modular. You can :

**Change email templates** :
- Edit the email node → Modify subject + body
- Use variables : `{{firstName}}` `{{company}}` `{{leadScore}}`

**Change CRM destination** :
- Remove Airtable node, add Notion/Salesforce node instead
- Map fields appropriately

**Change notification channel** :
- Remove Slack node, add Teams/Discord/webhook instead
- Update message format

**Adjust timing** :
- Change delay nodes (3 days → 1 day)
- Change polling frequency (30 min → 1 hour)

See individual workflow docs for specific customization options.

---

## 📖 Examples

### **Example 1 : Lead Qualification Bot**

**Scenario** : Restaurant receives lead via website contact form

**Flow** :
1. Customer submits form : "Hi, interested in catering for 50 people"
2. n8n webhook receives the submission
3. ChatGPT analyzes : "This is HOT lead (event, committed)"
4. Airtable entry created + tags: "HOT | Catering | 50ppl"
5. Email sent to customer (auto-confirm)
6. Slack notified (#leads channel) : "🔥 HOT lead - John Smith wants catering"
7. Restaurant staff clicks Slack link → views full lead + CRM entry
8. Staff replies → Slack threads → 2-way conversation starts
9. Follow-up email sent automatically in 24 hours if no response

**Result** : Lead routed & responded to in < 2 minutes. (Manual = 15 min)

---

### **Example 2 : Shopify Inventory Sync**

**Scenario** : Dropshipper updates supplier sheet, n8n auto-syncs to Shopify

**Flow** :
1. Supplier updates Google Sheets (new stock : 50 units of "Blue T-Shirt M")
2. Every 30 min : n8n checks for changes
3. Detects update (Blue T-Shirt M : 0 → 50)
4. Shopify API : Updates product variant inventory (50 units)
5. Shopify : Re-enables "Buy now" button (was grayed out)
6. Customer sees product available again
7. Alert : If inventory < 5, Slack notification sent to team

**Result** : No overselling. No manual syncing. Revenue recovered (customers could buy now).

---

### **Example 3 : Email Nurture Sequence**

**Scenario** : Customer purchases product. Auto-nurture sequence triggers.

**Flow** :
- **Day 0** : Purchase event fires
- **Day 1 (9 AM)** : Email #1 (Welcome + thank you + usage tips)
- **Day 3 (10 AM)** : Email #2 (Customer testimonial + social proof)
- **Day 7 (11 AM)** : Email #3 (Advanced features + video tutorial)
- **Day 14 (12 PM)** : Email #4 (Special offer + loyalty bonus)

**Result** : Higher engagement + repeat purchases. 30–50% revenue increase observed.

---

## 💬 Support

### **Stuck?**

1. **Check workflow docs** : Each workflow has its own `.md` file in `/docs`
2. **Read error logs** : n8n shows detailed error messages
3. **Discord community** : Join n8n Discord for general help
4. **n8n docs** : https://docs.n8n.io
5. **Issues tab** : Check if someone else had same problem → solution posted

### **Report a bug**

Found an issue? Help improve this repo :

1. Go to GitHub → Issues
2. Click "New issue"
3. Describe : What happened? What should happen?
4. Attach screenshot if helpful
5. Include n8n version + workflow name

### **Contribute**

Have a workflow idea? Want to add one?

1. Fork this repo
2. Create branch : `feature/workflow-name`
3. Add your workflow (JSON file + markdown docs)
4. Create pull request
5. I'll review + merge ✅

---

## 📚 Workflow Difficulty Ratings

| Rating | Meaning | Est. Setup Time |
|--------|---------|-----------------|
| ⭐ | Beginner | 15–20 min |
| ⭐⭐ | Easy | 20–30 min |
| ⭐⭐⭐ | Intermediate | 30–50 min |
| ⭐⭐⭐⭐ | Advanced | 45–60 min |
| ⭐⭐⭐⭐⭐ | Expert | 60+ min |

---

## 🚀 What's Coming Soon

- [ ] **Workflow #11** : SMS automation (Twilio)
- [ ] **Workflow #12** : Social media scheduling (Buffer, Meta)
- [ ] **Workflow #13** : Expense tracking (receipt → accounting software)
- [ ] **Video tutorials** : Setup guide videos for each workflow
- [ ] **n8n template library** : Share workflows directly on n8n (1-click import)
- [ ] **Discord bot** : Build workflows directly from Discord
- [ ] **Zapier parity** : All workflows compatible with Zapier (as backup)

---

## 📄 License

MIT License – Use freely for personal or commercial projects.

**Attribution** : Credit Halo Sphère appreciated but not required 😊

---

## 👥 About Halo Sphère

**Halo Sphère** is an automation & AI agency for SMBs.

We build custom workflows using n8n + ChatGPT to save businesses 10+ hours per week.

**Services** :
- Custom workflow development
- n8n consulting & training
- ChatGPT integration
- Process optimization

**Learn more** : https://halosphere.io  
**Contact** : hello@halosphere.io

---

## 🎯 Quick Links

- **Portfolio** : https://halosphere.io
- **Twitter** : @halosphere
- **LinkedIn** : linkedin.com/company/halosphere
- **YouTube** : youtube.com/@halosphere
- **Email** : hello@halosphere.io

---

## 🙏 Thank you!

If this repo helped you save time, consider :
- ⭐ Star this repo (helps others find it)
- 🤝 Share with a friend who needs automation
- 💬 Feedback : Open an issue or send suggestions
- 🎁 Commission : Use our workflows → refer customers → earn commissions

**Happy automating!** 🚀
