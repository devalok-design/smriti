# Devalok Email Components

> HTML email building blocks — headers, footers, typography, buttons, layouts.

---

## Contents

- Design tokens
- Font stack
- Email header (light background)
- Email footer (deep pink)
- Typography components (H1, H2, H3, greeting, body)
- Content components (blockquote, pull quote, highlight box, divider)
- Feature item (What's New)
- Buttons (primary, secondary)
- Two-column layout
- Image and video blocks
- Signature and contact blocks
- Complete email template structure

---

## Design Tokens

These are the canonical values for all Devalok emails, derived from Shilp Sutra.

### Colors

| Token | Hex | Usage |
|-------|-----|-------|
| background | #FFFFFF | Email body background |
| surfaceSubtle | #F7F8FA | Section backgrounds |
| surfaceBorder | #E5E5E5 | Borders, dividers |
| textPrimary | #1A1A1A | Headings |
| textBody | #51545E | Body text |
| textMuted | #6B6E76 | Secondary text |
| textCaption | #A8AAAF | Captions, metadata |
| accent | #D33163 | Padmavarna — CTAs, links, brand accents |
| accentSubtle | #FCF0F4 | Accent backgrounds |
| footerBg | #712846 | Deep pink footer |
| footerBottomBg | #612040 | Footer bottom strip |
| footerText | #EFD5D9 | Light text on footer |
| footerAccent | #932044 | Footer dividers |
| footerMuted | #DD9EB8 | Footer secondary text |
| footerDark | #B02651 | Footer legal text |

### Typography

| Element | Font | Weight | Size | Line Height |
|---------|------|--------|------|-------------|
| Heading | Arial, Helvetica, sans-serif | 700 | 24px | 1.25 |
| Body | Arial, Helvetica, sans-serif | 400 | 16px | 1.6 |
| Body Small | Arial, Helvetica, sans-serif | 400 | 14px | 1.5 |
| Caption | Arial, Helvetica, sans-serif | 400 | 12px | 1.5 |

**Note:** Emails use Arial/Helvetica for maximum client compatibility. Playfair Display can be used for editorial emails where supported (Apple Mail, iOS Mail, webmail), with Georgia as fallback.

### Spacing

| Token | Value |
|-------|-------|
| Container width | 600px |
| Content padding | 40px (24px mobile) |
| Section gap | 32px |
| Element gap | 20px |
| CTA margin | 32px |

---

## Font Import (Editorial Emails Only)

For newsletter-style emails where custom fonts enhance the reading experience:

```html
<!--[if mso]>
<style type="text/css">
  body, table, td { font-family: Arial, sans-serif !important; }
</style>
<![endif]-->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Playfair+Display:ital,wght@0,400;0,500;0,600;1,400&display=swap" rel="stylesheet">
```

For transactional emails, skip custom fonts entirely — use the Arial/Helvetica stack.

---

## Email Header (Light Background)

```html
<div style="padding: 48px 48px 40px; text-align: center; background-color: #ffffff;">
  <img
    src="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/brand/devalok/logos/monogram-brand-512.png"
    alt="Devalok"
    style="height: 52px; width: auto; margin: 0 auto;"
  />
  <div style="width: 1px; height: 32px; background-color: #E5E5E5; margin: 20px auto;"></div>
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 11px; font-weight: 500; letter-spacing: 2px; text-transform: uppercase; color: #A8AAAF; margin: 0;">
    <span style="color: #D33163;">Sankalan</span> · Issue 07 · December 2025
  </p>
</div>
```

---

## Email Footer (Deep Pink)

```html
<div style="background-color: #712846;">
  <!-- Footer Top -->
  <div style="padding: 40px 48px; text-align: center;">
    <img
      src="https://devalok-public-assets.s3.ap-south-1.amazonaws.com/email-logos/devalok-wordmark-white.png"
      alt="Devalok"
      style="height: 48px; width: auto; margin: 0 auto 24px;"
    />
    <p style="font-family: Arial, Helvetica, sans-serif; font-size: 11px; font-weight: 600; letter-spacing: 3px; text-transform: uppercase; color: #ffffff; margin: 0 0 8px 0;">Devalok</p>
    <p style="font-family: Georgia, serif; font-size: 14px; font-style: italic; color: #EFD5D9; margin: 0 0 32px 0;">Design and Strategy Studio</p>

    <!-- Divider -->
    <div style="width: 40px; height: 1px; background-color: #932044; margin: 24px auto;"></div>

    <!-- Footer Nav -->
    <div style="margin: 24px 0;">
      <a href="https://devalok.in/works" style="display: inline-block; margin: 0 16px; font-family: Arial, Helvetica, sans-serif; font-size: 12px; font-weight: 500; color: #EFD5D9; text-decoration: none;">Work</a>
      <a href="https://devalok.in" style="display: inline-block; margin: 0 16px; font-family: Arial, Helvetica, sans-serif; font-size: 12px; font-weight: 500; color: #EFD5D9; text-decoration: none;">About</a>
      <a href="https://talk.devalok.in" style="display: inline-block; margin: 0 16px; font-family: Arial, Helvetica, sans-serif; font-size: 12px; font-weight: 500; color: #EFD5D9; text-decoration: none;">Contact</a>
    </div>
  </div>

  <!-- Footer Bottom -->
  <div style="padding: 20px 48px; background-color: #612040; text-align: center;">
    <p style="font-family: Arial, Helvetica, sans-serif; font-size: 11px; color: #DD9EB8; margin: 0 0 8px 0;">
      Lucknow, India · Phoenix, Arizona
    </p>
    <p style="font-family: Arial, Helvetica, sans-serif; font-size: 10px; color: #B02651; margin: 0;">
      Devalok Design and Strategy Studio Pvt. Ltd.
    </p>
  </div>
</div>
```

---

## Typography Components

### Headline (H1) — Editorial

```html
<h1 style="font-family: 'Playfair Display', Georgia, serif; font-size: 28px; font-weight: 500; line-height: 1.3; margin: 0 0 24px 0; color: #1A1A1A;">
  A New Brand Takes Shape
</h1>
```

### Headline (H1) — Transactional

```html
<h1 style="font-family: Arial, Helvetica, sans-serif; font-size: 24px; font-weight: 700; line-height: 1.25; letter-spacing: -0.02em; margin: 0 0 20px 0; color: #1A1A1A;">
  Your Weekly Summary
</h1>
```

### Section Header (H2)

```html
<h2 style="font-family: 'Playfair Display', Georgia, serif; font-size: 22px; font-weight: 500; line-height: 1.35; margin: 48px 0 16px 0; color: #1A1A1A;">
  Behind the Work
</h2>
```

### Section Label (H3)

```html
<h3 style="font-family: Arial, Helvetica, sans-serif; font-size: 13px; font-weight: 600; line-height: 1.4; margin: 40px 0 20px 0; color: #D33163; text-transform: uppercase; letter-spacing: 1px;">
  What's New
</h3>
```

### Greeting

```html
<p style="font-family: 'Playfair Display', Georgia, serif; font-size: 24px; font-weight: 400; color: #1A1A1A; margin: 0 0 24px 0;">
  Namaskar,
</p>
```

### Body Paragraph

```html
<p style="font-family: Arial, Helvetica, sans-serif; font-size: 16px; margin: 0 0 16px 0; color: #51545E; line-height: 1.6;">
  Your paragraph text here.
</p>
```

---

## Content Components

### Blockquote

```html
<div style="margin: 32px 0; padding: 24px; background-color: #FCF0F4; border-left: 3px solid #D33163;">
  <p style="font-family: 'Playfair Display', Georgia, serif; font-size: 18px; font-style: italic; line-height: 1.6; color: #1A1A1A; margin: 0 0 8px 0;">
    "Design is not just what it looks like. It's what it holds — the story, the intention, the care."
  </p>
  <span style="font-family: Arial, Helvetica, sans-serif; font-size: 13px; color: #A8AAAF;">From our philosophy</span>
</div>
```

### Pull Quote (Centered)

```html
<div style="margin: 48px 0; padding: 32px 0; text-align: center; border-top: 2px solid #FCF0F4; border-bottom: 2px solid #FCF0F4;">
  <p style="font-family: 'Playfair Display', Georgia, serif; font-size: 22px; font-weight: 400; font-style: italic; line-height: 1.5; color: #1A1A1A; margin: 0;">
    "Every brand carries a <span style="color: #D33163;">story worth telling</span>."
  </p>
</div>
```

### Highlight Box

```html
<div style="margin: 32px 0; padding: 24px; background-color: #FCF0F4; border-left: 3px solid #D33163;">
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 14px; margin: 0; color: #51545E; line-height: 1.6;">
    <strong>Coming soon:</strong> A detailed case study on our approach to packaging design.
  </p>
</div>
```

### Divider

```html
<hr style="height: 1px; background-color: #E5E5E5; margin: 40px 0; border: none;">
```

---

## What's New Feature Item

```html
<div style="background-color: #F7F8FA; margin: 32px -48px; padding: 32px 48px;">
  <table width="100%" cellpadding="0" cellspacing="0" style="margin-bottom: 24px; padding-bottom: 24px; border-bottom: 1px solid #E5E5E5;">
    <tr>
      <td style="width: 56px; vertical-align: top; padding-right: 20px;">
        <div style="width: 44px; height: 44px; background-color: #ffffff; border: 1px solid #E5E5E5; text-align: center; line-height: 44px; font-size: 20px; color: #D33163;">
          *
        </div>
      </td>
      <td style="vertical-align: top;">
        <p style="font-family: 'Playfair Display', Georgia, serif; font-size: 18px; font-weight: 500; color: #1A1A1A; margin: 0 0 6px 0;">Team Growth</p>
        <p style="font-family: Arial, Helvetica, sans-serif; font-size: 14px; color: #51545E; margin: 0; line-height: 1.6;">We welcomed Shriman Visahan to the team as Operations Associate.</p>
        <a href="#" style="display: inline-block; margin-top: 8px; font-family: Arial, Helvetica, sans-serif; font-size: 13px; font-weight: 500; color: #D33163; text-decoration: none;">Learn more &rarr;</a>
      </td>
    </tr>
  </table>
</div>
```

---

## Buttons

### Primary CTA

```html
<a href="https://devalok.in/works" style="display: inline-block; padding: 14px 32px; background-color: #D33163; color: #ffffff; text-decoration: none; font-family: Arial, Helvetica, sans-serif; font-size: 13px; font-weight: 600; letter-spacing: 0.3px;">
  View Our Work
</a>
```

### Secondary CTA

```html
<a href="https://talk.devalok.in" style="display: inline-block; padding: 12px 28px; background-color: transparent; color: #1A1A1A; text-decoration: none; font-family: Arial, Helvetica, sans-serif; font-size: 13px; font-weight: 600; border: 1px solid #1A1A1A; margin-left: 12px;">
  Start a Conversation
</a>
```

---

## Two-Column Layout

```html
<div style="margin: 32px 0; background-color: #F7F8FA; padding: 24px;">
  <table width="100%" cellpadding="0" cellspacing="0">
    <tr>
      <td style="width: 48%; vertical-align: top; padding-right: 20px;">
        <h4 style="font-family: Arial, Helvetica, sans-serif; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; color: #D33163; margin: 0 0 8px 0;">For Brands</h4>
        <p style="font-family: Arial, Helvetica, sans-serif; font-size: 14px; margin: 0; color: #51545E; line-height: 1.6;">Building something meaningful? <a href="https://talk.devalok.in" style="color: #D33163;">Book a call &rarr;</a></p>
      </td>
      <td style="width: 48%; vertical-align: top; padding-left: 20px; border-left: 1px solid #E5E5E5;">
        <h4 style="font-family: Arial, Helvetica, sans-serif; font-size: 11px; font-weight: 600; text-transform: uppercase; letter-spacing: 1px; color: #D33163; margin: 0 0 8px 0;">For Creatives</h4>
        <p style="font-family: Arial, Helvetica, sans-serif; font-size: 14px; margin: 0; color: #51545E; line-height: 1.6;">Looking for a home that values craft? <a href="mailto:pac@devalok.in" style="color: #D33163;">Get in touch &rarr;</a></p>
      </td>
    </tr>
  </table>
</div>
```

---

## Image Block

```html
<div style="margin: 32px 0;">
  <img src="IMAGE_URL" alt="Description" style="width: 100%; height: auto; display: block;">
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 13px; color: #A8AAAF; margin-top: 12px; font-style: italic;">
    Caption text here
  </p>
</div>
```

---

## Video Block (Thumbnail + Play)

```html
<div style="margin: 32px 0;">
  <a href="VIDEO_URL" style="display: block; position: relative; text-decoration: none;">
    <img src="THUMBNAIL_URL" alt="Video" style="width: 100%; height: auto; display: block;">
    <div style="position: absolute; top: 50%; left: 50%; transform: translate(-50%, -50%); width: 64px; height: 64px; background-color: #D33163; text-align: center; line-height: 64px;">
      <span style="color: #ffffff; font-size: 24px;">&#9654;</span>
    </div>
  </a>
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 13px; color: #A8AAAF; margin-top: 12px;">
    Watch: Video Title &middot; Duration
  </p>
</div>
```

---

## Signature Block

```html
<div style="margin: 48px 0 0 0; padding-top: 32px; border-top: 1px solid #E5E5E5;">
  <p style="font-family: 'Playfair Display', Georgia, serif; font-size: 18px; color: #1A1A1A; margin: 0 0 4px 0;">Mudit Lal</p>
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 13px; color: #A8AAAF; margin: 0;">Founder, Devalok</p>
</div>
```

---

## Contact Block

```html
<div style="margin: 32px 0; padding: 20px 24px; background-color: #F7F8FA; text-align: center;">
  <p style="font-family: Arial, Helvetica, sans-serif; font-size: 14px; margin: 0; color: #51545E;">
    <a href="mailto:hello@devalok.in" style="color: #1A1A1A; font-weight: 500; text-decoration: none;">hello@devalok.in</a> &middot;
    <a href="tel:+917754850181" style="color: #1A1A1A; font-weight: 500; text-decoration: none;">+91 77548 50181</a>
  </p>
</div>
```

---

## Complete Email Template Structure

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <!--[if mso]>
  <style type="text/css">
    body, table, td { font-family: Arial, sans-serif !important; }
  </style>
  <![endif]-->
  <style>
    body {
      font-family: Arial, Helvetica, sans-serif;
      background-color: #f5f5f5;
      margin: 0;
      padding: 0;
    }
    .wrapper { width: 100%; background-color: #f5f5f5; padding: 32px 0; }
    .container { max-width: 600px; margin: 0 auto; background-color: #ffffff; }
  </style>
</head>
<body>
  <div class="wrapper">
    <div class="container">
      <!-- Header (monogram, divider, meta) -->
      <!-- Content (greeting, body, components) -->
      <!-- Footer (deep pink with white branding) -->
    </div>
  </div>
</body>
</html>
```

---

*Reference: brand/email-components.md | Version 1.0.0*
