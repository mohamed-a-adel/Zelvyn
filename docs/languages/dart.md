# Dart

Complete, copy-pasteable Dart requests for all 43 public Zelvyn API operations.

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

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.get(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/health'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/get-health.md) · [All languages](README.md)

<a id="op-statisticsMax"></a>

## statisticsMax — Maximum value

`POST /api/v1/statistics/max`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/max'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[3,1,4,1,5]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-max.md) · [All languages](README.md)

<a id="op-statisticsMean"></a>

## statisticsMean — Arithmetic mean

`POST /api/v1/statistics/mean`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/mean'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[10,20,30]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-mean.md) · [All languages](README.md)

<a id="op-statisticsMedian"></a>

## statisticsMedian — Median

`POST /api/v1/statistics/median`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/median'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[1,3,2,5,4]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-median.md) · [All languages](README.md)

<a id="op-statisticsMin"></a>

## statisticsMin — Minimum value

`POST /api/v1/statistics/min`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/min'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[3,1,4,1,5]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-min.md) · [All languages](README.md)

<a id="op-statisticsPercentile"></a>

## statisticsPercentile — Percentile (linear interpolation)

`POST /api/v1/statistics/percentile`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/percentile'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[1,2,3,4],"percentile":75}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-percentile.md) · [All languages](README.md)

<a id="op-statisticsRange"></a>

## statisticsRange — Range (max − min)

`POST /api/v1/statistics/range`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/range'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[3,1,4,1,5]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-range.md) · [All languages](README.md)

<a id="op-statisticsStandardDeviation"></a>

## statisticsStandardDeviation — Population standard deviation

`POST /api/v1/statistics/standard-deviation`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/standard-deviation'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[2,4,4,4,5,5,7,9]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-standard-deviation.md) · [All languages](README.md)

<a id="op-statisticsSum"></a>

## statisticsSum — Sum of a dataset

`POST /api/v1/statistics/sum`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/sum'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[10,20,30]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-sum.md) · [All languages](README.md)

<a id="op-statisticsVariance"></a>

## statisticsVariance — Population variance

`POST /api/v1/statistics/variance`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/statistics/variance'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[2,4,4,4,5,5,7,9]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/statistics-variance.md) · [All languages](README.md)

<a id="op-mathAdd"></a>

## mathAdd — Add numbers

`POST /api/v1/math/add`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/add'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[0.1,0.2,0.3]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-add.md) · [All languages](README.md)

<a id="op-mathCombinations"></a>

## mathCombinations — Combinations C(n, r)

`POST /api/v1/math/combinations`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/combinations'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"n":52,"r":5}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-combinations.md) · [All languages](README.md)

<a id="op-mathDivide"></a>

## mathDivide — Divide numbers (left to right)

`POST /api/v1/math/divide`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/divide'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[100,4,5]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-divide.md) · [All languages](README.md)

<a id="op-mathFactorial"></a>

## mathFactorial — Factorial

`POST /api/v1/math/factorial`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/factorial'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"n":5}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-factorial.md) · [All languages](README.md)

<a id="op-mathGcd"></a>

## mathGcd — Greatest common divisor

`POST /api/v1/math/gcd`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/gcd'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"a":12,"b":18}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-gcd.md) · [All languages](README.md)

<a id="op-mathLcm"></a>

## mathLcm — Least common multiple

`POST /api/v1/math/lcm`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/lcm'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"a":4,"b":6}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-lcm.md) · [All languages](README.md)

<a id="op-mathLn"></a>

## mathLn — Natural logarithm

`POST /api/v1/math/ln`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/ln'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"value":1}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-ln.md) · [All languages](README.md)

<a id="op-mathLog"></a>

## mathLog — Logarithm to a base (default 10)

`POST /api/v1/math/log`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/log'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"value":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-log.md) · [All languages](README.md)

<a id="op-mathMultiply"></a>

## mathMultiply — Multiply numbers

`POST /api/v1/math/multiply`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/multiply'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[2,3,4]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-multiply.md) · [All languages](README.md)

<a id="op-mathNthRoot"></a>

## mathNthRoot — N-th root

`POST /api/v1/math/nth-root`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/nth-root'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"value":27,"degree":3}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-nth-root.md) · [All languages](README.md)

<a id="op-mathPercentOf"></a>

## mathPercentOf — Percent of a value

`POST /api/v1/math/percent-of`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/percent-of'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"percentage":15,"value":240}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-percent-of.md) · [All languages](README.md)

<a id="op-mathPercentageChange"></a>

## mathPercentageChange — Percentage change between two values

`POST /api/v1/math/percentage-change`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/percentage-change'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"from":80,"to":100}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-percentage-change.md) · [All languages](README.md)

<a id="op-mathPermutations"></a>

## mathPermutations — Permutations P(n, r)

`POST /api/v1/math/permutations`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/permutations'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"n":5,"r":2}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-permutations.md) · [All languages](README.md)

<a id="op-mathPower"></a>

## mathPower — Raise a base to an exponent

`POST /api/v1/math/power`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/power'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"base":2,"exponent":10}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-power.md) · [All languages](README.md)

<a id="op-mathSqrt"></a>

## mathSqrt — Square root

`POST /api/v1/math/sqrt`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/sqrt'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"value":144}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-sqrt.md) · [All languages](README.md)

<a id="op-mathSubtract"></a>

## mathSubtract — Subtract numbers (left to right)

`POST /api/v1/math/subtract`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/math/subtract'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"values":[10,3,4]}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/math-subtract.md) · [All languages](README.md)

<a id="op-businessAov"></a>

## businessAov — Average order value AOV

`POST /api/v1/business/aov`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/aov'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"revenue":10000,"orders":200}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-aov.md) · [All languages](README.md)

<a id="op-businessBreakEven"></a>

## businessBreakEven — Break-even volume (units)

`POST /api/v1/business/break-even`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/break-even'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"fixedCosts":1000,"price":20,"variableCost":12}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-break-even.md) · [All languages](README.md)

<a id="op-businessCac"></a>

## businessCac — Customer acquisition cost CAC

`POST /api/v1/business/cac`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/cac'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"cost":5000,"customers":50}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-cac.md) · [All languages](README.md)

<a id="op-businessCagr"></a>

## businessCagr — Compound annual growth rate CAGR (percent)

`POST /api/v1/business/cagr`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/cagr'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"beginValue":100,"endValue":121,"periods":2}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-cagr.md) · [All languages](README.md)

<a id="op-businessChurnRate"></a>

## businessChurnRate — Churn rate (percent)

`POST /api/v1/business/churn-rate`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/churn-rate'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"churned":100,"starting":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-churn-rate.md) · [All languages](README.md)

<a id="op-businessClv"></a>

## businessClv — Customer lifetime value CLV

`POST /api/v1/business/clv`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/clv'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"averageOrderValue":50,"purchasesPerPeriod":12,"lifespanPeriods":3}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-clv.md) · [All languages](README.md)

<a id="op-businessConversionRate"></a>

## businessConversionRate — Conversion rate (percent)

`POST /api/v1/business/conversion-rate`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/conversion-rate'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"conversions":50,"sessions":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-conversion-rate.md) · [All languages](README.md)

<a id="op-businessCpa"></a>

## businessCpa — Cost per acquisition CPA

`POST /api/v1/business/cpa`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/cpa'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"cost":500,"conversions":25}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-cpa.md) · [All languages](README.md)

<a id="op-businessCpc"></a>

## businessCpc — Cost per click CPC

`POST /api/v1/business/cpc`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/cpc'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"cost":250,"clicks":100}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-cpc.md) · [All languages](README.md)

<a id="op-businessCpm"></a>

## businessCpm — Cost per mille CPM

`POST /api/v1/business/cpm`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/cpm'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"cost":500,"impressions":100000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-cpm.md) · [All languages](README.md)

<a id="op-businessCtr"></a>

## businessCtr — Click-through rate CTR (percent)

`POST /api/v1/business/ctr`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/ctr'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"clicks":100,"impressions":10000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-ctr.md) · [All languages](README.md)

<a id="op-businessMarkup"></a>

## businessMarkup — Markup (percent)

`POST /api/v1/business/markup`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/markup'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"price":120,"cost":100}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-markup.md) · [All languages](README.md)

<a id="op-businessProfit"></a>

## businessProfit — Profit

`POST /api/v1/business/profit`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/profit'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"revenue":1000,"costs":600}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-profit.md) · [All languages](README.md)

<a id="op-businessProfitMargin"></a>

## businessProfitMargin — Profit margin (percent)

`POST /api/v1/business/profit-margin`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/profit-margin'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"revenue":1000,"costs":600}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-profit-margin.md) · [All languages](README.md)

<a id="op-businessRetentionRate"></a>

## businessRetentionRate — Retention rate (percent)

`POST /api/v1/business/retention-rate`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/retention-rate'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"retained":900,"starting":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-retention-rate.md) · [All languages](README.md)

<a id="op-businessRoas"></a>

## businessRoas — Return on ad spend ROAS (ratio)

`POST /api/v1/business/roas`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/roas'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"revenue":4000,"adSpend":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-roas.md) · [All languages](README.md)

<a id="op-businessRoi"></a>

## businessRoi — Return on investment ROI (percent)

`POST /api/v1/business/roi`

```dart
import 'dart:convert';
import 'dart:io';
import 'package:http/http.dart' as http;

Future<void> main() async {
  final response = await http.post(
    Uri.parse('https://api-zelvyn.devs.surf/api/v1/business/roi'),
    headers: {
      'Authorization': 'Bearer ${Platform.environment['ZELVYN_API_KEY']}',
      'Content-Type': 'application/json',
    },
    body: jsonEncode({"profit":250,"investment":1000}),
  );
  print(response.body);
}
```

[Endpoint reference](../endpoints/business-roi.md) · [All languages](README.md)

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
