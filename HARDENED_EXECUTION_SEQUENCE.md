# HARDENED EXECUTION SEQUENCE
## Influential Digital v2025.1 - Launch Protocol
### Red Zen Gemini Validated

```
Status: READY TO EXECUTE
Total Time: ~2.5 hours
Confidence: VERY HIGH
Risk Level: MINIMIZED (testing integrated at each step)
```

---

## OVERVIEW

This is a refined execution sequence that integrates testing into each build step, eliminating the high-stakes QA block at the end.

**Key Principle:** Build → Verify at each step, not Build → Build → Build → Test.

---

## PHASE 1: AIVA HARDENING & ACTIVATION (30 minutes)

**Objective:** Deploy the complete pitch script to AIVA and verify it works.

### Step 1a: Deploy (5 min)

1. Log into GHL → Conversations → Voice AI
2. Select AIVA agent
3. Open `AIVA_GHL_PROMPT.txt` (in this folder)
4. Copy entire content
5. Paste into GHL system prompt field
6. Save changes

### Step 1b: Define & Execute Test Cases (25 min)

| Test Case | Input | Expected Behavior | Status |
|-----------|-------|-------------------|--------|
| **Happy Path** | "Hi, I'm interested in learning more about what you do" | AIVA follows pitch flow: Greeting → Discovery questions → Qualification → CTA | [ ] |
| **Brand Audit Intent** | "I downloaded the brand audit worksheet" | AIVA switches to Brand Audit Mode, asks about business | [ ] |
| **Boundary Case** | Mumbled or partial response | AIVA asks clarifying question, recovers gracefully | [ ] |
| **Negative Case** | "Wrong number" or "Not interested" | AIVA ends politely, thanks for calling | [ ] |
| **System Test** | After call, check GHL | Contact updated, call logged, correct tags applied | [ ] |

**Test number:** +61 468 080 000

### Phase 1 Checklist
- [ ] Script deployed to GHL
- [ ] Happy path test passed
- [ ] Brand audit intent test passed
- [ ] Boundary case handled
- [ ] Negative case handled
- [ ] GHL contact record correct

---

## PHASE 2: FUNNEL ASSEMBLY & INTEGRATED TESTING (105 minutes)

**Objective:** Build the Week 1 funnel with testing at each component.

### Step 2a: Asset & Environment Prep (10 min)

| Task | Action | Verification | Status |
|------|--------|--------------|--------|
| Upload PDF | Upload `Brand_Audit_Worksheet_Professional.pdf` to GHL Media Library | Get public URL, test download | [ ] |
| Domain Check | Verify funnel domain has valid SSL | Visit https://[domain] in browser, check lock icon | [ ] |
| Email Domain | Verify sending domain (SPF/DKIM records) | Check GHL Settings → Email | [ ] |

**CRITICAL:** Email deliverability check is essential. Spam folder issues are a common launch failure.

### Step 2b: Build & Unit Test: Pages (45 min)

**Opt-in Page (30 min)**

1. Create new funnel: "Brand Audit Funnel"
2. Add page: "Opt-in"
3. Copy content from `Brand_Audit_Optin_Landing_Page.md`:
   - Headline: "Is Your Brand Working As Hard As You Are?"
   - Subheadline: Copy the promise
   - Form fields: Name, Email, Business Name
   - Button: "Get My Brand Audit Worksheet"

**Unit Tests:**
- [ ] Form submits with valid email
- [ ] Form rejects invalid email (shows error)
- [ ] Page renders on mobile (check Chrome DevTools)
- [ ] Page renders on desktop
- [ ] Analytics/tracking firing (check DevTools Network tab)

**Thank You Page (15 min)**

1. Add page: "Thank You"
2. Message: "Check Your Inbox!"
3. Include PDF download link as backup
4. Add: "Questions? Call AIVA: +61 468 080 000"

**Unit Tests:**
- [ ] PDF link works (downloads file)
- [ ] Page renders on mobile
- [ ] Page renders on desktop

### Step 2c: Build & Unit Test: Automation (25 min)

1. Create automation trigger: "On Form Submit (Brand Audit)"
2. Actions:
   - Wait 0 min
   - Send Email (Brand Audit delivery - Day 0)
   - Add Tag: "brand-audit-downloaded"
   - Add to Campaign: "Brand Audit Nurture"
3. Create Campaign emails:
   - Day 0: PDF delivery (from landing page doc)
   - Day 2: Completion nudge
   - Day 4: The One Thing
   - Day 7: AI Impact Assessment invite

**Unit Tests:**
- [ ] Send test email to Gmail account - check spam folder
- [ ] Send test email to Outlook.com - check spam folder
- [ ] Email renders correctly (images load, links work)
- [ ] Automation triggers on test submission

