---
name: designing
description: Comprehensive UI/UX design system and frontend aesthetic standards for HaircutZonePro affiliate blogging portal. Defines color tokens, dark luxury styling, glassmorphism, typography, micro-interactions, responsive patterns, and Blogger XML compatibility.
---

# HaircutZonePro — Luxury Dark Aesthetic Design System

This skill documents and enforces the core design philosophy, visual design language, and technical implementation standards for the **HaircutZonePro** blogging & affiliate marketing platform.

---

## 🎨 1. Core Visual Identity & Color Palette

The interface is engineered around an **exclusive, dark-mode luxury barber lab** aesthetic with rich contrast, neon cyan accents, emerald signals, and deep slate navy surfaces.

### Primary Color Tokens
- **Background Root**: `#0a0f1d` (Deep midnight slate)
- **Card Surface**: `#111a2e` / `rgba(17, 26, 46, 0.85)` (High-contrast frosted slate)
- **Card Border**: `rgba(255, 255, 255, 0.08)` to `rgba(56, 189, 248, 0.25)` on hover
- **Brand Accent Cyan**: `#38bdf8` (Electric sky cyan for active links, buttons, key branding)
- **Brand Accent Indigo/Purple**: `#6366f1` / `#8b5cf6` (Secondary glow and gradient elements)
- **Signal Emerald (Success / Wins)**: `#10b981` / `#34d399` (Advantages, high ratings, verified badges)
- **Signal Rose (Alert / Watchouts)**: `#f43f5e` / `#fb7185` (Limitations, warnings, critical notes)
- **Signal Amber (Highlights / Ratings)**: `#f59e0b` / `#fbbf24` (Stars, ribbon badges, editor's choice)

### Typography Hierarchy
- **Primary Typeface**: `'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, sans-serif`
- **Headings**: Extra Bold to Black (`font-weight: 800 - 900`), tight tracking (`letter-spacing: -0.5px`)
- **Body Text**: `color: #cbd5e1`, `font-size: 15px - 17px`, `line-height: 1.7`
- **Subtitles & Metadata**: `color: #94a3b8`, `font-size: 13px - 14px`, `font-weight: 500`

---

## 💎 2. Card & Component Design Standards

### A. Product Cards (`.card`)
1. **Aspect Ratio & Image Frame**:
   - Product images must be centered within a clean, high-contrast frame with generous padding.
   - White/light background container (`#f8fafc`) with subtle inner shadow or rounded inset so product packaging is vividly readable regardless of bottle color.
   - Smooth `scale(1.04)` transition on card hover.
2. **Interactive Depth**:
   - Ambient drop shadows (`box-shadow: 0 10px 30px -10px rgba(0, 0, 0, 0.5)`).
   - Card lift on hover (`transform: translateY(-5px)`).
   - Border illumination from muted slate to cyan/indigo on hover.
3. **Category & Rating Badges**:
   - Compact uppercase pill badges with soft alpha backgrounds (`background: rgba(56, 189, 248, 0.12); color: #38bdf8`).
   - Clean star rating pill with amber glow.
4. **Call to Action Buttons (`.cta-btn`)**:
   - Vibrant gradient background (`linear-gradient(135deg, #2563eb, #1d4ed8)`).
   - Hover state: `linear-gradient(135deg, #3b82f6, #2563eb)` with glowing drop shadow (`box-shadow: 0 8px 24px rgba(37, 99, 235, 0.4)`).
   - Clear arrow icon (`→`) and affirmative action copy (*"Check Price on Amazon →"*).

### B. Pros & Cons / Comparison Modules (`.pros-cons`)
1. **No Pseudo-Element Text**:
   - NEVER rely on `content: '✓'` or `content: '✗'` in CSS pseudo-elements because Blogger's template compiler encodes them as raw `&#10003;` strings that overlap adjacent text.
   - Always use **inline vector SVGs** wrapped in styled circular flex badges (`.bullet-icon`).
2. **Micro-Card Structure**:
   - Each pro/con point must be an individual card-like row with a subtle background (`rgba(255, 255, 255, 0.02)`) and hover highlight (`translateX(4px)`).
   - Always start each bullet with a bold lead-in keyword (`<strong>Key Concept:</strong> ...`) for instant scannability.
3. **Header Pill Row**:
   - Include card icon pill, uppercase title, descriptive subtitle, and counter badge (`4 Wins`, `3 Watchouts`).

---

## ⚡ 3. Micro-Animations & Dynamic Feedback
1. **Reading Progress Bar**:
   - Fixed at `top: 0`, gradient fill (`#38bdf8` to `#c084fc`), glowing drop-shadow.
2. **Category Filter Tabs**:
   - Pills with count badges (`All Products (100)`, `Hair Styling (48)`).
   - Active state with glowing gradient and crisp white text.
3. **Floating Back-to-Top Button**:
   - Smooth appearance when scrolled past 400px with blur backdrop and pulsing subtle hover.
4. **Interactive Modal Reader**:
   - Backdrop blur (`backdrop-filter: blur(12px)`).
   - Elastic zoom entry (`scale(0.95)` to `scale(1)`).
   - Fixed header close button with clear accessibility tags.

---

## 🛡️ 4. Blogger XML & Cross-Platform Integrity
1. **CDATA Escaping**:
   - All script blocks must be wrapped in `//<![CDATA[ ... //]]>`.
   - All style blocks must be wrapped in `<b:skin><![CDATA[ ... ]]></b:skin>`.
2. **Image CDN Referencing**:
   - Always use full, high-speed jsDelivr CDN URLs:
     `https://cdn.jsdelivr.net/gh/Bimal-Web/Affilate-marketing-----blogging-site@main/images/[1-100].jpg`
   - Maintain dynamic JavaScript fallback engine (`resolveImageUrls`) to catch any dynamically injected posts or search results.
3. **Responsive Grid Breakpoints**:
   - Mobile: `< 640px` (single column cards, full-width CTAs, drawer menu).
   - Tablet: `640px - 1024px` (2 columns).
   - Desktop: `> 1024px` (3 to 4 columns, sticky header, multi-column comparison matrix).
