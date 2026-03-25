# Smriti · स्मृति

> *"That which is remembered"* — the preserved knowledge of Devalok, carried forward.

**Smriti** is the institutional knowledge repository of **Devalok Design and Strategy Studio Pvt. Ltd.** It contains the studio's complete identity, philosophy, history, processes, culture, terminology, brand guidelines, and operational details.

Feed any of these documents into an AI system and it will have the context to think, write, design, and operate the Devalok way.

---

## Structure

```
smriti/
├── core/                        # The master reference document
├── glossary/                    # Standalone term & pronunciation reference
├── publications/                # Printed publications converted to markdown
├── services/                    # Service capabilities & offerings detail
├── operations/                  # Internal operations (handbook, TBF, hiring)
├── brand/                       # Brand assets, document design, email components
├── writing/                     # Writing templates & content workflows
└── clients/                     # Client process, case studies
```

## Documents

| Document | Path | Version | Description |
|----------|------|---------|-------------|
| Complete Context | `core/devalok-complete-context.md` | v1.0.0 | The single comprehensive reference for Devalok. Start here. |
| Glossary | `glossary/devalok-glossary.md` | v1.0.0 | All Devalok terminology with etymology, meaning, and pronunciation. |
| Sahayak Handbook | `publications/sahayak-handbook.md` | v1.0.0 | Markdown conversion of the printed client handbook. |
| Mānas Vol. 01 | `publications/manas-vol01.md` | v1.0.0 | Portfolio book 2024–2025. 8 case studies with full design process narratives. |
| Service Capabilities | `services/service-capabilities.md` | v1.0.0 | Full capabilities report across all six disciplines. |
| Lokgranth (Handbook) | `operations/lokgranth-v1.md` | v1.0.0 | Internal team handbook — collaboration, roles, project rhythm, client ops. |
| Brand Assets | `brand/assets.md` | v1.0.0 | S3-hosted logo URLs, favicons, email logos, email icons, manifest reference. |
| Document Design | `brand/document-design.md` | v1.0.0 | Typography, colors, layout, structure, and writing rules for all Devalok documents. |
| Email Components | `brand/email-components.md` | v1.0.0 | HTML email building blocks: headers, footers, typography, buttons, layouts. |
| Client Templates | `writing/client-templates.md` | v1.0.0 | Client email templates (10 types) and proposal templates. |
| Content Templates | `writing/content-templates.md` | v1.0.0 | Social media, case study, newsletter, and internal communication templates. |
| LinkedIn Workflow | `writing/linkedin-workflow.md` | v1.0.0 | LinkedIn content creation — voice rules, personas, pillars, post structure. |

## Conventions

### Versioning

Each document carries a version number in its frontmatter. Versions follow semantic rules:

- **Patch** (v1.0.1) — corrections, clarifications, minor additions
- **Minor** (v1.1.0) — new sections, significant updates to existing content
- **Major** (v2.0.0) — structural rewrites, fundamental changes

Typo fixes and formatting do not require a version bump.

### Source of Truth

Some content exists in both standalone files and the complete context document (`core/devalok-complete-context.md`). The rule:

- **Both must be updated together.** When you change content that appears in multiple places, update all occurrences in the same commit.
- **Standalone files** carry the full detail (e.g., all deliverables, all sub-sections).
- **The complete context doc** carries a curated integration (e.g., summaries, key capabilities only).
- Neither "wins" — they must agree. If they disagree, it's a bug.

Current overlapping content:

| Topic | Standalone File | Complete Context Section |
|-------|----------------|------------------------|
| Glossary/Terminology | `glossary/devalok-glossary.md` | Section 29 |
| Service Capabilities | `services/service-capabilities.md` | Section 10 |
| Brand Assets | `brand/assets.md` | Section 8 (URLs only) |
| Writing Templates | `writing/client-templates.md` | Section 30 (principles only) |

### Naming

No `devalok-` prefix needed on filenames — the repo IS Devalok. Exception: `devalok-complete-context.md` keeps its prefix because it is THE Devalok document.

### Scope

Smriti is about **Devalok the studio** — not any specific product or codebase.

**Belongs here:** Philosophy, brand identity, services, processes, culture, team structure, client work, terminology, publications, operations frameworks.

**Does NOT belong here:** Application code, Karm technical docs, project implementation plans, deployment configs, environment variables.

---

*Devalok Design and Strategy Studio Pvt. Ltd.*
*Lucknow, Uttar Pradesh, Bharat (India) · Phoenix, Arizona, USA*

*आत्मतः शिल्पं कृत्वा — From the soul, we craft.*
