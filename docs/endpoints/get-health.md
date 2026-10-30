# GET /api/v1/health

**Liveness / readiness probe**

Stateless liveness/readiness probe: no database, dependencies, or external calls. Use it to verify reachability and read the running service/API versions.

## Authentication

This endpoint is public. No API key is required. See [authentication](../authentication.md).

Base URL: `https://api-zelvyn.devs.surf`

## Request

`GET /api/v1/health`

### Parameters

| Name | In | Required | Description |
| --- | --- | --- | --- |
| `x-request-id` | header | no | Optional client-supplied correlation id. Must match `^[A-Za-z0-9._-]{8,64}$`. A valid value is echoed in `meta.requestId` and the `x-request-id` response header; an absent or malformed value is replaced by a server-generated UUID v4. |

### cURL

```bash
curl -sS \
  -X GET 'https://api-zelvyn.devs.surf/api/v1/health' \
  -H 'Authorization: Bearer $ZELVYN_API_KEY' \
  -H 'Content-Type: application/json'
```

### Examples in every language

[cURL](../languages/curl.md#op-getHealth) · [JavaScript](../languages/javascript.md#op-getHealth) · [TypeScript](../languages/typescript.md#op-getHealth) · [Python](../languages/python.md#op-getHealth) · [PHP](../languages/php.md#op-getHealth) · [Go](../languages/go.md#op-getHealth) · [Java](../languages/java.md#op-getHealth) · [C#](../languages/csharp.md#op-getHealth) · [Ruby](../languages/ruby.md#op-getHealth) · [Rust](../languages/rust.md#op-getHealth) · [Kotlin](../languages/kotlin.md#op-getHealth) · [Swift](../languages/swift.md#op-getHealth) · [Dart](../languages/dart.md#op-getHealth)

## Response

```json
{
  "success": true,
  "data": {
    "status": "ok",
    "service": "zelvyn-api",
    "apiVersion": "v1",
    "version": "0.1.0",
    "environment": "production"
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
| `200` | Service is up. |
| `405` | The path exists but does not accept this HTTP method. The `allow` response header lists the supported methods. |

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
