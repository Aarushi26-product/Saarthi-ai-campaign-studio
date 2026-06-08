# Saarthi AI Campaign Studio — Hackathon Proposal

## Executive Summary

Saarthi AI Campaign Studio solves a cumbersome problem: **today, a partner who wants to create a single social media post waits 1-2 weeks** through content creation, compliance review, and Exchange approval cycles — by which time the content has often lost its relevance. Most partners (especially in Tier 2/3 cities) don't create content at all because they lack expertise in what to post, how to design it, and how to navigate the compliance maze.

This tool enables **any partner — even one with zero content creation expertise** — to select a topic, choose their language and audience, and get fully SEBI-compliant text content + campaign images + AI video scripts (using their own face and voice via HeyGen) in under 2 minutes. The 5-agent AI pipeline runs 25 automated compliance checks across 3 live SEBI circulars before the partner ever sees the output. No designers, no copywriters, no 2-week wait.

---

## Problem Statement

### The Content Creation Gap

Not all Angel One partners have the expertise to think about what type of content could attract investors. They know finance — but they don't know content strategy, trending hooks, audience psychology, or platform-native formats. Only a small fraction of "big APs" who have business social media accounts, dedicated resources, and content creation experience actually post regularly. The vast majority — especially in Tier 2/3 cities — simply don't create content because they don't know where to start.

### The Approval Bottleneck (1-2 Weeks Per Post)

Even when partners create content, they cannot post it directly on social media if the aim is to generate leads for Angel One. The current process:

1. **Content creation** — Partner creates content OR asks Angel One's team to create it based on their intent → **2-3 days**
2. **Internal compliance review** — Angel One's compliance team reviews the content → **2-3 days**
3. **Exchange approval** — Some content requires Exchange approval, with its own review cycle, change suggestions, and re-submissions → **additional days**
4. **Total: 1-2 weeks from idea to approved post**

By the time content is approved, the market event or news that inspired it has lost its significance. A post about "today's market crash" that arrives 10 days later is useless.

### The Video Problem

If a partner wants to create a video using their own face and voice (which drives 3-5x higher engagement):
- Angel One's team creates the script → compliance approval → sent to partner → partner manually records → sends recording back → team reviews video → finally approved
- This process is so cumbersome that **almost no partners create video content**, despite video being the highest-engagement format on every platform.

### The Regulatory Complexity

Three separate SEBI circulars now govern what APs/MFDs can post:

1. **SEBI Finfluencer Circular (Jan 2025)** — Prohibits unregistered investment advice, bans association with finfluencers, enforces a 3-month market data lag rule
2. **SEBI EoDI Circular (May 2026)** — Mandates registration name and number disclosure on ALL social media content, including WhatsApp and Telegram closed groups
3. **Angel One AP Guidelines + AMFI MFD Rules** — 17 specific advertising do's and don'ts

