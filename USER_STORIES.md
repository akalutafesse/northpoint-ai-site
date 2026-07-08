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
- [x] Run Lighthouse, record scores
- [x] Prepare DNS cutover records (not applied)

## Remaining

### SEO & Analytics 🟡 Should
- [ ] Add structured data (Organization, WebSite JSON-LD)
- [ ] Add Google Analytics / Plausible analytics
- [ ] Submit sitemap to Google Search Console

### DNS Cutover 🔴 Must (blocked on approval)
- [ ] Add CNAME file to repo
- [ ] Apply DNS records in Squarespace
- [ ] Enable HTTPS enforcement in GitHub Pages
- [ ] Verify propagation
- [ ] Decommission Google Sites

### Enhancements 🟢 Nice
- [ ] Add subtle hover microinteractions
- [ ] Performance optimization (WebP images, preload critical assets)
- [ ] Add 404.html page
- [ ] Contact form integration (Formspree or similar)
