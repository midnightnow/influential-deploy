# GHL QUICK DEPLOY GUIDE
## Influential Digital Week 1 - Brand Audit Funnel
### Everything You Need in One Place

```
Time Required: ~2.5 hours
Status: READY TO DEPLOY
```

---

## PART 1: AIVA VOICE AGENT (30 min)

### Step 1: Open GHL Voice AI

1. Log into GHL
2. Navigate to: **Conversations → Voice AI**
3. Select your AIVA agent

### Step 2: Replace System Prompt

Delete the current prompt and paste this entire block:

```
## AIVA VOICE AGENT PROMPT - INFLUENTIAL DIGITAL

You are AIVA, the AI receptionist for Influential Digital.
Your phone number is +61 468 080 000.

### CORE IDENTITY
- Name: AIVA (AI Virtual Assistant)
- Company: Influential Digital
- Owner: Dallas McMillan
- Location: Cairns, Australia (work with clients nationally/internationally)
- Tone: Warm, professional, helpful. Australian-friendly.

### PRIMARY GOAL
Convert callers into booked "AI Impact Assessment" calls with Dallas.
This is a FREE 15-minute strategy session.

### GREETING
"Hi, this is AIVA from Influential Digital. Thanks for calling! How can I help you today?"

### DISCOVERY QUESTIONS (Use 2-3)
1. "What kind of business are you in?"
2. "How are you currently handling your marketing and client attraction?"
3. "What's your biggest challenge right now when it comes to standing out online?"
4. "Have you thought about using AI to help with client communication?"

### QUALIFICATION QUESTION
"It sounds like you might benefit from our AI Impact Assessment. This is a free 15-minute call with Dallas where he'll show you exactly how AI tools like me could work for your specific business. Would you like me to book that for you?"

### BOOKING RESPONSE
If YES: "Perfect! I'll transfer you to our booking system. You'll be able to choose a time that works for you. Is there anything else I can help with before I do that?"

If NO/HESITANT: "No problem at all. Can I send you some information about how we help professional service firms stand out online? Just need your email address."

### BRAND AUDIT MODE
If caller mentions "brand audit", "downloaded worksheet", or "brand assessment":

Switch to this flow:
1. "Great! You've got the Brand Audit Worksheet. Have you had a chance to score yourself on the 7 areas yet?"
2. "Which area did you score lowest on?"
3. "That's actually one of the most common issues we see. Would you like to discuss it in a quick AI Impact Assessment call with Dallas? It's free and only takes 15 minutes."

### KEY INFORMATION TO SHARE
- Influential Digital helps professional service firms build "High Value Brands"
- We use AI, authority content, and automated sales systems
- Dallas has 10+ years experience in digital marketing for professionals
- The AI Impact Assessment is FREE and shows exactly how AI can help your specific business

### OBJECTION HANDLING
"I'm just looking": "Totally understand! Many of our best clients started by just exploring. The AI Impact Assessment is no-pressure - it's really just to show you what's possible."

"How much does it cost?": "Great question! We have different options depending on your needs. The best way to find out what would work for you is in a quick chat with Dallas. Shall I book that?"

"I'll think about it": "Of course! Would you like me to send you some information to review? I just need your email."

### CLOSING
Always end with:
"Thanks so much for calling Influential Digital. Have a great day!"

### TRANSFER/BOOKING
When ready to book: Transfer to Calendly or GHL booking widget.
URL: https://calendly.com/dallasm/15min
```

### Step 3: Save and Test

1. Click **Save**
2. Call +61 468 080 000 from your mobile
3. Test these scenarios:
   - General inquiry ("I'm interested in what you do")
   - Brand audit mention ("I downloaded the brand audit worksheet")
   - Booking request ("I'd like to book a call")

---

## PART 2: BRAND AUDIT FUNNEL (90 min)

### Step 1: Upload PDF (5 min)

1. Go to **Media Library**
2. Click **Upload**
3. Select: `Brand_Audit_Worksheet_Professional.pdf`
4. Copy the public URL

### Step 2: Create Funnel (10 min)

1. Go to **Sites → Funnels**
2. Click **+ New Funnel**
3. Name: "Brand Audit Funnel"
4. Add 2 pages: "Opt-in" and "Thank You"

### Step 3: Build Opt-in Page (30 min)

**Header Section:**
- Logo: Influential Digital
- Headline: **"Is Your Brand Working As Hard As You Are?"**
- Subheadline: "Most professional service firms are the best-kept secret in their market. This free Brand Audit Worksheet reveals exactly where your brand is strong—and where it's silently costing you clients."

**Form Section:**
- Fields: First Name, Email, Business Name (optional)
- Button: **"Get My Brand Audit Worksheet"**
- Button color: #2563EB (blue)

**What You'll Discover Section:**
- The 7 critical areas that determine whether clients find you or your competitors
- Your personal "Brand Score" across Message, Website, LinkedIn, Google, Authority, Lead Capture, and Response Speed
- Which single area, if fixed, would have the biggest impact on your client attraction

**Who This Is For:**
- Professional service firms ($1M-$50M revenue)
- Accountants, lawyers, consultants, financial advisors
- Business owners who want to attract better clients, not just more clients

**Social Proof (if available):**
- "This worksheet helped me identify exactly why our referrals had dried up." - [Client Name]

### Step 4: Build Thank You Page (15 min)

**Content:**
- Headline: **"Check Your Inbox!"**
- Message: "Your Brand Audit Worksheet is on its way. While you wait, here's something even better..."
- Sub-message: "Want to discuss your results with an expert? Book a FREE 15-minute AI Impact Assessment with Dallas."
- Button 1: **"Book My Free Assessment"** → https://calendly.com/dallasm/15min
- Button 2: **"Call AIVA Now"** → tel:+61468080000
- Backup: "Didn't get the email? [Download directly here]" → PDF URL

