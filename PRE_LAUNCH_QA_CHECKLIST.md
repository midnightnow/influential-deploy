# PRE-LAUNCH QA CHECKLIST
## Brand Audit Funnel - Quality Assurance Protocol
### Influential Digital v2025.1

```
Status: READY FOR QA
Purpose: Ensure everything works before going live
Time Required: 60-90 minutes
```

---

## CRITICAL PATH TEST (Do This First)

**The Happy Path:** A prospect downloads the worksheet and books a call.

```
VISIT OPT-IN → SUBMIT FORM → RECEIVE EMAIL → DOWNLOAD PDF → CALL AIVA → BOOK ASSESSMENT
```

### Quick Smoke Test (15 minutes)

- [ ] **1. Load opt-in page** - Does it render correctly on desktop?
- [ ] **2. Submit test form** - Does it accept: Name, Email, Business Type?
- [ ] **3. Check redirect** - Does Thank You page appear?
- [ ] **4. Check inbox** - Does Email 1 arrive within 2 minutes?
- [ ] **5. Download PDF** - Does the link work? Is it the styled version?
- [ ] **6. Call AIVA** - Does +61 468 080 000 answer?
- [ ] **7. Say "brand audit"** - Does AIVA enter audit mode?

**If any step fails: STOP. Fix before continuing.**

---

## DETAILED QA SECTIONS

### Section 1: Landing Page QA

#### Desktop Testing
- [ ] Page loads in <3 seconds
- [ ] All sections render correctly
- [ ] Images/mockups display properly
- [ ] Headline visible above the fold
- [ ] Form is visible without scrolling
- [ ] Trust line shows below form
- [ ] No broken links
- [ ] Calendly link works
- [ ] AIVA phone number clickable (tel: link)

#### Mobile Testing (iPhone/Android)
- [ ] Page is responsive
- [ ] Text is readable without zooming
- [ ] Form fields are tappable
- [ ] Keyboard doesn't obscure form
- [ ] Submit button is thumb-reachable
- [ ] Phone number is tap-to-call

#### Form Testing
- [ ] Name field accepts text
- [ ] Email field validates format
- [ ] Business Type dropdown works
- [ ] Submit button is clearly visible
- [ ] Error messages show for invalid input
- [ ] Double-submit prevention works

#### Thank You Page
- [ ] Redirect happens immediately after submit
- [ ] Correct URL (no form resubmission on refresh)
- [ ] "Check Your Inbox" message displays
- [ ] Assessment booking CTA visible
- [ ] Calendly link works
- [ ] AIVA phone number visible

---

### Section 2: Email Delivery QA

#### Email 1 (Immediate Delivery)
- [ ] Arrives within 2 minutes of form submit
- [ ] Subject line: "Your Brand Audit Worksheet is here"
- [ ] From name: Dallas / Influential Digital
- [ ] PDF download link works
- [ ] No broken images
- [ ] Personalization {{first_name}} renders correctly
- [ ] Reply-to address is monitored

#### Deliverability Testing
Test with multiple email providers:

| Provider | Inbox? | Spam? | Notes |
|----------|--------|-------|-------|
| Gmail | [ ] | [ ] | |
| Outlook | [ ] | [ ] | |
| Yahoo | [ ] | [ ] | |
| iCloud | [ ] | [ ] | |
| Proton | [ ] | [ ] | |

#### Email Sequence Timing (Verify Automation)
- [ ] Email 1: Immediate (0 hours)
- [ ] Email 2: Day 2 (48 hours)
- [ ] Email 3: Day 4 (96 hours)
- [ ] Email 4: Day 7 (168 hours)

#### Email Content Check
For each email:
- [ ] Subject line displays correctly
- [ ] Body renders properly (no HTML issues)
- [ ] Links are clickable and correct
- [ ] Unsubscribe link present and works
- [ ] Mobile-friendly layout

---

### Section 3: PDF Quality Check

