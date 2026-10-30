# Rate limits and quotas

Limits are reported by the live OpenAPI document as `x-zelvyn-limits`. The values below are generated from the current contract.

## Plan limits

| Plan | Account rate | Monthly quota | Account burst | Endpoint burst |
| --- | --- | --- | --- | --- |
| FREE | 60/minute | 10,000/month | 240/minute | 60/minute |
| PRO | 600/minute | 1,000,000/month | 2400/minute | 600/minute |

## Dimensions

| Dimension | Scope | Limit |
| --- | --- | --- |
| key | one API key | per-key requests per minute |
| account | plan × environment | see `plans` |
| endpoint | one endpoint × one caller | see `plans` |
| ip | anonymised caller hash | anonymousRateLimitPerMinute |
| global | the whole API | off unless configured |
| admin | private admin control plane | ADMIN_RATE_LIMIT_GLOBAL_PER_MINUTE / ADMIN_RATE_LIMIT_IP_PER_MINUTE / ADMIN_RATE_LIMIT_FAILED_PER_MINUTE (default 120 / 60 / 10 per minute) |

Anonymous traffic is limited to 60 requests per minute per anonymised caller hash. Calculation endpoints require a key by default, so anonymous limits apply only when an operator explicitly opens an endpoint.

## Request limits

- Maximum request body: **1 MiB**.
- Maximum dataset values in one request: **10,000**.
- Rate-limited responses include `retry-after` (seconds until the window resets).

## Handling 429

```json
{
  "success": false,
  "error": {
    "code": "RATE_LIMITED",
    "message": "Rate limit exceeded. Slow down and retry shortly.",
    "limit": 60,
    "windowSeconds": 60,
    "retryAfterSeconds": 42
  },
  "meta": { "requestId": "…", "timestamp": "…" }
}
```

Wait for `retry-after`, then retry with jitter. A monthly-quota failure uses `error.code = "QUOTA_EXCEEDED"`; waiting for a rate window will not fix it — upgrade the plan or wait for the quota reset.

---

[Endpoint index](endpoints/README.md) · [Authentication](authentication.md) · [Errors](errors.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
