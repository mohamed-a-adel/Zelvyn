# Errors

Every failure uses the same JSON envelope:

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Request validation failed."
  },
  "meta": {
    "requestId": "3f1c2b7a-9d4e-4f6a-8b2c-1a2b3c4d5e6f",
    "timestamp": "2026-01-15T12:00:00.000Z"
  }
}
```

`error.code` is stable and machine-readable. `error.message` is human-readable and may be reworded. Some codes add an `issues`, `index`, `limit` or `retryAfterSeconds` field inside `error`.

## Common status codes

| Component | Typical code | Meaning |
| --- | --- | --- |
| `BadRequest` | `VALIDATION_ERROR` | The request is malformed: wrong types, missing/unknown fields, out-of-range values, or invalid JSON. |
| `Unauthorized` | `UNAUTHORIZED` | A credential was presented but is invalid, revoked, expired, or malformed. Credential existence is never disclosed. |
| `Forbidden` | `FORBIDDEN` | The credential is valid but the account is not permitted to use the API (for example, suspended). |
| `NotFound` | `INVALID_OPERATION` | No endpoint or operation matches the requested path. |
| `MethodNotAllowed` | `METHOD_NOT_ALLOWED` | The path exists but does not accept this HTTP method. The `allow` response header lists the supported methods. |
| `Gone` | `ENDPOINT_SUNSET` | The endpoint has been retired (`ENDPOINT_SUNSET`). The `sunset` header carries the retirement date; remove the integration and use the replacement named in the response. |
| `PayloadTooLarge` | `PAYLOAD_TOO_LARGE` | The request body exceeds the 1048576-byte (1 MiB) limit. |
| `UnprocessableEntity` | `DIVISION_BY_ZERO` | The request is well-formed but mathematically or business-undefined for the given input (`DIVISION_BY_ZERO`, `UNDEFINED_RESULT`, or `INVALID_DATASET`). |
| `TooManyRequests` | `RATE_LIMITED` | The caller exceeded its rate limit (`RATE_LIMITED`) or its monthly quota (`QUOTA_EXCEEDED`). The `retry-after` header reports seconds until the rate-limit window resets. |
| `InternalServerError` | `INTERNAL_ERROR` | An unexpected internal error occurred. Details are logged server-side and never returned. |
| `ServiceUnavailable` | `SERVICE_UNAVAILABLE` | The control plane (authentication, rate limiting, or quota) is temporarily unavailable. Authenticated requests fail closed; anonymous traffic keeps being served. |

## Validation errors

`400 VALIDATION_ERROR` and `422 UNPROCESSABLE_ENTITY` include a bounded list of issues:

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Request validation failed.",
    "issues": [
      { "path": "values", "code": "too_small", "message": "Array must contain at least 1 element(s)" }
    ]
  },
  "meta": { "requestId": "…", "timestamp": "…" }
}
```

Unknown request fields are rejected because every body schema uses `additionalProperties: false`.

## Retrying

- `429` — honour `retry-after` (seconds). Do not retry immediately in a tight loop.
- `500` — retry with exponential backoff and jitter.
- `503` — the control plane is unavailable; authenticated requests fail closed. Retry later.
- `410` — the endpoint has been sunset; do not retry. Migrate to the replacement.

---

[Endpoint index](endpoints/README.md) · [Authentication](authentication.md) · [Rate limits](rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
