# Shiftframe developer guide

## Architecture

Shiftframe is a dependency-light Shopify Online Store 2.0 theme. The upload root contains:

```text
assets/
config/
layout/
locales/
sections/
snippets/
templates/
```

There is no storefront build step. `package.json` exists only for validation and release tooling in the source package.

## Core assets

- `assets/base.css` — commerce primitives, base layouts, forms, dialogs, product, cart, search, customer, and utility styling.
- `assets/shiftframe.css` — the original art-direction system, signature modules, preset behavior, archive treatments, and responsive overrides.
- `assets/theme.js` — custom elements and native storefront interactions.
- `assets/shiftframe-symbol.svg` — fallback SVG favicon/symbol.

## Visual tokens

`layout/theme.liquid` maps native Shopify color schemes and theme settings to CSS custom properties. Sections use `.color-<scheme id>` through `snippets/color-schemes.liquid`.

Key global tokens include:

- Typography: `--font-body`, `--font-heading`, `--body-scale`, `--heading-scale`.
- Color: `--section-bg`, `--section-fg`, `--section-accent`, `--section-border`, button and link roles.
- Layout: `--page-width`, `--page-margin`, `--section-space`, `--grid-gap`.
- Shape: content/card/button/input radii and border thickness.
- Motion: motion level, reveal style, hover zoom, and speed.

Do not hard-code preset colors into section markup. Use the section color role and CSS variables so all four presets remain coherent.

## Original brand graphics

`snippets/motif.liquid` outputs one of six inline vector systems: Orbit, Grid, Contour, Bloom, Rays, or Capsules. Pass a unique `id` when a motif uses SVG definitions, especially for repeated Grid motifs.

```liquid
{% render 'motif', motif: section.settings.motif, id: section.id %}
```

`snippets/brand-mark.liquid` provides Symbol, Seal, and Wordmark variants. The fallback wordmark and monogram are merchant settings; uploaded logos remain supported.

These SVGs are authored as theme primitives and inherit current section color variables. Avoid converting them to fixed-color image assets unless a campaign specifically requires it.

## Product-card system

`snippets/product-card.liquid` supports Poster, Catalog, Split, and Minimal treatments, product index, vendor, rating, sale/sold-out states, second image, quick add, image ratio, and fallback graphic presentation.

Pass section-specific options explicitly; global settings are the fallback. Preserve semantic product links and the native product form when extending quick add.

## Product information

`sections/main-product.liquid` is the primary product implementation. It handles:

- Product media and modal content.
- Native option values and swatches.
- Selected/first available variant, linked-product values, URL behavior, and unavailable recovery.
- Price, compare-at price, unit price, inventory, SKU, quantity rules, and volume pricing.
- Selling plans, dynamic checkout, Shop Pay terms, gift-card recipients, and app blocks.
- Pickup availability, complementary products, recommendations, and structured product content.

Do not replace Shopify product forms with custom endpoints. Any new product block must preserve form IDs, section IDs, and variant-selection behavior.

## JavaScript custom elements

`theme.js` defines or coordinates:

- `quantity-input`
- `recipient-form`
- `variant-selects`
- `cart-drawer`
- `cart-items`
- `product-form`
- `facet-filters-form`
- `predictive-search`
- `countdown-timer`
- `story-chapters`
- `bundle-builder`
- `image-reveal`

It also exposes a small `window.Shiftframe` dialog helper used by search, media, filters, and drawers.

Implementation principles:

- Progressive enhancement: native links/forms remain useful when JavaScript is unavailable wherever practical.
- No global third-party runtime.
- Reuse Shopify routes from `window.routes`.
- Reuse `window.theme.moneyFormat` and localized strings.
- Announce meaningful status changes through live regions.
- Respect `prefers-reduced-motion` and the theme motion setting.

## Bundle Studio contract

Bundle Studio submits:

```json
{
  "items": [
    { "id": 123456789, "quantity": 1 },
    { "id": 987654321, "quantity": 1 }
  ],
  "sections": ["cart-drawer"]
}
```

It adds independent cart lines; it does not create Shopify Bundles components or guarantee a fixed bundle price. Keep messaging aligned with actual discount configuration.

## Section conventions

- Sections should expose a `color_scheme` when they render a distinct surface.
- Signature sections use an indexed eyebrow/heading structure and support native motif fallbacks.
- New SVG IDs must be unique per section or block.
- Section defaults must avoid unsupported factual claims.
- All schema JSON must remain valid and editor-friendly.
- Use `image_url`, `image_tag`, dimensions, `loading`, and focal-point behavior for merchant images.
- Decorative SVG output must remain hidden from assistive technology; informative images need meaningful `alt` text.

## Alternate templates

JSON templates are intentionally opinionated compositions. When adding another template:

1. Reuse existing sections before creating near-duplicates.
2. Give the template one clear merchandising job.
3. Keep sample claims obviously instructional.
4. Test assignment on a representative Shopify resource.
5. Confirm the template does not depend on a particular demo-store handle.

## Localization

Customer-facing interface strings belong in `locales/en.default.json` and schema labels belong in `locales/en.default.schema.json` when translation keys are used. Campaign default copy may live in section presets, but permanent interface text should not be hard-coded.

When adding a locale, duplicate the complete keys and verify plural forms, date behavior, money formats, long labels, and right-to-left layouts where applicable.

## Validation and release

```bash
npm ci
npm run validate
python scripts/browser-smoke.py
npm run preview
npm run release
```

The checks cover JavaScript syntax, Shopify Theme Check, JSON parsing, section schemas, references, required templates, CSS parsing, static preview structure, browser interactions, console/page errors, responsive overflow, controls, alternative text, duplicate IDs, archive integrity, extracted-ZIP validation, file parity, manifests, and checksums.

Theme Check may attempt to refresh Shopify Liquid documentation. The included runner falls back to the version bundled with the installed package when network access is unavailable; the report still records the actual offenses returned by Theme Check.

## Safe extension points

Preferred:

- New section built on existing tokens.
- New block in Specimen Grid, Proof Wall, Story Chapters, or product information.
- App block in product information, rich text, or footer.
- New motif added to the single motif snippet and corresponding setting options.
- New preset through `settings_data.json` using existing visual tokens.

Use caution with:

- Replacing product forms, cart routes, predictive search, or filter URL handling.
- Duplicating variant logic inside a new section.
- Loading framework-sized JavaScript for a small effect.
- Hard-coded product/collection handles in distributed templates.
- CSS that assumes only one preset or one language direction.

## Versioning

Update `theme_version` in `config/settings_schema.json`, `package.json`, changelog/release notes, and docs together. Rebuild both archives and compare extracted upload contents before release.