### Step 2d: End-to-End Test (25 min)

**Use incognito browser + non-company test email**

| Step | Action | Expected Result | Status |
|------|--------|-----------------|--------|
| 1 | Visit opt-in page | Page loads, form visible | [ ] |
| 2 | Submit form with test email | Redirect to Thank You page | [ ] |
| 3 | Check email inbox | Email arrives within 5 min | [ ] |
| 4 | Open email | PDF attachment/link works | [ ] |
| 5 | Check GHL | Contact created, correct tags, in automation | [ ] |
| 6 | Call +61 468 080 000 | AIVA answers with new script | [ ] |
| 7 | Mention brand audit | AIVA switches to Brand Audit Mode | [ ] |

### Phase 2 Checklist
- [ ] PDF uploaded, URL works
- [ ] Opt-in page built and tested
- [ ] Thank you page built and tested
- [ ] Automation created
- [ ] Emails pass spam filter test
- [ ] End-to-end test passed

---

## PHASE 3: GO-LIVE & MONITOR (15 min + ongoing)

**Objective:** Launch and verify system is working in production.

### Step 3a: Go-Live (5 min)

1. Enable funnel (set to "Published")
2. Perform final smoke test on LIVE URL
3. Verify:
   - [ ] Live URL accessible
   - [ ] Form submits correctly
   - [ ] Thank you page displays
   - [ ] Email sends (check your own inbox)

### Step 3b: Announce (5 min)

1. Post LinkedIn article (from `Week_01_LinkedIn_Article_Brand_Audit.md`)
2. Send email to existing list with opt-in link
3. Add link to email signature

### Step 3c: Monitor (5 min initial, then hourly for first day)

| Metric | Where to Check | Alert Threshold |
|--------|----------------|-----------------|
| Page views | GHL Funnels Analytics | >0 = working |
| Form submissions | GHL Contacts | No submissions in 2 hours = check |
| Email sends | GHL Automations | Failed sends = immediate action |
| AIVA calls | GHL Voice | Track all |
| Errors | GHL Dashboard | Any errors = immediate action |

### Phase 3 Checklist
- [ ] Funnel live
- [ ] Smoke test passed
- [ ] LinkedIn posted
- [ ] Email sent
- [ ] Monitoring active

---

## SUCCESS METRICS (Week 1)

| Metric | Target | Tracking Location |
|--------|--------|-------------------|
| Page Views | 50+ | GHL Analytics |
| Opt-ins | 10+ | GHL Contacts |
| Email Opens | 40%+ | GHL Email Stats |
| AIVA Calls | Track all | GHL Voice Logs |
| AI Impact Assessments | 2+ | Calendly |

---

## MINIMUM VIABLE LAUNCH DEFINITION

The system is **LIVE** when:

- [x] Brand Audit opt-in page is accessible
- [x] PDF is delivered on submission
- [x] AIVA can handle brand audit conversations
- [x] Path to AI Impact Assessment is clear
- [x] Monitoring is active

---

## QUICK REFERENCE FILES

| File | Purpose |
|------|---------|
| `AIVA_GHL_PROMPT.txt` | Copy-paste into GHL Voice AI |
| `Brand_Audit_Worksheet_Professional.pdf` | Upload to GHL Media |
| `Brand_Audit_Optin_Landing_Page.md` | Copy for opt-in page |
| `AIVA_COMPLETE_CALL_SCRIPT.md` | Full call script reference |
| `PRE_LAUNCH_QA_CHECKLIST.md` | Detailed QA protocol |

---

## EXECUTION SUMMARY

```
┌─────────────────────────────────────────────────────────────────────────┐
│                                                                          │
│   HARDENED EXECUTION SEQUENCE                                           │
│                                                                          │
│   Phase 1: AIVA Hardening (30 min)                                      │
│   └── Deploy script + 5 test cases                                      │
│                                                                          │
│   Phase 2: Funnel Assembly (105 min)                                    │
│   ├── 2a: Asset prep (10 min)                                          │
│   ├── 2b: Pages + unit tests (45 min)                                  │
│   ├── 2c: Automation + unit tests (25 min)                             │
│   └── 2d: End-to-end test (25 min)                                     │
│                                                                          │
│   Phase 3: Go-Live (15 min + monitoring)                                │
│   ├── Enable funnel                                                     │
│   ├── Announce                                                          │
│   └── Monitor                                                           │
│                                                                          │
│   TOTAL: ~2.5 hours to live funnel with validated quality              │
│                                                                          │
└─────────────────────────────────────────────────────────────────────────┘
```

---

*Document created: November 29, 2025*
*Validated by: Red Zen Gemini ThinkDeep*
*Confidence: VERY HIGH*
