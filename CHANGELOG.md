# Changelog

## [1.3.0] — 2026-07-22 (v8 redesign)

### Changed
- Full site redesign to v8: dark gradient hero with animated compass mark + north-star glow
- Only two dark sections (hero + AI for Good), rest light with teal/violet/gold accents
- Partnership section rebuilt: animated "7+ years" hero, timeline, expertise chips, trust strip (U.S. Government Agencies · AT&T · Verizon · NVIDIA)
- Leadership reduced to headline + one sentence (no schools)
- Footer/contact: "Addis Ababa, Ethiopia" (no "Bole")
- Count-up + staggered-reveal scroll animations (IntersectionObserver)
- Updated logo-full-navy.webp (760×143)

### Added
- SuqHub added to portfolio (4 live product cards total)
- "Coming soon" pipeline: Yerase Tena (featured, gold), Fetan Delivery, ZedePay, X Digital Logistics
- logo-full-white.webp (760×143) for dark hero/nav
- Frosted-glass nav with dark→solid transition on scroll

### Preserved
- All meta tags, favicons, robots.txt, sitemap.xml, CNAME
- GitHub Actions deploy workflow
- HTTPS/TLS, apex canonical, www→apex redirect

## [1.2.0] — 2026-07-09 (Production launch)

### Changed
- DNS cutover: northpoint-ai.com now points to GitHub Pages (was Google Sites)
- A records: 4× GitHub Pages IPs (185.199.108–111.153), replacing Google Sites IPs
- AAAA records: 4× GitHub Pages IPv6 IPs (2606:50c0:800x::153), required for TLS cert
- CNAME: www → akalutafesse.github.io, replacing ghs.googlehosted.com
- CNAME file set to apex domain (northpoint-ai.com) — www redirects to apex
- TLS certificate issued (Let's Encrypt, expires 2026-10-07), HTTPS enforced
- Canonical URL, og:url, og:image, twitter:image, sitemap, robots.txt updated to apex domain
- Email/MX/TXT/SPF records preserved — no impact to info@northpoint-ai.com
- Google Sites custom domain mapping removed (site archived, domain claim released)

### Added
- DNS_BACKUP.md with full pre-cutover record inventory and rollback instructions

## [1.1.0-staging] — 2026-07-09

### Added
- Mobile hamburger menu (below 760px): animated hamburger → × toggle, frosted-glass dropdown, smooth-scroll + auto-close, Escape key support, click-outside and scroll-to-close, prefers-reduced-motion respected, aria-expanded toggling
- `<main>` landmark wrapping page content (nav and footer outside)
- Explicit width/height attributes on all `<img>` elements
- aria-label on Gratitude Systems partnership link to distinguish from identical URL

### Changed
- CSS inlined into `<style>` block in index.html (was external style.css) — eliminates render-blocking resource
- JS inlined into `<script>` block in index.html (was external main.js) — eliminates render-blocking resource
- All logo/mark images converted from PNG to WebP (logo-full-navy, mark-navy, mark-white, gratitude-logo)
- Oversized images resized to 2× max rendered size (logo-full-navy 552×104, mark-navy 214×192, gratitude-logo 437×104)

### Removed
- External assets/css/style.css (inlined)
- External assets/js/main.js (inlined)

## [1.0.0-staging] — 2026-07-08

### Added
- Initial production-grade site converted from approved v4 prototype
- Extracted CSS, JS, and images from single-file prototype
- Self-hosted all assets (logos, marks, Gratitude Systems logo)
- Generated favicons (ico, apple-touch-icon, 32px, 16px) from brand mark
- Open Graph and Twitter Card meta tags with generated OG image
- robots.txt and sitemap.xml
- GitHub Actions workflow for GitHub Pages deployment
- Foundation docs: CLAUDE.md, SPEC.md, USER_STORIES.md, CHANGELOG.md
- DNS cutover records prepared (not applied)
