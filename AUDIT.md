# QuickDry Restoration LLC - Current Website Audit

Source reviewed: `/Users/danielfavila/Downloads/index (1).html`
Briefs reviewed: `QuickDry_Codex_Brief.md`, `QuickDry_Logo_Brief.md`
Logo inspected: `/Users/danielfavila/Downloads/Quick Dry Solutions Logo Final (4).png`

Note: This is the required audit step before rebuild. No rebuild work has started.

## Critical Issues

1. Unsupported testimonials are published as if real.
   - Lines 1414-1444 include three named testimonials with star ratings and cities.
   - This directly conflicts with the honesty constraint to omit testimonials until real reviews exist.

2. Unsupported trust and performance claims create legal and credibility risk.
   - Line 7 says "insurance-approved"; line 1152 says "Insurance Approved"; neither is supported by the brief.
   - Lines 1279-1285 claim "Average Response Time" and "60 Minutes or Less"; the brief does not provide this statistic.
   - Lines 1297-1299 claim "100% Documented Jobs"; this is a stat-like claim that is not supported.
   - Lines 1371-1372 claim "Trusted by Local Plumbers"; no proof or approved partner/referral claim is provided.
   - Lines 1335-1336 and 1464 claim insured/general liability coverage; this may be true, but it is not in the supplied business facts and should not appear unless verified.

3. Contact information is wrong or unsafe to publish.
   - The phone number appears as `(760) 555-1234` with `tel:+17605551234` on lines 1082, 1121, 1138, 1452, and 1491.
   - The brief says the phone is a placeholder to be swapped by the owner, so the current visible number could mislead users.
   - Line 1492 uses `info@quickdryrestoration.net`, but the brief specifies `management@quickdryrestorationllc.biz`.

4. The site omits required brand assets and imagery.
   - There are zero `<img>` tags in the current page.
   - The actual logo is not used in the header, footer, favicon, or social image.
   - There are no WebP images, JPEG fallbacks, favicon files, Apple touch icon, or Open Graph image.

5. Missing SEO and local business fundamentals.
   - No canonical URL, Open Graph tags, Twitter Card tags, favicon links, or `LocalBusiness` schema.
   - No structured `serviceArea`, business identifiers, price range, contact point, language, or URL schema.
   - This blocks the requested SEO target and weakens local search relevance.

6. Mobile navigation disappears.
   - At line 1044 `.nav-links { display: none; }` removes all navigation and the emergency call CTA under 900px.
   - There is no replacement mobile menu or persistent call button, which is a serious conversion issue for emergency service traffic.

## Important Issues

1. Accessibility is not sufficient for a 100 Lighthouse accessibility target.
   - No `<main>` landmark or skip link.
   - Decorative canvas and SVGs are not marked `aria-hidden`.
   - Emoji icons are used throughout as visual icons and may be announced awkwardly by assistive tech.
   - Several text colors use low-opacity white, such as `rgba(255,255,255,0.35)` and `0.45`, likely failing WCAG contrast on navy.
   - No visible custom focus states for keyboard users.
   - Motion is not disabled for `prefers-reduced-motion`.

2. Animation is heavier than the site needs.
   - The fixed full-screen particle canvas starts immediately and runs forever.
   - The particle loop does pairwise distance checks each frame, which is wasteful for a marketing site.
   - SVG water lines, pulse rings, reveal transitions, and a spinning clock all animate without respecting reduced motion.
   - Fixed backdrop blur on the nav can be expensive on lower-end mobile devices.

3. Semantic HTML is weak.
   - The page uses 171 `<div>` elements and only 6 `<section>` elements.
   - Services use generic divs instead of articles/list items with real headings.
   - Trust bar, certification banner, and CTA strip are generic divs rather than semantic sections.
   - The footer has useful content, but the page lacks an overall semantic document structure.

