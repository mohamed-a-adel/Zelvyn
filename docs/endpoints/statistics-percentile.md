# POST /api/v1/statistics/percentile

**Percentile (linear interpolation)**

Returns the `percentile`-th percentile of `values` using linear interpolation between closest ranks (the NumPy/`PERCENTILE` inclusive definition). `percentile` is a finite number in [0, 100]; 0 is the minimum and 100 is the maximum. Accepts 1–10,000 finite numbers.

## Authentication

No API key is required. If you have a key, add `Authorization: Bearer $ZELVYN_API_KEY` (or `x-api-key`) to use your plan's higher rate limit and quota. See [authentication](../authentication.md).

Base URL: `https://api-zelvyn.devs.surf`

## Request

`POST /api/v1/statistics/percentile`

### Parameters

| Name | In | Required | Description |
| --- | --- | --- | --- |
| `x-request-id` | header | no | Optional client-supplied correlation id. Must match `^[A-Za-z0-9._-]{8,64}$`. A valid value is echoed in `meta.requestId` and the `x-request-id` response header; an absent or malformed value is replaced by a server-generated UUID v4. |
| `x-zelvyn-profile` | header | no | Selects a response field set. One of `compact`, `default`, `detailed`. `default` is the unprofiled v1 contract (`operation` + `result`) and is always available. `compact` and `detailed` are only honoured where the endpoint offers them, and never beyond the profile an administrator has activated. An unsupported value is rejected with 400 VALIDATION_ERROR rather than ignored. |

### Body schema

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `values` | array<number> | yes | min items 1 · max items 10000 |
| `percentile` | number | yes | min 0 · max 100 |

### Example body

```json
{
  "values": [
    1,
    2,
    3,
    4
  ],
  "percentile": 75
}
```

### cURL

```bash
# No API key needed. Optional: add this header for a higher limit:
#   -H 'Authorization: Bearer $ZELVYN_API_KEY'
curl -sS \
  -X POST 'https://api-zelvyn.devs.surf/api/v1/statistics/percentile' \
  -H 'Content-Type: application/json' \
  -d '{"values":[1,2,3,4],"percentile":75}'
```

### Examples in every language

[cURL](../languages/curl.md#op-statisticsPercentile) · [JavaScript](../languages/javascript.md#op-statisticsPercentile) · [TypeScript](../languages/typescript.md#op-statisticsPercentile) · [Python](../languages/python.md#op-statisticsPercentile) · [PHP](../languages/php.md#op-statisticsPercentile) · [Go](../languages/go.md#op-statisticsPercentile) · [Java](../languages/java.md#op-statisticsPercentile) · [C#](../languages/csharp.md#op-statisticsPercentile) · [Ruby](../languages/ruby.md#op-statisticsPercentile) · [Rust](../languages/rust.md#op-statisticsPercentile) · [Kotlin](../languages/kotlin.md#op-statisticsPercentile) · [Swift](../languages/swift.md#op-statisticsPercentile) · [Dart](../languages/dart.md#op-statisticsPercentile)

## Response

```json
{
  "success": true,
  "data": {
    "operation": "percentile",
    "result": 3.25
  },
  "meta": {
    "requestId": "3f1c2b7a-9d4e-4f6a-8b2c-1a2b3c4d5e6f",
    "timestamp": "2026-01-15T12:00:00.000Z"
  }
}
```

## Status codes

| Status | Meaning |
| --- | --- |
| `200` | Successful calculation. The result is in `data.result`. |
| `400` | The request is malformed: wrong types, missing/unknown fields, out-of-range values, or invalid JSON. |
| `401` | A credential was presented but is invalid, revoked, expired, or malformed. Credential existence is never disclosed. |
| `403` | The credential is valid but the account is not permitted to use the API (for example, suspended). |
| `405` | The path exists but does not accept this HTTP method. The `allow` response header lists the supported methods. |
| `410` | The endpoint has been retired (`ENDPOINT_SUNSET`). The `sunset` header carries the retirement date; remove the integration and use the replacement named in the response. |
| `413` | The request body exceeds the 1048576-byte (1 MiB) limit. |
| `422` | The request is well-formed but mathematically or business-undefined for the given input (`DIVISION_BY_ZERO`, `UNDEFINED_RESULT`, or `INVALID_DATASET`). |
| `429` | The caller exceeded its rate limit (`RATE_LIMITED`) or its monthly quota (`QUOTA_EXCEEDED`). The `retry-after` header reports seconds until the rate-limit window resets. |
| `500` | An unexpected internal error occurred. Details are logged server-side and never returned. |
| `503` | The control plane (authentication, rate limiting, or quota) is temporarily unavailable. Authenticated requests fail closed; anonymous traffic keeps being served. |

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
