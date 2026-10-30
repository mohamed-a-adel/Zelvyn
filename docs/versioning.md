# Versioning and compatibility

The public API is versioned in the path: every operation lives under `/api/v1`. The current document advertises API version `0.1.0` and OpenAPI `3.1.0`.

## Compatibility rules

- Additive changes (a new endpoint, a new optional response field) are non-breaking.
- Existing request fields keep their meaning. Removing or renaming a field is a breaking change and requires a new path version.
- Unknown request fields are rejected today, so send only the fields documented here.
- Errors remain JSON envelopes. Do not parse HTML error pages.
- Deprecated endpoints send `deprecation` and `sunset` headers; they keep serving until `sunset`, then answer `410 ENDPOINT_SUNSET`.

## Machine-readable contract

Always generate clients from the live document rather than copying this handbook:

<https://api-zelvyn.devs.surf/openapi.json>

The document includes request/response schemas, examples, error components, security schemes, and the `x-zelvyn-limits` extension used above.

---

[Endpoint index](endpoints/README.md) · [Authentication](authentication.md) · [Errors](errors.md) · [Rate limits](rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