#### File Verification
- [ ] `Brand_Audit_Worksheet_Professional.pdf` exists
- [ ] File size reasonable (500KB - 1MB)
- [ ] Opens correctly in Adobe Reader
- [ ] Opens correctly in Preview (macOS)
- [ ] Opens correctly in Chrome PDF viewer
- [ ] Opens correctly on mobile

#### Content Check
- [ ] Cover page renders with correct branding
- [ ] All 7 scoring sections present
- [ ] Score circles display correctly
- [ ] Tables render properly
- [ ] CTA section shows Calendly + AIVA
- [ ] Footer shows correct copyright
- [ ] No typos or formatting errors
- [ ] Print-friendly (test actual print)

---

### Section 4: AIVA Voice Agent QA

#### Connection Test
- [ ] +61 468 080 000 rings
- [ ] AIVA answers within 3 rings
- [ ] Greeting is clear and professional
- [ ] Audio quality is good

#### Brand Audit Mode Test
Say each trigger phrase and verify response:

| Trigger Phrase | AIVA Enters Audit Mode? |
|----------------|-------------------------|
| "brand audit" | [ ] |
| "I downloaded the worksheet" | [ ] |
| "I want to do the assessment" | [ ] |
| "score my brand" | [ ] |

#### Full Audit Flow Test
Complete a full 7-area audit:

- [ ] Opening explanation is clear
- [ ] Area 1 (Message Clarity) prompt works
- [ ] Area 2 (Website) prompt works
- [ ] Area 3 (LinkedIn) prompt works
- [ ] Area 4 (Google) prompt works
- [ ] Area 5 (Authority) prompt works
- [ ] Area 6 (Lead Capture) prompt works
- [ ] Area 7 (Response Speed) prompt works
- [ ] Total is calculated correctly
- [ ] Tier response is appropriate (test all 3)
- [ ] Lowest area is identified correctly
- [ ] Booking offer is made
- [ ] Email summary is sent (if opted in)

#### Edge Cases
- [ ] Caller says "I don't know" - AIVA prompts for estimate
- [ ] Caller interrupts - AIVA handles gracefully
- [ ] Caller hangs up mid-audit - Partial data saved
- [ ] Caller asks to restart - AIVA can reset

---

### Section 5: GHL Backend Verification

#### Contact Record Check
After test form submission:
- [ ] Contact created in GHL
- [ ] Name field populated
- [ ] Email field populated
- [ ] Business Type field populated
- [ ] Tag `brand-audit-downloaded` applied
- [ ] Tag `lead-source: brand-audit` applied
- [ ] Added to "Brand Audit" email sequence
- [ ] Pipeline stage: "Lead Magnet Downloaded"

#### Custom Fields (After AIVA Audit)
- [ ] message_clarity_score populated
- [ ] website_score populated
- [ ] linkedin_score populated
- [ ] google_score populated
- [ ] authority_score populated
- [ ] lead_capture_score populated
- [ ] response_speed_score populated
- [ ] total_brand_score calculated
- [ ] lowest_score_area identified
- [ ] brand_audit_date set
- [ ] brand_audit_method set (AIVA Call)

#### Automation Triggers
- [ ] Form submit → Email 1 fires immediately
- [ ] Form submit → Sequence starts
- [ ] AIVA audit complete → Score summary email sends
- [ ] Calendly booking → Contact moves to "Assessment Booked"

---

### Section 6: Analytics & Tracking

#### Event Tracking (Critical per Gemini)
Verify these events fire correctly:

| Event | Fires? | Data Correct? |
|-------|--------|---------------|
| Opt-in page load | [ ] | [ ] |
| Form viewed | [ ] | [ ] |
| Form started | [ ] | [ ] |
| Form submitted | [ ] | [ ] |
| Thank you page load | [ ] | [ ] |
| CTA button clicked | [ ] | [ ] |
| Calendly opened | [ ] | [ ] |

#### Attribution Tracking
- [ ] UTM parameters pass through form
- [ ] Source/Medium captured
- [ ] Campaign captured
- [ ] Content/Term captured (if used)

