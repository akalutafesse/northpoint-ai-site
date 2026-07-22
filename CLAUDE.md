# CLAUDE.md — North Point AI Website

## What this is
Static marketing site for North Point AI (northpoint-ai.com). Single-page, no build step.

## DO NOT TOUCH
- Design, copy, layout, colors, or section order — approved and final (v8)
- Email DNS records (MX, SPF TXT, google-site-verification TXT) in Squarespace

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
- Production: https://northpoint-ai.com (GitHub Pages, apex canonical, www redirects to apex)
- Auto-deploy on push to main
- TLS: Let's Encrypt, HTTPS enforced, cert expires 2026-10-07

## Brand colors
- Navy: #0d1544 (primary, hero bg)
- Navy soft: #28347c (hover)
- Ink: #10142b (text)
- Ink-2: #5c6072 (secondary text)
- Paper: #ffffff (background)
- Paper-2: #f5f6f9 (alt sections)
- Teal: #3ec6c6 (accent)
- Violet: #7c5cfc (accent)
- Gold: #c8960c (featured/Yerase Tena)

## Rules
1. Pixel-faithful to approved v8 prototype — no design changes without approval
2. All images self-hosted under assets/img/ — no external hotlinks
3. No external dependencies — no CDN, no Google Fonts, no analytics scripts (yet)
4. System font stack only — no custom font loading
5. All animations respect prefers-reduced-motion
6. Keep total transfer under 500KB
7. Lighthouse targets: >=95 all categories
8. Push after every commit
9. Images in WebP format with explicit width/height attributes

## DNS (live — cutover completed 2026-07-09)
- A records: @ → 185.199.108–111.153 (GitHub Pages IPv4)
- AAAA records: @ → 2606:50c0:800{0-3}::153 (GitHub Pages IPv6)
- CNAME: www → akalutafesse.github.io
- Email records (MX/SPF/TXT) unchanged — managed in Squarespace
- Rollback instructions in DNS_BACKUP.md

## New session checklist
1. Read this file
2. Check git status and recent commits
3. Confirm https://northpoint-ai.com loads with zero errors
4. Ask what we're working on today
