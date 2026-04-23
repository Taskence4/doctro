# Unit Economics
## Referral Doctor Digital Presence Program — Internal Document
### AI Lab | April 2026

> **Internal use only. Do not share with clients or doctors.**

---

## SECTION 1: VARIABLE COST PER DOCTOR PER MONTH

These are the direct, per-doctor costs incurred each month the subscription is active.

### 1A — Tool Costs (Variable, Per Doctor)

| Tool / Category | T1 Presence | T2 Growth Engine | T3 Authority OS |
|----------------|:-----------:|:----------------:|:---------------:|
| Claude API (content, reviews, analytics) | ₹200 | ₹400 | ₹600 |
| Canva API (branded visuals) | ₹80 | ₹120 | ₹150 |
| Buffer / Publer (scheduling) | ₹50 | ₹60 | ₹60 |
| WhatsApp API — Interakt (messages + flows) | ₹200 | ₹500 | ₹800 |
| n8n workflows (shared infra, allocated) | ₹30 | ₹80 | ₹120 |
| Hosting / domain (landing page, if applicable) | ₹80 | ₹150 | ₹150 |
| Looker Studio + analytics (shared, allocated) | — | ₹50 | ₹50 |
| **Total Tool Cost / Doctor / Month** | **₹640** | **₹1,360** | **₹1,930** |

*[ASSUMPTION] Claude API estimates based on ~6 posts + review responses (T1), ~16 posts + automation + analytics summary (T2/T3) at Claude Sonnet API rates. Actual usage may vary ±20%.*

*[ASSUMPTION] WhatsApp costs estimated at ~200 messages/month (T1), ~500/month (T2), ~800/month (T3) including broadcasts and flows.*

---

### 1B — Human Labor Costs (Variable, Per Doctor)

Blended labor rate: **₹350/hour** (mix of junior exec ₹250/hr + senior review ₹500/hr)

| Task | T1 hours/mo | T2 hours/mo | T3 hours/mo |
|------|:-----------:|:-----------:|:-----------:|
| Content QC + approval management | 1.0 | 1.5 | 2.5 |
| Review response QC + publishing | 0.5 | 1.0 | 1.0 |
| Account management + WhatsApp coordination | 0.5 | 1.0 | 1.5 |
| Analytics review + report QC | — | 0.5 | 1.0 |
| Reel coordination + script review | — | — | 2.0 |
| Brand / strategy (T3 only) | — | — | 1.5 |
| **Total Hours / Doctor / Month** | **2.0** | **4.0** | **9.5** |
| **Total Labor Cost / Doctor / Month** | **₹700** | **₹1,400** | **₹3,325** |

---

### 1C — Total Variable COGS Per Doctor Per Month

| | T1 Presence | T2 Growth Engine | T3 Authority OS |
|--|:-----------:|:----------------:|:---------------:|
| Tool costs | ₹640 | ₹1,360 | ₹1,930 |
| Labor costs | ₹700 | ₹1,400 | ₹3,325 |
| **Total COGS / Doctor / Month** | **₹1,340** | **₹2,760** | **₹5,255** |

---

## SECTION 2: UNIT MARGIN PER DOCTOR PER MONTH

| | T1 Presence | T2 Growth Engine | T3 Authority OS |
|--|:-----------:|:----------------:|:---------------:|
| Monthly revenue | ₹6,999 | ₹14,999 | ₹29,999 |
| Variable COGS | ₹1,340 | ₹2,760 | ₹5,255 |
| **Gross Profit / Doctor / Month** | **₹5,659** | **₹12,239** | **₹24,744** |
| **Gross Margin %** | **80.9%** | **81.6%** | **82.5%** |

> **Key insight:** All three tiers carry ~81–83% gross margin. T3 generates 4.4× the gross profit per doctor vs T1. The push toward T2 and T3 is strongly justified on economics.

---

## SECTION 3: SETUP FEE UNIT ECONOMICS (ONE-TIME)

Setup fees are one-time payments at onboarding. Costs are higher in the first month.

