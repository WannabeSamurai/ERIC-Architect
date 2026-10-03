# Security Policy

ERIC's production implementation, runtime state, development coordination, credentials, operator data, and machine-specific control configuration are private.

## Public Reporting Rule

Do not publish secrets, credentials, tokens, private keys, device-pairing material, personal/operator data, private runtime data, or detailed exploit instructions against the private ERIC host in a public issue or pull request.

If a suspected security problem cannot be described safely in public, do not post the sensitive payload publicly. Use GitHub's private security-reporting mechanism if it is available for this repository; otherwise contact the repository owner privately.

## Repository Boundary

This public repository intentionally contains architecture-level material only. It is not the production source repository and should not be used as evidence that a private implementation detail, credential, endpoint, host path, or security control exists unless explicitly documented here.

## Secrets

No secret is expected to be committed to this repository. If one is discovered, treat it as compromised: remove it from the current tree, rotate or revoke it at the provider, and assess repository history rather than assuming deletion from the latest revision is sufficient.

## Scope

Security claims follow ERIC's evidence rule: a designed control is not an applied control, and an applied control is not considered effective without verification.
