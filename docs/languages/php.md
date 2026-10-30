# PHP

Complete, copy-pasteable PHP requests for all 43 public Zelvyn API operations.

## Setup

```bash
export ZELVYN_API_KEY="zlv_live_..."   # create or receive a key first
```

Every calculation request sends the key as `Authorization: Bearer $ZELVYN_API_KEY`. The health probe is public, but the examples below keep the header so the same client works for every operation.

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

```php
<?php
$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/health");
curl_setopt_array($ch, [
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/get-health.md) · [All languages](README.md)

<a id="op-statisticsMax"></a>

## statisticsMax — Maximum value

`POST /api/v1/statistics/max`

```php
<?php
$payload = json_encode(["values" => [3, 1, 4, 1, 5]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/max");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-max.md) · [All languages](README.md)

<a id="op-statisticsMean"></a>

## statisticsMean — Arithmetic mean

`POST /api/v1/statistics/mean`

```php
<?php
$payload = json_encode(["values" => [10, 20, 30]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/mean");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-mean.md) · [All languages](README.md)

<a id="op-statisticsMedian"></a>

## statisticsMedian — Median

`POST /api/v1/statistics/median`

```php
<?php
$payload = json_encode(["values" => [1, 3, 2, 5, 4]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/median");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-median.md) · [All languages](README.md)

<a id="op-statisticsMin"></a>

## statisticsMin — Minimum value

`POST /api/v1/statistics/min`

```php
<?php
$payload = json_encode(["values" => [3, 1, 4, 1, 5]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/min");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-min.md) · [All languages](README.md)

<a id="op-statisticsPercentile"></a>

## statisticsPercentile — Percentile (linear interpolation)

`POST /api/v1/statistics/percentile`

```php
<?php
$payload = json_encode(["values" => [1, 2, 3, 4], "percentile" => 75]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/percentile");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-percentile.md) · [All languages](README.md)

<a id="op-statisticsRange"></a>

## statisticsRange — Range (max − min)

`POST /api/v1/statistics/range`

```php
<?php
$payload = json_encode(["values" => [3, 1, 4, 1, 5]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/range");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-range.md) · [All languages](README.md)

<a id="op-statisticsStandardDeviation"></a>

## statisticsStandardDeviation — Population standard deviation

`POST /api/v1/statistics/standard-deviation`

```php
<?php
$payload = json_encode(["values" => [2, 4, 4, 4, 5, 5, 7, 9]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/standard-deviation");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-standard-deviation.md) · [All languages](README.md)

<a id="op-statisticsSum"></a>

## statisticsSum — Sum of a dataset

`POST /api/v1/statistics/sum`

```php
<?php
$payload = json_encode(["values" => [10, 20, 30]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/sum");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-sum.md) · [All languages](README.md)

<a id="op-statisticsVariance"></a>

## statisticsVariance — Population variance

`POST /api/v1/statistics/variance`

```php
<?php
$payload = json_encode(["values" => [2, 4, 4, 4, 5, 5, 7, 9]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/statistics/variance");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/statistics-variance.md) · [All languages](README.md)

<a id="op-mathAdd"></a>

## mathAdd — Add numbers

`POST /api/v1/math/add`

```php
<?php
$payload = json_encode(["values" => [0.1, 0.2, 0.3]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/add");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-add.md) · [All languages](README.md)

<a id="op-mathCombinations"></a>

## mathCombinations — Combinations C(n, r)

`POST /api/v1/math/combinations`

```php
<?php
$payload = json_encode(["n" => 52, "r" => 5]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/combinations");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-combinations.md) · [All languages](README.md)

<a id="op-mathDivide"></a>

## mathDivide — Divide numbers (left to right)

`POST /api/v1/math/divide`

```php
<?php
$payload = json_encode(["values" => [100, 4, 5]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/divide");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-divide.md) · [All languages](README.md)

<a id="op-mathFactorial"></a>

## mathFactorial — Factorial

`POST /api/v1/math/factorial`

```php
<?php
$payload = json_encode(["n" => 5]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/factorial");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-factorial.md) · [All languages](README.md)

<a id="op-mathGcd"></a>

## mathGcd — Greatest common divisor

`POST /api/v1/math/gcd`

```php
<?php
$payload = json_encode(["a" => 12, "b" => 18]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/gcd");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-gcd.md) · [All languages](README.md)

<a id="op-mathLcm"></a>

## mathLcm — Least common multiple

`POST /api/v1/math/lcm`

```php
<?php
$payload = json_encode(["a" => 4, "b" => 6]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/lcm");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-lcm.md) · [All languages](README.md)

<a id="op-mathLn"></a>

## mathLn — Natural logarithm

`POST /api/v1/math/ln`

```php
<?php
$payload = json_encode(["value" => 1]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/ln");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-ln.md) · [All languages](README.md)

<a id="op-mathLog"></a>

## mathLog — Logarithm to a base (default 10)

`POST /api/v1/math/log`

```php
<?php
$payload = json_encode(["value" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/log");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-log.md) · [All languages](README.md)

<a id="op-mathMultiply"></a>

## mathMultiply — Multiply numbers

`POST /api/v1/math/multiply`

```php
<?php
$payload = json_encode(["values" => [2, 3, 4]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/multiply");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-multiply.md) · [All languages](README.md)

<a id="op-mathNthRoot"></a>

## mathNthRoot — N-th root

`POST /api/v1/math/nth-root`

```php
<?php
$payload = json_encode(["value" => 27, "degree" => 3]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/nth-root");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-nth-root.md) · [All languages](README.md)

<a id="op-mathPercentOf"></a>

## mathPercentOf — Percent of a value

`POST /api/v1/math/percent-of`

```php
<?php
$payload = json_encode(["percentage" => 15, "value" => 240]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/percent-of");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-percent-of.md) · [All languages](README.md)

<a id="op-mathPercentageChange"></a>

## mathPercentageChange — Percentage change between two values

`POST /api/v1/math/percentage-change`

```php
<?php
$payload = json_encode(["from" => 80, "to" => 100]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/percentage-change");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-percentage-change.md) · [All languages](README.md)

<a id="op-mathPermutations"></a>

## mathPermutations — Permutations P(n, r)

`POST /api/v1/math/permutations`

```php
<?php
$payload = json_encode(["n" => 5, "r" => 2]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/permutations");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-permutations.md) · [All languages](README.md)

<a id="op-mathPower"></a>

## mathPower — Raise a base to an exponent

`POST /api/v1/math/power`

```php
<?php
$payload = json_encode(["base" => 2, "exponent" => 10]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/power");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-power.md) · [All languages](README.md)

<a id="op-mathSqrt"></a>

## mathSqrt — Square root

`POST /api/v1/math/sqrt`

```php
<?php
$payload = json_encode(["value" => 144]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/sqrt");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-sqrt.md) · [All languages](README.md)

<a id="op-mathSubtract"></a>

## mathSubtract — Subtract numbers (left to right)

`POST /api/v1/math/subtract`

```php
<?php
$payload = json_encode(["values" => [10, 3, 4]]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/math/subtract");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/math-subtract.md) · [All languages](README.md)

<a id="op-businessAov"></a>

## businessAov — Average order value AOV

`POST /api/v1/business/aov`

```php
<?php
$payload = json_encode(["revenue" => 10000, "orders" => 200]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/aov");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-aov.md) · [All languages](README.md)

<a id="op-businessBreakEven"></a>

## businessBreakEven — Break-even volume (units)

`POST /api/v1/business/break-even`

```php
<?php
$payload = json_encode(["fixedCosts" => 1000, "price" => 20, "variableCost" => 12]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/break-even");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-break-even.md) · [All languages](README.md)

<a id="op-businessCac"></a>

## businessCac — Customer acquisition cost CAC

`POST /api/v1/business/cac`

```php
<?php
$payload = json_encode(["cost" => 5000, "customers" => 50]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/cac");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-cac.md) · [All languages](README.md)

<a id="op-businessCagr"></a>

## businessCagr — Compound annual growth rate CAGR (percent)

`POST /api/v1/business/cagr`

```php
<?php
$payload = json_encode(["beginValue" => 100, "endValue" => 121, "periods" => 2]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/cagr");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-cagr.md) · [All languages](README.md)

<a id="op-businessChurnRate"></a>

## businessChurnRate — Churn rate (percent)

`POST /api/v1/business/churn-rate`

```php
<?php
$payload = json_encode(["churned" => 100, "starting" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/churn-rate");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-churn-rate.md) · [All languages](README.md)

<a id="op-businessClv"></a>

## businessClv — Customer lifetime value CLV

`POST /api/v1/business/clv`

```php
<?php
$payload = json_encode(["averageOrderValue" => 50, "purchasesPerPeriod" => 12, "lifespanPeriods" => 3]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/clv");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-clv.md) · [All languages](README.md)

<a id="op-businessConversionRate"></a>

## businessConversionRate — Conversion rate (percent)

`POST /api/v1/business/conversion-rate`

```php
<?php
$payload = json_encode(["conversions" => 50, "sessions" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/conversion-rate");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-conversion-rate.md) · [All languages](README.md)

<a id="op-businessCpa"></a>

## businessCpa — Cost per acquisition CPA

`POST /api/v1/business/cpa`

```php
<?php
$payload = json_encode(["cost" => 500, "conversions" => 25]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/cpa");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-cpa.md) · [All languages](README.md)

<a id="op-businessCpc"></a>

## businessCpc — Cost per click CPC

`POST /api/v1/business/cpc`

```php
<?php
$payload = json_encode(["cost" => 250, "clicks" => 100]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/cpc");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-cpc.md) · [All languages](README.md)

<a id="op-businessCpm"></a>

## businessCpm — Cost per mille CPM

`POST /api/v1/business/cpm`

```php
<?php
$payload = json_encode(["cost" => 500, "impressions" => 100000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/cpm");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-cpm.md) · [All languages](README.md)

<a id="op-businessCtr"></a>

## businessCtr — Click-through rate CTR (percent)

`POST /api/v1/business/ctr`

```php
<?php
$payload = json_encode(["clicks" => 100, "impressions" => 10000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/ctr");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-ctr.md) · [All languages](README.md)

<a id="op-businessMarkup"></a>

## businessMarkup — Markup (percent)

`POST /api/v1/business/markup`

```php
<?php
$payload = json_encode(["price" => 120, "cost" => 100]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/markup");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-markup.md) · [All languages](README.md)

<a id="op-businessProfit"></a>

## businessProfit — Profit

`POST /api/v1/business/profit`

```php
<?php
$payload = json_encode(["revenue" => 1000, "costs" => 600]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/profit");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-profit.md) · [All languages](README.md)

<a id="op-businessProfitMargin"></a>

## businessProfitMargin — Profit margin (percent)

`POST /api/v1/business/profit-margin`

```php
<?php
$payload = json_encode(["revenue" => 1000, "costs" => 600]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/profit-margin");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-profit-margin.md) · [All languages](README.md)

<a id="op-businessRetentionRate"></a>

## businessRetentionRate — Retention rate (percent)

`POST /api/v1/business/retention-rate`

```php
<?php
$payload = json_encode(["retained" => 900, "starting" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/retention-rate");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-retention-rate.md) · [All languages](README.md)

<a id="op-businessRoas"></a>

## businessRoas — Return on ad spend ROAS (ratio)

`POST /api/v1/business/roas`

```php
<?php
$payload = json_encode(["revenue" => 4000, "adSpend" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/roas");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-roas.md) · [All languages](README.md)

<a id="op-businessRoi"></a>

## businessRoi — Return on investment ROI (percent)

`POST /api/v1/business/roi`

```php
<?php
$payload = json_encode(["profit" => 250, "investment" => 1000]);

$ch = curl_init("https://api-zelvyn.devs.surf/api/v1/business/roi");
curl_setopt_array($ch, [
    CURLOPT_POST => true,
    CURLOPT_POSTFIELDS => $payload,
    CURLOPT_HTTPHEADER => [
            "Authorization: Bearer " . getenv("ZELVYN_API_KEY"),
            "Content-Type: application/json",
        ],
        CURLOPT_RETURNTRANSFER => true,
]);

$result = json_decode(curl_exec($ch), true);
curl_close($ch);
```

[Endpoint reference](../endpoints/business-roi.md) · [All languages](README.md)

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
