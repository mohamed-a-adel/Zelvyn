# Zelvyn API — public handbook

[![API](https://i.postimg.cc/rFQymy4T/zelvyn.png)](https://api-zelvyn.devs.surf)
[![OpenAPI](https://img.shields.io/badge/OpenAPI-3.1-blue)](https://api-zelvyn.devs.surf/openapi.json)

The **Zelvyn API** is a stateless calculation and analytics platform for mathematics, statistics and business metrics. Every request is a JSON object; every response uses one envelope with a `meta.requestId` correlation id. Calculations are never persisted.

- Hosted documentation: <https://zelvyn.devs.surf/docs>
- Public API: <https://api-zelvyn.devs.surf>
- OpenAPI 3.1 document: <https://api-zelvyn.devs.surf/openapi.json>
- Public website: <https://zelvyn.devs.surf>

## Authentication

The health probe is public. **Every calculation endpoint requires an API key** unless an operator explicitly opens that endpoint for anonymous access.

```bash
export ZELVYN_API_KEY="zlv_live_..."
curl -sS https://api-zelvyn.devs.surf/api/v1/statistics/mean \
  -H "Authorization: Bearer $ZELVYN_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{"values":[10,20,30]}'
```

Send the key as `Authorization: Bearer <key>`, or as `x-api-key: <key>`. If both are present, `Authorization` wins. Keys are issued for a `LIVE` or `TEST` environment and a plan.

> This repository documents the public calculation API. Account/session endpoints (`/api/v1/account/*`) are cookie- and CSRF-authenticated, are excluded from the public OpenAPI document, and are not needed to call any endpoint in this handbook. Ask the Zelvyn operator for a key if you do not have one.

## All 43 requests

| Operation | Method | Path |
| --- | --- | --- |
| **Health** | | |
| [Liveness / readiness probe](docs/endpoints/get-health.md) | `GET` | `/api/v1/health` |
| **Statistics** | | |
| [Maximum value](docs/endpoints/statistics-max.md) | `POST` | `/api/v1/statistics/max` |
| [Arithmetic mean](docs/endpoints/statistics-mean.md) | `POST` | `/api/v1/statistics/mean` |
| [Median](docs/endpoints/statistics-median.md) | `POST` | `/api/v1/statistics/median` |
| [Minimum value](docs/endpoints/statistics-min.md) | `POST` | `/api/v1/statistics/min` |
| [Percentile (linear interpolation)](docs/endpoints/statistics-percentile.md) | `POST` | `/api/v1/statistics/percentile` |
| [Range (max − min)](docs/endpoints/statistics-range.md) | `POST` | `/api/v1/statistics/range` |
| [Population standard deviation](docs/endpoints/statistics-standard-deviation.md) | `POST` | `/api/v1/statistics/standard-deviation` |
| [Sum of a dataset](docs/endpoints/statistics-sum.md) | `POST` | `/api/v1/statistics/sum` |
| [Population variance](docs/endpoints/statistics-variance.md) | `POST` | `/api/v1/statistics/variance` |
| **Math** | | |
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
| **Business Analytics** | | |
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

Every request is documented in all of these languages. Each language page contains all 43 operations in one place.

| Language | Runtime | Complete examples |
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

Failures replace `data` with `error`:

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

## Documentation

- [Endpoint index](docs/endpoints/README.md)
- [Authentication](docs/authentication.md)
- [Errors](docs/errors.md)
- [Rate limits and quotas](docs/rate-limits.md)
- [Versioning and compatibility](docs/versioning.md)
- [Language index](docs/languages/README.md)
- [OpenAPI JSON](openapi.json) (live: https://api-zelvyn.devs.surf/openapi.json)

## Conventions

- Request bodies are strictly validated. Unknown fields are rejected (`additionalProperties: false`).
- Percentage metrics return **percent points** (`40` means 40%). `roas` is a plain ratio (`4` means 4×).
- Percentages never carry a `%` sign and are never fractions.
- Exact integer results beyond `Number.MAX_SAFE_INTEGER` are returned as decimal strings, never rounded.
- Every error is a JSON envelope. API paths never return an HTML error page.
- `x-request-id` is echoed in `meta.requestId` when valid; otherwise the server generates a UUID v4.

## License

Proprietary. See the terms published at <https://zelvyn.devs.surf>.

---

Generated from the live OpenAPI document. Do not edit the endpoint or language pages by hand — regenerate them when the contract changes.
