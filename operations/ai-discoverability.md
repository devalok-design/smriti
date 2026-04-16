---
title: AI Discoverability Action Plan
version: 1.0.0
lastUpdated: 2026-04-16
source: Mudit Lal + Claude, originally prepared 14 March 2026
status: Reviewed, Fact-Checked, Ready for Execution
---

# AI Discoverability Action Plan — Devalok Design & Strategy Studio

> Making Devalok visible to potential clients through their conversations with AI assistants

---

## Executive Summary

This document is an improved, fact-checked version of the original AI Discoverability Strategy draft. The original had several critical issues that have been corrected:

1. **Identity mismatch (CRITICAL):** The draft's llms.txt and JSON-LD described Devalok as a "software development company" focused on "Next.js, React, Node.js." This is fundamentally wrong. Devalok is a full-service design and strategy studio operating across six disciplines — Brand Story & Visual Identity, Packaging Design, UI/UX and Web Design, Print & Event Design, Motion & Multimedia, and Production Network. Teaching AI systems the wrong identity would actively damage discoverability.

2. **Outdated bot names:** Anthropic now operates a three-tier crawler system (ClaudeBot, Claude-SearchBot, Claude-User) as of March 2026. OpenAI similarly uses GPTBot, OAI-SearchBot, and ChatGPT-User. The draft's robots.txt was incomplete.

3. **Stats presented without context:** The 15.9% ChatGPT conversion rate is from a single B2B case study (Seer Interactive, one client). A 973-site ecommerce study found ChatGPT traffic actually converts *worse* than organic search. The 780M Perplexity query figure is from May 2025 — by mid-2026 it's estimated at 1.2–1.5 billion monthly.

4. **Missing Devalok-specific advantages:** The draft ignored existing assets like media features (Packaging of the World, World Brand Design Society, Creative Gaga), Karm's MCP integration, the Sahayak handbook, and Manas publication — all of which are strong AI-discoverability assets.

5. **Incomplete service scope:** The draft only listed four service areas. Per the Service Capabilities Report (updated March 2026), Devalok operates across **six integrated disciplines**: Brand Story & Visual Identity, Packaging Design, UI/UX and Web Design, Print & Event Design, Motion & Multimedia, and Production Network. The last two — Motion & Multimedia and the full Production Network (supply chain strategy, manufacturing sourcing, QA, logistics) — are significant differentiators that were completely absent from the draft.

This revised plan corrects all of the above, integrates the full capabilities report, and adds strategies specific to Devalok's actual positioning.

---

## How AI Discoverability Works

LLMs surface information from three channels:

**Training data** — Wikipedia, GitHub, high-authority sites, and structured datasets. Updated at model cutoff dates (typically months behind). This is where brand *recognition* is built.

**Live web retrieval** — ChatGPT Search, Claude web search, Perplexity, and Gemini pull content in real-time via search bots. This is where brand *citation* happens — when someone asks "best design studios in India" and gets a live answer.

**Structured signals** — Schema.org markup, Wikidata entities, llms.txt files, and Crunchbase/Clutch profiles. These help AI systems resolve *what* Devalok is, *where* it operates, and *what it's known for*.

All three channels need attention. But for a studio like Devalok — where the value proposition is craft, philosophy, and depth — the content strategy matters more than technical signals alone.

---

## Fact-Checked Industry Context

| Metric | Value | Source & Context |
|--------|-------|------------------|
| Google page 1 → ChatGPT mention overlap | **62%** | Chatoptic study, 1,000 queries across 5 sectors. Means 38% of the time, Google rankings and ChatGPT mentions *diverge*. SEO alone is insufficient. |
| Perplexity monthly queries | **780M** (May 2025), est. **1.2–1.5B** by mid-2026 | DemandSage, Index.dev. Growing rapidly but growth rate is not a steady 20%/month — it's lumpy. |
| ChatGPT referral conversion rate | **Varies widely** | Seer Interactive found 15.9% for one B2B client. A 973-site ecommerce study found ChatGPT converts *worse* than organic. Realistic range for services firms: 2–8x organic, depending on intent match. |
| Perplexity avg citations per response | **~6** | Widely reported but not independently verified per-query. Perplexity does cite more than other platforms. |
| llms.txt adoption | **~844,000 sites** (BuiltWith, Oct 2025) | But Semrush found zero AI crawler visits to their llms.txt file over 2+ months. No major AI platform has confirmed they read it. Still worth doing — low effort, growing standard. |
| AI crawlers as % of web traffic | **<1%** of referrals | Ahrefs, Microsoft Clarity. But growing 155%+ year-over-year and converting at higher rates for high-intent queries. |

