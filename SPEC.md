# SPEC.md — North Point AI Website

## 1. Overview
Single-page static marketing site for North Point AI. Presents the company's mission, capabilities, portfolio, partnership, leadership, Ethiopia use cases, AI for Good vision, and contact information.

## 2. Design System

### 2.1 Colors (CSS custom properties)
| Variable      | Value     | Usage                    |
|---------------|-----------|--------------------------|
| --ink         | #10142b   | Primary text             |
| --ink-2       | #5c6072   | Secondary text           |
| --paper       | #ffffff   | Background               |
| --paper-2     | #f5f6f9   | Alt section background   |
| --navy        | #0d1544   | Brand primary, headings   |
| --navy-soft   | #28347c   | Hover states             |
| --night-ink   | #f5f6f9   | Dark section text        |
| --night-ink-2 | #9aa2c4   | Dark section secondary   |
| --radius      | 24px      | Card border radius       |
| --ease        | cubic-bezier(.22,.61,.36,1) | Animation easing |

### 2.2 Typography
- Font: System font stack (-apple-system, BlinkMacSystemFont, SF Pro Display, Segoe UI, Roboto, Helvetica, Arial)
- h1: clamp(40px, 7vw, 78px), weight 700, tracking -0.035em
- h2: clamp(32px, 5vw, 56px), weight 700, tracking -0.03em
- h3: 21px, weight 600, tracking -0.015em
- .lede: clamp(18px, 2.2vw, 23px), line-height 1.45
- .eyebrow: 13px, weight 600, uppercase, tracking 0.08em
- Body: line-height 1.5

### 2.3 Components
- `.btn` — pill buttons (border-radius: 980px), 14px/30px padding
- `.btn-primary` — navy bg, white text
- `.btn-ghost` — navy text, underline on hover
- `.card` — 24px radius, 1px border, subtle shadow, lift on hover
- `.stat` — 18px radius stat card with large bold number
- `.pipe` — dashed border card for pipeline items

## 3. Page Structure (section order)

1. **Nav** — fixed, blur backdrop, logo + links + CTA
2. **Hero** (#top) — compass mark, h1, lede, two CTAs, meridian SVG background
3. **Why we exist** (#gap) — eyebrow, h2, 3 gap-points + sovereign layers SVG
4. **What we build** (#build) — 3 pillar cards (AI, Cloud, Public platforms)
5. **Portfolio** (#work) — 3 delivered product cards + 2 pipeline cards
6. **Partnership** (#partnership) — Gratitude Systems collab, 4 stat cards
7. **Leadership** (#leadership) — lede + 3 capability cards
8. **Ethiopia** (#ethiopia) — 6 use case cards
9. **AI for Good** (#good) — dark navy section, quote, 4 items
10. **Contact** (#contact) — CTA, email, phone, address
11. **Footer** — logo, copyright, nav links

## 4. Asset Inventory
| File                        | Type | Size   | Usage                        |
|-----------------------------|------|--------|------------------------------|
| logo-full-navy.png          | PNG  | 26KB   | Nav, partner, footer         |
| mark-navy.png               | PNG  | 22KB   | Hero compass mark            |
| mark-white.png              | PNG  | 35KB   | Night section bg mark        |
| gratitude-logo.png          | PNG  | 13KB   | Partnership section          |
| og-image.png                | PNG  | 22KB   | Open Graph / Twitter card    |
| favicon.ico                 | ICO  | <1KB   | Browser tab                  |
| apple-touch-icon.png        | PNG  | 12KB   | iOS home screen              |
| favicon-32x32.png           | PNG  | 1KB    | Standard favicon             |
| favicon-16x16.png           | PNG  | <1KB   | Small favicon                |

## 5. Deployment Architecture

### 5.1 Staging (current)
- Platform: GitHub Pages
- Trigger: auto-deploy on push to main via GitHub Actions
- URL: https://akalutafesse.github.io/northpoint-ai-site/

### 5.2 Production (pending cutover)
- Platform: GitHub Pages with custom domain
- Domain: www.northpoint-ai.com + northpoint-ai.com (apex)
- CNAME file added to repo root

### 5.3 DNS Cutover Plan
1. Add CNAME file with `www.northpoint-ai.com` to repo
2. In Squarespace DNS, add:
   - A @ 185.199.108.153
   - A @ 185.199.109.153
   - A @ 185.199.110.153
   - A @ 185.199.111.153
   - CNAME www → akalutafesse.github.io
   - TTL: 3600 (1 hour)
3. Enable "Enforce HTTPS" in GitHub Pages settings
4. Verify propagation (dig, curl)
5. Remove/redirect old Google Sites

## 6. Performance Targets
- Lighthouse Performance: >= 95
- Lighthouse Accessibility: >= 95
- Lighthouse Best Practices: >= 95
- Lighthouse SEO: >= 95
- Total transfer: < 500KB
- First Contentful Paint: < 1.5s
- Largest Contentful Paint: < 2.5s
