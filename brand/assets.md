# Devalok Brand Assets

> All brand assets are hosted on AWS S3. Use these URLs in HTML emails, web outputs, and documents.

---

## Contents

- Asset system overview
- URL pattern and manifest
- Devalok logos (monogram, wordmark, shell, coin, shloka, dass, chakra)
- Karm logos (icon, wordmark, wordmark-icon)
- Favicons
- Email logos (PNG — for email headers/footers)
- Email icons (custom 3D PNGs)
- Logo usage guide (hierarchy, color rules, watermark spec)
- Web implementation snippets

---

## Asset System Overview

| Property | Value |
|----------|-------|
| **S3 Bucket** | `devalok-public-assets` |
| **Region** | ap-south-1 |
| **Base URL** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com` |
| **Brand Assets Base** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand` |
| **Manifest** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/manifest.json` |
| **Total Assets** | 172 |
| **Last Generated** | 2026-03-19 |

---

## URL Pattern

All brand logos follow a consistent pattern:

```
{base}/brand/{brand}/logos/{type}-{color}-{size}.{format}
```

**Brands:** `devalok`, `karm`

**Formats:** `png`, `webp`, `svg` (SVG available for wordmark, dass, chakra, and Karm types)

**Sizes:** `512`, `1024` (SVGs have no size suffix)

**Colors:** `brand` (Padmavarna pink), `black`, `white`

### Example URLs

```
https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/logos/monogram-brand-1024.png
https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/logos/wordmark-brand.svg
https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/karm/logos/wordmark-icon-brand.svg
```

---

## Devalok Logos

### Available Types

| Type | Description | Colors | Formats |
|------|-------------|--------|---------|
| **monogram** | Icon only (hand with lotus) | brand, black, white | png, webp |
| **monogram-wordmark** | Icon + "DEVALOK" text | brand, black, white | png, webp |
| **monogram-shell** | Icon in circular container | brand, black, white | png, webp |
| **monogram-shell-wordmark** | Icon in shell + text | brand, black, white | png, webp |
| **monogram-coin-wordmark** | Icon in coin style + text | brand, black, white | png, webp |
| **wordmark** | "DEVALOK" text only | brand, black, white | svg, png, webp |
| **dass** | "Design and Strategy Studio" | brand, black, white | svg, png, webp |
| **shloka** | Sanskrit verse version | brand, black, white | png, webp |
| **chakra** | Svadhisthana flower mark | brand, black, white | svg, png, webp |

### Default — Devalok Wordmark (Brand)

```
https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/logos/wordmark-brand.svg
```

---

## Karm Logos

| Type | Description | Colors | Formats |
|------|-------------|--------|---------|
| **icon** | Karm icon only | brand, black, white | svg, png, webp |
| **wordmark** | "KARM" text only | brand, black, white | svg, png, webp |
| **wordmark-icon** | Icon + "KARM" text | brand, black, white | svg, png, webp |

### Default — Karm Wordmark + Icon (Brand)

```
https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/karm/logos/wordmark-icon-brand-1024.png
```

---

## Favicons

Favicons are at `{base}/brand/{brand}/favicons/` — check the manifest for exact paths and sizes. Available for both Devalok and Karm in png, ico, and svg formats.

---

## Email Logos (PNG)

For use in HTML email headers and footers. These are optimized PNG versions at `{base}/email-logos/`.

| Logo | URL |
|------|-----|
| **Karm — Brand** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-logos/karm-wordmark-icon-brand.png` |
| **Karm — White** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-logos/karm-wordmark-icon-white.png` |
| **Devalok — Brand** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-logos/devalok-wordmark-brand-no-padding.png` |
| **Devalok — White** | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-logos/devalok-wordmark-white.png` |

---

## Email Icons (Custom 3D PNGs)

Custom Devalok 3D-style icons at `{base}/email-icons/`. Used in transactional and notification emails.

| Icon | URL |
|------|-----|
| alarm-clock | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/alarm-clock.png` |
| bar-chart | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/bar-chart.png` |
| bell | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/bell.png` |
| clipboard | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/clipboard.png` |
| envelope | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/envelope.png` |
| handshake | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/handshake.png` |
| hourglass | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/hourglass.png` |
| megaphone | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/megaphone.png` |
| memo | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/memo.png` |
| padlock | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/padlock.png` |
| party-popper | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/party-popper.png` |
| speech-balloon | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/speech-balloon.png` |
| warning | `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-icons/warning.png` |

---

## Logo Usage Guide

### Devalok — Logo Hierarchy

Devalok has three primary logo assets. Use them in this priority order:

| Priority | Logo | When to Use | Sizing |
|----------|------|-------------|--------|
| **Default** | **Wordmark** | Most contexts: email headers, document headers, web, presentations. Clearly conveys "Devalok" — this is the everyday logo. | Any size |
| **Premium** | **Monogram Shell Wordmark** | Reserved for large, prominent placements that give the logo prime real estate: hero sections, cover pages, presentation title slides. This logo has many fine details that need room to breathe. | Medium to large only |
| **Signature** | **Chakra** | Document watermark/signature. Marks a document as Devalok's. Not always used — primarily for Word docs, PDFs, and formal deliverables. | Proportional to page |

**All other Devalok logo types** (monogram, monogram-wordmark, monogram-coin-wordmark, shloka, dass) are available in the asset system but are rarely used in standard documents.

### Karm — Logo Hierarchy

| Priority | Logo | When to Use |
|----------|------|-------------|
| **Default** | **Wordmark + Icon** | Full Karm logo for regular placements |
| **Mark** | **Icon** | Compact Karm mark — the Devalok Chakra in curly braces, signifying Karm |

### Color Rules

| Color | Fill Value | When to Use |
|-------|-----------|-------------|
| **Brand** (Padmavarna pink) | `#D33163` | Default. Light backgrounds, standard contexts. |
| **White** | `#FFFFFF` | Dark backgrounds — dark sections, email footers, dark headers. |
| **Black** | `#000000` | Monochrome contexts, formal printing, when brand pink doesn't fit. |