One compliance violation can lead to registration suspension, penalties, or debarment. Partners either self-censor (don't post at all) or risk violations (post without review). Neither outcome is acceptable.

### The Scale Problem

- 70,000+ APs and MFDs in Angel One's network
- Each needs 3-5 posts per week across Instagram, WhatsApp, and LinkedIn
- That's 210,000 - 350,000 pieces of content per week
- No compliance team can manually review this volume

---

## Solution Architecture

### 5-Agent AI Pipeline

| Agent | Role | Model | Tokens | Fires When |
|-------|------|-------|--------|------------|
| Agent 1 | Content Generator | Claude Sonnet 4 | 2,200 | Always |
| Agent 2 | Compliance Validator (25 checks) | Claude Sonnet 4 | 600 | Always |
| Agent 3 | Auto-Fix Engine | Claude Sonnet 4 | 2,200 | Only on rejection |
| Agent 4A | Content Extractor | Claude Sonnet 4 | 900 | Always |
| Agent 4B | Canvas Renderer (JS) | None (browser) | — | Always |
| Agent 5 | HeyGen Video Script | Claude Sonnet 4 | 2,000 | Always |

### What Makes This Different

1. **Compliance-first architecture** — Rules are enforced at generation (Agent 1 prompt) AND validated independently (Agent 2 audit). Two separate LLM calls ensure no single point of failure.

2. **Platform-native output** — Instagram gets bold poster content, WhatsApp gets conversational message-card content, LinkedIn gets professional editorial content. Not one template resized — genuinely different content per platform.

3. **Search-intent driven angles** — 130+ sub-angles across 11 topics, each based on what Indian investors actually Google. Content addresses real questions, not generic categories.

4. **Live news integration** — Partners can create content around today's headlines. The tool fetches live news via web search and builds content around the selected story.

5. **Video script generation** — HeyGen-ready prompts with Seedance 2.0 cinematic scene directions (walking, scene changes, camera tracking) — not just a talking head script.

6. **Zero infrastructure** — Single HTML file. No server, no database, no deployment pipeline. Partners can use it offline after the first load.

---

## Success Metrics

### Primary KPIs (measurable within 90 days of launch)

| Metric | Current State | Target (90 days) | Measurement Method |
|--------|--------------|-------------------|-------------------|
| **Partner content posting frequency** | 18% of APs post weekly | 50% of APs post weekly | Angel One CRM + social media tracking |
| **Time to create one compliant post** | 2-4 hours | Under 2 minutes | In-app timer (generation start to download) |
| **Compliance first-pass approval rate** | ~65% | 95%+ | Agent 2 approval rate logged in-app |
| **Cost per content piece** | ₹500-2,000 (designer + compliance review) | ₹3-5 (API cost only) | API usage tracking |
| **Partner-generated leads per month** | Varies widely | 2x baseline | Angel One lead attribution system |

### Secondary KPIs (measurable within 6 months)

| Metric | Target | Measurement |
|--------|--------|-------------|
| **SEBI EoDI compliance rate** | 100% of generated content includes registration disclosure | Agent 2 B1/B2 check pass rate |
| **Content variety** | Partners use 5+ different angles per month (vs 1-2 today) | In-app angle selection tracking |
| **Video adoption** | 30% of active partners generate at least 1 video script per month | Agent 5 usage logging |
| **MFD compliance** | Zero scheme-specific violations in generated content | Agent 2 C17 check rate |
| **Partner retention** | 70% of onboarded partners use the tool monthly | Monthly active user tracking |

### Business Impact Metrics (measurable within 12 months)

| Metric | Target | Impact |
|--------|--------|--------|
| **New client acquisition from partner social media** | 15% increase over baseline | Direct revenue impact |
| **Compliance team workload reduction** | 60% fewer manual content reviews | Operational cost saving |
| **Partner satisfaction (NPS)** | 60+ NPS among tool users | Partner retention and expansion |
| **Content volume** | 500,000+ posts generated per quarter | Brand presence at scale |

---

## Roadmap

### Phase 1: Foundation (Current — Hackathon Prototype) ✅

- [x] 5-agent AI pipeline (content + compliance + fix + extraction + rendering)
- [x] 25-check compliance framework (3 SEBI circulars)
- [x] 11 topics × 130+ search-intent sub-angles
- [x] Live news integration
- [x] 3 platform campaign images (LinkedIn, Instagram, WhatsApp)
- [x] HeyGen video script generation with Seedance cinematic directions
- [x] Angel One brand design system matching approved creatives
- [x] 4 languages (Hinglish, English, Hindi, Marathi)
- [x] SEBI EoDI registration disclosure automation

### Phase 2: Production Readiness (Month 1-2)

- [ ] **Backend API wrapper** — Move API calls to a secure backend (no API key in browser)
- [ ] **Partner authentication** — Login via Angel One partner portal credentials
- [ ] **Usage logging & analytics** — Track which topics, angles, and hooks generate most engagement
- [ ] **Content approval workflow** — Send generated content to compliance team for approval via internal system
- [ ] **Persistent hero asset library** — Cloud-stored compliance-approved 3D visuals
- [ ] **Carousel image rendering** — Multi-slide image generation (currently text-only script)

### Phase 3: Scale & Intelligence (Month 3-6)

- [ ] **Auto-posting integration** — Direct publish to Instagram (Graph API), LinkedIn (API), WhatsApp Business
- [ ] **Performance feedback loop** — Track which content gets most engagement, feed back into Agent 1 prompt to improve future content
- [ ] **Partner content library** — Save, search, tag, and reuse past approved content
- [ ] **Batch generation** — Generate a full week's content calendar in one session
- [ ] **Regional language expansion** — Gujarati, Tamil, Telugu, Kannada, Bengali
- [ ] **AI-generated 3D hero assets** — Recraft V4.1 API integration for on-demand brand-consistent visuals (~₹3.3/image)

### Phase 4: Platform & Ecosystem (Month 6-12)

- [ ] **Content scheduling** — Calendar view with optimal posting time recommendations
- [ ] **Lead attribution** — Track which specific post generated which lead
- [ ] **Partner leaderboard** — Gamify content creation with engagement metrics
- [ ] **Compliance dashboard** — Real-time view of content compliance across all partners for the compliance team
- [ ] **Multi-broker white-label** — Abstract the compliance framework to work for any broker's AP network
- [ ] **Voice and video cloning pipeline** — Streamlined Digital Twin creation flow for partners

---

## Competitive Advantage

| Feature | Angel One AI Engine | Canva/Generic Tools | Manual Process |
|---------|-------------------|-------------------|----------------|
| SEBI compliance built-in | ✅ 25 automated checks | ❌ No financial compliance | ❌ Manual review required |
| EoDI disclosure automation | ✅ Auto-injected per circular | ❌ Not applicable | ❌ Partner must remember |
| 3-month data lag enforcement | ✅ Agent 2 Check A3 | ❌ Not applicable | ❌ Often violated unknowingly |
| Platform-native content | ✅ Different content per platform | ⚠️ Same content resized | ⚠️ Depends on skill |
| Campaign image generation | ✅ Auto-rendered, brand-matched | ⚠️ Manual design required | ⚠️ Expensive |
| Video script generation | ✅ HeyGen-ready with scenes | ❌ Not available | ❌ Requires video expertise |
| Time to create | < 2 minutes | 30-60 minutes | 2-4 hours |
| Cost per content | ₹3-5 | ₹0 (tool) + ₹500+ (time) | ₹500-2,000 |
| Works for 70,000 partners | ✅ Scales infinitely | ❌ Each partner designs manually | ❌ Not scalable |

---

## Cost Analysis

### Per Content Generation

| Component | Cost |
|-----------|------|
| Agent 1 (Content) — 2,200 tokens out | ~₹1.5 |
| Agent 2 (Compliance) — 600 tokens out | ~₹0.4 |
| Agent 3 (Fix, conditional) — ~30% fire rate | ~₹0.5 avg |
| Agent 4A (Extraction) — 900 tokens out | ~₹0.6 |
| Agent 5 (Video) — 2,000 tokens out | ~₹1.3 |
| **Total per generation** | **₹3-5** |

### At Scale (70,000 partners × 3 posts/week)

| Scenario | Monthly API Cost | Cost per Partner |
|----------|-----------------|-----------------|
| 10% adoption (7,000 partners) | ~₹2.5 lakh | ₹36/partner/month |
| 30% adoption (21,000 partners) | ~₹7.5 lakh | ₹36/partner/month |
| 50% adoption (35,000 partners) | ~₹12.5 lakh | ₹36/partner/month |

**Compare to current cost:** ₹5,000-15,000/month per partner for manual design + compliance review.

---

## Technical Specifications

- **Runtime:** Browser-only (HTML5 + JavaScript). No server required.
- **AI Model:** Anthropic Claude Sonnet 4 (claude-sonnet-4-20250514)
- **API Calls per Generation:** 4-5 (Agent 1 + Agent 2 + Agent 3 conditional + Agent 4A + Agent 5)
- **Image Rendering:** HTML5 Canvas API (client-side, no GPU needed)
- **News Fetch:** Anthropic web_search tool (type: web_search_20250305)
- **File Size:** ~140KB single HTML file
- **Browser Support:** Chrome, Edge, Safari, Firefox (modern versions)
- **Video Output:** HeyGen Video Agent with Seedance 2.0 + Avatar V engines

---

## Team

Built as a solo project for the Angel One AI Hackathon 2026.

---

*This proposal accompanies a fully functional working prototype. Download `angel_one_content_simulator.html` and open in any browser to test.*
