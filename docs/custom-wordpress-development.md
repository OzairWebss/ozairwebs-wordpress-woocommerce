# Custom WordPress development decisions

Model the content before selecting a theme. Identify which records are edited, reused, searched and approved. A consultancy service, an author biography and a booking request have different lifetimes and permissions. Keep business rules in a plugin when they should survive a theme change.

## Content and editor architecture

Custom post types organise distinct records; taxonomies express reusable classifications. Registered fields should have defined data types, permission boundaries and migration behaviour. A field that appears in an admin form is not automatically appropriate for public REST output. Document ownership and the expected publishing workflow.

Block themes and Full Site Editing support template editing, while theme.json can constrain shared design choices. Custom Gutenberg blocks are useful for repeated editorial structures with defined inputs and accessible output. The Interactivity API and Block Bindings are separate tools: one supports interactive behaviour, while the other connects supported block attributes to data sources. Check supported behaviour on the target release and avoid describing all Gutenberg-plugin features as core.

WordPress 7.1 brought further responsive styling and editor capabilities. Verify the actual theme and extension set before adoption. An editor's ability to adjust a layout must be balanced with readable content and a repeatable design system. [Global settings and styles](https://developer.wordpress.org/themes/global-settings-and-styles/) explains the theme configuration surface.

## Scope checklist

- [ ] Define content types, relationships and required fields.
- [ ] Identify draft, review and publication roles.
- [ ] Specify which data may enter public API responses.
- [ ] Choose multilingual URL and translation ownership rules.
- [ ] Review Multisite only when shared governance justifies it.
- [ ] Inventory legacy shortcodes, theme logic and licensed dependencies.
- [ ] Test editing, preview, keyboard use, mobile layouts and error messages.
- [ ] Plan schema/content migrations and a rollback boundary.

Administrative customisation should make tasks clearer without granting broad permissions to ordinary editors. REST endpoints need explicit permission callbacks and validated inputs. Keep editorial handover practical: demonstrate how an editor completes common tasks and recovers from mistakes. This guide describes architecture decisions rather than a ready-made theme.