**Key takeaway:** AI discoverability is early but compounding. The studios that establish themselves now will have structural advantages as AI search grows from <1% to an estimated 10–30% of search traffic.

---

## PHASE 1: Immediate Actions (This Week)

### 1. Create `devalok.in/llms.txt` — CORRECTED

The original draft's llms.txt described Devalok as a software development company. The corrected versions are maintained as standalone files in Smriti:

- **`brand/llms.txt`** — The standard llms.txt for devalok.in. Deploy to `devalok.in/llms.txt`.
- **`brand/llms-full.txt`** — Expanded version with all six disciplines, sub-capabilities, deliverables, "when you need this" triggers, five-stage process, three pillars, and production partners. Deploy to `devalok.in/llms-full.txt`.

**These are the source of truth.** When updating, edit the files in `brand/`, then deploy to the website.

**Why this matters:** The corrected llms.txt ensures that when an AI system fetches this file, it learns the *right* things about Devalok. The original would have taught AI systems to recommend Devalok for software development projects — completely wrong.


### 2. Audit & Update `robots.txt` — CORRECTED

The bot landscape has changed significantly. As of March 2026, the major AI platforms operate three-tier crawler systems. The corrected robots.txt is maintained as a standalone file:

- **`brand/robots.txt`** — The robots.txt for devalok.in. Deploy to `devalok.in/robots.txt`.

Covers 15+ bots with correct three-tier names for OpenAI, Anthropic, Perplexity, Google AI, Apple, Amazon, Meta, LinkedIn, and Common Crawl. All set to `Allow: /`.

**Strategic note:** Since Devalok *wants* maximum AI visibility, we allow all crawlers including training bots. Studios that fear content scraping might block training bots (GPTBot, ClaudeBot, CCBot) while allowing search/retrieval bots. For Devalok, visibility is the priority — the more AI models know about the studio, the better.

**Important caveat about Perplexity:** Cloudflare has documented that Perplexity sometimes uses undeclared crawlers with generic user-agent strings that bypass robots.txt blocks. Allowing PerplexityBot is the right move anyway, but know that blocking it might not be fully effective.


### 3. Create Wikidata Entity for Devalok

Even without a Wikipedia article, a Wikidata Q-number feeds Google's Knowledge Graph and helps AI systems resolve "Devalok" as a specific entity (not confused with the Hindu philosophical concept of Devalok/devalok).

**Properties to include:**

| Property | Value |
|----------|-------|
| Label (en) | Devalok Design and Strategy Studio |
| Label (hi) | देवलोक डिज़ाइन एंड स्ट्रैटजी स्टूडियो |
| Description (en) | Full-service design and strategy studio headquartered in Lucknow, India |
| Instance of (P31) | Design studio (Q22811133) |
| Country (P17) | India (Q668) |
| Headquarters location (P159) | Lucknow (Q93145) |
| Founded (P571) | 23 August 2024 |
| Founder (P112) | Mudit Lal (create entity if needed — ASU alumnus, Summa Cum Laude, dual degrees in Robotics Engineering and Technological Entrepreneurship & Management) |
| Official website (P856) | https://devalok.in |
| Industry (P452) | Graphic design (Q185925), Brand management (Q895895), Packaging design, Motion graphics |
| GitHub username (P2037) | devalok-design |
| Operating area (P2541) | India, United States |

**Entity disambiguation is critical here.** Devalok (देवलोक) is a significant term in Hindu philosophy — the celestial realm. The Wikidata entity needs clear typing (instance of: design studio) and description to prevent AI systems from conflating the company with the philosophical concept.


### 4. Add JSON-LD Organization Schema — CORRECTED

