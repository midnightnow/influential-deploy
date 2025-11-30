# AIVA Brand Audit Scoring System
## Automated Call-Based Brand Assessment

---

## OVERVIEW

This system allows AIVA to conduct a **verbal brand audit** during discovery calls, capturing scores in real-time and syncing them to GHL for follow-up.

**Use Cases:**
1. Inbound callers who mention "brand audit" or "assessment"
2. Post-download follow-up calls
3. AI Impact Assessment qualification calls

---

## AIVA VOICE PROMPT - BRAND AUDIT MODE

### Trigger Phrases
When caller says any of:
- "brand audit"
- "I downloaded the worksheet"
- "I want to do the assessment"
- "score my brand"

### AIVA Prompt (Add to GHL Voice Agent)

```
## BRAND AUDIT MODE

When the caller wants to do a brand audit, switch to this mode:

### Opening
"Perfect! I can walk you through a quick brand checkup right now. It takes about 5 minutes and I'll score you on 7 key areas. Ready to start?"

[Wait for confirmation]

### Instructions
"I'll describe each area and you tell me where you'd rate yourself from 1 to 10. Be honest — your lowest score is actually your biggest opportunity."

### Area 1: Message Clarity
"First up: Message Clarity. This is about whether someone can instantly understand what you do and why it matters to them. 

A 1 means your message is confusing or generic — you describe services rather than outcomes.
A 5 means you have some clarity but it's vague — you could fit lots of different firms.
A 10 means crystal clear — you can say 'I help WHO solve PROBLEM so they can OUTCOME' in one sentence.

Where would you score yourself on Message Clarity?"

[Capture: message_clarity_score]

### Area 2: Website Effectiveness
"Next: Website Effectiveness. Does your site turn visitors into enquiries?

A 1 means it's basically a digital brochure — looks professional but generates almost no leads.
A 5 means functional but underperforming — you get some enquiries but they're often price-sensitive.
A 10 means it's a quiet workhorse — consistent qualified leads every month.

Where would you score your website?"

[Capture: website_score]

### Area 3: LinkedIn Presence
"Third: LinkedIn Presence. Is your profile and activity building your expert status?

A 1 means it's basically an online CV — job title headline, wall of text about your history.
A 5 means present but passive — you post occasionally but nothing consistent.
A 10 means authority profile — clear positioning, weekly content, and people mention your posts on calls.

Where would you score your LinkedIn?"

[Capture: linkedin_score]

### Area 4: Google Presence
"Fourth: Google Presence. What happens when someone Googles your name or firm?

A 1 means invisible or messy — you're not on page 1 for your own name.
A 5 means basic footprint — Google Business Profile with some reviews, nothing impressive.
A 10 means confidence-building — strong rating, articles and media appearances show up, prospects feel confident just from the search.

Where would you score your Google presence?"

[Capture: google_score]

### Area 5: Authority Content
"Fifth: Authority Content. Do you have visible proof of your expertise online?

A 1 means best-kept secret — most of your knowledge lives in your head or client work.
A 5 means patchy presence — a few good articles exist but they're scattered and hard to find.
A 10 means obvious expert — you have flagship content, supporting pieces, and prospects arrive pre-sold.

Where would you score your authority content?"

[Capture: authority_score]

### Area 6: Lead Capture
"Sixth: Lead Capture and Nurture. Do you have a system to turn visitors into warm leads?

A 1 means leaky bucket — no lead magnet, no email list, you rely on chance.
A 5 means some capture, little nurture — you have an opt-in but rarely email the list.
A 10 means simple effective funnel — clear lead magnet, helpful email sequence, and subscribers book calls.

Where would you score your lead capture?"

[Capture: lead_capture_score]

### Area 7: Response Speed
"Last one: Response Speed and Call Handling. How quickly do you respond to new enquiries?

A 1 means slow and inconsistent — calls go to voicemail, emails sit for days.
A 5 means generally okay — you get back within 24-48 hours most of the time.
A 10 means always on — calls answered 24/7, every enquiry gets prompt response, prospects comment on how organised you are.

Where would you score your response speed?"

[Capture: response_speed_score]

### Summary & Handoff

[Calculate total]

"Great! Let me add those up... Your total Brand Score is [TOTAL] out of 70.

[If 55-70]: That's a strong foundation! You're in the 'High Value Brand' range. The focus now is optimising what's working and scaling.

[If 35-54]: You've got a solid foundation with some clear opportunities. You're leaving money on the table in a few areas, but that's fixable.

[If 0-34]: There are some significant gaps here, but that's actually good news — every improvement will have real leverage on your results.

Your lowest score was [LOWEST AREA] at [LOWEST SCORE]. That's your biggest opportunity.

Would you like me to have Dallas reach out to walk through these results and help you build a 90-day action plan? He does free AI Impact Assessments for professional services firms."

[If yes → book assessment]
[If no → "No problem. You'll receive an email summary of your scores. Feel free to call back anytime."]
```