4. The current design conflicts with the rebuild brief.
   - The page leans generic dark-blue emergency SaaS with particles, emoji icons, and glowing cards.
   - The display type is Bebas Neue, which the brief explicitly says not to use.
   - There is no editorial photography or place-grounding imagery.
   - The palette is dominated by navy/blue variations, making the site feel one-note rather than premium editorial.

5. Required content is missing or incomplete.
   - No bilingual note or "Se Habla Espanol" mention.
   - No founder-operator "Daniel" positioning.
   - No founded-2024 framing that honestly explains the newer business.
   - Service area omits Seeley, Niland, Salton City, and Yuma County expansion.
   - CA LLC entity number and Federal EIN are not present.

6. Conversion copy is too generic in several places.
   - The hero is urgent, but the phone number is isolated in a card and lost on mobile when the nav CTA disappears.
   - "Complete Water Restoration Under One Roof" feels generic and close to the kind of broad claim the brief wants to avoid.
   - The site overuses badges and mini stats rather than building trust from documented process, certification, and local presence.

7. CSS and delivery architecture are not production-grade.
   - CSS and JS are embedded in a single 46 KB HTML file, preventing browser caching of CSS/JS as separate assets.
   - There are 11 inline `style` attributes, which makes maintenance and responsive fixes harder.
   - The single breakpoint at 900px is not enough for the requested 375px, 768px, 1280px, and 1920px testing.
   - Inline mobile overrides lose to inline styles, such as the CTA strip padding.

8. Footer and business facts are inconsistent.
   - Copyright says 2025, but the current date and business context point to a 2026 rebuild.
   - Footer repeats the wrong email and fake phone number.
   - Footer does not include all required identifiers and service area details from the brief.

## Minor Issues

1. The Google Fonts URL uses raw ampersands; an HTML validator warns they should be escaped as `&amp;`.
2. Several comments use decorative Unicode box-drawing characters; `tidy` reports character warnings.
3. Smooth scrolling is globally enabled and does not respect reduced-motion preferences.
4. Anchor jumps may land under the fixed nav because sections do not define `scroll-margin-top`.
5. External link to `quickdryrestoration.net` in the footer is not clearly distinguished from internal navigation.
6. Decorative inline SVGs should include `aria-hidden="true"` and `focusable="false"`.
7. The nav logo is plain text, not the supplied logo, and it is not a homepage link.
8. The page uses many emoji symbols, which look less premium and can render inconsistently across platforms.

## Logo Asset Audit

- Format: PNG, 500 x 500, 8-bit RGBA.
- File size: 40 KB.
- Transparency: yes, alpha channel is present.
- Variants found nearby: multiple similarly named PNG exports, but no SVG, no confirmed wordmark-only file, and no confirmed icon-only file.
- Usability concern: the provided logo is a combined square icon plus wordmark. If scaled to the requested 36-44px nav height, the wordmark may become difficult to read.
- Favicon concern: the full logo will not be legible at 16px or 32px. A favicon should use a simplified crop/variant derived from the logo, without recoloring or redrawing.
- Background concern: the logo uses blue shapes, white lettering, and dark outlines/shadowing. It should work best on clean light or very controlled dark backgrounds. It should not be placed over busy photography.
- Design compatibility: the logo is more practical/restoration-service than editorial-luxury. Recommended handling is to keep the editorial site direction, but place the logo in controlled nav/footer treatments rather than making it the visual center of the design.

## Rebuild Implications

- Remove testimonials, fabricated stats, unsupported insurance/partner claims, and fake urgency numbers.
- Use the supplied logo as-is, with controlled background placement and a derived favicon crop only if needed.
- Use the real email from the brief and a clearly labeled phone placeholder in the README/site source until the real number is supplied.
- Add required generated imagery, optimized WebP/JPEG fallbacks, alt text, favicon set, Open Graph image, schema, semantic structure, and accessibility safeguards.
- Replace the all-dark particle aesthetic with the requested premium editorial direction.
