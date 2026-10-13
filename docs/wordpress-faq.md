# WordPress and WooCommerce buyer FAQ

## Should we commission a custom theme or use an existing one?

Compare editorial structure, accessible output, design constraints and maintenance responsibility. A supported theme may fit a standard business site. Custom work becomes useful when templates or interactions need a controlled design that existing options cannot sustain. Review content modelling and update ownership before choosing.

## Is fewer plugins always better?

No. Judge each dependency by purpose, quality, interoperability and maintenance. Removing a maintained extension to create an unsupported replacement can increase risk. Conversely, overlapping plugins and unrelated global assets can create conflicts. Inventory the actual behaviour instead of selecting a numerical plugin limit.

## Will an HPOS declaration make our plugin compatible?

A declaration should follow an audit and tests. Direct order access through postmeta or obsolete database assumptions can fail when the authoritative datastore changes. Use WooCommerce APIs and verify supported storage modes and critical order paths. The declaration alone proves no behaviour.

## Can a classic checkout customization be reused with blocks?

Not automatically. Checkout Blocks and classic checkout have different extension surfaces. Check the chosen extension's support and test the actual store workflow, including payment and address validation. Do not promise compatibility based only on a similar visual result.

## Does WordPress 7.1 provide a complete AI assistant?

Core includes relevant building blocks, but provider connections and a permitted application workflow are still required. The MCP Adapter and experimental AI-plugin work are separate components. Feature detection, privacy, permissions and approval remain implementation responsibilities.

## Can you build a courier or local-payment integration?

Potential scope depends on the provider's supported API, merchant eligibility, credentials and operational process. Confirm those dependencies before estimating. Testing must include retries, duplicate requests and reconciliation, not only a successful demonstration.

## Who owns a private custom plugin?

Ownership, licensing, dependencies and support should be written into the agreement. WordPress and included software licences affect distribution rights. Keep the client source private and clarify the actual handover rather than treating a generic service description as legal advice.

## What should we send for an initial review?

Public site URLs, current versions, a dependency list, the difficult workflow and the desired outcome. Keep customer exports, API keys and passwords out of public repository issues. Use [OzairWebs contact information](https://ozairwebs.com/company/contact/) for business enquiries and a private channel for security reports.
