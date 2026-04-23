# SKILLS.md — Claude Upskilling & Context Awareness Log
## Referral Doctor Digital Presence Build
### AI Lab | Living Document — Update on every major session

---

## PURPOSE

This file tracks:
1. **Domain skills** Claude should develop for this project
2. **Prompt patterns** that work well (and what to avoid)
3. **Lessons learned** from each build phase
4. **Gaps to close** — areas where Claude needs more context or refinement

Update this file whenever: a new workflow is built, a content format is tested, a prompt is refined, or a new domain insight is gained.

---

## DOMAIN SKILLS REQUIRED

### 1. Indian Healthcare Content Writing
**What Claude must know:**
- MCI advertising guidelines: no drug/brand names, no outcome guarantees, no before/after
- Indian patient psyche: trust signals (qualifications, hospital affiliations), family-centric messaging, value of doctor's experience
- Telugu/Hindi health content: maintain warmth and respect (`Dr. saab`, `aapki sehat`)
- Practo/JustDial copy conventions: character limits, keyword-rich but conversational

**Current level:** Intermediate — prompt templates exist; need more Telugu examples

---

### 2. Local SEO for Clinics (Google Business Profile)
**What Claude must know:**
- GBP description: 750 character limit, primary keyword in first 100 chars, CTA required
- NAP consistency: Name, Address, Phone must match across all directories exactly
- Review strategy: NPS improvement tactics, QR code placement, timing of review requests
- GBP post types: What's New, Event, Offer — cadence and character limits
- Category selection: Primary vs. secondary GBP categories for Indian medical specialties

**Current level:** Basic — needs deeper GBP API workflow knowledge

---

### 3. GEO (Generative Engine Optimization)
**What Claude must know:**
- How ChatGPT, Gemini, Perplexity surface local doctor recommendations
- Structured data (schema.org) for Physician, LocalBusiness, FAQPage
- Entity authority building: Wikipedia mentions, consistent NAP, citations in medical directories
- Content strategies that make doctors appear in AI-generated answers

**Skill to build:** Write schema markup templates for each doctor tier; test GEO prompts in Perplexity

---

### 4. WhatsApp Business Automation (India)
**What Claude must know:**
- Interakt template categories: Transactional, Utility, Marketing (different approval rules)
- Template character limits and variable placeholders: `{{1}}`, `{{2}}`
- Broadcast vs. chatbot flows — when to use each
- TRAI regulations for bulk WhatsApp messaging in India
- Opt-in/opt-out requirements for patient lists

**Current level:** Template examples exist in `06_Content_Templates/`; need opt-in flow design

---

### 5. n8n Workflow Design
**What Claude must know:**
- n8n node types: Trigger, HTTP Request, IF, Set, Split In Batches, Code (JS), Wait
- Rate limiting: Claude API and Canva API throttling — need delay nodes for batch operations
- Error handling: Always add Error Trigger node to catch failures and Slack-notify
- Google Sheets node: Read rows, append rows, update rows by row number
- Webhook setup: Unique webhook URLs per doctor intake form

**Skill to build:** Full JSON export templates for all 5 core workflows

---

### 6. Canva API Integration
**What Claude must know:**
- Canva Connect API: Design creation, template duplication, element substitution
- Brand Kit: Font, color, logo injection via API
- Export formats: PNG for social, PDF for reports, JPG for WhatsApp cards
- Auto-fill with doctor variables: name, photo, specialty, clinic name

**Current level:** Stack doc references it; no actual API call templates built yet

---

### 7. Healthcare Pitch & Sales
**What Claude must know:**
- Yashoda stakeholder language: ROI framing for the Marketing Head, operational simplicity framing for Relationship Managers
- Doctor objection handling: "I don't have time", "My patients find me through word-of-mouth", "Is this HIPAA/patient-data safe?"
- Proposal writing: One-page quick-close format for field teams

**Current level:** Pitch deck and executive summary exist; objection handling doc not yet built

---

## PROVEN PROMPT PATTERNS

