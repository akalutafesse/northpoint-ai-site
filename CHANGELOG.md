# Changelog

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
