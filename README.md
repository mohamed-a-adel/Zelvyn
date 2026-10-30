<div align="center">

<img src="https://i.postimg.cc/rFQymy4T/zelvyn.png" alt="Zelvyn" height="56" />

### Math. Data. Decisions.

A stateless calculation and analytics API for mathematics, statistics and business metrics.

[![Website](https://img.shields.io/badge/website-zelvyn.devs.surf-0f172a?style=for-the-badge)](https://zelvyn.devs.surf)
[![Docs](https://img.shields.io/badge/docs-read%20the%20handbook-2563eb?style=for-the-badge)](https://zelvyn.devs.surf/docs)
[![API](https://img.shields.io/badge/API-api--zelvyn.devs.surf-16a34a?style=for-the-badge)](https://api-zelvyn.devs.surf/api/v1/health)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.1-7c3aed?style=for-the-badge)](https://api-zelvyn.devs.surf/openapi.json)

</div>

---

Zelvyn accepts JSON, returns JSON, and never stores your calculation inputs. Every response shares one envelope with a `meta.requestId`, so a result can be traced end-to-end without a session. **No API key is required** for any calculation endpoint; keys exist only to raise limits.

| | |
| --- | --- |
| **Public API** | <https://api-zelvyn.devs.surf> |
| **Hosted documentation** | <https://zelvyn.devs.surf/docs> |
| **OpenAPI 3.1 document** | <https://api-zelvyn.devs.surf/openapi.json> |
| **Website** | <https://zelvyn.devs.surf> |
| **Support** | <https://zelvyn.devs.surf/support> |

## Quick start

```bash
curl -sS https://api-zelvyn.devs.surf/api/v1/statistics/mean \
  -H "Content-Type: application/json" \
  -d '{"values":[10,20,30]}'
```

```json
{
  "success": true,
  "data": { "operation": "mean", "result": 20 },
  "meta": {
    "requestId": "3f1c2b7a-9d4e-4f6a-8b2c-1a2b3c4d5e6f",
    "timestamp": "2026-01-15T12:00:00.000Z"
  }
}
```

Prefer a typed client? Jump straight to the [Python](docs/languages/python.md), [JavaScript](docs/languages/javascript.md), [TypeScript](docs/languages/typescript.md) or any of the [13 language guides](#pick-a-language).

## Contents

- [Authentication](#authentication)
- [Endpoint catalog](#endpoint-catalog)
- [Pick a language](#pick-a-language)
- [Response envelope](#response-envelope)
- [Conventions](#conventions)
- [Documentation](#documentation)
- [Community](#community)
- [License](#license)

## Authentication

**Every calculation endpoint works keyless** and is covered by the anonymous rate limit. That is the public contract — no signup, token or header is needed to make the first request.

If you hold a Zelvyn API key, attach it for the higher plan limit. It is always optional:

```bash
curl -sS https://api-zelvyn.devs.surf/api/v1/statistics/mean \
  -H "Authorization: Bearer $ZELVYN_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"values":[10,20,30]}'
```

- Send the key as `Authorization: Bearer <key>` or `x-api-key: <key>`. If both are present, `Authorization` wins.
- Keys are issued per `LIVE` or `TEST` environment and per plan.
- An invalid, revoked or expired key still returns `401` — omit the header to stay on the anonymous limit.
- Need a higher limit? [Contact support](https://zelvyn.devs.surf/support).

> This repository documents the public calculation API. Account and session endpoints (`/api/v1/account/*`) are cookie- and CSRF-authenticated, are excluded from the public OpenAPI document, and are never required to call an endpoint in this handbook.

## Endpoint catalog

43 operations across four groups. Every operation has a dedicated page with request fields, constraints, a worked example and the error cases.

### Health

| Operation | Method | Path |
| --- | --- | --- |
| [Liveness / readiness probe](docs/endpoints/get-health.md) | `GET` | `/api/v1/health` |

### Statistics

| Operation | Method | Path |
| --- | --- | --- |
| [Maximum value](docs/endpoints/statistics-max.md) | `POST` | `/api/v1/statistics/max` |
| [Arithmetic mean](docs/endpoints/statistics-mean.md) | `POST` | `/api/v1/statistics/mean` |
| [Median](docs/endpoints/statistics-median.md) | `POST` | `/api/v1/statistics/median` |
| [Minimum value](docs/endpoints/statistics-min.md) | `POST` | `/api/v1/statistics/min` |
| [Percentile (linear interpolation)](docs/endpoints/statistics-percentile.md) | `POST` | `/api/v1/statistics/percentile` |
| [Range (max − min)](docs/endpoints/statistics-range.md) | `POST` | `/api/v1/statistics/range` |
| [Population standard deviation](docs/endpoints/statistics-standard-deviation.md) | `POST` | `/api/v1/statistics/standard-deviation` |
| [Sum of a dataset](docs/endpoints/statistics-sum.md) | `POST` | `/api/v1/statistics/sum` |
| [Population variance](docs/endpoints/statistics-variance.md) | `POST` | `/api/v1/statistics/variance` |

### Mathematics

| Operation | Method | Path |
| --- | --- | --- |
| [Add numbers](docs/endpoints/math-add.md) | `POST` | `/api/v1/math/add` |
| [Combinations C(n, r)](docs/endpoints/math-combinations.md) | `POST` | `/api/v1/math/combinations` |
| [Divide numbers (left to right)](docs/endpoints/math-divide.md) | `POST` | `/api/v1/math/divide` |
| [Factorial](docs/endpoints/math-factorial.md) | `POST` | `/api/v1/math/factorial` |
| [Greatest common divisor](docs/endpoints/math-gcd.md) | `POST` | `/api/v1/math/gcd` |
| [Least common multiple](docs/endpoints/math-lcm.md) | `POST` | `/api/v1/math/lcm` |
| [Natural logarithm](docs/endpoints/math-ln.md) | `POST` | `/api/v1/math/ln` |
| [Logarithm to a base (default 10)](docs/endpoints/math-log.md) | `POST` | `/api/v1/math/log` |
| [Multiply numbers](docs/endpoints/math-multiply.md) | `POST` | `/api/v1/math/multiply` |
| [N-th root](docs/endpoints/math-nth-root.md) | `POST` | `/api/v1/math/nth-root` |
| [Percent of a value](docs/endpoints/math-percent-of.md) | `POST` | `/api/v1/math/percent-of` |
| [Percentage change between two values](docs/endpoints/math-percentage-change.md) | `POST` | `/api/v1/math/percentage-change` |
| [Permutations P(n, r)](docs/endpoints/math-permutations.md) | `POST` | `/api/v1/math/permutations` |
| [Raise a base to an exponent](docs/endpoints/math-power.md) | `POST` | `/api/v1/math/power` |
| [Square root](docs/endpoints/math-sqrt.md) | `POST` | `/api/v1/math/sqrt` |
| [Subtract numbers (left to right)](docs/endpoints/math-subtract.md) | `POST` | `/api/v1/math/subtract` |

### Business analytics

| Operation | Method | Path |
| --- | --- | --- |
| [Average order value AOV](docs/endpoints/business-aov.md) | `POST` | `/api/v1/business/aov` |
| [Break-even volume (units)](docs/endpoints/business-break-even.md) | `POST` | `/api/v1/business/break-even` |
| [Customer acquisition cost CAC](docs/endpoints/business-cac.md) | `POST` | `/api/v1/business/cac` |
| [Compound annual growth rate CAGR (percent)](docs/endpoints/business-cagr.md) | `POST` | `/api/v1/business/cagr` |
| [Churn rate (percent)](docs/endpoints/business-churn-rate.md) | `POST` | `/api/v1/business/churn-rate` |
| [Customer lifetime value CLV](docs/endpoints/business-clv.md) | `POST` | `/api/v1/business/clv` |
| [Conversion rate (percent)](docs/endpoints/business-conversion-rate.md) | `POST` | `/api/v1/business/conversion-rate` |
| [Cost per acquisition CPA](docs/endpoints/business-cpa.md) | `POST` | `/api/v1/business/cpa` |
| [Cost per click CPC](docs/endpoints/business-cpc.md) | `POST` | `/api/v1/business/cpc` |
| [Cost per mille CPM](docs/endpoints/business-cpm.md) | `POST` | `/api/v1/business/cpm` |
| [Click-through rate CTR (percent)](docs/endpoints/business-ctr.md) | `POST` | `/api/v1/business/ctr` |
| [Markup (percent)](docs/endpoints/business-markup.md) | `POST` | `/api/v1/business/markup` |
| [Profit](docs/endpoints/business-profit.md) | `POST` | `/api/v1/business/profit` |
| [Profit margin (percent)](docs/endpoints/business-profit-margin.md) | `POST` | `/api/v1/business/profit-margin` |
| [Retention rate (percent)](docs/endpoints/business-retention-rate.md) | `POST` | `/api/v1/business/retention-rate` |
| [Return on ad spend ROAS (ratio)](docs/endpoints/business-roas.md) | `POST` | `/api/v1/business/roas` |
| [Return on investment ROI (percent)](docs/endpoints/business-roi.md) | `POST` | `/api/v1/business/roi` |

## Pick a language

Each page lists all 43 operations in one place, ready to copy into a project.

| Language | Runtime | Examples |
| --- | --- | --- |
| [cURL](docs/languages/curl.md) | Any shell (macOS, Linux, Windows) | All 43 requests |
| [JavaScript](docs/languages/javascript.md) | Node.js 18+ or any modern browser | All 43 requests |
| [TypeScript](docs/languages/typescript.md) | Node.js 18+ with TypeScript 5+ | All 43 requests |
| [Python](docs/languages/python.md) | Python 3.9+ with `requests` | All 43 requests |
| [PHP](docs/languages/php.md) | PHP 8+ with the cURL extension | All 43 requests |
| [Go](docs/languages/go.md) | Go 1.21+ | All 43 requests |
| [Java](docs/languages/java.md) | Java 11+ | All 43 requests |
| [C#](docs/languages/csharp.md) | .NET 6+ | All 43 requests |
| [Ruby](docs/languages/ruby.md) | Ruby 3+ | All 43 requests |
| [Rust](docs/languages/rust.md) | Rust 1.75+ with `reqwest` | All 43 requests |
| [Kotlin](docs/languages/kotlin.md) | Kotlin/JVM 1.9+ on Java 11+ | All 43 requests |
| [Swift](docs/languages/swift.md) | Swift 5.9+ on macOS or Linux | All 43 requests |
| [Dart](docs/languages/dart.md) | Dart 3+ with `package:http` | All 43 requests |

## Response envelope

Every successful response returns data under `data` and correlation details under `meta`:

```json
{
  "success": true,
  "data": { "operation": "mean", "result": 20 },
  "meta": {
    "requestId": "3f1c2b7a-9d4e-4f6a-8b2c-1a2b3c4d5e6f",
    "timestamp": "2026-01-15T12:00:00.000Z"
  }
}
```

Failures replace `data` with `error` and keep the same `meta`:

```json
{
  "success": false,
  "error": {
    "code": "VALIDATION_ERROR",
    "message": "Request validation failed.",
    "issues": [{ "path": "values", "code": "too_small", "message": "..." }]
  },
  "meta": {
    "requestId": "3f1c2b7a-9d4e-4f6a-8b2c-1a2b3c4d5e6f",
    "timestamp": "2026-01-15T12:00:00.000Z"
  }
}
```

See [Errors](docs/errors.md) for the full code list.

## Documentation

- [Endpoint index](docs/endpoints/README.md)
- [Authentication](docs/authentication.md)
- [Errors](docs/errors.md)
- [Rate limits and quotas](docs/rate-limits.md)
- [Versioning and compatibility](docs/versioning.md)
- [Language index](docs/languages/README.md)
- [OpenAPI JSON](openapi.json) · [live document](https://api-zelvyn.devs.surf/openapi.json)

## Conventions

- Request bodies are strictly validated. Unknown fields are rejected (`additionalProperties: false`).
- Percentage metrics return **percent points** (`40` means 40%). `roas` is a plain ratio (`4` means 4×).
- Percentages never carry a `%` sign and are never fractions.
- Exact integer results beyond `Number.MAX_SAFE_INTEGER` are returned as decimal strings, never rounded.
- Every error is a JSON envelope. API paths never return an HTML error page.
- `x-request-id` is echoed in `meta.requestId` when valid; otherwise the server generates a UUID v4.

## Community

- [Contributing](CONTRIBUTING.md)
- [Code of conduct](CODE_OF_CONDUCT.md)
- [Security policy](SECURITY.md)
- [Accessibility statement](ACCESSIBILITY.md)
- [Support](https://zelvyn.devs.surf/support)

## License

Proprietary. See [LICENSE](LICENSE) and the terms published at <https://zelvyn.devs.surf>.

---

<div align="center">
<sub>Generated from the live OpenAPI document. Do not edit the endpoint or language pages by hand — regenerate them when the contract changes.</sub>
</div>
