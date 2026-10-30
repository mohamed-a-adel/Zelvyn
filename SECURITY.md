# Security policy

## Supported versions

The hosted Zelvyn API is a continuously deployed service. The current
`/api/v1` contract and the public handbook in this repository are supported.
Older endpoint versions are supported until their announced sunset date; see
[Versioning](docs/versioning.md).

## Reporting a vulnerability

**Please do not open a public issue, discussion, or pull request for a security
problem.** Public disclosure puts every user at risk.

Report privately using one of these channels:

1. **GitHub private vulnerability reporting** — open the **Security** tab of this
   repository and choose **Report a vulnerability**. This is the preferred
   channel.
2. **Support form** — <https://zelvyn.devs.surf/support>, choose
   **Security or vulnerability report**. Do not include live secrets.

Include as much of the following as you can:

- A description of the issue and its potential impact.
- The affected endpoint, path, or page.
- Reproduction steps or a minimal proof of concept.
- The `meta.requestId` from any affected response.
- Your environment (language, runtime, browser) when relevant.

**Never include a live API key, access code, password, session cookie, or
another person's data.** If you must demonstrate a credential issue, use a
revoked test key and say so.

## What to expect

- We aim to acknowledge a report within **3 business days**.
- We will investigate, keep you updated on material progress, and tell you when
  a fix is deployed.
- We will credit you in the advisory if you want credit, and we will respect a
  request to remain anonymous.
- Please give us a reasonable window to fix the issue before any public
  disclosure. We will agree a disclosure date with you.

## Scope

In scope:

- The hosted API at `https://api-zelvyn.devs.surf`.
- The public website and admin surfaces at `https://zelvyn.devs.surf`.
- This documentation repository.

Out of scope:

- Denial-of-service testing, load testing, or spam against production.
- Social engineering of staff or users.
- Vulnerabilities in third-party services we do not control.
- Reports that require a compromised device, browser extension, or physical
  access.
- Missing security headers or cookie flags with no demonstrated impact.
- Automated scanner output without a reproducible issue.

## Safe harbour

We will not pursue legal action against researchers who:

- Act in good faith and follow this policy.
- Avoid privacy violations, data destruction, and service disruption.
- Only interact with accounts they own or have explicit permission to test.
- Report the issue privately and give us reasonable time to respond.

## Hardening notes for integrators

- Every calculation endpoint works without a key. A key is optional and only
  raises your rate limit; treat it as a secret anyway.
- Send credentials only in the `Authorization` or `x-api-key` header. Never put
  a key in a URL, a browser bundle, a public repository, or a log.
- Store keys in a secret manager and rotate them if exposure is suspected.
- Validate the `success` flag and `error.code` in every response before using
  `data`.
