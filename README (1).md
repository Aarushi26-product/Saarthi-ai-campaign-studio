# Saarthi AI Campaign Studio

> A browser-based multi-agent AI tool that enables Angel One Authorised Persons (APs) and Mutual Fund Distributors (MFDs) to generate **SEBI-compliant** social media content, campaign images, and AI-powered videos using their own face and voice — in minutes, not weeks.

---

## The Problem

Angel One has **70,000+ Authorised Persons and MFDs** across India. Social media content is their #1 tool for generating new client leads. But the current content creation process is **broken at every step:**

### 1. Most partners don't know what to create

Not all partners have the expertise to think about what type of content could attract investors. They know finance — but they don't know content strategy, trending hooks, audience psychology, or platform-native formats. Only a small fraction of "big APs" who have business social media accounts, dedicated resources, and content creation experience actually post regularly. The vast majority — especially in Tier 2/3 cities — simply don't create content because they don't know where to start.

### 2. Even when they create content, they can't post it directly

Partners cannot post content aimed at lead generation for Angel One without approval. The current process:

- **Step 1:** Partner creates content (or asks Angel One's team to create it based on the partner's intent) → **2-3 days**
- **Step 2:** Content goes through Angel One's internal compliance review → **2-3 days**
- **Step 3:** Some content requires Exchange approval, which involves its own review cycle, suggested changes, and re-submissions → **additional days**
- **Total time from idea to approved post: 1-2 weeks**

By the time content is approved, the market event or news story that inspired it may no longer be relevant. A post about "today's market crash" that arrives 10 days later is useless.

### 3. Video content is even harder

If a partner wants to create a video using their own face and voice (which drives 3-5x more engagement than static posts):

- Angel One's team first creates the script
- Script gets compliance-approved
- Script is sent back to the partner
- Partner manually records themselves reading it
- Partner sends the recording back to the team
- Team reviews the video for compliance
- Video finally gets approved

This process is so cumbersome that **almost no partners create video content**, despite video being the highest-engagement format on every social media platform.

### 4. The regulatory maze

Three separate SEBI circulars now govern what APs/MFDs can post:

- **SEBI Finfluencer Circular (Jan 2025)** — Prohibits unregistered investment advice, enforces a 3-month market data lag rule, bans association with unregistered tipsters
- **SEBI EoDI Circular (May 2026)** — Mandates registration name and number disclosure on ALL social media content, including WhatsApp and Telegram closed groups
- **Angel One AP Guidelines + AMFI MFD Rules** — 17 specific advertising restrictions