### Chakra Watermark Specification

When using the Chakra as a document signature:

- **Position:** Top-right corner of the page/document
- **Opacity:** 30%
- **Padding:** Equal right and top padding, proportional to document margins
- **Effect:** A light, subtle mark indicating "this is a Devalok document"

### Asset Selection by Context

| Use Case | Recommended Asset | URL Snippet |
|----------|-------------------|-------------|
| **Document header** | Devalok wordmark, brand, SVG | `.../devalok/logos/wordmark-brand.svg` |
| **Document watermark** | Devalok chakra, brand, SVG (30% opacity) | `.../devalok/logos/chakra-brand.svg` |
| **Premium hero/cover** | Devalok monogram-shell-wordmark, brand, 1024 PNG | `.../devalok/logos/monogram-shell-wordmark-brand-1024.png` |
| **Email Header** | Devalok email logo, brand, PNG | `.../email-logos/devalok-wordmark-brand-no-padding.png` |
| **Email Footer (dark bg)** | Devalok email logo, white, PNG | `.../email-logos/devalok-wordmark-white.png` |
| **Web Logo (scalable)** | Devalok wordmark, brand, SVG | `.../devalok/logos/wordmark-brand.svg` |
| **Dark Background** | Any `white` variant | `...-white-{size}.{format}` |
| **Light Background** | `brand` or `black` variant | `...-brand-{size}.{format}` |
| **Karm UI (full)** | Karm wordmark-icon, brand | `.../karm/logos/wordmark-icon-brand-1024.png` |
| **Karm UI (compact)** | Karm icon, brand | `.../karm/logos/icon-brand-1024.png` |
| **Social / OG Image** | Devalok monogram-shell-wordmark, brand, 1024 PNG | `.../devalok/logos/monogram-shell-wordmark-brand-1024.png` |

All snippet paths are relative to `https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand`.

---

## Web Implementation

### Favicon HTML

```html
<link rel="icon" type="image/svg+xml" href="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/favicons/favicon.svg">
<link rel="icon" type="image/png" href="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/favicons/favicon.png">
<link rel="apple-touch-icon" href="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/favicons/apple-touch-icon.png">
```

### Open Graph / Social Meta

```html
<meta property="og:image" content="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/logos/monogram-wordmark-brand-1024.png">
```

---

## Notes

- **Old CDN links (jsDelivr)** are deprecated. All assets are now on S3.
- **The manifest** (`manifest.json`) is the canonical listing of all 172 assets. Fetch it programmatically for dynamic asset selection.
- **Email logos** are separate from brand logos — optimized PNGs for email client compatibility.
- **To add new assets**: Upload to the S3 bucket, run the upload script (`scripts/upload-brand-assets.mjs` in Karm), and regenerate the manifest.

---

*Reference: brand/assets.md | Version 1.0.0*
