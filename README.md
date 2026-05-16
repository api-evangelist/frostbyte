# Frostbyte (frostbyte)

Free API platform for developers and AI agents — 40+ services including IP Geolocation, Crypto Prices, Screenshots, DNS Lookup, Web Scraping, and Code Execution. The platform is also known as the **Clawdia Agent Gateway**.

- **Source:** https://api-catalog-three.vercel.app/
- **APIs.json:** https://api-catalog-three.vercel.app/apis.json
- **Unified OpenAPI:** https://api-catalog-three.vercel.app/openapi.json
- **Postman Collection:** https://api-catalog-three.vercel.app/agent-gateway-collection.json
- **Getting Started:** https://api-catalog-three.vercel.app/guides/getting-started
- **api-search issue:** [#20](https://github.com/api-search/network/issues/20)

## Type

`company` — commercial (but free-at-point-of-use) developer-API platform with USDC-on-Base micropayments for higher volume.

## APIs Profiled (7)

| API | Description | OpenAPI |
|---|---|---|
| Frostbyte IP Geolocation API | IP-to-geo, timezone, distance, batch | `openapi/frostbyte-ip-geolocation-openapi.yml` |
| Frostbyte Crypto Prices API | Real-time prices for 38+ pairs (Binance source) | `openapi/frostbyte-crypto-prices-openapi.yml` |
| Frostbyte Screenshot API | Headless-Chromium URL screenshots | `openapi/frostbyte-screenshot-openapi.yml` |
| Frostbyte DNS Lookup API | A/AAAA/MX/NS/TXT/CNAME/SOA plus WHOIS plus propagation | `openapi/frostbyte-dns-lookup-openapi.yml` |
| Frostbyte Web Scraper API | Text/HTML/structured-data extraction (JS rendering) | `openapi/frostbyte-web-scraper-openapi.yml` |
| Frostbyte Code Execution API | Sandboxed Python/JS/TS/Bash execution | `openapi/frostbyte-code-execution-openapi.yml` |
| Frostbyte Agent Gateway (Full API) | Unified 40+-service gateway | `openapi/frostbyte-agent-gateway-openapi.yml` |

## Tags

Developer Tools, Utility APIs, Geolocation, Cryptocurrency, Screenshots, DNS, Scraping, AI Agents

## Commercial Model

- **Free tier**: 200 credits issued on key creation (50 credits for the Screenshot API). 1 credit per request. No signup, no credit card.
- **Pay-as-you-go**: x402 micropayments in USDC on the Base network. Topping up extends key expiry from 30 days to 90 days.
- See `plans/frostbyte-plans-pricing.yml`, `rate-limits/frostbyte-rate-limits.yml`, `finops/frostbyte-finops.yml`.

## Layout

```
frostbyte/
├── apis.yml
├── README.md
├── openapi/         # 7 per-API specs
├── capabilities/    # Naftiko capabilities (1 workflow + 7 shared)
│   └── shared/
├── rules/           # Spectral ruleset
├── json-schema/     # 3 entity schemas
├── json-structure/  # 1 structure
├── json-ld/         # JSON-LD context
├── vocabulary/      # Domain vocabulary
├── examples/        # 27 operation examples
├── plans/           # Pricing (free + pay-as-you-go)
├── rate-limits/     # Credit quotas, expiry, 402 fallback
└── finops/          # FOCUS-aligned billing surface
```

## Notes

- Most per-service rate limits (RPS, concurrency) are **not published**; `reconciled: false` in `apis.yml`. The credit quota and the HTTP 402 / x402 payment fallback are the documented enforcement surface.
- The unified `frostbyte-agent-gateway-openapi.yml` contains 156 operations across 40+ services (agent memory, scheduler, wallets, DeFi, contract deployer, etc.) beyond the seven APIs profiled individually.
- All operation summaries normalized to Title Case.
