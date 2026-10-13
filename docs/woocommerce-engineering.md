# WooCommerce compatibility and order engineering

A store's correctness is measured through order journeys. Begin with catalogue ownership, inventory, payment confirmation and fulfilment rules. Configure tax and compliance requirements with the responsible merchant/adviser. A demo checkout cannot establish eligibility for a payment provider or the correctness of regional requirements.

## Original compatibility checklist

- [ ] Record core, PHP, theme, gateway and extension versions.
- [ ] Confirm support for HPOS and the chosen order datastore.
- [ ] Audit direct order postmeta/database access and use supported WooCommerce APIs.
- [ ] Test each extension against Checkout Blocks or classic checkout as actually used.
- [ ] Review Store API interactions separately from administrative REST integrations.
- [ ] Test simple products, variants, custom options and unavailable stock.
- [ ] Exercise coupons, discounts, shipping zones and regional address rules.
- [ ] Verify signed payment callbacks, duplicate events and rejected payments.
- [ ] Test refunds, cancellation, stock restoration and email delivery.
- [ ] Check renewals if subscriptions and the selected gateway support them.
- [ ] Inspect B2B/wholesale permissions and price visibility where applicable.
- [ ] Verify product feeds and structured data after catalogue updates.
- [ ] Document cutover, reconciliation and recovery evidence.

HPOS stores orders in dedicated tables. Access through WooCommerce CRUD and query APIs rather than assuming the posts store is authoritative. A plugin must not declare compatibility solely to remove a warning. The [HPOS recipe book](https://developer.woocommerce.com/docs/features/orders/high-performance-order-storage/recipe-book/) and [compatibility guide](https://developer.woocommerce.com/docs/extensions/best-practices-extensions/compatibility/) define review concerns.

## Fulfilment and customer communication

For COD, distinguish order placement, confirmation, dispatch and collected payment. Courier integrations require verified provider credentials and supported operations. Make repeat booking requests idempotent and define how returned parcels affect stock. A manual correction should have an audit trail.

Abandoned-cart workflows need a lawful, consent-aware communication policy and data retention boundary. Do not infer permission to contact someone merely from a partially completed checkout. Product options, stock and order synchronization need reconciliation when an external system is unavailable.

WooCommerce 11.2.1 fixed checkout regressions at the review date, reinforcing the need for address and checkout testing after updates. Read the [release notes](https://developer.woocommerce.com/2026/10/09/woocommerce-11-2-1-release-notes/) rather than assuming a minor update cannot affect business journeys.
