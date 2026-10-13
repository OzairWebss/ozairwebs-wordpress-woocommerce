# Private plugin scoping and maintenance

A custom plugin is appropriate when the required business behaviour is distinctive or supported extensions cannot meet the data and recovery requirements. Compare configuration, an extension and custom work against operating cost. An unsupported override can be more fragile than a well-scoped plugin, while unnecessary bespoke code creates maintenance debt.

## Original plugin-scoping checklist

- [ ] State the business workflow and actors who may perform each action.
- [ ] Define authoritative records, stable identifiers and data retention.
- [ ] Document supported WordPress, PHP and relevant WooCommerce versions.
- [ ] Identify hooks, admin screens, REST endpoints and scheduled work.
- [ ] Specify validation, capabilities, nonce use and output contexts.
- [ ] Describe activation, schema upgrades, deactivation and uninstall behaviour.
- [ ] Define API access, retry, duplicate detection and reconciliation.
- [ ] Agree observability, operational commands and error handling.
- [ ] Set tests, release ownership, update delivery and support boundaries.
- [ ] Confirm code ownership and licensing, including dependency obligations.

Use namespaced modules with clear responsibilities. Hooks and filters should have documented assumptions and avoid unnecessary global side effects. Composer can manage dependencies, but autoloading and version conflicts need review. Database schema changes should be recoverable and support the agreed upgrade path. Do not delete business data on uninstall unless the owner explicitly chooses that policy.

## Scheduling and integrations

WP-Cron runs through site visits and is not a precise scheduler. Time-sensitive workflows may need an external trigger or supported queue. Use stable job identifiers, bounded retries and operator-visible failures. WP-CLI commands can provide safe reconciliation and diagnostics when access and command behaviour are documented.

Settings API forms need validation and permission checks. REST routes must enforce capabilities and record ownership. A valid nonce helps establish request intent, but does not grant authority. See [WordPress endpoint guidance](https://developer.wordpress.org/rest-api/extending-the-rest-api/adding-custom-endpoints/) and [security review](wordpress-security.md).

Private commissioning should define source delivery, future maintenance and dependency licensing. Paid distribution needs an update and support model consistent with WordPress and included licences. Do not expose a client's implementation to illustrate the service. The [scope register](../examples/README.md) is a reusable planning asset without client code.
