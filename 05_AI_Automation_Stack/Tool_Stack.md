# AI & Automation Tool Stack
## Referral Doctor Digital Presence Program

---

## Stack Overview

```
LAYER               TOOLS                           PURPOSE
─────────────────────────────────────────────────────────────────────
Content AI          Claude API (Sonnet 4.6)         Text generation, bio writing, captions
                    ChatGPT-4o                      Secondary content drafting
                    Canva Magic AI                  Visual content, template auto-fill

Automation          n8n (self-hosted)               Core workflow orchestration
                    Make.com                        Lightweight trigger automations
                    Zapier                          3rd-party app connectors

Publishing          Buffer / Publer                 Social media scheduling
                    Meta Business Suite             Facebook/Instagram native scheduler
                    Google Business Profile API     GBP post scheduling

WhatsApp            Interakt / Wati / AiSensy       WhatsApp Business API (India)
                    Landbot                         WhatsApp chatbot builder

CRM / Data          Google Sheets (master)          Doctor profiles, content tracker
                    Notion                          Approval workflow, project management
                    Airtable                        Content calendar, asset library

Analytics           Google Looker Studio            Dashboards
                    Google Search Console           SEO tracking
                    Meta Insights API               Social analytics

SEO / GEO           Semrush / Ahrefs               Keyword research
                    BrightLocal                     Local citation management
                    Screaming Frog                  Technical SEO audit

Review Mgmt         GBP API + Zapier               Review monitoring alerts
                    ReviewTrackers                  Centralized review management

AI Search           Perplexity API                  GEO query testing
                    Custom GPT monitor              Check ChatGPT mentions

Video               CapCut / DaVinci Resolve        Reel editing
                    Whisper AI (OpenAI)             Auto-subtitles
                    ElevenLabs                      AI voiceover (optional)

Email / Comms       Gmail API                       Client communication
                    Slack                           Internal team alerts
```

---

## Core Automation: n8n Workflow Map

### Workflow 1: New Doctor Onboarding Pipeline
```
Trigger: Google Form Submission (Doctor Intake)
→ Google Sheets: Create doctor row
→ Claude API: Generate bio + 10 starter posts + GBP description
→ Canva API: Create branded template set with doctor's info
→ Google Drive: Create doctor folder, upload all assets
→ Notion: Create setup checklist task for execution team
→ WhatsApp (Interakt): Send welcome message to doctor
→ Slack: Alert execution team "New doctor onboarded: Dr. [Name]"
```

### Workflow 2: Monthly Content Generation
```
Trigger: 1st of every month (cron job)
→ Google Sheets: Pull active doctors list + specialty
→ For each doctor:
   → Claude API: Generate 12 posts (captions + hashtags)
   → Canva API: Fill templates with doctor data
   → Google Drive: Save to doctor's content folder
   → Notion: Create approval task
   → WhatsApp: Send "Your [Month] content is ready for review"
→ Buffer API: Schedule approved content
```

### Workflow 3: Review Alert & Response
```
Trigger: New review detected (GBP API webhook / polling)
→ Classify: Positive / Neutral / Negative (Claude API)
→ If Negative: Slack urgent alert to team
→ Claude API: Draft response (context-aware, specialty-appropriate)
→ Notion: Create review response task with draft
→ After human approval: Publish via GBP API
→ Google Sheets: Log review + response + sentiment
```

### Workflow 4: Weekly WhatsApp Health Tip
```
Trigger: Every Monday 9:00 AM IST
→ Google Sheets: Get specialty + language preference per doctor
→ Claude API: Generate health tip per specialty (50 words)
→ Canva API: Generate branded WhatsApp card
→ Interakt API: Schedule broadcast to each doctor's patient list
→ Sheets: Log send status
```

### Workflow 5: Monthly Analytics Report
```
Trigger: Last day of month
→ GBP API: Pull monthly metrics (views, calls, directions)
→ Meta Graph API: Pull social metrics
→ Looker Studio: Refresh dashboard
→ Claude API: Write natural language summary of performance
→ PDF generation (Puppeteer or Looker export)
→ WhatsApp: Send PDF report to doctor
→ Email: Copy to Yashoda program manager
```

---

## Prompt Library (Master Index)