---

## GHL CUSTOM FIELDS

### Contact Fields to Create

| Field Name | Field ID | Type | Options |
|------------|----------|------|---------|
| Message Clarity Score | message_clarity_score | Number | 1-10 |
| Website Score | website_score | Number | 1-10 |
| LinkedIn Score | linkedin_score | Number | 1-10 |
| Google Score | google_score | Number | 1-10 |
| Authority Score | authority_score | Number | 1-10 |
| Lead Capture Score | lead_capture_score | Number | 1-10 |
| Response Speed Score | response_speed_score | Number | 1-10 |
| Total Brand Score | total_brand_score | Number | 1-70 |
| Lowest Score Area | lowest_score_area | Dropdown | Message Clarity, Website, LinkedIn, Google, Authority, Lead Capture, Response Speed |
| Brand Audit Date | brand_audit_date | Date | |
| Brand Audit Method | brand_audit_method | Dropdown | AIVA Call, Self-Assessment, Consultant Review |

---

## GHL AUTOMATION - POST AUDIT

### Workflow: Brand Audit Completed (AIVA)

**Trigger:** Custom Field Updated → total_brand_score is not empty

**Actions:**

1. **Calculate Total & Lowest**
   - Math: Sum all 7 scores → total_brand_score
   - Find minimum → lowest_score_area

2. **Tag Based on Score Range**
   - If total_brand_score >= 55 → Tag: "brand-tier: high-value"
   - If total_brand_score 35-54 → Tag: "brand-tier: solid-foundation"
   - If total_brand_score < 35 → Tag: "brand-tier: significant-gaps"

3. **Tag Based on Lowest Area**
   - Tag: "priority: {{lowest_score_area}}"

4. **Send Email Summary**
   ```
   Subject: Your Brand Audit Results: {{total_brand_score}}/70

   Hey {{first_name}},

   Thanks for completing the Brand Audit with AIVA! Here's your scorecard:

   📊 YOUR SCORES
   
   Message Clarity: {{message_clarity_score}}/10
   Website Effectiveness: {{website_score}}/10
   LinkedIn Presence: {{linkedin_score}}/10
   Google Presence: {{google_score}}/10
   Authority Content: {{authority_score}}/10
   Lead Capture: {{lead_capture_score}}/10
   Response Speed: {{response_speed_score}}/10

   ━━━━━━━━━━━━━━━━
   TOTAL: {{total_brand_score}}/70
   ━━━━━━━━━━━━━━━━

   🎯 YOUR PRIORITY AREA
   
   Your lowest score was {{lowest_score_area}} at {{lowest_score}}/10.

   This is your biggest opportunity. Fix this first, and everything else gets easier.

   📅 NEXT STEP
   
   Want help building a 90-day action plan to move that score from a {{lowest_score}} to a 7+?

   Book your free AI Impact Assessment:
   https://calendly.com/dallasm/15min

   Talk soon,
   Dallas & AIVA

   P.S. If your Response Speed score was low, ask me about AIVA — our AI receptionist that answers calls 24/7 so you never miss an opportunity.
   ```

5. **Add to Pipeline**
   - Pipeline: AIVA Brand Audit
   - Stage: Based on score tier

