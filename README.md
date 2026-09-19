# Zircon Polygon/Massive connector fork

Based on QuantConnect/Lean.DataSource.Polygon at
`9bc2adc9e0f730eb3c1a46991e2749a5c3b35b31`.

This fork removes the QuantConnect entitlement request and its machine/network
metadata collection. Massive authentication and data entitlements remain required.
Equities, options, indices, streaming, history and upstream tests are retained.
This is a Zircon-maintained fork, not an official QuantConnect release.

Build against the same LEAN source as the execution container, currently
`f78c35d7c88c3ea0be9fbd1aeabce3d4ee2347f5`:

```sh
dotnet test QuantConnect.Polygon.Tests/QuantConnect.DataSource.Polygon.Tests.csproj -c Release -p:LeanRoot=/absolute/path/to/Lean
```

Network-dependent tests remain explicit, including the upstream rename-history
test that previously lacked that annotation. Keep the checkout next to a `Lean`
checkout (or symlink) so the upstream test data paths resolve. A passing offline suite does not establish
live reconnect, subscription or price-freshness behavior; those need a paper soak.

---

# Lean Polygon.io Data Source Plugin

[![Build Status](https://github.com/QuantConnect/Lean.DataSource.Polygon/workflows/Build%20%26%20Test/badge.svg)](https://github.com/QuantConnect/Lean.DataSource.Polygon/actions?query=workflow%3A%22Build%20%26%20Test%22)

## Introduction

This repository hosts the Polygon.io Data Source Plugin Integration with the QuantConnect LEAN Algorithmic Trading Engine. LEAN is a brokerage agnostic operating system for quantitative finance. Thanks to plugins such as this [LEAN](https://github.com/QuantConnect/Lean) can use data from many different sources.

[LEAN](https://github.com/QuantConnect/Lean) is maintained primarily by [QuantConnect](https://www.quantconnect.com), a US based technology company hosting a cloud algorithmic trading platform. QuantConnect has successfully hosted more than 200,000 live algorithms since 2015, and trades more than $1B volume per month.

### About Polygon.io

[Polygon.io](https://polygon.io) was founded in 2017 by Quinton Pike as a "market data platform that allows developers to interface with the world's most accurate real-time and historical financial data" and which mission is "to break down the barriers that have traditionally limited access to high-quality financial data for all". Polygon.io provides institutional-grade Stocks, Options, Indices and Forex and Crypto Currencies data for business and educational purposes.