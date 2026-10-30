# Authentication

## No key required

Every endpoint in this handbook works without an API key. Keyless requests are served on the anonymous rate limit (per anonymised caller hash) and are fully functional.

## Optional API key

If you have a Zelvyn API key, send it to use your account's plan rate limit and monthly quota instead of the anonymous limit. Send it in exactly one of these forms:

```http
Authorization: Bearer zlv_live_<keyId>_<secret>
```

```http
x-api-key: zlv_live_<keyId>_<secret>
```

`Authorization` takes precedence if both headers are present. Never put a key in a URL, a browser bundle, a public repository, or a log.

## Getting a higher limit

Keys are scoped to an account, an environment (`LIVE` or `TEST`) and a plan. To request a higher limit, [contact support](https://zelvyn.devs.surf/support) and tell us about your workload. The operator issues the key for your account. There is no public self-service key page in this handbook.

When a key is created, the plaintext value is returned **once**. Store it in a secret manager. The API stores only an HMAC hash.

## What happens on failure

| Situation | HTTP | `error.code` |
| --- | --- | --- |
| Keyless request | `200` | — (anonymous rate limit) |
| Malformed, unknown, revoked or expired key | `401` | `UNAUTHORIZED` |
| Key valid, plan or endpoint denied | `403` | `FORBIDDEN` |
| Too many requests | `429` | `RATE_LIMITED` |
| Monthly quota exhausted | `429` | `QUOTA_EXCEEDED` |
| Auth/control plane unavailable | `503` | `SERVICE_UNAVAILABLE` |

A key you present is always validated. An invalid key is rejected rather than silently downgraded to an anonymous request. Failures are uniform: an unknown key and a revoked key deliberately produce the same response.

## Request id

Send an optional `x-request-id` header to correlate your own traces. A valid value is echoed in `meta.requestId` and the `x-request-id` response header. An absent or malformed value is replaced by a server-generated UUID v4.

---

[Endpoint index](endpoints/README.md) · [Errors](errors.md) · [Rate limits](rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
