# POST /api/v1/math/subtract

**Subtract numbers (left to right)**

Returns `values₀ − values₁ − values₂ − …`, evaluated strictly left to right (the array is the expression). Requires at least two finite values.

## Authentication

No API key is required. If you have a key, add `Authorization: Bearer $ZELVYN_API_KEY` (or `x-api-key`) to use your plan's higher rate limit and quota. See [authentication](../authentication.md).

Base URL: `https://api-zelvyn.devs.surf`

## Request

`POST /api/v1/math/subtract`

### Parameters

| Name | In | Required | Description |
| --- | --- | --- | --- |
| `x-request-id` | header | no | Optional client-supplied correlation id. Must match `^[A-Za-z0-9._-]{8,64}$`. A valid value is echoed in `meta.requestId` and the `x-request-id` response header; an absent or malformed value is replaced by a server-generated UUID v4. |
| `x-zelvyn-profile` | header | no | Selects a response field set. One of `compact`, `default`, `detailed`. `default` is the unprofiled v1 contract (`operation` + `result`) and is always available. `compact` and `detailed` are only honoured where the endpoint offers them, and never beyond the profile an administrator has activated. An unsupported value is rejected with 400 VALIDATION_ERROR rather than ignored. |

### Body schema

| Field | Type | Required | Description |
| --- | --- | --- | --- |
| `values` | array<number> | yes | min items 2 · max items 10000 |

### Example body

```json
{
  "values": [
    10,
    3,
    4
  ]
}
```

### cURL

```bash
# No API key needed. Optional: add this header for a higher limit:
#   -H 'Authorization: Bearer $ZELVYN_API_KEY'
curl -sS \
  -X POST 'https://api-zelvyn.devs.surf/api/v1/math/subtract' \
  -H 'Content-Type: application/json' \
  -d '{"values":[10,3,4]}'
```

### Examples in every language

[cURL](../languages/curl.md#op-mathSubtract) · [JavaScript](../languages/javascript.md#op-mathSubtract) · [TypeScript](../languages/typescript.md#op-mathSubtract) · [Python](../languages/python.md#op-mathSubtract) · [PHP](../languages/php.md#op-mathSubtract) · [Go](../languages/go.md#op-mathSubtract) · [Java](../languages/java.md#op-mathSubtract) · [C#](../languages/csharp.md#op-mathSubtract) · [Ruby](../languages/ruby.md#op-mathSubtract) · [Rust](../languages/rust.md#op-mathSubtract) · [Kotlin](../languages/kotlin.md#op-mathSubtract) · [Swift](../languages/swift.md#op-mathSubtract) · [Dart](../languages/dart.md#op-mathSubtract)

## Response

```json
{
  "success": true,
  "data": {
    "operation": "subtract",
    "result": 3
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
