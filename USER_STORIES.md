# USER_STORIES.md — North Point AI Website

## Completed

### Design (v1–v4)
- [x] Initial design concepts and iterations
- [x] v4 prototype approved — single-file HTML with all sections finalized
- [x] Copy, layout, colors, and section order signed off

### Session 1 — Foundation & Staging Deploy
- [x] Create GitHub repo (northpoint-ai-site, private)
- [x] Convert prototype: CSS/JS extracted, base64 images to files
- [x] Self-host Gratitude Systems logo
- [x] Generate favicons from brand mark
- [x] Add meta tags (OG, Twitter Card, theme-color, canonical)
- [x] Add robots.txt and sitemap.xml
- [x] Create foundation docs (CLAUDE.md, SPEC.md, USER_STORIES.md, CHANGELOG.md)
- [x] Deploy to GitHub Pages staging
- [x] Verify: zero 404s, zero console errors, HTTPS
- [x] Run Lighthouse, record scores (100/98/96/100)
- [x] Prepare DNS cutover records (not applied)

### Session 2 — Mobile Menu & Lighthouse Audit Fixes
- [x] Mobile hamburger menu (Apple-style, frosted glass, accessible)
- [x] Inline CSS into <style> block (eliminate render-blocking)
- [x] Inline JS into <script> block (eliminate render-blocking)
- [x] Convert images to WebP format
- [x] Resize oversized images to 2× max rendered size
- [x] Add explicit width/height attributes to all <img>
- [x] Wrap page content in <main> landmark
- [x] Add distinguishing aria-label to Gratitude Systems link
- [x] Verify mobile menu at 375px — all behaviors working
- [x] Verify desktop rendering unchanged at 1440px

## Remaining

### SEO & Analytics 🟡 Should
- [ ] Add structured data (Organization, WebSite JSON-LD)
- [ ] Add Google Analytics / Plausible analytics
- [ ] Submit sitemap to Google Search Console

### Session 3 — DNS Cutover (2026-07-09)
- [x] Add CNAME file to repo
- [x] Backup all DNS records (DNS_BACKUP.md)
- [x] Apply DNS records in Squarespace (user-approved)
- [x] Verify DNS propagation (A records + CNAME resolving)
- [x] Verify HTTP site loads, apex redirects to www
- [x] Verify email records (MX/SPF/TXT) untouched
- [x] Add AAAA records for apex (required for cert provisioning)
- [x] TLS certificate issued (Let's Encrypt, expires 2026-10-07)
- [x] Enable HTTPS enforcement in GitHub Pages
- [x] Verify HTTPS on apex and www, all images 200
- [ ] Decommission Google Sites (Session 4)

### Enhancements 🟢 Nice
- [ ] Add 404.html page
- [ ] Contact form integration (Formspree or similar)