6. **Internal Notification**
   - To: Dallas
   - "New Brand Audit completed: {{contact.name}} scored {{total_brand_score}}/70. Lowest area: {{lowest_score_area}}. {{if total_brand_score < 35}}⚠️ Significant gaps - high priority follow-up{{/if}}"

---

## SMART LISTS FOR FOLLOW-UP

### List: Low Response Speed Scores
**Filter:** response_speed_score <= 4
**Use:** AIVA upsell campaign

### List: High-Value Brand Tier
**Filter:** total_brand_score >= 55
**Use:** Consulting/Strategy upsell

### List: Significant Gaps
**Filter:** total_brand_score < 35
**Use:** Priority follow-up, done-for-you services

### List: Message Clarity Priority
**Filter:** lowest_score_area = "Message Clarity"
**Use:** Positioning workshop invite

### List: Authority Content Priority
**Filter:** lowest_score_area = "Authority Content"
**Use:** Kindle book / content engine offer

---

## REPORTING DASHBOARD

### Metrics to Track

**Volume:**
- Brand audits completed (weekly/monthly)
- Audit method breakdown (AIVA vs Self vs Consultant)

**Scores:**
- Average total score
- Score distribution by tier
- Most common lowest area (pie chart)

**Conversion:**
- Audit → Assessment booked rate
- Audit → Paid service rate
- Revenue attributed to brand audit leads

**Insights:**
- Score correlation with deal value
- Industry breakdown of scores
- Score improvement over time (repeat audits)

---

## ADVANCED: COMPARATIVE SCORING

### Industry Benchmarks (To Build Over Time)

| Industry | Avg Total | Typical Lowest |
|----------|-----------|----------------|
| Accounting/Tax | 42 | Response Speed |
| Business Consulting | 38 | Authority Content |
| Financial Planning | 45 | Lead Capture |
| Legal | 40 | LinkedIn |
| Healthcare | 35 | Website |

### AIVA Can Reference Benchmarks
"Your total of 42 is actually above average for accounting firms — most score around 40. But your Response Speed at 3 is a common pain point in your industry."

---

## INTEGRATION WITH CALLSCORE

If using CallScore or similar call analytics:

1. **Auto-tag calls** where brand audit was conducted
2. **Extract scores** from transcript using AI
3. **Flag incomplete audits** (caller hung up mid-assessment)
4. **Score AIVA's delivery** (did it explain each area clearly?)

---

## QUICK START CHECKLIST

- [ ] Create 10 custom fields in GHL (7 scores + total + lowest + date + method)
- [ ] Add Brand Audit Mode prompt to AIVA Voice Agent
- [ ] Set up "Brand Audit Completed" workflow
- [ ] Create email template for score summary
- [ ] Build "AIVA Brand Audit" pipeline with 3 stages
- [ ] Create 5 smart lists for segmented follow-up
- [ ] Test full flow: Call AIVA → Complete audit → Check email arrives → Verify GHL fields populated

---

## SAMPLE CALL TRANSCRIPT

**AIVA:** "Hey there! Thanks for calling AIVA at Influential Digital. How can I help you today?"

**Caller:** "Hi, I downloaded the brand audit worksheet but I'd rather just do it over the phone."

**AIVA:** "Perfect! I can walk you through a quick brand checkup right now. It takes about 5 minutes and I'll score you on 7 key areas. Ready to start?"

**Caller:** "Yeah, let's do it."

**AIVA:** "Great. I'll describe each area and you tell me where you'd rate yourself from 1 to 10. Be honest — your lowest score is actually your biggest opportunity. First up: Message Clarity..."

[...continues through all 7 areas...]

**AIVA:** "...Your total Brand Score is 38 out of 70. You've got a solid foundation with some clear opportunities. Your lowest score was Authority Content at 3. That's your biggest opportunity. Would you like me to have Dallas reach out to walk through these results?"

**Caller:** "Yeah, that would be great."

**AIVA:** "Wonderful. What's the best email to send your score summary and booking link?"

[Captures email, sends confirmation, books callback]
