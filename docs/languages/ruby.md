# Ruby

Complete, copy-pasteable Ruby requests for all 43 public Zelvyn API operations.

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

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/health")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Get.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/get-health.md) · [All languages](README.md)

<a id="op-statisticsMax"></a>

## statisticsMax — Maximum value

`POST /api/v1/statistics/max`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/max")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [3, 1, 4, 1, 5] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-max.md) · [All languages](README.md)

<a id="op-statisticsMean"></a>

## statisticsMean — Arithmetic mean

`POST /api/v1/statistics/mean`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/mean")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [10, 20, 30] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-mean.md) · [All languages](README.md)

<a id="op-statisticsMedian"></a>

## statisticsMedian — Median

`POST /api/v1/statistics/median`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/median")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [1, 3, 2, 5, 4] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-median.md) · [All languages](README.md)

<a id="op-statisticsMin"></a>

## statisticsMin — Minimum value

`POST /api/v1/statistics/min`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/min")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [3, 1, 4, 1, 5] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-min.md) · [All languages](README.md)

<a id="op-statisticsPercentile"></a>

## statisticsPercentile — Percentile (linear interpolation)

`POST /api/v1/statistics/percentile`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/percentile")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [1, 2, 3, 4], percentile: 75 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-percentile.md) · [All languages](README.md)

<a id="op-statisticsRange"></a>

## statisticsRange — Range (max − min)

`POST /api/v1/statistics/range`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/range")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [3, 1, 4, 1, 5] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-range.md) · [All languages](README.md)

<a id="op-statisticsStandardDeviation"></a>

## statisticsStandardDeviation — Population standard deviation

`POST /api/v1/statistics/standard-deviation`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/standard-deviation")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [2, 4, 4, 4, 5, 5, 7, 9] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-standard-deviation.md) · [All languages](README.md)

<a id="op-statisticsSum"></a>

## statisticsSum — Sum of a dataset

`POST /api/v1/statistics/sum`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/sum")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [10, 20, 30] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-sum.md) · [All languages](README.md)

<a id="op-statisticsVariance"></a>

## statisticsVariance — Population variance

`POST /api/v1/statistics/variance`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/statistics/variance")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [2, 4, 4, 4, 5, 5, 7, 9] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/statistics-variance.md) · [All languages](README.md)

<a id="op-mathAdd"></a>

## mathAdd — Add numbers

`POST /api/v1/math/add`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/add")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [0.1, 0.2, 0.3] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-add.md) · [All languages](README.md)

<a id="op-mathCombinations"></a>

## mathCombinations — Combinations C(n, r)

`POST /api/v1/math/combinations`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/combinations")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { n: 52, r: 5 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-combinations.md) · [All languages](README.md)

<a id="op-mathDivide"></a>

## mathDivide — Divide numbers (left to right)

`POST /api/v1/math/divide`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/divide")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [100, 4, 5] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-divide.md) · [All languages](README.md)

<a id="op-mathFactorial"></a>

## mathFactorial — Factorial

`POST /api/v1/math/factorial`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/factorial")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { n: 5 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-factorial.md) · [All languages](README.md)

<a id="op-mathGcd"></a>

## mathGcd — Greatest common divisor

`POST /api/v1/math/gcd`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/gcd")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { a: 12, b: 18 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-gcd.md) · [All languages](README.md)

<a id="op-mathLcm"></a>

## mathLcm — Least common multiple

`POST /api/v1/math/lcm`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/lcm")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { a: 4, b: 6 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-lcm.md) · [All languages](README.md)

<a id="op-mathLn"></a>

## mathLn — Natural logarithm

`POST /api/v1/math/ln`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/ln")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { value: 1 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-ln.md) · [All languages](README.md)

<a id="op-mathLog"></a>

## mathLog — Logarithm to a base (default 10)

`POST /api/v1/math/log`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/log")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { value: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-log.md) · [All languages](README.md)

<a id="op-mathMultiply"></a>

## mathMultiply — Multiply numbers

`POST /api/v1/math/multiply`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/multiply")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [2, 3, 4] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-multiply.md) · [All languages](README.md)

<a id="op-mathNthRoot"></a>

## mathNthRoot — N-th root

`POST /api/v1/math/nth-root`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/nth-root")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { value: 27, degree: 3 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-nth-root.md) · [All languages](README.md)

<a id="op-mathPercentOf"></a>

## mathPercentOf — Percent of a value

`POST /api/v1/math/percent-of`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/percent-of")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { percentage: 15, value: 240 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-percent-of.md) · [All languages](README.md)

<a id="op-mathPercentageChange"></a>

## mathPercentageChange — Percentage change between two values

`POST /api/v1/math/percentage-change`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/percentage-change")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { from: 80, to: 100 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-percentage-change.md) · [All languages](README.md)

<a id="op-mathPermutations"></a>

## mathPermutations — Permutations P(n, r)

`POST /api/v1/math/permutations`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/permutations")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { n: 5, r: 2 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-permutations.md) · [All languages](README.md)

<a id="op-mathPower"></a>

## mathPower — Raise a base to an exponent

`POST /api/v1/math/power`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/power")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { base: 2, exponent: 10 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-power.md) · [All languages](README.md)