One compliance violation can result in registration suspension, penalties, or debarment. Partners either self-censor (don't post at all) or risk violations (post without review). Neither is acceptable.

---

## The Solution

A single-page browser app where **any partner — even one with zero content creation expertise** — can:

1. **Select** what they want to talk about (from 130+ research-backed content angles across 11 financial topics)
2. **Choose** their language, tone, target audience, and hook style
3. **Get** fully SEBI-compliant text content for Instagram, WhatsApp, and LinkedIn — with all required disclaimers automatically inserted
4. **Download** brand-matched campaign images for all 3 platforms — ready to post
5. **Generate** a HeyGen video prompt — paste it into HeyGen with their own digital avatar and voice clone to get a professional video with walking scenes, camera changes, and text overlays

**Total time: Under 2 minutes. Not 2 weeks.**

The compliance layer isn't an afterthought — it's built into the generation pipeline itself. Content is validated against 25 automated checks across all 3 SEBI circulars before the partner ever sees it. If any violation is detected, an auto-fix engine rewrites only the violating parts while preserving the partner's authentic voice.

---

## How It Works

```
Partner fills profile (one-time: name, registration number, language, tone)
    ↓
Selects topic + specific angle + hook type + target audience
    ↓
Agent 1 (Content Generator) → Platform-native text for Instagram, WhatsApp, LinkedIn, Carousel
    ↓
Agent 2 (Compliance Validator) → 25-check audit across 3 SEBI/Angel One frameworks
    ↓
Agent 3 (Auto-Fix Engine) → Rewrites ONLY violating parts if needed (preserves partner voice)
    ↓
Agent 4A (Content Extractor) → Structured data for image rendering
    ↓
Agent 4B (Canvas Renderer) → LinkedIn (1200×627) + Instagram (1080×1080) + WhatsApp (1080×1080)
    ↓
Agent 5 (Video Script Generator) → HeyGen-ready prompt with cinematic scene directions
    ↓
Partner copies video prompt → Pastes into HeyGen → Gets video with their own face + voice
```

### What changes for the partner

| Today | With AI Content Engine |
|-------|----------------------|
| "I don't know what to post" | 130+ proven content angles with "why it works" rationale — just pick one |
| 2-3 days to create content | Generated in 30 seconds |
| 2-3 days for compliance review | 25 checks run automatically in 5 seconds |
| Additional days for Exchange approval | Content pre-validated against all 3 SEBI circulars |
| 1-2 weeks total cycle time | Under 2 minutes end-to-end |
| Manually records video, sends back and forth | Paste prompt into HeyGen → AI video with your face and voice in 3 minutes |
| Only "big APs" with resources create content | Any partner, any city, any experience level can create professional content |

---

## Key Features

- **5-Agent AI Pipeline** — Content generation, compliance validation, auto-fixing, campaign image rendering, video scripting
- **25-Check Compliance Framework** — SEBI Finfluencer Circular + SEBI EoDI Circular + Angel One AP Guidelines + AMFI MFD Rules
- **130+ Search-Intent Sub-Angles** — Based on what Indian investors actually search for on Google
- **Live News Integration** — Fetches today's headlines for timely content
- **Platform-Native Campaign Images** — Matching Angel One's compliance-approved design system
- **HeyGen Video Scripts** — Complete cinematic prompts with Seedance 2.0 walking scenes + Avatar V talking head + camera directions + text overlays
- **SEBI EoDI Auto-Compliance** — Registration name and number automatically injected into every piece of content
- **4 Languages** — Hinglish, English, Hindi, Marathi
- **Zero Infrastructure** — Single HTML file, runs entirely in the browser

---

## Compliance Framework

| Framework | Source Circular | Checks | Key Rules |
|-----------|----------------|--------|-----------|
| **A** — SEBI Finfluencer | SEBI/HO/MIRSD/MIRSD-PoD-1/P/CIR/2025/11 | 5 | No unregistered advice, no return claims, 3-month data lag rule, no finfluencer association |
| **B** — SEBI EoDI | HO/(79)2026-MIRSD-PODMMC | 4 | Registration name + number mandatory on all social media content |
| **C** — Angel One AP + AMFI | Internal + AMFI FAQs | 16 | No urgency, no superlatives, no incentives, no celebrities, MFD scheme restrictions |

**Total: 25 automated compliance checks per content generation.**

---

## Live Demo

1. Download `angel_one_content_simulator.html`
2. Open in any modern browser (Chrome, Edge, Safari, Firefox)
3. Fill in the partner profile → Select topic → Generate
4. See text content, campaign images, and video script — all compliance-validated

---

## Tech Stack

| Component | Technology | Cost |
|-----------|-----------|------|
| Frontend | Single HTML file, vanilla JS | Free |
| AI Engine | Anthropic Claude API (claude-sonnet-4-20250514) | ~₹3-5 per content generation |
| Image Rendering | HTML5 Canvas (client-side) | Free |
| Video | HeyGen Video Agent + Seedance 2.0 | ~₹80-160 per video |
| News Fetch | Claude web_search tool | Included in API cost |

---

## File Structure

```
├── angel_one_content_simulator.html   # Complete working prototype (single file — Saarthi AI)
├── angel_one_agent_prompts.docx       # All 5 agent prompts with full rule sets
├── angel_one_brd_v3.docx             # Business Requirements Document v3
├── PROPOSAL.md                        # Success metrics & roadmap for future enhancements
└── README.md                          # This file
```

---

## Regulatory References

1. **SEBI Circular SEBI/HO/MIRSD/MIRSD-PoD-1/P/CIR/2025/11** (January 29, 2025) — Provisions on association with persons engaged in prohibited activities
2. **SEBI Circular HO/(79)2026-MIRSD-PODMMC** (February 26, 2026) — Disclosure of registered name and registration number on Social Media Platforms
3. **Angel One AP Advertisement Guidelines** — Internal compliance document
4. **AMFI FAQs on Role of MFDs** — Scheme-specific content restrictions

---

## Author

Built for the Angel One AI Hackathon 2026.

**Saarthi** (सारथी) = Guide / Charioteer — the one who steers you in the right direction.

## License

Proprietary — Angel One Ltd. Internal use only.