### Works Well
- **Specialty-first framing:** Always mention the doctor's specialty in the first prompt token — Claude produces more accurate medical vocabulary
- **MCI constraint upfront:** Put "No drug names, no treatment guarantees, follow MCI guidelines" in SYSTEM prompt, not USER prompt
- **Language switching:** Specify `Language: Telugu` clearly; Claude handles Telugu well but needs explicit instruction
- **Persona-tagged prompts:** Label prompts with `[Persona A]`, `[Persona B]` etc. — output tone shifts correctly

### Avoid
- **Asking Claude to invent clinic metrics** — always pass real numbers or mark clearly as `[SAMPLE DATA]`
- **Generic "write a social post"** without specialty + platform + language — produces bland output
- **Long prompt chains without examples** — for new content types, add 1 example of the expected output format

---

## BUILD LOG (Session History)

| Date | What Was Built | Key Decision |
|------|---------------|--------------|
| April 2026 | Full project structure, 8-folder system | Chose Markdown-first for easy AI editing |
| April 2026 | Pricing tiers (T1–T4), ROI model | Tier 2 as default sell; Tier 1 as entry |
| April 2026 | Tool stack + 5 n8n workflow maps | n8n self-hosted chosen for cost and data control |
| April 2026 | Doctor bio, social, reel, review, GBP prompts | MCI constraint added to all system prompts |
| April 2026 | HTML pitch deck (Pitch_Deck.html) | Built for leadership presentation |
| April 2026 | CLAUDE.md + SKILLS.md created | Context persistence across Claude sessions |

---

## OPEN GAPS (Prioritized)

| # | Gap | Priority | Owner |
|---|-----|----------|-------|
| 1 | Objection handling playbook for field sales | High | AI Lab |
| 2 | n8n workflow JSON exports (importable) | High | AI Lab |
| 3 | Telugu content samples (10 posts) | High | Content Team |
| 4 | GEO schema markup templates (Physician, FAQ) | Medium | AI Lab |
| 5 | Canva API call templates | Medium | AI Lab |
| 6 | WhatsApp opt-in flow design | Medium | AI Lab |
| 7 | Pilot tracking dashboard (Google Sheets template) | Medium | AI Lab |
| 8 | Doctor NPS survey template | Low | Marketing |
| 9 | Competitor comparison matrix | Low | Strategy |

---

## CONTENT CALIBRATION NOTES

### Review Response Quality Checks
- Positive reviews: responses should feel personal, not templated — use reviewer's name if visible
- Negative reviews: never admit fault, always offer offline resolution, max 120 words
- Test: read response aloud — if it sounds like a robot, rewrite

### Social Post Quality Checks
- Hook in first line (no "Did you know...?" — overdone)
- Health tip must be actionable, not just informational
- CTA must be WhatsApp-first for Indian audience (`Send us a WhatsApp message at +91-XXXXX`)
- Hashtags: 3–5, mix of specialty + city + awareness (`#HeartHealth #HyderabadDoctors #YashodaHospitals`)

### Reel Script Quality Checks
- Hook must work without sound (text-on-screen assumption)
- Doctor should not appear to diagnose or prescribe in the script
- Teleprompter format: short sentences, [PAUSE] markers, emphasis in CAPS

---

## SKILLS TO ADD IN NEXT SESSIONS

- [ ] Meta Ads copywriting for doctors (awareness campaigns, post boost)
- [ ] Looker Studio dashboard design for doctor reporting
- [ ] Practo profile optimization patterns
- [ ] YouTube Shorts strategy for doctors (cross-posting Reels)
- [ ] Patient education content series (seasonal health calendar)
- [ ] Cross-referral analytics: linking digital signals to Yashoda patient intake data

---

## REFERENCE LINKS (Internal)

| Resource | Location |
|----------|----------|
| Full prompt library | `05_AI_Automation_Stack/Tool_Stack.md` |
| Content templates | `06_Content_Templates/` |
| Pricing details | `04_Commercials/Pricing_Tiers.md` |
| ROI model | `04_Commercials/ROI_Model.md` |
| Onboarding flow | `07_Onboarding/` |
| Analytics template | `08_Analytics_Reporting/Monthly_Report_Template.md` |

---

*SKILLS.md Version 1.0 | April 2026 | AI Lab — Update this file every session*
