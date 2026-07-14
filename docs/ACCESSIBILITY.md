# Shiftframe accessibility guide

## Theme implementation

Shiftframe includes:

- Semantic landmarks, headings, lists, tables, forms, buttons, links, and native dialogs.
- Skip-to-content and visible `:focus-visible` treatment.
- Keyboard-accessible navigation, mobile menu, search, filters, FAQ rows, media, variants, quantities, cart, account forms, story chapters, bundle selection, and image reveal.
- Focus management and focus return for drawers and dialogs.
- Live-region announcements for predictive search, cart actions, bundle actions, product-form errors, and quantity/cart updates.
- Labels, instructions, error association, status regions, unavailable-option text, and screen-reader price context.
- Decorative treatment for original motif SVGs and fallback brand graphics.
- Native range control plus output/ARIA value text for Image Reveal.
- Current-step state and hidden visual-state management for Story Chapters.
- Disabled state for unavailable Bundle Studio items.
- Reduced-motion behavior for motif motion, marquees, reveals, smooth transitions, and animated campaign elements.
- Responsive layouts designed to avoid required horizontal page scrolling.
- Alternative-text output through Shopify image objects and empty alternatives for decorative images.

## Content responsibilities

The merchant controls much of the final accessibility result. Before launch:

- Write alternative text that explains the purpose of informative images. Do not repeat nearby captions verbatim.
- Leave decorative campaign images empty only when they communicate no information.
- Keep one logical page heading and a sensible heading hierarchy after moving sections.
- Test every customized color scheme for text, control, focus, link, border, and badge contrast.
- Use specific link/button labels rather than repeated “Learn more” or “Click here.”
- Caption or transcribe meaningful audio/video.
- Do not rely on animation, color, position, or image text as the only way to communicate information.
- Keep product options, filters, dimensions, care, ingredients, and form instructions explicit.
- Verify tables remain understandable on small screens and at zoom.
- Remove unsupported claims; accessibility includes accurate, understandable content.

## Signature-module checks

### Graphic Hero and Brand Canvas

Ensure product pins have understandable product destinations, text remains readable over uploaded media, and visual notes are not the only location of essential information.

### Story Chapters

Each chapter should have a unique descriptive heading. Test keyboard selection and confirm the visual is supplementary to the written chapter.

### Bundle Studio

Product titles and availability must be clear. Test selection, total updates, error messages, successful add, and cart review with keyboard and screen reader.

### Image Reveal

Use images that still make sense with the before/after labels. The slider should not be the only source of the comparison conclusion; explain the outcome in nearby text.

### Proof Wall

Provide named sources and context for quotes, ratings, press, metrics, certifications, and commitments. Logos require alternative text when they convey the source.

## Required live-store testing

Source validation is not a substitute for testing merchant content and installed apps. On the deployed store test:

1. Keyboard-only navigation from announcement bar through footer.
2. Search, filters, variants, add-to-cart, drawer, full cart, customer, and contact forms.
3. Story Chapters, Bundle Studio, Image Reveal, FAQ, media modal, and mobile menu.
4. 200% and 400% browser zoom where applicable.
5. Reduced-motion preference.
6. Current screen readers on at least one desktop and one mobile platform.
7. Automated accessibility analysis on representative home, product, collection, search, cart, and content pages.
8. Third-party app blocks, app embeds, reviews, consent tools, chat, analytics controls, and personalization.

Document issues, affected templates, reproduction steps, and fixes before release.
