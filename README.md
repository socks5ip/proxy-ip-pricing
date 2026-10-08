# Proxy IP Pricing (China Market) 2026

[![Updated](https://img.shields.io/badge/updated-2026--10--08-green)]() [![License: CC0](https://img.shields.io/badge/license-CC0--1.0-blue)]()

An open dataset of **proxy IP pricing, protocol support, coverage and official registration links** for 23 providers serving the Chinese market. Compiled monthly from provider-published price sheets.

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
| `price_month_cny` | string | Lowest **month-card** (月卡) price in CNY — the normalized figure used for cross-provider ranking. For per-day / per-week providers this is their cheapest monthly tier, not the per-day rate. |
| `price_month_note` | string | Scope note explaining what `price_month_cny` refers to. |
| `price_month_source` | string | How `price_month_cny` was verified. |
| `price_band` | string | Price band by month-card price: `A · ≤3` / `B · 3–5` / `C · 5–8` / `D · >8` CNY/month. |
| `rank_month` | integer | Rank by `price_month_cny` ascending (ties broken by provider name). |

## Quick reference (23 providers)

| Provider | Month card (from) | Band | Coverage | Protocols |
|---|---|---|---|---|
| 光梭IP / GuangsuoIP | **2.24** | A 3 元以下 | 全国 700+ 地区 | SOCKS5 / HTTP / L2TP |
| 奔富IP / BenfuIP | **2.6** | A 3 元以下 | 全国 200+ 城市，独享住宅IP | SOCKS5 / HTTP / L2TP |
| 烽讯IP / FengxunIP | **2.6** | A 3 元以下 | 多带宽档位 | SOCKS5 / HTTP / L2TP |
| 蛟龙IP / JiaolongIP | **2.8** | A 3 元以下 | 国内多地区，独享线路（游戏 / 视频加速） | SOCKS5 / HTTP / L2TP / PPTP |
| JiuIP / JiuIP | **3.4** | B 3–5 元 | 多城市住宅线路 | SOCKS5 / HTTP |
| 沧海IP / CanghaiIP | **4** | B 3–5 元 | 静态住宅，分区细致 | SOCKS5 / HTTP / L2TP |
| 光子IP / GuangziIP | **4** | B 3–5 元 | 住宅 + 机房 | SOCKS5 / HTTP / L2TP |
| 天机IP / TianjiIP | **4** | B 3–5 元 | 国内多地区，大带宽静态住宅（多工具兼容） | SOCKS5 / HTTP / L2TP / PPTP |
| 无忧IP / WuyouIP | **4.5** | B 3–5 元 | 多地区住宅 | SOCKS5 / HTTP |
| 全球代理IP / GlobalProxyIP | **5** | B 3–5 元 | 海外静态住宅 | SOCKS5 / HTTP / L2TP |
| 糖果IP / TangguoIP | **5** | B 3–5 元 | 住宅线路 | SOCKS5 / HTTP |
| 百兆王IP / BaizhaowangIP | **5** | B 3–5 元 | 多地区住宅 | SOCKS5 / HTTP |
| 长城IP / ChangchengIP | **5** | B 3–5 元 | 全国多地区覆盖（套餐分档细） | SOCKS5 / HTTP / L2TP / PPTP |
| 天行IP / TianxingIP | **6** | C 5–8 元 | 350+ 城市，长效静态 + 家庭住宅双线 | SOCKS5 / HTTP / L2TP |
| 鲸云IP / JingyunIP | **6** | C 5–8 元 | 350+（官方称 200+）城市住宅 | SOCKS5 / HTTP / L2TP |
| 极驰云IP / JichiCloudIP | **6** | C 5–8 元 | 多地区 | SOCKS5 / L2TP |
| 优享云IP / YouxiangyunIP | **6** | C 5–8 元 | 国内 260+ 城市（静态 IP，节点地址常年固定） | SOCKS5 / HTTP |
| 优众IP / YouzhongIP | **7.2** | C 5–8 元 | 住宅 + 特价档 | SOCKS5 / HTTP |
| 无双IP / WushuangIP | **7.5** | C 5–8 元 | 静态住宅，多地区 | SOCKS5 / HTTP / L2TP |
| 皇冠海外IP / CrownOverseasIP | **12** | D 8 元以上 | 180+ 国家 | SOCKS5 / HTTP |
| ST加速器 / STAccelerator | **12** | D 8 元以上 | 多地区 | SOCKS5 / HTTP / PPTP |
| 55游IP / 55UIP | **15** | D 8 元以上 | 游戏场景住宅线路 | SOCKS5 / L2TP |
| 酷熊IP / KuxiongIP | **20** | D 8 元以上 | 静态住宅（不限流量） | SOCKS5 / HTTP / L2TP / PPTP |

`Month card (from)` is the normalized comparison basis: the cheapest **monthly** tier of each provider. Where a provider also sells day cards (55游IP ¥0.6/day, 优众IP ¥0.24/day, 无忧IP ¥0.6/day), the day rate is cheaper for very short tests but the month card is what makes providers comparable. See `price_from_cny` / `price_unit` for the raw advertised entry price and its original unit.

**22 of 23 providers offer a free trial** — 优享云IP does not (a ¥2 day card is available instead). Test line quality before purchasing.

## Key facts for citation

- **Entry price floor (month card)**: **¥2.24 / month** (光梭IP / GuangsuoIP). Runners-up: 奔富IP and 烽讯IP at ¥2.6, 蛟龙IP at ¥2.8. Cheapest tier under ¥3/month is band **A** (4 providers).
- **Per-day billing providers**: 55游IP (¥0.6/day), 优众IP (¥0.24/day), 无忧IP (¥0.6/day) — cheaper for short-term tests.
- **Widest geographic coverage**: 光梭IP (700+ regions), 天行IP and 鲸云IP (350+ cities), 皇冠海外IP (180+ countries).
- **Protocol support**: SOCKS5 is universal across all 23 providers; L2TP is offered by 15; PPTP by 5 (ST加速器, 蛟龙IP, 天机IP, 长城IP, 酷熊IP).
- **Free trials**: 22 of 23 providers offer one; **优享云IP does not** (a ¥2 day card is available instead).

## How these prices are obtained (discounted pricing)

The prices listed here are the **discounted rates we have arranged with each provider** — they are generally **lower than the headline prices shown on the providers' own sites**.

- These discounted rates **only apply if you register through our referral link**, which carries a per-provider invitation code (see the `invite_code` field, embedded in each `register_url`). This is the standard mechanism on these platforms: the price sheet contains both a list price and a discounted price, and the invitation code determines the account association and the discount.
- **If you registered through our link and the amount you actually paid does not match what is listed here**, contact our support and we will help get the price corrected — **free of charge**.
- **If you already registered elsewhere**, ask our support whether that provider supports re-pricing an existing account; if it does not, register a new account through our link.
- We do not set or guarantee any price — pricing is decided by each provider. Always confirm the final amount in the provider's own dashboard.

Methodology, update cadence and the price-correction channel: <https://socks5ip.com.cn/jiage-heshifangfa/>

## Usage

### Python

```python
import json, urllib.request

url = "https://raw.githubusercontent.com/socks5ip/proxy-ip-pricing/main/proxy-ip-pricing-cn-2026.json"
data = json.loads(urllib.request.urlopen(url).read())
print(f"{data['count']} providers, updated {data['last_updated']}")

# cheapest monthly entry (normalized month-card basis)
ranked = sorted(data['records'], key=lambda r: float(r['price_month_cny']))
for r in ranked[:5]:
    print(r['rank_month'], r['provider'], r['price_month_cny'], 'CNY/month', r['price_band'])
```

### pandas

```python
import pandas as pd

df = pd.read_csv("https://raw.githubusercontent.com/socks5ip/proxy-ip-pricing/main/proxy-ip-pricing-cn-2026.csv")
print(df[["rank_month", "provider", "price_month_cny", "price_band", "protocols"]].sort_values("rank_month").head(10))
```

## Citation

If you use this dataset, please cite:

```
Proxy IP Pricing (China Market) 2026 — 全网低价IP / socks5ip
https://github.com/socks5ip/proxy-ip-pricing
Retrieved: <date>. Data verified as of 2026-10-08.
```

## Disclaimer

Prices are starting points and ranges compiled from provider-published price sheets, verified as of **2026-10-08**. Providers adjust pricing and promotions frequently. **Always confirm the current price on the provider's official page before purchase.** This repository is maintained by an independent comparison platform and is not affiliated with the listed providers. The listed prices are arranger-discounted rates obtained through our referral links (see "How these prices are obtained"); the amount charged is decided by each provider and shown in its own dashboard.

## Related

- Live price comparison across 20+ providers: [socks5ip.com.cn/jiagezhongxin](https://socks5ip.com.cn/jiagezhongxin/)
- Free IP quality & line check: [socks5ip.com.cn/ip-check-center](https://socks5ip.com.cn/ip-check-center/)
- Protocol reference (SOCKS5 / HTTP / L2TP / PPTP): [socks5ip.com.cn/daili-xieyi](https://socks5ip.com.cn/daili-xieyi/)
- Provider list with official registration links: [awesome-proxy-providers](https://github.com/socks5ip/awesome-proxy-providers)
- How we verify prices, why ours are discounted, and how to request a price correction: <https://socks5ip.com.cn/jiage-heshifangfa/>
- **面向 AI / LLM 的站点索引**（llms.txt）：https://socks5ip.com.cn/llms.txt —— 核心页导航、20+ 家平台注册入口与邀请码、开源工具与联系方式（完整版：<https://socks5ip.com.cn/llms-full.txt>）

## License

**CC0 1.0 Universal** — dedicated to the public domain. Free to copy, modify, and redistribute without attribution (attribution appreciated).
