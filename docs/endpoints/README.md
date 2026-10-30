# Endpoint index

All 43 public operations, grouped by their OpenAPI tag. Every link opens a request reference with the schema, example body, example response, cURL, and links to all 13 languages.

| Operation | Method | Path |
| --- | --- | --- |
| **Health** | | |
| [Liveness / readiness probe](get-health.md) | `GET` | `/api/v1/health` |
| **Statistics** | | |
| [Maximum value](statistics-max.md) | `POST` | `/api/v1/statistics/max` |
| [Arithmetic mean](statistics-mean.md) | `POST` | `/api/v1/statistics/mean` |
| [Median](statistics-median.md) | `POST` | `/api/v1/statistics/median` |
| [Minimum value](statistics-min.md) | `POST` | `/api/v1/statistics/min` |
| [Percentile (linear interpolation)](statistics-percentile.md) | `POST` | `/api/v1/statistics/percentile` |
| [Range (max − min)](statistics-range.md) | `POST` | `/api/v1/statistics/range` |
| [Population standard deviation](statistics-standard-deviation.md) | `POST` | `/api/v1/statistics/standard-deviation` |
| [Sum of a dataset](statistics-sum.md) | `POST` | `/api/v1/statistics/sum` |
| [Population variance](statistics-variance.md) | `POST` | `/api/v1/statistics/variance` |
| **Math** | | |
| [Add numbers](math-add.md) | `POST` | `/api/v1/math/add` |
| [Combinations C(n, r)](math-combinations.md) | `POST` | `/api/v1/math/combinations` |
| [Divide numbers (left to right)](math-divide.md) | `POST` | `/api/v1/math/divide` |
| [Factorial](math-factorial.md) | `POST` | `/api/v1/math/factorial` |
| [Greatest common divisor](math-gcd.md) | `POST` | `/api/v1/math/gcd` |
| [Least common multiple](math-lcm.md) | `POST` | `/api/v1/math/lcm` |
| [Natural logarithm](math-ln.md) | `POST` | `/api/v1/math/ln` |
| [Logarithm to a base (default 10)](math-log.md) | `POST` | `/api/v1/math/log` |
| [Multiply numbers](math-multiply.md) | `POST` | `/api/v1/math/multiply` |
| [N-th root](math-nth-root.md) | `POST` | `/api/v1/math/nth-root` |
| [Percent of a value](math-percent-of.md) | `POST` | `/api/v1/math/percent-of` |
| [Percentage change between two values](math-percentage-change.md) | `POST` | `/api/v1/math/percentage-change` |
| [Permutations P(n, r)](math-permutations.md) | `POST` | `/api/v1/math/permutations` |
| [Raise a base to an exponent](math-power.md) | `POST` | `/api/v1/math/power` |
| [Square root](math-sqrt.md) | `POST` | `/api/v1/math/sqrt` |
| [Subtract numbers (left to right)](math-subtract.md) | `POST` | `/api/v1/math/subtract` |
| **Business Analytics** | | |
| [Average order value AOV](business-aov.md) | `POST` | `/api/v1/business/aov` |
| [Break-even volume (units)](business-break-even.md) | `POST` | `/api/v1/business/break-even` |
| [Customer acquisition cost CAC](business-cac.md) | `POST` | `/api/v1/business/cac` |
| [Compound annual growth rate CAGR (percent)](business-cagr.md) | `POST` | `/api/v1/business/cagr` |
| [Churn rate (percent)](business-churn-rate.md) | `POST` | `/api/v1/business/churn-rate` |
| [Customer lifetime value CLV](business-clv.md) | `POST` | `/api/v1/business/clv` |
| [Conversion rate (percent)](business-conversion-rate.md) | `POST` | `/api/v1/business/conversion-rate` |
| [Cost per acquisition CPA](business-cpa.md) | `POST` | `/api/v1/business/cpa` |
| [Cost per click CPC](business-cpc.md) | `POST` | `/api/v1/business/cpc` |
| [Cost per mille CPM](business-cpm.md) | `POST` | `/api/v1/business/cpm` |
| [Click-through rate CTR (percent)](business-ctr.md) | `POST` | `/api/v1/business/ctr` |
| [Markup (percent)](business-markup.md) | `POST` | `/api/v1/business/markup` |
| [Profit](business-profit.md) | `POST` | `/api/v1/business/profit` |
| [Profit margin (percent)](business-profit-margin.md) | `POST` | `/api/v1/business/profit-margin` |
| [Retention rate (percent)](business-retention-rate.md) | `POST` | `/api/v1/business/retention-rate` |
| [Return on ad spend ROAS (ratio)](business-roas.md) | `POST` | `/api/v1/business/roas` |
| [Return on investment ROI (percent)](business-roi.md) | `POST` | `/api/v1/business/roi` |

---

- [Authentication](../authentication.md)
- [Errors](../errors.md)
- [Rate limits](../rate-limits.md)
- [Language index](../languages/README.md)
- [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
