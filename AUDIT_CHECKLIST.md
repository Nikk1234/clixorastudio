# CLIXORA Studio Website Audit Checklist

Date: 2026-02-05
Scope: Static HTML/CSS/JS files in this repo
Goal: Provide a comprehensive, step-by-step upgrade checklist

Note: For an ordered execution plan (manufacturer-first repositioning + phased rollout), see `UPGRADE_PLAN.md`.

## Repositioning (Manufacturer-First)
- [x] Update site messaging to focus on manufacturers/exporters first; keep creators as a secondary path/page.
- [x] Replace "Pod" terminology with simpler language ("Growth Team" / "Marketing Team" / "Export Growth Service").
- [x] Rewrite claims to manufacturer KPIs (RFQs/inquiries/CPL/qualified lead rate) instead of creator KPIs (CTR/retention).
- [x] Remove or rewrite high-risk service claims (account sales, proxy/bypass, selling contact lists) from public pages.
- [ ] Decide if a compliance statement should appear anywhere (currently removed per request).

## Critical Blockers
- [x] Fix broken legal/trust links by creating `privacy.html`, `terms.html`, and `data-security.html`, or remove/replace the links if not needed. Files: `index.html`, `about.html`, `pricing.html`, `results.html`, `contact.html`, `careers.html`

## High Priority UX/Navigation
- [x] Make the top nav “Services” link work on all pages by changing `href="#services"` to `href="index.html#services"` (or add matching `id="services"` sections on each page). Files: `about.html`, `results.html`, `pricing.html`, `contact.html`, `careers.html`
- [x] Fix the featured pricing CTA class typo so the button gets the intended style (`primary--cta` -> `primary-cta` or a defined class). File: `pricing.html`
- [ ] Replace placeholder social links (`href="#"`) with real profiles or remove the icons. Files: `index.html`, `about.html`, `results.html`, `pricing.html`, `contact.html`, `careers.html`

## High Priority Compliance/Trust Copy
- [x] Remove or rewrite "provide FBA seller contacts / Amazon seller info" to a policy-safe offering (public/company sources, client-provided lists, opt-out handling).
- [x] Remove or rewrite "proxy / account sales / overseas number resources" language to policy-compliant troubleshooting guidance.
- [x] Remove or rewrite "add friends daily / send letters" language to a compliant outreach system (templates, deliverability, opt-out).

## High Priority Styling/Logic Bugs
- [x] Align contact form container styles with actual markup by renaming `.contact-form-container` to `.contact-form-wrapper` (or update HTML to match). Files: `contact.html`, `contact.css`
- [x] Define missing CSS variables or replace them with existing ones. Missing: `--text-light`, `--accent-yellow`. Files: `variables.css`, `layout.css`, `sections.css`, `pages.css`
- [x] Fix responsive rules that target the wrong layout type (grid vs flex). `.case-study-detail` is flex but responsive overrides use grid, and `.problem-solution-module` is grid but responsive overrides use flex. Files: `pages.css`, `responsive.css`
- [x] Update Font Awesome references to a single version and icon set. The site loads FA6; swap unsupported icons to FA6. Files: `index.html`, `pricing.html`, `results.html`
- [x] Fix AOS attributes that do nothing (either add AOS library or remove `data-aos` usage). File: `careers.html`

## Medium Priority Content/Presentation
- [x] Replace Markdown `**` in HTML with real emphasis tags (`<strong>...</strong>`). Files: `index.html`, `about.html`, `results.html`, `pricing.html`
- [ ] Replace placeholder “client logos” and “visual-placeholder” blocks with real assets or remove them. Files: `index.html`, `about.html`
- [x] Add unique page titles and meta descriptions per page (current titles are mostly unique; meta descriptions still missing). Files: all `*.html`
- [ ] Add a favicon and standard site icons. Files: all `*.html` (head), add assets
- [ ] Verify CTA URLs that use query params are handled as intended (e.g., `contact.html?audit=true`). Files: `index.html`, `results.html`, `pricing.html`, `about.html`, `contact.html`
- [x] Ensure `section-header` and `section-header-centered` wrappers are styled or removed. Files: `index.html`, `pricing.html`