| | T1 | T2 | T3 |
|--|:--:|:--:|:--:|
| Setup fee (revenue) | ₹4,999 | ₹7,999 | ₹9,999 |
| Setup labor (hours) | 5 hrs | 9 hrs | 13 hrs |
| Setup labor cost (₹350/hr) | ₹1,750 | ₹3,150 | ₹4,550 |
| Tool setup costs (one-time) | ₹250 | ₹400 | ₹700 |
| **Total Setup Cost** | **₹2,000** | **₹3,550** | **₹5,250** |
| **Setup Profit** | **₹2,999** | **₹4,449** | **₹4,749** |
| **Setup Margin** | **60%** | **55.6%** | **47.5%** |

> Setup fees are profitable from day one. They also filter out uncommitted prospects — a doctor who pays ₹7,999 upfront is invested.

---

## SECTION 4: CUSTOMER LIFETIME VALUE (LTV)

Assumptions:
- Average retention: 14 months [ASSUMPTION — industry avg for subscription health services]
- Churn: ~7% monthly after month 3 (higher in months 1–3 due to early exits)
- Upsell rate: 25% of T1 doctors upgrade to T2 within 6 months [ASSUMPTION]

| | T1 Presence | T2 Growth Engine | T3 Authority OS |
|--|:-----------:|:----------------:|:---------------:|
| Monthly gross profit | ₹5,659 | ₹12,239 | ₹24,744 |
| Avg. retention (months) | 12 | 15 | 18 |
| **LTV (recurring GP)** | **₹67,908** | **₹1,83,585** | **₹4,45,392** |
| Setup fee profit | ₹2,999 | ₹4,449 | ₹4,749 |
| **Total LTV** | **₹70,907** | **₹1,88,034** | **₹4,50,141** |

> A single T2 doctor retained for 15 months generates ₹1.88L in gross profit. A T3 doctor retained 18 months = ₹4.5L. Retention investment (quality, NPS, QBRs) pays outsized dividends.

---

## SECTION 5: COST DRIVERS TO WATCH

| Driver | Risk Level | Mitigation |
|--------|:----------:|-----------|
| WhatsApp API costs per message | Medium | Use broadcast templates efficiently; cap messages per tier |
| Claude API token usage (long contexts) | Low-Medium | Cache system prompts; use structured outputs |
| Labor creep on T1 accounts | High | Strict SOP — T1 is mostly automated; max 2h/doctor hard cap |
| Reel production time (T3) | High | Video batching — shoot 3–4 doctors per visit day |
| Onboarding labor overrun | Medium | Strict intake form + checklist; no custom work in setup |

---

## SECTION 6: BREAK-EVEN TARGETS

Break-even is the point where gross profit covers all fixed overhead.

### Fixed Overhead by Team Size

| Scale | Team | Monthly Fixed Overhead |
|-------|------|----------------------|
| 25 doctors (pilot) | 1 manager + 1 editor + 0.5 tech | ₹2,20,000 |
| 50 doctors | 2 AMs + 1 editor + 1 tech | ₹3,40,000 |
| 100 doctors | 3 AMs + 2 editors + 1 tech + 1 manager | ₹5,50,000 |

### Break-even Doctor Count

Using blended gross profit at target tier mix (20% T1 / 65% T2 / 15% T3):
- Blended gross profit per doctor = (0.20 × ₹5,659) + (0.65 × ₹12,239) + (0.15 × ₹24,744)
- = ₹1,132 + ₹7,955 + ₹3,712 = **₹12,799 blended GP/doctor/month**

| Overhead Level | Break-even Doctor Count |
|---------------|:-----------------------:|
| ₹2,20,000 (lean team) | **18 doctors** |
| ₹3,40,000 (50-doc team) | **27 doctors** |
| ₹5,50,000 (100-doc team) | **43 doctors** |

> **Bottom line:** With even a modest team, the business turns profitable well before 50 doctors. The pilot (25 doctors, mostly T2) is profitable from month 1 if managed lean.

---

*Unit Economics v1.0 | April 2026 | AI Lab | Internal use only*