---

### Section 7: Security & Compliance

#### Form Security
- [ ] HTTPS on all pages
- [ ] Form data transmitted securely
- [ ] No sensitive data in URL parameters
- [ ] CAPTCHA or honeypot present (if needed)

#### Email Compliance
- [ ] Physical address in email footer
- [ ] Unsubscribe link present
- [ ] CAN-SPAM compliant
- [ ] GDPR notice (if targeting EU)

#### Data Privacy
- [ ] Privacy policy linked on opt-in page
- [ ] Clear consent statement
- [ ] Data stored securely in GHL

---

## TEST ACCOUNTS

Use these for testing:

| Purpose | Email | Notes |
|---------|-------|-------|
| Primary Test | `test+brandaudit1@[yourdomain]` | Main test account |
| Gmail Test | `[personal]@gmail.com` | Deliverability check |
| Outlook Test | `[personal]@outlook.com` | Microsoft deliverability |
| Mobile Test | `[personal phone email]` | Mobile rendering |

---

## QA SIGN-OFF

### Pre-Launch Approval

| Area | Tested By | Date | Status |
|------|-----------|------|--------|
| Landing Page | | | [ ] Pass |
| Email Delivery | | | [ ] Pass |
| PDF Quality | | | [ ] Pass |
| AIVA Voice | | | [ ] Pass |
| GHL Backend | | | [ ] Pass |
| Analytics | | | [ ] Pass |
| Security | | | [ ] Pass |

### Final Checklist

- [ ] All critical path steps work
- [ ] No broken links anywhere
- [ ] Emails deliver to inbox (not spam)
- [ ] PDF opens on all platforms
- [ ] AIVA handles audit correctly
- [ ] Data flows to GHL correctly
- [ ] Analytics tracking verified

### Sign-Off

```
QA Completed By: _____________________

Date: _____________________

Status: [ ] APPROVED FOR LAUNCH  [ ] NEEDS FIXES

Notes:
_______________________________________
_______________________________________
_______________________________________
```

---

## POST-LAUNCH MONITORING (First 48 Hours)

### Hour 1 Checks
- [ ] First organic submission received?
- [ ] Email delivered successfully?
- [ ] No error alerts from GHL?

### Day 1 Checks
- [ ] Review all form submissions
- [ ] Check email delivery rates
- [ ] Review AIVA call logs
- [ ] Check for any support requests

### Day 2 Checks
- [ ] Email 2 firing correctly?
- [ ] Any spam complaints?
- [ ] Conversion rate acceptable?
- [ ] Any unexpected user behavior?

---

## EMERGENCY CONTACTS

| Issue | Contact | Method |
|-------|---------|--------|
| GHL Technical | GHL Support | In-app chat |
| AIVA Issues | AIVA Support | [support email] |
| Domain/DNS | GoDaddy/Cloudflare | Account login |
| Urgent | Dallas | [phone] |

---

```
┌─────────────────────────────────────────────────────────────────┐
│                                                                  │
│   QA CHECKLIST STATUS                                           │
│                                                                  │
│   Landing Page:      [ ] Tested                                 │
│   Email Delivery:    [ ] Tested                                 │
│   PDF Quality:       [ ] Tested                                 │
│   AIVA Voice:        [ ] Tested                                 │
│   GHL Backend:       [ ] Tested                                 │
│   Analytics:         [ ] Tested                                 │
│   Security:          [ ] Tested                                 │
│                                                                  │
│   READY FOR LAUNCH:  [ ] YES  [ ] NO                            │
│                                                                  │
└─────────────────────────────────────────────────────────────────┘
```

---

**Document Created:** November 29, 2025
**Status:** READY FOR QA EXECUTION
**Time Estimate:** 60-90 minutes for complete QA

---

*"Trust, but verify. Then ship."*

**INFLUENTIAL.DIGITAL**
v2025.1 | QA PROTOCOL
