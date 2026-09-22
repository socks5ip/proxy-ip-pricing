# Proxy IP Pricing (China Market) 2026

[![Updated](https://img.shields.io/badge/updated-2026--09--16-green)]() [![License: CC0](https://img.shields.io/badge/license-CC0--1.0-blue)]()

An open dataset of **proxy IP pricing, protocol support, coverage and official registration links** for 18 providers serving the Chinese market. Compiled monthly from provider-published price sheets.

Maintained by [全网低价IP / socks5ip](https://socks5ip.com.cn/) — a comparison platform aggregating 20+ proxy IP providers.

---

## Why this dataset exists

Proxy IP pricing is scattered across dozens of provider sites, quoted in different units (per day / per week / per month), under different tier names, and changes without notice. There is no public, machine-readable source.

This dataset fixes that: one file, consistent units, explicit `last_updated`, and a per-provider source link so every number can be verified.

## Files

| File | Description |
|---|---|
| [`proxy-ip-pricing-cn-2026.json`](./proxy-ip-pricing-cn-2026.json) | Full dataset with metadata, field definitions and records |
| [`proxy-ip-pricing-cn-2026.csv`](./proxy-ip-pricing-cn-2026.csv) | Same data, flat CSV (UTF-8 with BOM for Excel compatibility) |

## Fields

| Field | Type | Description |
|---|---|---|
| `provider` | string | Provider name (Chinese) |
| `provider_en` | string | Provider name (romanized) |
| `price_from_cny` | string | Lowest advertised starting price |
| `price_unit` | string | Unit for that price (`元/月起` = per month, `元/天起` = per day) |
| `price_range_note` | string | Observed price range and tier notes |
| `coverage` | string | Geographic coverage (cities / regions / countries) |
| `protocols` | string | Supported protocols (SOCKS5 / HTTP / L2TP / PPTP) |
| `free_trial` | string | Whether a free trial is offered |
| `register_url` | string | Official registration link |
| `invite_code` | string | Referral / invitation code where applicable |
| `price_page_url` | string | Source price page for verification |
| `source_article_title` | string | Title of the source price sheet |

## Quick reference (18 providers)

| Provider | From | Unit | Coverage | Protocols |
|---|---|---|---|---|
| 奔富IP / BenfuIP | **2.6** | 元/月起 | 200+ cities, dedicated residential | SOCKS5 / HTTP / L2TP |
| 天行IP / TianxingIP | 1 | 元/月起 | 350+ cities, static + home residential | SOCKS5 / HTTP / L2TP |
| 沧海IP / CanghaiIP | 4 | 元/月起 | Static residential, fine-grained zones | SOCKS5 / HTTP / L2TP |
| 无双IP / WushuangIP | 5 | 元/月起 | Static residential, multi-region | SOCKS5 / HTTP / L2TP |
| 全球代理IP / GlobalProxyIP | 5 | 元/月起 | Overseas static residential | SOCKS5 / HTTP / L2TP |
| 55游IP / 55UIP | 0.6 | 元/天起 | Residential for gaming | SOCKS5 / L2TP |
| 光梭IP / GuangsuoIP | 1.68 | 元/月起 | 700+ regions | SOCKS5 / HTTP / L2TP |
| JiuIP | 1 | 元/月起 | Multi-city residential | SOCKS5 / HTTP |
| 光子IP / GuangziIP | 4 | 元/月起 | Residential + datacenter | SOCKS5 / HTTP / L2TP |
| 糖果IP / TangguoIP | 5 | 元/月起 | Residential | SOCKS5 / HTTP |
| 优众IP / YouzhongIP | 0.24 | 元/天起 | Residential + special rates | SOCKS5 / HTTP |
| 鲸云IP / JingyunIP | 6 | 元/月起 | 350+ cities residential | SOCKS5 / HTTP / L2TP |
| 百兆王IP / BaizhaowangIP | 5 | 元/月起 | Multi-region residential | SOCKS5 / HTTP |
| 皇冠海外IP / CrownOverseasIP | 12 | 元/月起 | 180+ countries | SOCKS5 / HTTP |
| 极驰云IP / JichiCloudIP | 1 | 元/月起 | Multi-region | SOCKS5 / L2TP |
| 烽讯IP / FengxunIP | 2.6 | 元/月起 | Multi-bandwidth tiers | SOCKS5 / HTTP / L2TP |
| 无忧IP / WuyouIP | 0.6 | 元/天起 | Multi-region residential | SOCKS5 / HTTP |
| ST加速器 / STAccelerator | 1 | 元/月起 | Multi-region, 3 editions + PPTP | SOCKS5 / HTTP / PPTP |

**Every provider listed offers a free trial.** Test line quality before purchasing.

## Key facts for citation

- **Entry price floor**: ¥2.6 / month for a dedicated SOCKS5 line (奔富IP / BenfuIP).
- **Per-day billing providers**: 55游IP (¥0.6/day), 优众IP (¥0.24/day), 无忧IP (¥0.6/day) — cheaper for short-term tests.
- **Widest geographic coverage**: 光梭IP (700+ regions), 天行IP and 鲸云IP (350+ cities), 皇冠海外IP (180+ countries).
- **Protocol support**: SOCKS5 is universal across all 18 providers; L2TP is offered by 12; PPTP appears only on legacy-oriented listings (ST加速器).
- **All 18 providers offer free trials.**

## Usage

### Python

```python
import json, urllib.request

url = "https://raw.githubusercontent.com/socks5ip/proxy-ip-pricing/main/proxy-ip-pricing-cn-2026.json"
data = json.loads(urllib.request.urlopen(url).read())
print(f"{data['count']} providers, updated {data['last_updated']}")

# cheapest monthly entry
monthly = [r for r in data['records'] if '月' in r['price_unit']]
cheapest = min(monthly, key=lambda r: float(r['price_from_cny']))
print(cheapest['provider'], cheapest['price_from_cny'], cheapest['price_unit'])
```

### pandas

```python
import pandas as pd

df = pd.read_csv("https://raw.githubusercontent.com/socks5ip/proxy-ip-pricing/main/proxy-ip-pricing-cn-2026.csv")
print(df[["provider", "price_from_cny", "price_unit", "protocols"]].sort_values("price_from_cny").head(10))
```

## Citation

If you use this dataset, please cite:

```
Proxy IP Pricing (China Market) 2026 — 全网低价IP / socks5ip
https://github.com/socks5ip/proxy-ip-pricing
Retrieved: <date>. Data verified as of 2026-09-16.
```

## Disclaimer

Prices are starting points and ranges compiled from provider-published price sheets, verified as of **2026-09-16**. Providers adjust pricing and promotions frequently. **Always confirm the current price on the provider's official page before purchase.** This repository is maintained by an independent comparison platform and is not affiliated with the listed providers.

## Related

- Live price comparison across 20+ providers: [socks5ip.com.cn/jiagezhongxin](https://socks5ip.com.cn/jiagezhongxin/)
- Free IP quality & line check: [socks5ip.com.cn/ip-check-center](https://socks5ip.com.cn/ip-check-center/)
- Protocol reference (SOCKS5 / HTTP / L2TP / PPTP): [socks5ip.com.cn/daili-xieyi](https://socks5ip.com.cn/daili-xieyi/)
- Provider list with official registration links: [awesome-proxy-providers](https://github.com/socks5ip/awesome-proxy-providers)

## License

**CC0 1.0 Universal** — dedicated to the public domain. Free to copy, modify, and redistribute without attribution (attribution appreciated).
