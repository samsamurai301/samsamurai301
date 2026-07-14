# Troubleshooting

## A section is missing from “Add section”

Confirm that you are editing a JSON template that supports sections. Some sections are intentionally limited to compatible templates. Customer-account and issued gift-card routes have different Shopify constraints.

## A product cannot be added to cart

1. Confirm an available variant exists.
2. Confirm the selected option combination is available.
3. Remove custom code and temporarily disable recently added app embeds.
4. Test in a clean unpublished duplicate of the current Shiftframe release.
5. Check whether quantity rules, selling plans, markets, or inventory policies restrict the purchase.

## Product price or media does not change with a variant

Check that option values map to real Shopify variants and that variant images are assigned in the product record. Test without third-party product-option or subscription scripts to identify conflicts.

## Filters do not appear

Create and enable filters in Shopify Search & Discovery, then confirm the collection has enough relevant product data for those filters. Empty filters are not displayed.

## Predictive search has no results

Verify storefront search is enabled, products are published to the Online Store sales channel, and the search term matches searchable catalog content. App or custom search scripts can also override native behavior.

## The cart drawer does not open

Check the global cart behavior setting, browser console errors, and recently added app scripts. Confirm the cart icon has not been replaced by custom markup.

## Layout shifts or overflows on mobile

Review long unbroken text, oversized embedded content, app blocks, tables, custom Liquid, and images with hard-coded dimensions. Test at 320px, 375px, 390px, and landscape widths.

## Colors fail contrast checks

Adjust the complete color scheme rather than only one control. Test body text, muted text, links, buttons, focus rings, borders, badges, sale states, and disabled controls.

## A countdown shows the wrong time

Use an explicit date/time and timezone that represents the campaign deadline. Test both active and expired states. Do not use a countdown unless the deadline is real.

## Theme editor preview differs from the live store

Confirm you are viewing the same theme, market, language, template assignment, product, and device width. Clear storefront cache, review app embeds, and verify that the edited theme has been saved.

## Before opening a support request

Reproduce the issue in an unpublished duplicate of an unmodified current release. Record the exact URL, template, device, browser, steps, expected result, actual result, and recent changes. Then use the [Shiftframe support form](https://github.com/samsamurai301/samsamurai301/issues/new?template=shiftframe-support.yml).