<a id="op-mathSqrt"></a>

## mathSqrt — Square root

`POST /api/v1/math/sqrt`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/sqrt")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { value: 144 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-sqrt.md) · [All languages](README.md)

<a id="op-mathSubtract"></a>

## mathSubtract — Subtract numbers (left to right)

`POST /api/v1/math/subtract`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/math/subtract")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { values: [10, 3, 4] }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/math-subtract.md) · [All languages](README.md)

<a id="op-businessAov"></a>

## businessAov — Average order value AOV

`POST /api/v1/business/aov`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/aov")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { revenue: 10000, orders: 200 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-aov.md) · [All languages](README.md)

<a id="op-businessBreakEven"></a>

## businessBreakEven — Break-even volume (units)

`POST /api/v1/business/break-even`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/break-even")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { fixedCosts: 1000, price: 20, variableCost: 12 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-break-even.md) · [All languages](README.md)

<a id="op-businessCac"></a>

## businessCac — Customer acquisition cost CAC

`POST /api/v1/business/cac`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/cac")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { cost: 5000, customers: 50 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-cac.md) · [All languages](README.md)

<a id="op-businessCagr"></a>

## businessCagr — Compound annual growth rate CAGR (percent)

`POST /api/v1/business/cagr`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/cagr")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { beginValue: 100, endValue: 121, periods: 2 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-cagr.md) · [All languages](README.md)

<a id="op-businessChurnRate"></a>

## businessChurnRate — Churn rate (percent)

`POST /api/v1/business/churn-rate`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/churn-rate")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { churned: 100, starting: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-churn-rate.md) · [All languages](README.md)

<a id="op-businessClv"></a>

## businessClv — Customer lifetime value CLV

`POST /api/v1/business/clv`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/clv")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { averageOrderValue: 50, purchasesPerPeriod: 12, lifespanPeriods: 3 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-clv.md) · [All languages](README.md)

<a id="op-businessConversionRate"></a>

## businessConversionRate — Conversion rate (percent)

`POST /api/v1/business/conversion-rate`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/conversion-rate")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { conversions: 50, sessions: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-conversion-rate.md) · [All languages](README.md)

<a id="op-businessCpa"></a>

## businessCpa — Cost per acquisition CPA

`POST /api/v1/business/cpa`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/cpa")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { cost: 500, conversions: 25 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-cpa.md) · [All languages](README.md)

<a id="op-businessCpc"></a>

## businessCpc — Cost per click CPC

`POST /api/v1/business/cpc`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/cpc")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { cost: 250, clicks: 100 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-cpc.md) · [All languages](README.md)

<a id="op-businessCpm"></a>

## businessCpm — Cost per mille CPM

`POST /api/v1/business/cpm`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/cpm")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { cost: 500, impressions: 100000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-cpm.md) · [All languages](README.md)

<a id="op-businessCtr"></a>

## businessCtr — Click-through rate CTR (percent)

`POST /api/v1/business/ctr`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/ctr")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { clicks: 100, impressions: 10000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-ctr.md) · [All languages](README.md)

<a id="op-businessMarkup"></a>

## businessMarkup — Markup (percent)

`POST /api/v1/business/markup`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/markup")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { price: 120, cost: 100 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-markup.md) · [All languages](README.md)

<a id="op-businessProfit"></a>

## businessProfit — Profit

`POST /api/v1/business/profit`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/profit")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { revenue: 1000, costs: 600 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-profit.md) · [All languages](README.md)

<a id="op-businessProfitMargin"></a>

## businessProfitMargin — Profit margin (percent)

`POST /api/v1/business/profit-margin`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/profit-margin")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { revenue: 1000, costs: 600 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-profit-margin.md) · [All languages](README.md)

<a id="op-businessRetentionRate"></a>

## businessRetentionRate — Retention rate (percent)

`POST /api/v1/business/retention-rate`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/retention-rate")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { retained: 900, starting: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-retention-rate.md) · [All languages](README.md)

<a id="op-businessRoas"></a>

## businessRoas — Return on ad spend ROAS (ratio)

`POST /api/v1/business/roas`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/roas")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { revenue: 4000, adSpend: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-roas.md) · [All languages](README.md)

<a id="op-businessRoi"></a>

## businessRoi — Return on investment ROI (percent)

`POST /api/v1/business/roi`

```ruby
require "json"
require "net/http"

uri = URI("https://api-zelvyn.devs.surf/api/v1/business/roi")
http = Net::HTTP.new(uri.host, uri.port)
http.use_ssl = true

request = Net::HTTP::Post.new(uri)
request["Content-Type"] = "application/json"
# No API key needed. Optional: add this line for a higher limit:
# request["Authorization"] = "Bearer #{ENV.fetch("ZELVYN_API_KEY")}"
request.body = { profit: 250, investment: 1000 }.to_json

response = http.request(request)
puts JSON.parse(response.body)["data"]
```

[Endpoint reference](../endpoints/business-roi.md) · [All languages](README.md)

---

[All endpoints](../endpoints/README.md) · [Authentication](../authentication.md) · [Errors](../errors.md) · [Rate limits](../rate-limits.md) · [OpenAPI](https://api-zelvyn.devs.surf/openapi.json)
