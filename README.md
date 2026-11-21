# 🛡️ CyberShield· Digital Safety Awareness Hub

> **One internet. Four ways to stay safe.**
> A picture-first, bilingual (English + हिंदी) digital-safety hub for new internet users, children, seniors, and women facing online harassment. No jargon. No sign-up. No tracking.

**Live demo:** `<https://your-username.github.io/cybershield/>`
**Course:** Social Engineering & Awareness · Capstone Project · 2026



## 🔍 Overview

Most security-awareness material assumes a confident reader, a fast connection, and a personal device. CyberShield starts from the opposite assumption: the user may be reading on a shared phone, may not read fluently, may be under pressure from a scammer, or may be monitored by the person harming them.

The hub therefore reduces every lesson to **the next safe step**, delivered through four open modules — no gating, no accounts, and no data collection.

**Design principles**

1. **Recognition over recall** — pictures and large tap targets instead of terminology.
2. **Calm under pressure** — urgency is named as a red flag, not used as a design tactic.
3. **Leave no trace by default** — progress lives in the browser; a Panic exit clears it.
4. **Bilingual by design** — Hindi is a first-class layout, not an afterthought.

---

## 👥 Who Is This For?

| # | Path | Audience | Core outcome |
|:-:|------|----------|--------------|
| 01 | **Picture safety** | Low-literacy / first-time users | Recognise a fake OTP request, a suspicious link, and a scam call |
| 02 | **Children & teens** | Ages 9+ | Understand what a photo reveals: face, uniform, home, location |
| 03 | **Seniors** | Older adults on WhatsApp | Slow down urgent money requests; keep OTP and PIN private |
| 04 | **Women & girls** | Anyone facing online harassment | Preserve evidence, lock down accounts, report to the right authority |

All four modules remain open to every visitor — the paths are entry points, not silos.

---

## ✨ Features

### 01 · Picture Safety — *"Spot the danger. No reading needed."*

- Illustrated SVG scenes rendered inline (crisp at any zoom level).
- Two oversized answer buttons: **Safe** / **Scam**, colour + icon coded.
- Immediate, plain-language feedback with a corrective explanation.
- Progress bar and scene counter (`1 / n`) for orientation.
- 🔊 **Read-aloud button** using the Web Speech API (`speechSynthesis`) so a scene can be heard instead of read.
- Completion screen with score and a restart action.

### 02 · Children & Teens — *"Would you share this photo?"*

- A photo-sharing decision game built around a simple, memorable rule set.
- **The 3-question photo check** sidebar:
  1. Is my face, school or uniform showing?
  2. Is my home, street or location showing?
  3. Did I ask everyone in the photo?
- Framing message: *"The internet remembers. A screenshot can travel further than the post."*

### 03 · Seniors — *"Urgent can wait. Check first."*

- **A− / A+ text-size controls** driven by a CSS custom property (`--elder-scale`), with disabled states at the limits.
- A realistic WhatsApp-style mock-up of a family-impersonation scam, with the red flags (**URGENT**, **NEW NUMBER**) labelled in place.
- Three numbered rules: call the saved number, slow down when it is urgent, never share an OTP or PIN.
- The golden rule, stated once and large: **"Your OTP is a key. Never hand it to anyone."**
- A **Quick check** practice scenario with correct/incorrect feedback and a *Try again* reset.
- Recovery guidance if an OTP was already shared: call the bank, then report on **1930**.

### 04 · Women & Girls — *"Save proof. Lock down. Report."*

- **One-tap helpline cards** (`112`, `181`, `1930`) using `tel:` links.
- **Step one — Evidence:** four-step capture guide (full screen, unedited original, factual log, record every handover) plus a plain-words explanation of **chain of custody**.
- **Step two — Account lockdown:** official Instagram and Facebook guides, location-tagging advice, and a **7-item privacy checklist** with a live progress bar and counter, persisted in `localStorage`, with a *Reset checklist* action.
- **Step three — Reporting:** NCW online complaints (helpline **14490**), the National Cyber Crime Portal, and in-app reporting links for Instagram, Facebook and WhatsApp.
- Explicit reminder: you may report to the platform, NCW **and** the cybercrime portal — you do not have to choose only one.

### Cross-cutting

- 🌐 **English ⇄ हिंदी toggle** with `<html lang>` switching, Devanagari-aware typography, and persisted preference.
- 🚨 **Panic exit** — a fixed, always-reachable button that clears this site's saved activity and replaces the current page.
- 🧭 Sticky header, horizontally scrollable section nav, skip link, and a top status strip.
- 🖨️ Print stylesheet that strips chrome and games, leaving a readable guidance sheet.

---

## ♿ Accessibility

Accessibility is treated as a functional requirement, not a polish pass.

| Concern | Implementation |
|---------|----------------|
| Keyboard use | Visible `:focus-visible` rings (3px), contrast-inverted on dark bands; logical tab order; skip link to `#main` |
| Low vision | Base `18px` body type; **Atkinson Hyperlegible**; per-module A−/A+ scaling; `prefers-contrast: more` thickens borders and darkens muted text |
| Motion sensitivity | Full `prefers-reduced-motion: reduce` override for transitions, animations and smooth scrolling |
| Touch targets | Minimum ~44–66px heights on all interactive controls; 62px Panic exit |
| Screen readers | Semantic landmarks, `[hidden]` for inactive states, decorative sprite hidden from the a11y tree |
| Non-readers | Picture-first module plus speech synthesis; icons never carry meaning alone |
| Language | `lang="hi"` typographic branch: increased line-height, zero letter-spacing on Devanagari, resized display headings |
| Anchor navigation | `scroll-padding-top` keeps headings clear of the sticky header |