### Step 5: Create Email Automation (20 min)

**Trigger:** Form submission on Brand Audit opt-in

**Email 1 - Immediate (Day 0):**
```
Subject: Your Brand Audit Worksheet is here

Hi {{contact.first_name}},

Here's your Brand Audit Worksheet as promised.

[DOWNLOAD BUTTON → PDF URL]

This worksheet helps you score your brand across 7 critical areas:
1. Message Clarity
2. Website Experience
3. LinkedIn Presence
4. Google Visibility
5. Authority Positioning
6. Lead Capture
7. Response Speed

Take 15 minutes to complete it honestly. The insights might surprise you.

When you're done, I'd love to discuss your results in a quick AI Impact Assessment call. It's free and takes just 15 minutes.

[BOOK YOUR CALL → Calendly link]

Or call AIVA directly: +61 468 080 000

Cheers,
Dallas McMillan
Influential Digital
```

**Email 2 - Day 2:**
```
Subject: Did you complete your Brand Audit?

Hi {{contact.first_name}},

Quick check-in on your Brand Audit Worksheet.

Have you had a chance to score yourself across the 7 areas?

If not, here's the worksheet again: [DOWNLOAD]

If yes, what was your lowest score?

Most professionals I work with score lowest on either:
- Authority Positioning (being seen as the expert)
- Response Speed (how fast you respond to inquiries)

Both of these are fixable with the right systems.

Want to discuss your specific results? Book a free 15-minute call:
[BOOK NOW → Calendly]

Dallas
```

**Email 3 - Day 4:**
```
Subject: The one thing that would change everything

Hi {{contact.first_name}},

Here's something most business owners don't realize:

You don't need to fix all 7 areas of your brand.

You just need to fix ONE.

The one that's causing the biggest leak in your client attraction system.

For some, it's their website (looks outdated, doesn't convert).
For others, it's their Google presence (invisible to local searches).
For many, it's response speed (leads go cold while waiting for a reply).

The Brand Audit Worksheet helps you identify YOUR one thing.

Want help figuring out which area would have the biggest impact for you?

[BOOK A FREE 15-MIN CALL → Calendly]

Dallas
```

**Email 4 - Day 7:**
```
Subject: Your AI Impact Assessment invitation

Hi {{contact.first_name}},

I wanted to personally invite you to an AI Impact Assessment.

In 15 minutes, I'll show you:
- How AI tools like AIVA (our AI receptionist) could work for YOUR business
- Which of the 7 brand areas is costing you the most clients
- A simple 90-day roadmap to fix it

This call is free. No pitch, no pressure—just practical insights you can use immediately.

[BOOK YOUR CALL → Calendly]

Or call AIVA now: +61 468 080 000

Talk soon,
Dallas McMillan
Influential Digital
```

### Step 6: Set Up Tags & Automation

**Tags to add on form submission:**
- `brand-audit-downloaded`
- `lead-source:brand-audit`

**Automation flow:**
1. Form submitted → Add tags
2. Wait 0 min → Send Email 1
3. Add to Campaign "Brand Audit Nurture"

---

## PART 3: GO LIVE (15 min)

### Pre-Launch Checklist

- [ ] AIVA script deployed and tested
- [ ] Opt-in page looks good on mobile
- [ ] Form submission works
- [ ] PDF delivers in email
- [ ] Thank you page displays correctly
- [ ] All links work (Calendly, phone, PDF)

### Launch Steps

1. Set funnel status to **Published**
2. Test live URL one more time
3. Post to LinkedIn (see article in archive)
4. Send to email list

### Monitor

Watch these for first 24 hours:
- GHL funnel analytics (views, submissions)
- Email delivery stats
- AIVA call logs

---

## QUICK REFERENCE

| Asset | Location |
|-------|----------|
| AIVA Prompt | Above (copy-paste) |
| PDF | `Brand_Audit_Worksheet_Professional.pdf` |
| Landing Page Copy | `Brand_Audit_Optin_Landing_Page.md` |
| Full AIVA Script | `AIVA_COMPLETE_CALL_SCRIPT.md` |
| QA Checklist | `PRE_LAUNCH_QA_CHECKLIST.md` |
| Hardened Sequence | `HARDENED_EXECUTION_SEQUENCE.md` |
| **Copy Library** | `AIVA_PROBLEMS_SOLUTIONS_LIBRARY.md` |

---

## COPY LIBRARY (For Page Builders)

The `AIVA_PROBLEMS_SOLUTIONS_LIBRARY.md` contains modular copy blocks you can mix and match:

| Format | Best For |
|--------|----------|
| Problem/Solution Tables | Landing page proof sections |
| Before/After Tables | Transformation widgets |
| Single Headlines | Ad copy, email subjects |
| PAS Long-Form | Sales pages, nurture emails |
| Industry-Specific | Vertical landing pages |

**Recommended for Brand Audit funnel:**
- "Missed calls?" → AIVA 24/7
- "Sound like everyone else?" → Brand Audit
- "Too busy to market?" → Automation

**Recommended for AIVA-specific funnel:**
- Full Before/After AIVA table
- Response Speed problem set
- Capacity problem set

---

## SUCCESS METRICS (Week 1)

| Metric | Target |
|--------|--------|
| Page Views | 50+ |
| Opt-ins | 10+ |
| Email Opens | 40%+ |
| AI Impact Assessments | 2+ |

---

*Document created: November 29, 2025*
*Status: READY TO EXECUTE*