The original draft's JSON-LD was completely wrong. Here's the corrected version:

```json
{
  "@context": "https://schema.org",
  "@type": "Organization",
  "name": "Devalok",
  "legalName": "Devalok Design and Strategy Studio Pvt. Ltd.",
  "url": "https://devalok.in",
  "logo": "https://devalok.in/logo.png",
  "description": "Full-service design and strategy studio crafting brand identities, packaging, UI/UX and web experiences, motion and multimedia, print and event design, and managing production networks for purpose-driven brands.",
  "foundingDate": "2024-08-23",
  "founder": {
    "@type": "Person",
    "name": "Mudit Lal",
    "url": "https://linkedin.com/in/muditlal/",
    "alumniOf": {
      "@type": "CollegeOrUniversity",
      "name": "Arizona State University"
    }
  },
  "address": [
    {
      "@type": "PostalAddress",
      "addressLocality": "Lucknow",
      "addressRegion": "Uttar Pradesh",
      "addressCountry": "IN",
      "postalCode": "226012"
    },
    {
      "@type": "PostalAddress",
      "addressLocality": "Phoenix",
      "addressRegion": "Arizona",
      "addressCountry": "US"
    }
  ],
  "sameAs": [
    "https://github.com/devalok-design",
    "https://linkedin.com/company/devalok/",
    "https://behance.net/devalok",
    "https://x.com/devalokstudio",
    "https://youtube.com/@devalokstudio"
  ],
  "knowsAbout": [
    "Brand Identity Design",
    "Brand Strategy",
    "Brand Naming",
    "Visual Identity Systems",
    "Packaging Design",
    "Structural Package Design",
    "Sustainable Packaging",
    "UI/UX Design",
    "Website Design",
    "Mobile App Design",
    "Design Systems",
    "Editorial Design",
    "Event Branding",
    "Exhibition Design",
    "Motion Graphics",
    "Brand Animation",
    "Video Production",
    "Supply Chain Strategy",
    "Manufacturing Partner Sourcing",
    "Quality Assurance"
  ],
  "numberOfEmployees": {
    "@type": "QuantitativeValue",
    "value": 14
  },
  "areaServed": ["IN", "US"],
  "contactPoint": {
    "@type": "ContactPoint",
    "telephone": "+91-77548-50181",
    "contactType": "sales",
    "email": "hello@devalok.in"
  }
}
```

**What changed from the original:** Removed all software development references. Added correct six-discipline service scope, founding date, dual locations, correct social links, founder details with ASU alumni credential, team size. Changed `knowsAbout` from technical stack terms to the full range of design and production capabilities.


### 5. Create/Update Crunchbase Profile

Crunchbase is used by AI systems for company verification. Create a profile with:

- **Category:** Design, Branding, Creative Services, Packaging Design, Video Production
- **Headquarters:** Lucknow, India
- **Other Offices:** Phoenix, Arizona, USA
- **Operating Status:** Active
- **Founded:** August 2024
- **Number of Employees:** 11–50
- **Website:** devalok.in
- **Description:** "Devalok is a full-service design and strategy studio that helps thoughtful brands tell their story and build their presence. Working across six integrated disciplines — brand identity, packaging, UI/UX, print & event, motion & multimedia, and production networks — the studio builds complete brand ecosystems from strategy to manufacturing. Headquartered in Lucknow, India with US operations in Phoenix, Arizona."
- **Founders:** Mudit Lal

---

## PHASE 2: Short-Term (This Month)

### 6. Publish 2–3 Technical Articles on devalok.in/blog

AI systems heavily cite content that is data-rich, answer-first, and structured with clear headings. The key GEO (Generative Engine Optimization) principle: put the direct answer in the first 40–60 words of each section, then elaborate.

