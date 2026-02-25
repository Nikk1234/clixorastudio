# CLIXORA Website Upgrade Plan (Manufacturer-First)

Date: 2026-02-05  
Repo: `d:\Nik\Clixora Studio`  
Purpose: A step-by-step execution plan to upgrade the site efficiently, with clear priorities and checklists.

## Phase 0: Lock The Direction (Do This First)
- [x] Confirm primary audience: Chinese manufacturers / exporters / trading companies (B2B lead generation).
- [x] Confirm secondary audience: creators (kept as supplementary page/section).
- [x] Replace "Pod" language site-wide with simpler terms.
- [x] Decide the new primary term: "Growth Team" vs "Marketing Team" vs "Export Growth Service".
- [x] Confirm primary conversion goal: RFQs/inquiries vs distributor leads vs ecommerce (Amazon/Shopify).
- [x] Confirm languages: English only vs English + Chinese (Simplified).
- [x] Confirm primary contact channel: Email vs WhatsApp vs WeChat (and what to show in the header/footer).
- [x] Confirm whether you want to keep the brand name `CLIXORA STUDIO` or adjust it for manufacturing (optional).

## Phase 1: Fix Critical Trust + Broken UX
Goal: no broken links, no broken nav, no obvious styling regressions.

- [x] Create or remove legal pages referenced in every footer.
- [ ] Create `privacy.html`.
- [ ] Create `terms.html`.
- [ ] Create `data-security.html`.
- [x] Fix top nav "Services" links on non-home pages (currently `href="#services"` points nowhere).
- [x] Fix featured pricing CTA class typo (`primary--cta`).
- [x] Fix contact page styling mismatch between HTML and CSS (`.contact-form-wrapper` vs `.contact-form-container`).
- [x] Define missing CSS variables and remove references to undefined tokens.
- [x] Fix Font Awesome version mismatch in CSS (FA5 vs FA6 font-family) and normalize icon usage.

Files typically involved: `index.html`, `about.html`, `pricing.html`, `results.html`, `contact.html`, `careers.html`, `variables.css`, `layout.css`, `pages.css`, `sections.css`, `responsive.css`, `contact.css`.

## Phase 2: Reposition The Site (Manufacturer-First)
Goal: the site reads like a premium B2B growth agency for manufacturers, with creators as a secondary path.

- [x] Update the global header nav labels and destinations.
- [x] Add a new nav item for manufacturers (if you split pages) or make Home manufacturer-first.
- [x] Move creators into a clearly secondary route (nav last item: `For Creators`).
- [x] Rewrite hero copy on `index.html` to target manufacturers and overseas buyers.
- [x] Rename CTAs:
- [x] "Free Strategy Audit" -> "Free Growth Audit" or "Free Export Marketing Audit".
- [x] Replace "Channel growth" language with "inquiries/RFQs/leads".
- [x] Replace all Markdown `**bold**` occurrences with real HTML emphasis (`<strong>`).
- [x] Replace sections that only make sense for creators (CTR/thumbnails/retention) with manufacturer equivalents (RFQs, CPL, landing pages, qualification).
- [x] Add a short "Who we work with" block: OEM/ODM, trading companies, exporters, target regions.
- [ ] Add a short "Compliance & Data" block (see Phase 3) to build trust (currently removed per request).

Recommended page structure (simple and clear):
- [ ] Keep `index.html` as the manufacturer-first homepage.
- [ ] Add a new page `creators.html` for creator services (or keep existing sections but moved + reduced).
- [ ] Add `services.html` if you want a clean services overview (optional but recommended for clarity).

## Phase 3: Clean, Safe Service Catalog (Avoid Risky Claims)
Goal: keep your full capability list, but present it in grouped, understandable categories and policy-safe wording.

### 3A: Rewrite the service list into categories
- [ ] Website: WordPress/Shopify builds for B2B inquiries (RFQ/quote forms, landing pages).
- [ ] SEO: technical SEO + on-page + multilingual pages + Google exposure.
- [ ] Ads: Google Ads setup/management/training; Meta Ads setup/management/training.
- [ ] Social operations: LinkedIn/TikTok/Reddit presence, content production + posting cadence.
- [ ] Prospect research: targeted B2B prospect lists using public/company sources.
- [ ] Trade ops guidance: workflows, CRM basics, lead qualification, landing pages, tracking.
- [ ] Technical troubleshooting: verification issues, account stability troubleshooting (policy-compliant).