## Medium Priority Accessibility
- [ ] Convert accordion headers to accessible buttons and add `aria-expanded`, `aria-controls`, and keyboard support. Files: `pricing.html`, `pricing.css`, inline script in `pricing.html`
- [x] Add `for`/`id` pairs to form labels and inputs, and include `autocomplete` attributes. File: `contact.html`
- [ ] Add `rel="noopener noreferrer"` to all `target="_blank"` links. File: `contact.html`
- [x] Add `aria-expanded` toggle behavior on the mobile menu button. Files: all `*.html` with menu toggle script
- [x] Add a reduced-motion mode to disable non-essential animations when `prefers-reduced-motion: reduce`. Files: `sections.css`, `pages.css`, `pricing.css`, `careers.css`

## Medium Priority CSS Maintainability
- [ ] Remove duplicate `@keyframes float` and duplicated `::before` blocks to avoid confusion and unintended overrides. Files: `sections.css`, `pages.css`
- [ ] Consolidate repeated `.process-grid` definitions across `sections.css` and `pages.css` and make responsive rules consistent. Files: `sections.css`, `pages.css`, `responsive.css`
- [ ] Move `--transition-smooth` and similar global design tokens to `variables.css` and remove duplicate `:root` blocks from page-specific styles. Files: `variables.css`, `pricing.css`
- [ ] Scope pricing-specific `.cta-button` overrides so they don’t affect other pages. File: `pricing.css`

## Medium Priority Visual/Responsive
- [ ] Fix mobile nav positioning relative to the header height (menu currently opens at `top: 70px` while header height is `90px`). File: `responsive.css`
- [ ] Make `.section-header` and `.section-header-centered` styles real, or remove unused wrappers. Files: `index.html`, `pricing.html`, add CSS to `sections.css` or `pages.css`
- [ ] Update `.pod-roles-grid` references in responsive rules to match `.pod-roles-flow`. Files: `responsive.css`, `pages.css`
- [x] Ensure `.footer::before` decorative element is visible by adding `position: relative` to `.footer`. File: `layout.css`

## Low Priority Polishing
- [ ] Standardize phone number formatting and include `tel:+1...` format for international compatibility. File: `contact.html`
- [ ] Replace generic email (gmail) with a branded address if desired. Files: all footers
- [ ] Add missing alt text if/when real images are introduced. Files: all `*.html`
- [ ] Add sitemap and robots.txt for basic SEO hygiene. Add files at repo root

## Recent Visual & UX Upgrades (Completed)
- [x] Added bilingual toggle (EN/中文) with per-language content switching.
- [x] Manufacturer-first copy updated across all pages.
- [x] Added scroll-reveal motion and subtle ambient glows (balanced motion).
- [x] Centered key section headings/subheads and CTAs.
- [x] Added special border accents for Services, Results, Workflow, and Pricing cards.
- [x] Replaced header logos with `assets/logo.png` and footer with clean text wordmark.
- [x] Fixed CTA readability issues in footer and pricing sections.

## Performance and SEO Enhancements
- [x] Add Open Graph and Twitter Card metadata for social sharing. Files: all `*.html`
- [ ] Add canonical URLs to prevent duplicate indexing. Files: all `*.html`
- [ ] Consider bundling/minifying CSS and deferring non-critical CSS for faster paint. Files: CSS build process
- [ ] Consider self-hosting critical fonts/icons to avoid third-party blocking or latency. Files: all `*.html`, assets

## Optional Enhancements
- [ ] Add analytics (privacy‑compliant) and cookie notice if required by target regions. Files: all `*.html`
- [ ] Add a simple “Back to top” link or sticky CTA on mobile for conversion lift. Files: `index.html`, `sections.css`, `responsive.css`
- [ ] Add structured data (Organization, FAQ) for rich results. Files: `index.html`, `pricing.html`

