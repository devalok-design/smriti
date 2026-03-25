# Devalok Document Design Guidelines

> Visual and typographic specifications for all Devalok-produced documents — proposals, briefs, SOWs, and deliverables.

---

## Contents

- Font and typography scale
- Color palette and usage
- Page layout and paper size
- Chakra watermark
- Spacing
- List formatting
- Document structure (proposals and briefs)
- Emphasis patterns
- Sign-off rules
- Writing rules (anti-AI)
- What Devalok documents do NOT have
- Design principles

---

## Font

**Inter** exclusively. No secondary typeface. Every element — headings, body, labels, tables, footer — is Inter.

---

## Typography Scale

| Element | Size | Weight | Color | Notes |
|---------|------|--------|-------|-------|
| Document title | 23–24pt | Bold | `#d33163` or `#1a1a1a` | Pink for Devalok-originated docs (briefs). Dark for client-facing (proposals). |
| Client/project subtitle | 12–13pt | SemiBold | `#712846` or client accent | ALL CAPS for client name, sentence case for project type. Pipe-separated when combined. |
| Section heading | 13pt | **SemiBold** | `#712846` | Not Bold. SemiBold. Authoritative without being heavy. |
| Section heading (large) | 18pt | SemiBold | `#1a1a1a` | For major structural sections in longer documents. Use sparingly. |
| Phase/sub-heading | 13pt | Bold | `#d33163` | Pink distinguishes phases from section headings. |
| Body text | 11pt | Regular | `#1a1a1a` | Primary reading text. |
| Body emphasis | 11pt | Bold | `#1a1a1a` | Key terms, lead-in phrases in bullet lists. |
| Client name (in-text) | 11pt | Bold | Client accent color | Adapts to each client's brand. Devalok's colors stay on structural elements. |
| Metadata labels | 10pt | Bold | `#1a1a1a` or `#712846` | "Prepared for:", "Client:", "Date:" etc. |
| Metadata values | 10pt | Regular | `#1a1a1a` | Paired with metadata labels. |
| Timing/phase duration | 11pt | Italic | `#4a4a4a` | "Week 1–2", "Day 1". Muted gray, never black. |
| Intro/descriptive paragraph | 10pt | Regular | `#666666` | Document-opening context paragraphs. Softer than body text. |
| Key figures (investment, timeline) | 16pt | Bold | `#d33163` | "$24,000 USD", "8–10 weeks". These numbers command attention. |
| Table header | 9pt | Bold | `#000000` | |
| Table body | 9pt | Regular | `#000000` | Background: `#f8f4f5` |
| Footer — company name | 9pt | Regular | `#4a4a4a` | "Devalok Design and Strategy Studio Pvt. Ltd." |
| Footer — tagline | 9pt | Italic | `#d33163` | "Different by Design" — always italic, always pink. |

---

## Color Palette

| Color | Hex | Role |
|-------|-----|------|
| **Padmavarna (pink)** | `#d33163` | Document titles, phase headings, key figures, footer tagline, accent elements |
| **Devalok dark** | `#712846` | Section headings, field labels, list markers — structural/secondary accent |
| **Primary text** | `#1a1a1a` | Body text, bold emphasis, large section headings |
| **Muted text** | `#4a4a4a` | Timing info, footnotes, sub-notes |
| **Soft text** | `#666666` | Introductory/descriptive paragraphs |
| **True black** | `#000000` | Tables. Also acceptable for body text. |
| **Table/banner background** | `#f8f4f5` | Light warm background for tables and investment banners |
| **White** | `#ffffff` | Text on colored backgrounds (investment banner) |
| **Client accent** | Varies | Client name mentions in body text. Bold + client's primary brand color. |

### Client Color Adaptation

When creating documents for a specific client, their brand color appears for their name mentions within body text. Devalok's own colors (`#d33163`, `#712846`) remain for structural elements — headings, phases, key figures. The two systems layer, never compete.

---

## Page Layout