### Doctor Bio Generation
```
SYSTEM: You are a medical content writer specializing in SEO-optimized doctor profiles
for Indian healthcare. Write factual, warm, and trustworthy content. Never include
drug names, specific treatment claims, or before/after guarantees. Follow MCI
advertising guidelines.

USER: Write a 400-word professional doctor bio for:
- Name: {doctor_name}
- Qualification: {qualification}
- Specialty: {specialty}
- Years of experience: {years}
- Clinic location: {location}
- Languages: {languages}
- Hospital affiliation: Yashoda Hospitals
- Key focus areas: {focus_areas}

Include:
1. Opening sentence with primary keyword "{specialty} in {location}"
2. Education and qualifications
3. Areas of expertise (3-4 bullet points)
4. Patient-centric approach paragraph
5. Closing with clinic contact CTA
6. Write in 3rd person, warm and professional tone
```

### Social Media Post (Health Tip)
```
SYSTEM: You are a healthcare social media content writer for Indian doctors.
Write accessible, educational posts that build patient trust. Use simple language
(suitable for Class 8 reading level), no medical jargon. Always end with a
warm CTA. No drug recommendations. Language: {language}.

USER: Write a social media health tip post for:
- Doctor specialty: {specialty}
- Topic: {topic}
- Platform: {Instagram/Facebook}
- Language: {Hindi/English/Telugu}
- Tone: Friendly, educational, reassuring
- Length: 100-150 words
- Include: 3-5 relevant hashtags
- End with: "Book your appointment with Dr. {name}" style CTA
```

### Reel Script (FAQ Format)
```
SYSTEM: You are writing a 60-second doctor Reel script for Instagram/YouTube.
The doctor will speak directly to camera. Keep it conversational, warm, and simple.
Structure: Hook (0-5s) → Problem/Question (5-15s) → Answer (15-50s) → CTA (50-60s)

USER: Write a Reel script for:
- Doctor: Dr. {name}, {specialty}
- Topic/FAQ: {topic}
- Language: {language}
- Audience: Patients in {city}
- Include teleprompter-friendly formatting (short sentences, pauses marked)
```

### Review Response (Positive)
```
USER: Write a warm, professional Google review response for a doctor.
Review: "{review_text}"
Doctor: Dr. {name}, {specialty}, {clinic_name}
Keep under 100 words. Thank the reviewer personally. Add soft CTA to return.
Do not make medical claims. Mention Yashoda affiliation naturally if relevant.
```

### Review Response (Negative)
```
USER: Write an empathetic, professional Google review response for a doctor.
Review: "{review_text}" — Sentiment: Negative — Issue type: {issue_type}
Doctor: Dr. {name}, {specialty}
Keep under 120 words. Acknowledge concern without admitting fault.
Offer to resolve offline. Provide contact: {contact}.
Tone: Calm, empathetic, professional. Do not be defensive.
```

### GBP Description
```
USER: Write a Google Business Profile description for a doctor clinic.
- Doctor: Dr. {name}, {qualification}
- Specialty: {specialty}
- Location: {address}, {city}
- Hospital affiliation: Yashoda Hospitals
- Key services: {services}
- Languages: {languages}
Keep under 750 characters. Include primary keyword: "{specialty} in {city}".
Include WhatsApp/phone CTA. Warm, professional tone.
```

### Monthly Report Summary
```
USER: Write a 150-word plain English monthly performance summary for a doctor's
digital presence report. Use these metrics:
- GBP Views: {views} ({change}% vs last month)
- GBP Calls: {calls}
- Google Reviews: {new_reviews} new (Total: {total})
- Instagram Followers: {followers} (+{new})
- Instagram Reach: {reach}
- Top performing post: "{post_title}" with {engagement} engagement

Write in a congratulatory, encouraging tone. Highlight 2 wins and 1 opportunity.
End with a tip for next month. Address to "Dear Dr. {name}".
```

---

## Monthly Tool Cost Estimate (100 doctors)

| Tool | Plan | Monthly Cost (INR) |
|------|------|--------------------|
| Claude API (Sonnet 4.6) | Pay-per-use ~2M tokens | ₹8,000 |
| n8n (self-hosted) | VPS hosting | ₹2,000 |
| Canva Pro Teams | 5 users | ₹4,000 |
| Buffer Publish | Team plan (100 channels) | ₹6,000 |
| Interakt WhatsApp API | Growth plan | ₹8,000 |
| BrightLocal | Agency plan | ₹5,000 |
| Looker Studio | Free (Google) | ₹0 |
| Semrush | Pro | ₹9,000 |
| ReviewTrackers | Starter | ₹4,000 |
| Notion | Business | ₹2,500 |
| **Total** | | **~₹48,500/month** |

*Per-doctor AI tool cost: ~₹485/month — very high margin on all tiers*

---

*Stack Version 1.0 | April 2026*
