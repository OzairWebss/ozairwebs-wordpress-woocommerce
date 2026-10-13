# WordPress AI capability and permission boundaries

Reviewed on 13 October 2026. Distinguish platform building blocks from a finished workflow. WordPress version, provider implementation, connection configuration and plugin availability all affect what a site can do. A model connection does not grant permission to use customer data or publish its output.

| Component | Verified status | What remains to implement |
| --- | --- | --- |
| Abilities API | Core infrastructure introduced before 7.0 and extended subsequently | Register meaningful operations, schemas and permission checks |
| WordPress AI Client | Added to core in 7.0 | Approved provider connection, feature detection and application workflow |
| Connectors | Core connection infrastructure associated with 7.0 | Provider configuration and owned credentials |
| MCP Adapter | Separate integration component | Scoped exposure, supported version and acting identity |
| AI plugin experiments | Features developed separately; roadmap is not a release guarantee | Compatibility, maturity and production acceptance review |

The [7.0 Field Guide](https://make.wordpress.org/core/2026/05/14/wordpress-7-0-field-guide/) and [AI Client note](https://make.wordpress.org/core/2026/03/24/introducing-the-ai-client-in-wordpress-7-0/) explain the shipped boundary. The [7.2 roadmap](https://make.wordpress.org/core/2026/09/18/roadmap-to-7-2/) explicitly distinguishes continuing AI-plugin work from guaranteed core inclusion. Do not treat an optional library's API as universally available on every installation.

## A controlled import workflow

Receive approved supplier or job-listing data, validate required fields, match stable identifiers and stage differences. A model may propose classification or extract structure, while deterministic checks enforce allowed values and an editor reviews ambiguous records. Duplicate detection should use identifiers and business rules, not a model's confidence alone.

n8n, CRM or ERP integrations require defined permissions, retries and reconciliation. Record external transfers and minimise retained data. A knowledge assistant should retrieve only sources permitted for its user, with provenance and removal handling.

## Before enabling writes

Define permitted tools, role/capability checks, argument validation, audit records and human approval for sensitive actions. Treat prompts, imported descriptions and retrieved documents as untrusted inputs. They cannot alter authorization. Feature detection and fallback should handle missing providers, unsupported outputs and exhausted quotas.

Scheduled content workflows need reliable execution, clear publication ownership and a recovery path. Do not promise that autonomous publication is inherently safe. The [plugin-scoping guide](custom-plugin-development.md) helps convert an AI idea into testable operational requirements.
