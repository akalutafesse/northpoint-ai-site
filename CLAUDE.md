# CLAUDE.md — North Point AI Website

## What this is
Static marketing site for North Point AI (northpoint-ai.com). Single-page, no build step.

## DO NOT TOUCH
- Live Google Sites at northpoint-ai.com — stays up until explicit cutover instruction
- Squarespace DNS records — do not modify until cutover approval
- Design, copy, layout, colors, or section order — approved and final (v4)

## Stack
Static HTML/CSS/JS. No framework, no build step, no dependencies.

## Structure
```
index.html              — single page, all sections, CSS inlined in <style>, JS inlined in <script>
assets/img/             — WebP logos, marks, favicons, OG image
robots.txt, sitemap.xml — SEO
.github/workflows/      — GitHub Pages deploy
```

Note: CSS and JS are inlined in index.html (not external files) to eliminate render-blocking resources.

## Deploy
- Staging: GitHub Pages (auto-deploy on push to main)
- Production: GitHub Pages with custom domain www.northpoint-ai.com (pending DNS cutover)

## Brand colors
- Navy: #0d1544 (primary)
- Navy soft: #28347c (hover)
- Ink: #10142b (text)
- Ink-2: #5c6072 (secondary text)
- Paper: #ffffff (background)
- Paper-2: #f5f6f9 (alt sections)

## Rules
1. Pixel-faithful to approved v4 prototype — no design changes without approval (mobile menu is the one approved addition)
2. All images self-hosted under assets/img/ — no external hotlinks
3. No external dependencies — no CDN, no Google Fonts, no analytics scripts (yet)
4. System font stack only — no custom font loading
5. All animations respect prefers-reduced-motion
6. Keep total transfer under 500KB
7. Lighthouse targets: >=95 all categories
8. Push after every commit
9. Images in WebP format with explicit width/height attributes

## DNS cutover records (prepared, NOT applied)
When approved, add in Squarespace DNS:
- A record: @ → 185.199.108.153
- A record: @ → 185.199.109.153
- A record: @ → 185.199.110.153
- A record: @ → 185.199.111.153
- CNAME: www → akalutafesse.github.io

## New session checklist
1. Read this file
2. Check git status and recent commits
3. Confirm staging URL loads with zero errors
4. Ask what we're working on today