| Property | Value |
|----------|-------|
| **US clients** | US Letter (8.5" x 11" / 612 x 792pt) |
| **Indian clients** | A4 (210 x 297mm / 595 x 842pt) |
| Left margin | 36pt (~0.5" / ~12.7mm) |
| Right margin | 36pt |
| Top margin | 36pt |
| Bottom margin | ~36pt |
| Content width | ~540pt (Letter) / ~523pt (A4) |

**Rule:** Paper size follows the client's geography, not Devalok's. US clients get Letter. Indian and international clients get A4.

---

## Chakra Watermark

- **Present on every page** (or at minimum, page 1)
- **Position:** Top-right corner
- **Rendered size:** ~23 x 23pt
- **Source:** Devalok Chakra asset, brand color
- **Opacity:** ~30% — subtle enough to not compete with content
- **Effect:** A quiet brand signature — "this is a Devalok document"

---

## Spacing

| Between | Gap |
|---------|-----|
| Document title to subtitle/metadata | ~20–30pt |
| Section heading to first body text | ~28–31pt |
| Between body paragraphs | ~20–22pt |
| Between bullet items | ~17pt |
| Phase heading to timing line | ~24pt |
| Timing line to first bullet | ~20pt |

**Line height:** ~1.3x font size for body text (11pt text with ~14pt leading).

**Principle:** Content breathes. Generous vertical spacing. Never cramped.

---

## List Formatting

### Bullet Lists

- Bullet marker at ~50pt from left margin, text at ~63pt
- **Bold lead-in phrase** + regular continuation on same line
- Bullet markers can be colored (`#712846`) or neutral
- Example: **Responsive logo variants:** Favicon, mobile header, social profile versions

### Numbered Lists

- Number + period, optionally colored `#712846`
- Same indent structure as bullets
- For sequential steps, ranked items

### Lettered Lists

- "A.", "B.", "C." in `#712846`
- For deliverable categories, non-sequential groupings

---

## Document Structure

### Proposals (Client-Facing)

```
1. Title Block
   - Document title (large)
   - Client name (ALL CAPS) | Project type
   - Metadata: Prepared for, Prepared by, Date
   - Key figures callout (Investment, Timeline) in pink

2. Understanding / Context
   - What we understood from the brief
   - Numbered priorities/goals

3. Scope of Work
   - Phased breakdown (Phase 1, 2, 3...)
   - Each phase: pink heading -> italic gray timing -> bullet list

4. Investment
   - Banner: white text on #f8f4f5 background
   - Payment structure
   - Timeline summary

5. What's Included / Not Included
   - Clean bullet lists
   - "Not Included" and "Optional Add-Ons" as sub-sections with pink headings

6. Why Devalok
   - The ONE section heading that earns #d33163 instead of #1a1a1a
   - Brief narrative + bullet list with bold lead-ins

7. Next Steps
   - Simple numbered list

8. Closing
   - "With warmth," (italic)
   - Name (bold)
   - Title, email (regular)

9. Footer
   - "Devalok Design and Strategy Studio Pvt. Ltd." (small, muted)
   - "Different by Design" (small, italic, pink)
```

### Briefs (Internal / Pre-Project)

```
1. Title Block
   - Document title in #d33163 Bold
   - Client + project type in #712846 SemiBold

2. Context Paragraph
   - 10pt, #666666 — sets the stage softly

3. Project Overview
   - Key-value pairs (Client, Location, Heritage, Objective)
   - Labels in #712846 Bold, values in body color

4. Content Sections
   - Section headings in #712846 SemiBold
   - Body text with bold emphasis for key terms
   - Bullet/lettered lists for deliverables

5. Timeline / Execution
   - Simple table (9pt, #f8f4f5 background)
   - Day / Phase / Deliverable columns

No closing or sign-off. Briefs are working documents, not correspondence.
```

---

## Sign-Off Rules

| Document Type | Sign-Off |
|---------------|----------|
| **Proposals** | "With warmth," (italic) + name (bold) + title and contact (regular) |
| **Briefs** | None. Internal working documents. |
| **SOWs** | Formal signature block as needed |
| **Internal docs** | None, or informal as appropriate |

---

## Emphasis Patterns

| Technique | When to Use |
|-----------|-------------|
| Bold + client color | Client's company name in body text |
| Bold `#1a1a1a` | Key terms, deliverable names, lead-in phrases in lists |
| Bold `#d33163` | Phase headings, key monetary/timeline figures, "Not Included" / "Optional" labels |
| Bold `#712846` | Field labels in metadata blocks (Client:, Location:, etc.) |
| Italic `#4a4a4a` | Phase timing ("Week 1–2"), secondary temporal info |
| Italic `#1a1a1a` | Closing salutation ("With warmth,") |
| Small muted text | Footnotes, sub-bullets, third-party cost notes |

---

## Writing Rules (Anti-AI)

These apply to all Devalok document content. They prevent writing from feeling machine-generated.

### Banned Patterns

| Banned | Why / What to Do Instead |
|--------|--------------------------|
| Em dashes (—) | Restructure with commas, periods, or colons. |
| "It's not X, it's Y" structures | Overused LLM cliche. Rewrite as a direct statement. |
| Motivational/poetic closers | End with substance, not inspiration. |
| Vague fillers: "quietly," "deeply," "visionary," "in today's world," "here's the thing" | Say the specific thing or cut the sentence. |
| Content creator energy | Not dramatic, not performative. State things with calm authority. |

### Writing Discipline

- **Simple, clear sentences.** Each adds meaning and moves the thought forward.
- **Grounded in specifics.** Real details, real names, real context. Not vague inspiration.
- **State, don't sell.** Calm authority. No hype, no superlatives.
- **No padding.** Content dictates length. Short and complete beats long and repetitive.

---

## What Devalok Documents Do NOT Have

- No decorative borders, lines, or dividers (whitespace does the job)
- No page numbers
- No running headers or footers (just the Chakra watermark)
- No icons or illustrations in the body
- No colored section backgrounds (one exception: investment/table banner at `#f8f4f5`)
- No drop shadows, gradients, or decorative flourishes
- No underlined text
- No ALL CAPS headings (only client names in subtitles)

---

## Design Principles

1. **Typography is the design.** Hierarchy comes from size, weight, and color — not boxes, lines, or decorations.
2. **Restraint is premium.** Every element earns its place. Nothing ornamental.
3. **Two accents, two jobs.** `#d33163` for emphasis. `#712846` for structure. They never blur.
4. **Adapt without losing identity.** Client's color enters for their name; Devalok's colors own the scaffolding.
5. **Warmth in small things.** "With warmth," not "Best regards." Italic pink tagline. Chakra on every page.
6. **Content breathes.** Generous spacing. Short paragraphs. No walls of text.
7. **SemiBold over Bold for headings.** Lighter touch. Confident without shouting.

---

*Reference: brand/document-design.md | Version 1.0.0*
