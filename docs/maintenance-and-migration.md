# Maintenance and migration runbook

Inventory the current environment: core/PHP versions, theme, extensions, custom code, licence ownership, scheduled jobs, APIs, storage and public URLs. Include dependencies that an owner cannot immediately replace, such as a courier account or licensed checkout extension. A migration estimate needs those constraints.

## Rehearse on staging

Create an isolated staging environment with appropriately protected data. Confirm backups can be restored and that the restored site supports important tasks. Test a compatibility matrix for publishing, checkout, payment callbacks, order exports, email, stock and refunds. Compare content and search output with the existing site.

Plan database cutover carefully. A store can receive orders while a copy is made; define a write freeze, incremental synchronization or another validated strategy. Reverting to an old backup after new orders arrive can lose records. Document reconciliation as part of rollback.

## Launch checklist

- [ ] Verify domain, HTTPS, host and application settings.
- [ ] Remove unintended staging index controls.
- [ ] Test mapped redirects and missing-page responses.
- [ ] Confirm content, media, canonicals and sitemap output.
- [ ] Verify order totals, provider callbacks, shipping and customer email.
- [ ] Confirm background schedules and queued work resume safely.
- [ ] Inspect logs and retain a named response owner.
- [ ] Record accepted differences and unresolved dependencies.

## Routine care

Review security notices promptly and test proportionate changes on staging. A minor update can affect checkout; WooCommerce 11.2.1 fixed regressions from the preceding release. Keep a release record and critical workflow tests. Avoid bundling unrelated upgrades into one change without a recoverable boundary.

Maintain licences, integration contacts and backup retention. Demonstrate restoration periodically, including files, database and secrets required to operate. Monitor failures that require action rather than collecting unactionable alerts. Editors should know how to report a defect with a reproducible example and no private data.

The business owns the recovery objectives and support agreement. This runbook supplies planning steps, not a monitored maintenance service or an assurance that data cannot be lost.
