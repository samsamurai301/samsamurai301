# Shiftframe merchant guide

## Recommended setup order

### 1. Duplicate and keep unpublished

Upload the theme ZIP, duplicate it for working changes, and keep the release candidate unpublished until the acceptance matrix at the end of this guide is complete.

### 2. Choose the visual system first

Open **Customize → Theme settings** and select Shiftframe, Chromalab, Pantryprint, or Quietform. Then configure:

- Fallback wordmark, monogram, wordmark treatment, logo, inverse logo, and favicon.
- Six native color schemes and the default, header, drawer, sale, and sold-out roles.
- Visual mode, motif family, density, opacity, animation, shape language, dividers, media treatment, and surface depth.
- Display/body fonts, typography character, scales, tracking, and label behavior.
- Page width, margins, section spacing, grid gap, border thickness, and corner language.
- Motion level, reveal style, hover zoom, and speed.
- Global product-card layout and information density.

Make these global decisions before tuning individual sections. Shiftframe is designed as a coherent system; arbitrary per-section styling should be the exception.

### 3. Connect store foundations

Configure these Shopify resources before editing long pages:

- Main menu and footer menu.
- Products, variants, media, prices, inventory, vendors, SKUs, tags, and descriptions.
- Collections and collection images.
- Search & Discovery filters, complementary products, and related products.
- Policies, markets, currencies, languages, pickup locations, shipping, taxes, and customer accounts.
- Blog, pages, contact destination, social profiles, and newsletter behavior.

### 4. Replace sample claims

Default template copy is intentionally directional. Replace sample metrics, review scores, press labels, guarantees, edition quantities, delivery times, and environmental claims with verifiable information—or remove the corresponding blocks.

## Homepage strategy

The default homepage follows a deliberate conversion sequence:

1. **Graphic Hero** — establish the campaign and strongest action.
2. **Product Atlas** — make the current edit immediately shoppable.
3. **Marquee** — reinforce a short verbal code.
4. **Brand Canvas** — show identity or campaign world.
5. **Story Chapters** — explain origin, process, or use.
6. **Drop Room** — concentrate launch urgency and product action.
7. **Specimen Grid** — make evidence and features visual.
8. **Bundle Studio** — increase product discovery and set-building.
9. **Image Reveal** — demonstrate a visible difference.
10. **Proof Wall** — close with sourced credibility.

Remove modules that do not support the current campaign. A shorter specific page is stronger than a long generic one.

## Alternate templates

### Product launch

Assign `product.launch` to a launch, collaboration, limited edition, preorder, or hero product. It places launch framing and deeper storytelling around the native product information. Set a real countdown deadline and verify the expired state.

### Editorial collection

Assign `collection.editorial` to a collection that needs an introduction, material story, campaign narrative, or proof layer before the full catalog archive.

### Campaign page

Create a page, assign `page.campaign`, and use it for seasonal edits, collaborations, founder launches, events, guides, or a shoppable content feature.

### Brand book

Create a page, assign `page.brand-book`, and use it for About, Studio, Process, Materials, Ingredients, Sourcing, Standards, Impact, Care, or Service.

Template assignment is managed from the page, product, or collection record in Shopify admin.

## Product data checklist

For every hero product, review:

- Product title, vendor, description, SEO title, and meta description.
- Alternative text and focal points for every image.
- Hosted/external videos and 3D models where relevant.
- Variant names and values that are understandable without images.
- Native swatches or option-value imagery.
- SKU, inventory, unit price, compare-at price, quantity rules, volume pricing, and selling plans.
- Pickup availability and gift-card recipient behavior where applicable.
- Complementary products and recommendations through Shopify Search & Discovery.
- Size/specification page, care information, and collapsible content.
- App blocks for reviews, subscriptions, personalization, or other merchant apps.

The main product section can display breadcrumbs, an index label, product badges, vendor, title, text, price, rating, SKU, inventory, variant picker, quantity selector, buy buttons, gift recipient fields, feature list, icon callouts, description, accordions, specification chart, pickup, share, Custom Liquid, and app blocks.

## Bundle Studio

Each Bundle Studio block points to a product. The theme uses the selected or first available variant and submits chosen items as separate cart lines in one native AJAX request.

