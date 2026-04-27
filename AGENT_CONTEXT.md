# 🤖 AGENT_CONTEXT.md — AI Agent Handoff Document
> **Purpose:** This file helps any AI agent (Gemini, Claude, GPT, Cursor, etc.) quickly understand the project, what design tools were used, what the plan was, and what has already been done. Read this before making ANY changes.

---

## 🏢 Project Overview

**Client:** JYJ & CO. — Chartered Accountants  
**Website Type:** Professional CA firm website (static HTML + Vite)  
**Location:** Rajkot, Gujarat, India  
**Stack:** HTML, Tailwind CSS (CDN), Vanilla JS, Vite (dev server)

### Key Pages
| File | Purpose |
|---|---|
| `index.html` | Homepage with services, hero, testimonials, footer |
| `knowledge.html` | Knowledge Center — articles, compliance hub, filters |
| `article.html` | Dynamic article reader (URL param `?id=` selects content) |
| `careers.html` | Careers / job listings page |

---

## 🛠️ AI Agent & Skills Used

**AI Agent:** Google Gemini (Antigravity) — Agentic coding assistant  
**Design Approach:** Followed web design best practices:
- **Glassmorphism** — frosted glass cards (`backdrop-filter: blur`)
- **Dark + Gold** brand palette (`navy-950` #0a2342, `gold-500` #c9932a / #f6921e)  
- **Tailwind CSS** for utility-first styling (loaded via CDN in all pages)
- **Font Awesome** for icons (loaded via CDN)
- **Google Fonts: Inter** for typography

**Image Generation:** Used AI image generation tools to create:
- `taxation_hero_premium_*.png` — Hero for taxation article
- `gst_compliance_card_*.png` — GST article card cover
- `audit_security_card_*.png` — Audit article card cover
- `business_strategy_roadmap_*.png` — Strategy article card cover

---

## 📋 What Was Planned (The Design Goal)

The overall goal was to modernize the **Knowledge Center** (`knowledge.html`) into a premium, high-impact destination:

1. **Immersive Hero Section** — Replace a basic gradient with a deep navy mesh + background image, bold "Elite Financial Intelligence" heading, and dual CTAs.
2. **Glassmorphic Article Cards** — Cards with `backdrop-filter: blur`, gold hover borders, and lift animations.
3. **Staggered Masonry Grid** — Even columns with alternating vertical offsets for dynamic layout.
4. **Interactive Category Explorer** — Sticky floating filter bar (All / Taxation / Audit / Strategy) with smooth JS filtering.
5. **Live Compliance Hub Sidebar** — A timeline of monthly GST/TDS/IT filing deadlines with color-coded status badges.
6. **Scroll Reveal Animations** — `IntersectionObserver` to fade/slide elements in as the user scrolls.

---

## ✅ What Has Been Done (Completed Work)

### Homepage (`index.html`)
- [x] 13-service grid with modal popups linking to `article.html`
- [x] "Quick Access Portals" section with Indian govt portal links
- [x] Premium 3-column footer (Brand + Portal Hub + Contact)
- [x] "Free Consultation" CTA in navigation

### Knowledge Center (`knowledge.html`)
- [x] Categorized article filter system (Vanilla JS)  
- [x] Smart Compliance Hub sidebar (standardized layout)
- [x] Consolidated set of 13+ article cards (linking to article.html)
- [x] Removed extreme code redundancy and interleaving garbage
- [x] Standardized footer modals (Privacy, Terms, Disclaimer) for site-wide consistency
- [x] Progressive scroll reveal animations (IntersectionObserver)

### Article Reader (`article.html`)
- [x] Dynamic content rendering via `?id=` URL query param
- [x] Content library includes: `taxation`, `gst`, `audit`, `advisory`, `ipo`, `compliance`
- [x] Tailwind CSS + Font Awesome integrated
- [x] Standard footer (brand + legal links)

### Careers Page (`careers.html`)
- [x] Operating hours added
- [x] "Free Consultation" CTA standardized
- [x] Footer standardized with portal links

---

### Current State:
- `knowledge.html` has been completely reconstructed to resolve significant code corruption and redundancy.
- The page now uses a clean "White Glass" premium aesthetic with functional category filtering and a sticky compliance hub.
- All footer modals have been consolidated at the end of the file, matching the structure of `index.html`.

---

## 🎨 Brand Design System

```css
/* Core Color Palette (Tailwind Config / Custom) */
Navy (Dark BG):    #0a2342  →  .bg-navy-950
Navy (Medium):     #113a69  →  .bg-navy-900
Gold (Primary):    #f6921e  →  .text-gold-500 (in Tailwind CDN)
Gold (Hover):      #c9932a  →  .text-gold-600

/* Typography */
Font Family: Inter (Google Fonts)
Hero: text-5xl → text-7xl, font-bold, tracking-tight
Body: text-gray-500, text-sm → text-base, leading-relaxed
Labels: text-[8px]-[10px], font-black, uppercase, tracking-widest
```

---

## 🔗 External Dependencies (CDN — No Install Needed)
```html
<!-- Tailwind CSS -->
<script src="https://cdn.tailwindcss.com"></script>

<!-- Font Awesome Icons -->
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css">

<!-- Google Fonts: Inter -->
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700;800;900&display=swap" rel="stylesheet">
```

---

## 🚀 Development Server

```bash
# Start local dev server (hot reload)
cd /Users/jaydevnakum/Digvijay_Nakum/JYJCO/JYJCO
npm run dev

# Runs at: http://localhost:5173
```

---

## 📁 File Structure (Relevant)

```
JYJCO/
├── index.html          ← Homepage
├── knowledge.html      ← Knowledge Center (main page to work on)
├── article.html        ← Dynamic article reader
├── careers.html        ← Careers page
├── hero_bg.jpg         ← Hero background image
├── AGENT_CONTEXT.md    ← THIS FILE (AI handoff doc)
├── package.json        ← Vite config (dev: "vite --host")
└── vite.config.js      ← (if present)
```

---

## 💡 Agent Instructions for Next Session

1. **Read this file first** before touching any code.
2. **Check `knowledge.html` line ~44** for current CSS state (hero-gradient vs hero-mesh).
3. **The Tailwind config** is extended inside `<script>` tags at the top of each HTML file — custom colors like `navy-950`, `gold-500`, `gold-600` are defined there.
4. **Article content** is a JS object in `article.html` — add new articles there, not in separate files.
5. **Footer** should be consistent across all pages — refer to `index.html` footer as the master template.
6. **Do NOT** add a separate backend or database — this is a pure static site.
