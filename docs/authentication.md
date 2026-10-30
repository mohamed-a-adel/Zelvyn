# Authentication

## Public endpoint

`GET /api/v1/health` is public. It does not require a key and is not metered as a calculation.

## Calculation endpoints

Every other endpoint in this handbook requires a Zelvyn API key unless an operator has explicitly opened that endpoint for anonymous access. Send it in exactly one of these forms:

```http
Authorization: Bearer zlv_live_<keyId>_<secret>
```

```http
x-api-key: zlv_live_<keyId>_<secret>
```

`Authorization` takes precedence if both headers are present. Never put a key in a URL, a browser bundle, a public repository, or a log.

## Getting a key

Keys are scoped to an account, an environment (`LIVE` or `TEST`) and a plan. Ask the Zelvyn operator for a key, or create an account with `POST /api/v1/account/register` and then create a key through `POST /api/v1/account/keys`. This handbook deliberately does not publish a fake "sign up and click a button" flow: the account routes are cookie- and CSRF-authenticated and are excluded from the public OpenAPI document.

When a key is created, the plaintext value is returned **once**. Store it in a secret manager. The API stores only an HMAC hash.

## What happens on failure

| Situation | HTTP | `error.code` |
| --- | --- | --- |
| Missing key | `401` | `UNAUTHORIZED` |
| Malformed or unknown key | `401` | `UNAUTHORIZED` |
| Revoked or expired key | `401` | `UNAUTHORIZED` |
| Key valid, plan or endpoint denied | `403` | `FORBIDDEN` |
| Too many requests | `429` | `RATE_LIMITED` |
| Monthly quota exhausted | `429` | `QUOTA_EXCEEDED` |
| Auth/control plane unavailable | `503` | `SERVICE_UNAVAILABLE` |

Failures are uniform: an unknown key and a revoked key deliberately produce the same response.

## Request id

Send an optional `x-request-id` header to correlate your own traces. A valid value is echoed in `meta.requestId` and the `x-request-id` response header. An absent or malformed value is replaced by a server-generated UUID v4.

---

[Endpoint index](endpoints/README.md) · [Errors](errors.md) · [Rate limits](rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
