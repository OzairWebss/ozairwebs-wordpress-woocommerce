# WordPress performance diagnosis

Measure representative pages and tasks before changing caching or plugins. A logged-out cached homepage can be fast while product filtering, checkout or administration remains slow. Capture field metrics where available and use lab tools to reproduce specific problems.

## Identify the expensive layer

Inspect PHP/server response time, database query count and duration, remote requests, page-builder output and browser assets. Large autoloaded options, unbounded queries and slow integrations can affect routes independently of media weight. An object cache may reduce repeated work, but it does not justify an incorrect query or uncontrolled retention.

Page caching, persistent object caching and CDN delivery have different roles. Review cart, checkout and account responses for user-specific data and cache exclusions. Redis needs a considered configuration, eviction policy and outage behaviour. Clearing every cache on each edit can remove the benefit; failing to invalidate important output can show stale prices or content.

## Browser and content delivery

Optimise images for their layout, reserve dimensions and lazy-load noncritical media. Avoid delaying the primary visible content unnecessarily. Review font loading, critical rendering paths and scripts loaded globally when they are only used on a few pages. Test keyboard interaction and layout movement after removing or deferring assets.

LCP, INP and CLS describe different aspects of experience. Compare templates and device groups rather than treating one score as the whole site. Tracking, consent and chat tools belong in performance review because they can add substantial browser work. Set a budget and retest important journeys after updates.

## Practical acceptance sample

Check a service page, article, product, category filter, cart and checkout under relevant conditions. Include warm/cold caches and signed-in/out behaviour. Record the change, conditions and evidence. Verify catalogue facts and customer permissions after cache changes.

The [maintenance guide](maintenance-and-migration.md) explains staging and rollback. Performance improvement is a measured outcome, not a guarantee of rankings or sales. WordPress version updates and WooCommerce features may change bottlenecks; recheck before adopting an old optimisation recipe.