### 3B: Remove or reword high-risk items
- [x] Remove "sell Amazon/FBA seller contacts" language.
- [x] Remove "proxy/account sales/overseas number resources" language.
- [x] Remove "add friends daily/send letters" language (rewrite as compliant outreach systems and templates).
- [ ] Add a simple policy statement:
- [ ] "We do not sell private personal data."
- [ ] "We use public/company data sources and client-provided lists."
- [ ] "We follow opt-out and anti-spam best practices."

## Phase 4: Lead Capture That Matches Manufacturers
Goal: forms and CTAs collect the info needed to qualify a factory/exporter fast.

- [x] Update `contact.html` form fields:
- [x] Add lead type selector: Manufacturer/Exporter vs Creator.
- [x] Add manufacturer fields: company name, product category, target countries, website, monthly ad budget range, preferred contact channel.
- [x] Add `for`/`id` label associations for accessibility.
- [x] Add `autocomplete` attributes.
- [ ] Add `rel="noopener noreferrer"` to `target="_blank"` links.
- [x] Ensure WhatsApp link is correct and consistent across the site.
- [x] Update the header/footer contact info to match the new focus (B2B buyers trust professionalism).

Optional but recommended:
- [ ] Add a "Book a call" CTA (Calendly or similar) alongside the form.
- [ ] Add a "Download capability deck" lead magnet CTA (PDF).

## Phase 5: Credibility Upgrades (Manufacturing-Style Proof)
Goal: reduce skepticism and increase conversion with proof that matches B2B manufacturing expectations.

- [ ] Replace placeholders:
- [ ] Replace "client logos placeholder" with real logos (or remove entirely until real).
- [ ] Replace hero visuals/placeholder blocks with premium visuals that fit B2B export (factory, logistics, trade, analytics).
- [ ] Rewrite "Results" content to emphasize:
- [ ] inquiries/RFQs per month
- [ ] cost per lead (CPL)
- [ ] qualified lead rate
- [ ] quote-to-order rate (if available)
- [ ] Add 2-3 manufacturing case studies (even anonymized).
- [ ] Add a simple "Industries served" strip (icons + text).
- [ ] Add testimonials (even short quotes) with role/company if possible.

## Phase 6: Accessibility, SEO, Performance, Maintainability
Goal: polish and professional-grade baseline.

Accessibility:
- [ ] Make FAQ accordion accessible (buttons + `aria-expanded` + keyboard support).
- [x] Add reduced-motion support (`prefers-reduced-motion: reduce`) to disable heavy animations.
- [x] Add `aria-expanded` management to the mobile menu toggle.

SEO:
- [ ] Make page titles unique (each page currently uses the same title).
- [x] Add per-page `meta name="description"`.
- [x] Add Open Graph and Twitter Card meta tags.
- [ ] Add canonical URLs (if you have a real domain).
- [ ] Add `sitemap.xml` and `robots.txt`.

Performance:
- [ ] Reduce CSS bleed by loading page-specific styles only where needed, or scoping selectors.
- [ ] Consider self-hosting fonts/icons if reliability matters.
- [ ] Remove duplicate CSS blocks and consolidate repeated components.

Responsive:
- [x] Fix responsive layout mismatches (grid vs flex) in `responsive.css`.

Maintainability:
- [ ] Remove duplicated keyframes and duplicated selector blocks.
- [ ] Consolidate repeated header/footer scripts (optional: move to `main.js`).

## Next Recommended Upgrades (Priority Order)
1. Create legal pages (`privacy.html`, `terms.html`, `data-security.html`) or remove legal links.
2. Replace placeholder social links with real profiles (or remove icons).
3. Add meta descriptions, Open Graph, and Twitter Card tags per page.
4. Add favicon + standard icons.
5. Fix responsive layout mismatches in `responsive.css` (grid vs flex).
6. Add a reduced-motion mode for all non-essential animations.
7. Replace remaining placeholders (client logos, hero visuals) with real assets.

## QA Checklist (Run After Each Phase)
- [ ] Open each page on desktop and mobile widths: `index.html`, `about.html`, `pricing.html`, `results.html`, `contact.html`, `careers.html`.
- [ ] Verify mobile menu opens/closes and all links navigate correctly.
- [ ] Verify contact form is styled correctly and submits to Formspree.
- [ ] Verify icons render correctly (Font Awesome).
- [ ] Verify there are no literal `**` characters visible in page text.
- [ ] Verify footer legal links work.
- [ ] Verify no page has obvious broken layout (overlaps, clipping, missing spacing).
