# WordPress security review

Define the threat and the protected data before adding controls. A public catalogue, an editorial dashboard and an order export expose different risks. Record administrative access, integration credentials, writable files and customer-data retention. No configuration can guarantee complete protection from compromise.

## Application checks

Use capability and resource checks for sensitive actions. Nonces contribute to CSRF defences but are not authentication or authorization. Validate inputs against the expected meaning; sanitise where appropriate and escape at the output context. Use supported APIs or prepared queries to reduce SQL-injection risk. Avoid displaying raw errors or request contents to visitors.

REST endpoints must define permission callbacks and permitted arguments. File uploads need checks on type, size, storage and access, with inspection suitable to the risk. Do not trust a browser-provided MIME value alone. Review the [nonce reference](https://developer.wordpress.org/apis/security/nonces/) and [custom endpoint documentation](https://developer.wordpress.org/rest-api/extending-the-rest-api/adding-custom-endpoints/).

## Operational checklist

- [ ] Restrict administrator roles and review unused accounts.
- [ ] Use appropriate two-factor authentication and recovery procedures.
- [ ] Keep core, themes and plugins current through tested updates.
- [ ] Check dependency and vulnerability notices for installed versions.
- [ ] Protect API keys from browser output, public code and routine logs.
- [ ] Apply minimum necessary integration permissions and revocation procedures.
- [ ] Monitor relevant malware/security signals and investigate suspicious changes.
- [ ] Configure a WAF where justified, without assuming it repairs insecure code.
- [ ] Store recoverable backups separately and demonstrate restoration.
- [ ] Define an incident owner, escalation route and evidence-retention policy.

Security hardening should preserve needed publishing, checkout and integration behaviour. Test denied requests and valid workflows. Broken administration caused by an indiscriminate rule is an operational failure, not proof of stronger protection.

AI tools add prompt-injection and external-transfer concerns. Model output should not control permissions, select arbitrary destinations or invoke unrestricted writes. Use explicit approval boundaries and audit identities. Report vulnerabilities privately through the documented channel rather than posting credentials or exploit details in a public documentation issue.