Important behavior:

- Unavailable products cannot be selected.
- The displayed total is the sum of selected variant prices.
- Shopify automatic discounts are not simulated by the theme; they appear according to store configuration in cart or checkout.
- For variant-specific kits, create dedicated products/variants or use a compatible bundling app and app block.
- Do not describe the module as a fixed-price Shopify bundle unless the underlying product/discount setup actually provides that behavior.

## Collection and search archives

Collection archives support editorial split, poster overlap, or compact headers; collection image or native motif; filtering, sorting, pagination, several column counts, regular/modular/poster rhythms, and four card styles.

Search archives support product, article, and page results, suggested routes, native motif, no-result guidance, filters, sorting, pagination, editorial result cards, and multiple catalog rhythms.

Configure filters in **Shopify Search & Discovery**. Keep filter labels short and product data consistent so the archive remains useful.

## Header, footer, cart, and search

- The header supports frame or centered layouts, sticky behavior, promotional mega-menu blocks, mobile navigation, account, localization, search, and cart.
- The footer supports manifesto or structured layouts, motif/mark controls, newsletter, social links, menus, text, app blocks, policies, payment icons, and localization.
- Cart drawer, empty cart, full cart, and search dialog use the same configurable indexed graphic system as campaign pages.
- The theme never replaces Shopify checkout. Checkout branding and capabilities depend on the merchant’s Shopify plan and checkout configuration.

## Image guidance

Shiftframe can remain distinctive without constant photography, but real product imagery still matters.

- Hero: 2400px or wider, with a mobile crop or mobile image.
- Product cards: consistent framing within a collection, even when the grid is asymmetric.
- Story Chapters: one visual idea per chapter.
- Image Reveal: two images with matching dimensions and camera position.
- Brand Canvas and motif fallbacks: use when photography is unavailable or when a graphic campaign is intentional.
- Avoid text baked into images; use editable theme text for accessibility and responsiveness.

## Performance guidance

- Prefer Shopify-hosted video and avoid multiple autoplay videos on one page.
- Compress oversized source images before upload; Shopify will generate responsive derivatives, but source weight still affects processing and media management.
- Remove unused app embeds and duplicate analytics.
- Use the provided native modules before adding a page-builder app.
- Measure performance on the deployed store with representative products, apps, fonts, consent tools, and analytics.

## Launch acceptance matrix

### Commerce

- [ ] Standard, sale, sold-out, unavailable, and single-variant products.
- [ ] Native swatches, linked-product values, variant media, and URL changes.
- [ ] Unit pricing, subscriptions/selling plans, quantity rules, and volume pricing where used.
- [ ] Gift-card recipient, pickup, Shop Pay terms, dynamic checkout, recommendations, and complementary products.
- [ ] Quick add, Bundle Studio, cart drawer, full cart, discounts, notes, accelerated checkout buttons, and checkout handoff.

### Discovery

- [ ] Main and mobile navigation, nested menus, promotional mega menu, footer links.
- [ ] Predictive search, full search, filters, sort, pagination, no-results, and browser Back/Forward behavior.
- [ ] Collection default and editorial templates.

### Content

- [ ] Homepage, campaign, brand-book, product launch, page, contact, blog, article, collections index, 404, and password pages.
- [ ] All sample claims and placeholders replaced or removed.
- [ ] Every meaningful image has useful alternative text.
- [ ] Heading order remains logical after rearranging sections.

### International and account

- [ ] Country/language selectors, market currencies, translated content, and RTL review where relevant.
- [ ] Login, registration, activation, reset, account, order, and address flows.
- [ ] Policies, tax/shipping wording, consent tools, and customer privacy behavior.

### Devices and quality

- [ ] Current Safari, Chrome, Firefox, and Edge on desktop.
- [ ] Current iOS Safari and Android Chrome on real devices.
- [ ] Keyboard-only use, visible focus, 200% zoom, reduced motion, and a screen-reader pass.
- [ ] Live Lighthouse checks on representative home, product, and collection pages.
- [ ] App blocks, app embeds, pixels, analytics, and consent configuration.

Publish only after the deployed store—not only the source package—passes this matrix.