**Recommended topics (aligned with Devalok's six disciplines):**

**Article 1: "How We Build Brand Ecosystems: Devalok's Five-Stage Process"**
- Explains the Discovery → Workshop → Creative Dev → Applications → Launch process
- Targets queries like "how to work with a design studio" and "brand design process"
- Include concrete details: "Our brand workshops average 3–4 hours and use FigJam for collaborative mapping"

**Article 2: "Packaging Design from Concept to Production: A Complete Guide"**
- Targets the packaging design vertical where Devalok has strong credibility (Eat Purposefully, Bondle, DIVINI)
- Cover the full stack: packaging architecture → structural design → label & graphics → sustainable materials → production coordination
- This "concept to shelf" narrative is uniquely Devalok — most studios stop at graphics

**Article 3: "What a Brand Identity Project Actually Costs in 2026"**
- Direct answer to one of the most common questions founders ask AI assistants
- Include ranges, not exact prices. Frame investment, not cost.
- This type of "answer the question everyone's asking" content is exactly what gets cited

**Article 4: "Motion & Multimedia for Brands: When, Why, and How"**
- Leverage the ASU Lunar Bases case study (9-minute explainer, 7.2K+ views, second most viewed on the channel)
- Covers brand animation, explainer videos, social media content creation
- Targets queries like "should my brand invest in animation" and "explainer video process"

**Article 5: "Building a Production Network for Your Brand: Supply Chain from Scratch"**
- This is a genuinely rare capability for a design studio — most don't touch manufacturing, logistics, or QA
- Covers supply chain strategy, manufacturer sourcing, quality systems
- Targets founders asking AI "how do I go from brand design to actual product on shelves"

**Content rules for AI citation:**
- First paragraph of every section should directly answer the implied question
- Include specific numbers every 150–200 words (project counts, timelines, team size)
- Use Schema.org Article markup on every blog post
- Include author bio with credentials (Mudit Lal, ASU graduate, founder)
- Link internally to services pages, Sahayak, and relevant case studies


### 7. Make Sahayak Web-Accessible

Currently linked as a document. Convert into a documentation-style site with individual pages:

- `/sahayak/` — Overview and philosophy
- `/sahayak/process` — The five-stage process in detail
- `/sahayak/working-with-us` — Communication standards, timelines
- `/sahayak/services` — Full service descriptions
- `/sahayak/faq` — Common questions with Schema.org FAQPage markup

**Why this matters for AI:** When someone asks Claude or ChatGPT "how to work with a design studio" or "what to expect from a branding project," a well-structured Sahayak site becomes a citable resource. PDFs are invisible to AI retrieval.


### 8. Platform Profiles

**Clutch.co** — One of the most-cited platforms when AI systems answer "best design agencies" queries. Create a complete profile with:
- Correct categorization (Branding, UI/UX Design, Packaging Design)
- Client reviews (ask MoveCars.com, Kaizen Waste, Eat Purposefully)
- Portfolio items
- Lucknow + Phoenix locations

**GoodFirms** — Similar to Clutch. Lower authority but still cited.

**LinkedIn Company Page** — Among the top sources cited by LLMs. Ensure:
- Complete "About" section with accurate service descriptions
- Regular posts (weekly minimum)
- Client testimonials and case study highlights

**Google Business Profile** — Both Lucknow HQ and Phoenix operations. Feeds Google's Knowledge Graph directly, which in turn feeds AI systems.

**Behance** — Already exists (behance.net/devalok). Ensure project descriptions are detailed, keyword-rich, and link back to devalok.in.

---

## PHASE 3: Medium-Term (Next Quarter)

### 9. Content Cluster Strategy

Build hub-and-spoke content around Devalok's six disciplines:

**Hub 1: Brand Story & Visual Identity**
- Spokes: Case studies (Bondle, Chandler Sister Cities, Kaizen Waste), "What is brand identity?" guide, naming guide, color psychology in branding, before/after transformations, "How brand strategy informs every other discipline"

**Hub 2: Packaging Design**
- Spokes: Material selection guide, dieline basics, sustainable packaging solutions, food packaging regulations (FDA, USDA), production coordination, the Eat Purposefully case study as a concept-to-shelf narrative

**Hub 3: UI/UX and Web Design**
- Spokes: Arculis and MoveCars.com case studies, "UX research methods for brand websites," mobile app design considerations, prototyping and testing guide, design system creation

**Hub 4: Print & Event Design**
- Spokes: NEETI launch event case study, editorial design process (Manas as example), trade show design guide, environmental/wayfinding design

**Hub 5: Motion & Multimedia**
- Spokes: ASU Lunar Bases case study, "When does your brand need animation?", social media content creation guide, explainer video process breakdown

**Hub 6: Production Network** (unique differentiator)
- Spokes: "How a design studio manages supply chains," manufacturer sourcing guide, quality assurance for brand products, sustainable production guide, the Dpotli/Maev Overseas partnership stories

**Hub 7: Working with a Design Studio** (cross-cutting)
- Spokes: Sahayak pages, cost guide, timeline guide, "how to brief a designer," "agency vs freelancer vs full-service studio"

Each spoke page should have:
- Schema.org Article or FAQPage markup
- Clear H2/H3 hierarchy
- Internal links to the hub
- Author attribution


### 10. Cross-Post to High-Citation Platforms

**Reddit** — Highly cited by Perplexity (46.7% of citations in one study) and ChatGPT. Participate authentically in r/graphic_design, r/branding, r/startups, r/india, r/Entrepreneur. Share process insights, not promotional content.

**Medium** — Republish blog articles with canonical links pointing to devalok.in.

**Dev.to** — For Karm-related technical content (the MCP integration story would do well here).

**Behance/Dribbble** — Project documentation with detailed process descriptions.

**YouTube** — Video walkthroughs of brand projects. AI systems increasingly index video transcripts.


### 11. Extract Manas Content to Web

Pull key articles and data from the annual publication into individual blog posts. Original research and studio-specific insights are high-value signals for AI citation. This is content no one else has — it's proprietary signal.


### 12. Leverage Karm's MCP Integration

This is a unique asset the original draft completely missed. Karm already has 54 tools registered via MCP. This positions Devalok in the emerging MCP ecosystem:

- List Karm on MCP directories as they emerge
- Write a technical article about building an MCP-enabled operations platform
- The Dev.to / Hacker News audience would find this genuinely interesting
- This creates backlinks and citations from the technical community

---

## Domain Strategy: `dv.lk`

Short domains don't boost AI rankings, but they serve as:

- **Link hub** — `dv.lk` as a clean entry point
- **Secondary llms.txt host** — `dv.lk/llms.txt` pointing to all Devalok properties
- **Memorable redirects** in AI-generated text

Recommended URL structure:

```
dv.lk           → Link hub / landing page
dv.lk/manas     → Annual publication
dv.lk/sahayak   → Client handbook
dv.lk/karm      → Karm platform
dv.lk/github    → GitHub org
dv.lk/talk      → Book a discovery call
```

Keep `devalok.in` as the canonical domain for all structured data and SEO authority.

---

## Long-Term Play

### Wikipedia

Wikipedia remains the single highest-impact asset for AI visibility. It appears in virtually every LLM's training data and is the most-cited domain by ChatGPT.

**Current notability status:** Devalok has some early notability signals — media features in Packaging of the World, World Brand Design Society, and Creative Gaga. But these likely aren't sufficient for a standalone Wikipedia article yet.

**Building toward notability:**
- Continue pursuing press coverage and industry features
- Enter design awards (Communication Arts, D&AD, Red Dot, IIID)
- Seek third-party profiles and interviews (not self-published)
- Any coverage of Karm, Sarathi, or Mudit's ASU achievements helps

Once 3–5 independent reliable sources exist, a Wikipedia article becomes viable. Don't rush this — a poorly-sourced article will be deleted and that's harder to recover from.


### Monitor AI Mentions

- **Manual testing:** Regularly ask ChatGPT, Claude, Perplexity, and Gemini queries like "design studios in India," "brand identity design Lucknow," "best packaging design studios"
- **Track referral traffic:** Set up GA4 custom channel groups for AI referrals (chatgpt.com, claude.ai, perplexity.ai)
- **Tools:** Qwairy, Profound, or similar AI visibility monitoring platforms as they mature

---

## Execution Checklist

### This Week (Priority Order)

- [ ] **CRITICAL:** Create corrected `devalok.in/llms.txt` (use version in this document, NOT the original draft)
- [ ] Update `robots.txt` with complete three-tier AI bot allowances
- [ ] Add corrected JSON-LD Organization schema to homepage
- [ ] Create Wikidata entity with proper disambiguation from the philosophical concept
- [ ] Create Crunchbase profile

### This Month

- [ ] Add Schema.org markup to all key pages (services, about, works, blog)
- [ ] Create Clutch.co profile and request client reviews
- [ ] Create/complete GoodFirms profile
- [ ] Ensure Google Business Profile is complete for both locations
- [ ] Publish first blog article (recommend the process article)
- [ ] Set up `dv.lk/llms.txt` as cross-property entry point
- [ ] Begin converting Sahayak to web-accessible format
- [ ] Publish Service Capabilities Report as web pages at `devalok.in/capabilities`

### Next Quarter

- [ ] Publish 4 more blog articles (packaging, motion, production network, cost guide)
- [ ] Build content clusters around all six disciplines (7 hubs)
- [ ] Create case study web pages (not PDFs) for 5+ projects (Bondle, Eat Purposefully, Arculis, MoveCars, NEETI)
- [ ] Cross-post content to Medium, Dev.to, Reddit
- [ ] Write and publish the Karm MCP technical article
- [ ] Create FAQ pages with Schema.org FAQPage markup for each discipline
- [ ] Extract 2–3 articles from Manas to web
- [ ] Add Schema.org Service markup to each capabilities/discipline page

### Ongoing

- [ ] Monitor AI mentions monthly
- [ ] Track AI referral traffic in GA4
- [ ] Update key content quarterly for freshness
- [ ] Build toward Wikipedia notability
- [ ] Enter 1–2 design awards per quarter
- [ ] Post weekly on LinkedIn company page

---

## What Changed from the Original Draft

| Issue | Original | Corrected |
|-------|----------|-----------|
| **Company description** | "Software development company" | "Full-service design and strategy studio" |
| **Service scope** | 4 services implied | 6 integrated disciplines from capabilities report |
| **llms.txt services** | Next.js, React, Node.js, Mobile Apps | Brand identity, packaging, UI/UX, print & event, motion & multimedia, production network |
| **JSON-LD knowsAbout** | 8 software terms | 20 design/production terms across all 6 disciplines |
| **robots.txt bots** | 5 bots listed, some incorrect names | 15+ bots with correct three-tier names |
| **15.9% conversion stat** | Presented as universal fact | Contextualized as single B2B case study |
| **780M Perplexity queries** | Presented as current | Noted as May 2025 figure, now ~1.2–1.5B |
| **Karm/MCP** | Not mentioned | Added as unique discoverability asset |
| **Media features** | Not mentioned | Included as existing notability signals |
| **Motion & Multimedia** | Not mentioned | Full discipline with ASU case study (7.2K views) |
| **Production Network** | Briefly mentioned as "manufacturing partnerships" | Full supply chain capability — strategy, sourcing, QA, logistics |
| **Case studies referenced** | None specific | Bondle, Eat Purposefully, Arculis, MoveCars, NEETI, ASU |
| **Blog article topics** | 3 software-focused topics | 5 topics aligned with actual disciplines |
| **Content clusters** | 3 hubs | 7 hubs covering all disciplines + cross-cutting |
| **Sahayak strategy** | Brief mention | Detailed web-accessible documentation plan |

---

## Bonus: The Capabilities Report as a Discoverability Asset

The Service Capabilities Report itself is one of Devalok's strongest AI discoverability assets — but only if it's web-accessible. Currently it lives in Google Docs.

**Recommended action:** Publish a web version at `devalok.in/capabilities` with:
- Individual pages for each of the six disciplines
- Schema.org Service markup on each discipline page
- Case study callouts with structured data
- Clear "When You Need This" sections (these directly match how people query AI systems)

The "When You Need This" triggers in the capabilities report are essentially pre-built GEO content — they mirror the exact phrasing people use when asking AI assistants for help. For example, "Launching a new brand or venture," "Entering new markets or categories," and "Replacing underperforming suppliers" are all real queries that AI systems field daily.

---

*This document should be treated as a living action plan. Review and update quarterly as the AI search landscape evolves.*