> **Note for reviewers:** automated checks are necessary but not sufficient. Manual keyboard traversal, 200% zoom, and a screen-reader pass in both languages are part of the test plan.

---

## 🔒 Privacy & Safety Design

- **No accounts, no analytics, no cookies, no network calls for user data.**
  1. language preference;
  2. privacy-checklist progress.
- **Panic exit** clears this site's saved activity and replaces the current page.

> ⚠️ **Honest limitation, disclosed in the footer:** browsers do **not** allow a website to erase the entire browsing history. Panic exit is a risk-reduction feature, not a guarantee. Anyone on a monitored device should also be advised about private browsing and device-level history.

---

## 📞 Emergency Helplines (India)

| Number | Service | When to use |
|:------:|---------|-------------|
| **112** | National emergency | Immediate danger — call first |
| **1930** | Cyber-fraud helpline | Money lost to an online scam |
| **181** | Women's helpline | Support and counselling |
| **14490** | NCW helpline | Cybercrimes against women |

**Official portals**

- National Cyber Crime Reporting Portal — <https://cybercrime.gov.in/>
- NCW online complaints — <https://ncwapps.nic.in/onlinecomplaintsv2/>

---

## 🧰 Tech Stack

| Layer | Choice | Rationale |
|-------|--------|-----------|
| Markup | HTML5 | Semantic, no build step required |
| Styling | CSS3 + Bootstrap 5 (grid/utilities) | Custom design system in CSS custom properties; Bootstrap only for layout |
| Behaviour | Vanilla JavaScript (ES6+) | No framework weight; runs on low-end phones |
| Graphics | Inline SVG + SVG sprite | Scales, themes with `currentColor`, no image requests |
| Speech | Web Speech API | Read-aloud without audio assets |
| Persistence | `localStorage` | Device-only state, no backend |
| Fonts | Atkinson Hyperlegible · DM Serif Display · Noto Sans Devanagari | Legibility, editorial voice, full Devanagari coverage |

---

## 📁 Project Structure

```text
cybershield/
├── index.html          # Single-page app: all four modules, icon sprite, bilingual copy
├── styles.css          # Design tokens, components, responsive + a11y media queries
├── favicon.svg         # Shield-and-padlock mark (64×64, navy / yellow)
├── script.js           # Game logic, language toggle, text scaling, checklist, panic exit
└── README.md
```

> If your JavaScript is currently inline in `index.html`, extract it to `script.js` before submission — separation of concerns is easier to assess, and it enables a stricter Content-Security-Policy later.

---

## 🚀 Getting Started

### Prerequisites

A modern browser. No Node.js, no package manager, no build step.

### Option A — open directly

```bash
git clone https://github.com/<your-username>/cybershield.git
cd cybershield
```

Then open `index.html` in your browser.

### Option B — local server (recommended)

Some browsers restrict speech synthesis and storage on `file://` origins.

```bash
# Python 3
python -m http.server 8000
```

```bash
# or Node.js
npx serve .
```

Visit `http://localhost:8000`.

### Deploy to GitHub Pages

1. Push the repository to GitHub.
2. **Settings → Pages**.
3. **Source:** *Deploy from a branch* → `main` → `/ (root)` → **Save**.
4. Your site appears at `https://<your-username>.github.io/cybershield/`.

---

## 🎨 Customisation

### Design tokens

All colour, type and elevation decisions live in `:root` in `styles.css`.

| Token | Value | Role |
|-------|-------|------|
| `--ink` | `#16212a` | Primary text |
| `--paper` | `#fffaf1` | Page background |
| `--navy` | `#0c2238` | Header, footer, dark modules |
| `--yellow` | `#f5c94a` | Primary accent / CTA |
| `--safe` | `#0f6b4f` | Correct / safe state |
| `--danger` | `#b42318` | Scam / error / panic |
| `--blue` | `#145da0` | Links, children's module |
| `--plum` | `#7d2957` | Women's safety accents |
| `--focus` | `#005fcc` | Focus ring |
| `--shadow` | `6px 6px 0 var(--line)` | Hard offset "sticker" elevation |
| `--font-body` | Atkinson Hyperlegible → Noto Sans Devanagari | Body copy |
| `--font-display` | DM Serif Display → Noto Sans Devanagari | Headings |

### Adding a picture-safety scene

1. Add the scene object (illustration id, prompt, correct answer, feedback strings) to the scene array in `script.js`.
2. Provide **both** `en` and `hi` strings — an untranslated scene should fail your review, not your user.
3. Draw the illustration as inline SVG using `currentColor` so it inherits the theme.
4. Re-test: keyboard order, read-aloud output, and the 480px breakpoint.

### Adding a checklist item

Add the item to the privacy-checklist markup and its label to both language dictionaries; the counter and progress bar are derived, so update the total (`0 / 7`) accordingly.

---

## 🌍 Browser Support

| Browser | Support |
|---------|---------|
| Chrome / Edge (current) | ✅ Full |
| Firefox (current) | ✅ Full |
| Safari 15+ (iOS/macOS) | ✅ Full |
| Android Chrome | ✅ Full |
| Legacy / IE | ❌ Not supported |

Read-aloud depends on `speechSynthesis` and on an installed voice for the active language; the button should degrade gracefully (hidden or disabled) when unavailable.

---

## 🗺️ Roadmap

- [ ] Extract JavaScript into a documented module with unit-testable pure functions
- [ ] Expand the picture library (UPI collect-request scams, QR-code traps, fake job
