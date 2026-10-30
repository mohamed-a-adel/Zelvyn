# Python

Complete, copy-pasteable Python requests for all 43 public Zelvyn API operations.

## Setup

No API key is needed for any request in this handbook. Every snippet is ready to run keyless on the anonymous rate limit.

If you have a Zelvyn API key, add it to the request for a higher plan limit:

```bash
export ZELVYN_API_KEY="zlv_live_..."
```

Send it as `Authorization: Bearer $ZELVYN_API_KEY` or `x-api-key: $ZELVYN_API_KEY`. Each snippet below includes the exact line to add, commented out. See [authentication](../authentication.md) and [contact support](https://zelvyn.devs.surf/support) to request a higher limit.

Base URL: `https://api-zelvyn.devs.surf`

## Contents

- [getHealth — Liveness / readiness probe](#op-getHealth)
- [statisticsMax — Maximum value](#op-statisticsMax)
- [statisticsMean — Arithmetic mean](#op-statisticsMean)
- [statisticsMedian — Median](#op-statisticsMedian)
- [statisticsMin — Minimum value](#op-statisticsMin)
- [statisticsPercentile — Percentile (linear interpolation)](#op-statisticsPercentile)
- [statisticsRange — Range (max − min)](#op-statisticsRange)
- [statisticsStandardDeviation — Population standard deviation](#op-statisticsStandardDeviation)
- [statisticsSum — Sum of a dataset](#op-statisticsSum)
- [statisticsVariance — Population variance](#op-statisticsVariance)
- [mathAdd — Add numbers](#op-mathAdd)
- [mathCombinations — Combinations C(n, r)](#op-mathCombinations)
- [mathDivide — Divide numbers (left to right)](#op-mathDivide)
- [mathFactorial — Factorial](#op-mathFactorial)
- [mathGcd — Greatest common divisor](#op-mathGcd)
- [mathLcm — Least common multiple](#op-mathLcm)
- [mathLn — Natural logarithm](#op-mathLn)
- [mathLog — Logarithm to a base (default 10)](#op-mathLog)
- [mathMultiply — Multiply numbers](#op-mathMultiply)
- [mathNthRoot — N-th root](#op-mathNthRoot)
- [mathPercentOf — Percent of a value](#op-mathPercentOf)
- [mathPercentageChange — Percentage change between two values](#op-mathPercentageChange)
- [mathPermutations — Permutations P(n, r)](#op-mathPermutations)
- [mathPower — Raise a base to an exponent](#op-mathPower)
- [mathSqrt — Square root](#op-mathSqrt)
- [mathSubtract — Subtract numbers (left to right)](#op-mathSubtract)
- [businessAov — Average order value AOV](#op-businessAov)
- [businessBreakEven — Break-even volume (units)](#op-businessBreakEven)
- [businessCac — Customer acquisition cost CAC](#op-businessCac)
- [businessCagr — Compound annual growth rate CAGR (percent)](#op-businessCagr)
- [businessChurnRate — Churn rate (percent)](#op-businessChurnRate)
- [businessClv — Customer lifetime value CLV](#op-businessClv)
- [businessConversionRate — Conversion rate (percent)](#op-businessConversionRate)
- [businessCpa — Cost per acquisition CPA](#op-businessCpa)
- [businessCpc — Cost per click CPC](#op-businessCpc)
- [businessCpm — Cost per mille CPM](#op-businessCpm)
- [businessCtr — Click-through rate CTR (percent)](#op-businessCtr)
- [businessMarkup — Markup (percent)](#op-businessMarkup)
- [businessProfit — Profit](#op-businessProfit)
- [businessProfitMargin — Profit margin (percent)](#op-businessProfitMargin)
- [businessRetentionRate — Retention rate (percent)](#op-businessRetentionRate)
- [businessRoas — Return on ad spend ROAS (ratio)](#op-businessRoas)
- [businessRoi — Return on investment ROI (percent)](#op-businessRoi)

---

<a id="op-getHealth"></a>

## getHealth — Liveness / readiness probe

`GET /api/v1/health`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "GET",
    "https://api-zelvyn.devs.surf/api/v1/health",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/get-health.md) · [All languages](README.md)

<a id="op-statisticsMax"></a>

## statisticsMax — Maximum value

`POST /api/v1/statistics/max`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/max",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[3,1,4,1,5]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-max.md) · [All languages](README.md)

<a id="op-statisticsMean"></a>

## statisticsMean — Arithmetic mean

`POST /api/v1/statistics/mean`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/mean",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[10,20,30]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-mean.md) · [All languages](README.md)

<a id="op-statisticsMedian"></a>

## statisticsMedian — Median

`POST /api/v1/statistics/median`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/median",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[1,3,2,5,4]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-median.md) · [All languages](README.md)

<a id="op-statisticsMin"></a>

## statisticsMin — Minimum value

`POST /api/v1/statistics/min`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/min",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[3,1,4,1,5]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-min.md) · [All languages](README.md)

<a id="op-statisticsPercentile"></a>

## statisticsPercentile — Percentile (linear interpolation)

`POST /api/v1/statistics/percentile`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/percentile",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[1,2,3,4],"percentile":75},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-percentile.md) · [All languages](README.md)

<a id="op-statisticsRange"></a>

## statisticsRange — Range (max − min)

`POST /api/v1/statistics/range`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/range",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[3,1,4,1,5]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-range.md) · [All languages](README.md)

<a id="op-statisticsStandardDeviation"></a>

## statisticsStandardDeviation — Population standard deviation

`POST /api/v1/statistics/standard-deviation`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/standard-deviation",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[2,4,4,4,5,5,7,9]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-standard-deviation.md) · [All languages](README.md)

<a id="op-statisticsSum"></a>

## statisticsSum — Sum of a dataset

`POST /api/v1/statistics/sum`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/sum",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[10,20,30]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-sum.md) · [All languages](README.md)

<a id="op-statisticsVariance"></a>

## statisticsVariance — Population variance

`POST /api/v1/statistics/variance`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/statistics/variance",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[2,4,4,4,5,5,7,9]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/statistics-variance.md) · [All languages](README.md)

<a id="op-mathAdd"></a>

## mathAdd — Add numbers

`POST /api/v1/math/add`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/add",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[0.1,0.2,0.3]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-add.md) · [All languages](README.md)

<a id="op-mathCombinations"></a>

## mathCombinations — Combinations C(n, r)

`POST /api/v1/math/combinations`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/combinations",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"n":52,"r":5},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-combinations.md) · [All languages](README.md)

<a id="op-mathDivide"></a>

## mathDivide — Divide numbers (left to right)

`POST /api/v1/math/divide`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/divide",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[100,4,5]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-divide.md) · [All languages](README.md)

<a id="op-mathFactorial"></a>

## mathFactorial — Factorial

`POST /api/v1/math/factorial`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/factorial",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"n":5},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-factorial.md) · [All languages](README.md)

<a id="op-mathGcd"></a>

## mathGcd — Greatest common divisor

`POST /api/v1/math/gcd`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/gcd",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"a":12,"b":18},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-gcd.md) · [All languages](README.md)

<a id="op-mathLcm"></a>

## mathLcm — Least common multiple

`POST /api/v1/math/lcm`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/lcm",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"a":4,"b":6},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-lcm.md) · [All languages](README.md)

<a id="op-mathLn"></a>

## mathLn — Natural logarithm

`POST /api/v1/math/ln`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/ln",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"value":1},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-ln.md) · [All languages](README.md)

<a id="op-mathLog"></a>

## mathLog — Logarithm to a base (default 10)

`POST /api/v1/math/log`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/log",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"value":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-log.md) · [All languages](README.md)

<a id="op-mathMultiply"></a>

## mathMultiply — Multiply numbers

`POST /api/v1/math/multiply`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/multiply",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[2,3,4]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-multiply.md) · [All languages](README.md)

<a id="op-mathNthRoot"></a>

## mathNthRoot — N-th root

`POST /api/v1/math/nth-root`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/nth-root",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"value":27,"degree":3},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-nth-root.md) · [All languages](README.md)

<a id="op-mathPercentOf"></a>

## mathPercentOf — Percent of a value

`POST /api/v1/math/percent-of`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/percent-of",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"percentage":15,"value":240},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-percent-of.md) · [All languages](README.md)

<a id="op-mathPercentageChange"></a>

## mathPercentageChange — Percentage change between two values

`POST /api/v1/math/percentage-change`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/percentage-change",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"from":80,"to":100},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-percentage-change.md) · [All languages](README.md)

<a id="op-mathPermutations"></a>

## mathPermutations — Permutations P(n, r)

`POST /api/v1/math/permutations`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/permutations",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"n":5,"r":2},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-permutations.md) · [All languages](README.md)

<a id="op-mathPower"></a>

## mathPower — Raise a base to an exponent

`POST /api/v1/math/power`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/power",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"base":2,"exponent":10},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-power.md) · [All languages](README.md)

<a id="op-mathSqrt"></a>

## mathSqrt — Square root

`POST /api/v1/math/sqrt`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/sqrt",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"value":144},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-sqrt.md) · [All languages](README.md)

<a id="op-mathSubtract"></a>

## mathSubtract — Subtract numbers (left to right)

`POST /api/v1/math/subtract`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/math/subtract",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"values":[10,3,4]},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/math-subtract.md) · [All languages](README.md)

<a id="op-businessAov"></a>

## businessAov — Average order value AOV

`POST /api/v1/business/aov`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/aov",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"revenue":10000,"orders":200},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-aov.md) · [All languages](README.md)

<a id="op-businessBreakEven"></a>

## businessBreakEven — Break-even volume (units)

`POST /api/v1/business/break-even`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/break-even",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"fixedCosts":1000,"price":20,"variableCost":12},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-break-even.md) · [All languages](README.md)

<a id="op-businessCac"></a>

## businessCac — Customer acquisition cost CAC

`POST /api/v1/business/cac`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/cac",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"cost":5000,"customers":50},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-cac.md) · [All languages](README.md)

<a id="op-businessCagr"></a>

## businessCagr — Compound annual growth rate CAGR (percent)

`POST /api/v1/business/cagr`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/cagr",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"beginValue":100,"endValue":121,"periods":2},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-cagr.md) · [All languages](README.md)

<a id="op-businessChurnRate"></a>

## businessChurnRate — Churn rate (percent)

`POST /api/v1/business/churn-rate`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/churn-rate",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"churned":100,"starting":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-churn-rate.md) · [All languages](README.md)

<a id="op-businessClv"></a>

## businessClv — Customer lifetime value CLV

`POST /api/v1/business/clv`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/clv",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"averageOrderValue":50,"purchasesPerPeriod":12,"lifespanPeriods":3},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-clv.md) · [All languages](README.md)

<a id="op-businessConversionRate"></a>

## businessConversionRate — Conversion rate (percent)

`POST /api/v1/business/conversion-rate`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/conversion-rate",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"conversions":50,"sessions":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-conversion-rate.md) · [All languages](README.md)

<a id="op-businessCpa"></a>

## businessCpa — Cost per acquisition CPA

`POST /api/v1/business/cpa`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/cpa",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"cost":500,"conversions":25},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-cpa.md) · [All languages](README.md)

<a id="op-businessCpc"></a>

## businessCpc — Cost per click CPC

`POST /api/v1/business/cpc`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/cpc",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"cost":250,"clicks":100},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-cpc.md) · [All languages](README.md)

<a id="op-businessCpm"></a>

## businessCpm — Cost per mille CPM

`POST /api/v1/business/cpm`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/cpm",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"cost":500,"impressions":100000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-cpm.md) · [All languages](README.md)

<a id="op-businessCtr"></a>

## businessCtr — Click-through rate CTR (percent)

`POST /api/v1/business/ctr`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/ctr",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"clicks":100,"impressions":10000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-ctr.md) · [All languages](README.md)

<a id="op-businessMarkup"></a>

## businessMarkup — Markup (percent)

`POST /api/v1/business/markup`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/markup",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"price":120,"cost":100},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-markup.md) · [All languages](README.md)

<a id="op-businessProfit"></a>

## businessProfit — Profit

`POST /api/v1/business/profit`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/profit",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"revenue":1000,"costs":600},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-profit.md) · [All languages](README.md)

<a id="op-businessProfitMargin"></a>

## businessProfitMargin — Profit margin (percent)

`POST /api/v1/business/profit-margin`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/profit-margin",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"revenue":1000,"costs":600},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-profit-margin.md) · [All languages](README.md)

<a id="op-businessRetentionRate"></a>

## businessRetentionRate — Retention rate (percent)

`POST /api/v1/business/retention-rate`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/retention-rate",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"retained":900,"starting":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-retention-rate.md) · [All languages](README.md)

<a id="op-businessRoas"></a>

## businessRoas — Return on ad spend ROAS (ratio)

`POST /api/v1/business/roas`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/roas",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"revenue":4000,"adSpend":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-roas.md) · [All languages](README.md)

<a id="op-businessRoi"></a>

## businessRoi — Return on investment ROI (percent)

`POST /api/v1/business/roi`

```python
import os  # Optional: only needed for the commented API-key header
import requests

response = requests.request(
    "POST",
    "https://api-zelvyn.devs.surf/api/v1/business/roi",
    headers={
        "Content-Type": "application/json",
        # Optional: add this line if you have a key (higher rate limit).
        # "Authorization": f"Bearer {os.environ['ZELVYN_API_KEY']}",
    },
    json={"profit":250,"investment":1000},
)
data = response.json()["data"]
```

[Endpoint reference](../endpoints/business-roi.md) · [All languages](README.md)

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
