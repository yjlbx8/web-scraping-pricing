# best web scraping services: Real Prices, the Credit Rules Nobody Quotes, and How to Pick Without Overpaying

Most roundups of the best web scraping services stop at a ranked table. That table hides the one thing that actually decides your bill: these services charge in completely different units — credits, requests, delivered records, or dollar balances — so a $19 plan and a $49 plan often can't be compared on volume alone. This guide sorts the main players by what they actually sell, then digs into ScraperAPI's full plan lineup and the billing fine print (credits that don't roll over, per-site credit multipliers, pay-as-you-go limits) that most reviews leave out.

> **Quick take:** If you already write code and keep getting blocked, ScraperAPI is the fastest fix — one GET endpoint handles proxy rotation, retries, CAPTCHAs and JS rendering. Plans start at $49/month for 100,000 credits, and every new account gets 5,000 free credits for 7 days with no credit card. 👉 [Start the free trial and check current plan prices](https://www.scraperapi.com/?fp_ref=coupons)

## What a web scraping service actually does

A web scraping service runs the proxies, headless browsers and anti-bot work for you, so your code sends a URL and gets data back instead of a CAPTCHA page. Two very different shapes exist in this market, and picking the wrong shape costs more than picking the wrong brand.

**Self-serve scraper APIs**: you send a request, the service routes it through a rotating IP pool and returns HTML or parsed JSON. Your crawler logic stays on your side. This fits price monitors, SERP rank trackers, lead-gen scrapers — anything where you want programmatic control.

**Managed data delivery**: you describe the dataset you need and the vendor builds and maintains the pipeline, delivering on a schedule. This fits teams without developers or one-off data projects, not ongoing tooling.

The reviews that rank seven or ten brands in one list usually mix these two categories together, which is why their "prices" don't line up. Know which shape you need first.

## How the main services compare

Here are the documented entry prices from each vendor's own pricing page as of mid-2026:

| Service | Entry paid price | Billing unit | Free entry | Best for |
| --- | --- | --- | --- | --- |
| ScraperAPI | $49/mo (Hobby) | Credits per request | 1,000/mo + 5,000 for 7 days | Simple URL-in, HTML-out at scale |
| ScrapingBee | $49/mo (Freelance) | Credits | 1,000 credits, no card | Rendering plus easy integration |
| Apify | $29/mo (Starter) | Dollar usage balance | $5 usage/mo, no card | Reusing prebuilt scrapers |
| Zyte | $0.13/1K requests (PAYG) | Dollar balance by site difficulty | $5 credit, 30 days | Auto-extraction, difficulty-based pricing |
| Oxylabs | $0.25/1K results (PAYG) | Delivered results | 2,000 results, no card | Pay-per-result with site parsers |
| Bright Data | $1.50/1K records (PAYG) | Delivered records | 5,000 records/mo | Enterprise scale and product breadth |

Read the billing-unit column before anything else. Oxylabs and Bright Data charge per delivered result or record, which means failed requests are their problem, not yours. ScraperAPI, ScrapingBee and ChocoData sell credits or requests, which shifts more of the modeling onto you — that's exactly where the hidden costs in the next sections come from.

One more warning that applies to every row: success rate and uptime are different metrics. A vendor advertising 99.9% uptime is telling you the API is reachable, not that your target page came back with usable data. The published performance figures across these vendors are self-reported, and independent same-methodology benchmarks are thin on the ground.

## ScraperAPI's full plan lineup

ScraperAPI's pricing page currently shows eight tiers, from a free plan to custom Enterprise. All paid plans include the same feature set — JS rendering, premium residential and mobile IPs, CAPTCHA and anti-bot bypass, JSON auto-parsing, structured data endpoints, DataPipeline and full crawler access. What changes between tiers is the credit allowance, concurrency, geotargeting range, and how long your analytics dashboard keeps history.

| Plan | Monthly price | Annual billing | Credits/month | Concurrent threads | Buy |
| --- | --- | --- | --- | --- | --- |
| Free | $0 | — | 1,000 | 5 | — |
| Hobby | $49 | $44.10/mo | 100,000 | 20 | [ Check the Hobby plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Startup | $149 | $134.10/mo | 1,000,000 | 50 | [ Check the Startup plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Business | $299 | $269.10/mo | 3,000,000 | 100 | [ Check the Business plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Scaling | $475 | $427.50/mo | 5,000,000 | 200 | [ Check the Scaling plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Professional | $975 | $877.50/mo | 10,500,000 | 300 | [ Check the Professional plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Advanced | $1,975 | $1,777.50/mo | 21,500,000 | 500 | [ Check the Advanced plan](https://www.scraperapi.com/pricing?fp_ref=coupons) |
| Enterprise | Custom | Custom | 22,000,000+ | 500+ | [ Talk to sales about Enterprise](https://www.scraperapi.com/?fp_ref=coupons) |

Two details in that table deserve attention. Hobby and Startup only keep 30 days of analytics history and are limited to US and EU geotargeting; Business and up get unlimited history and country-level targeting worldwide. And annual billing saves 10% across the board — $44.10/month on Hobby, $269.10 on Business.

If you're sizing a plan, the honest fit per an independent 2026 review is a solo developer or small team running 20,000–200,000 pages a month against standard e-commerce and search targets — roughly the Hobby-to-Startup range. 👉 [Compare all eight plans side by side](https://www.scraperapi.com/pricing?fp_ref=coupons)

## The credit cost nobody quotes you upfront

Here's the part most comparisons skip: a "standard page" costs 1 credit, but most of the pages people actually want aren't standard. ScraperAPI's own pricing page spells out the multipliers:

- Standard page: 1 credit
- Amazon: 5 credits
- Google and Bing (including subdomains): 25 credits
- LinkedIn: 30 credits
- Sites behind Cloudflare, Datadome or PerimeterX: +10 credits per request when bypassed
- JS rendering (`render=true`): roughly 10 credits

Run the math on a real job. A SERP rank tracker hitting Google at 25 credits per query burns through Hobby's 100,000 credits in 4,000 queries — about 130 queries a day. A project that needs both `render=true` and `premium=true` on a protected target can cost 20–30× the headline per-credit price. One 2026 review worked it out for Amazon search pages with rendering enabled: 1,000,000 credits might only cover 40,000–100,000 actual pages, not a million.

Before you pick a plan, list your target domains and their monthly volume, then use the Domain Cost Estimator in ScraperAPI's dashboard to check the exact per-URL cost. You can also set a `max_cost` per scrape so no single request blows past your limit. This two-minute exercise matters more than the price column in any comparison table — including mine.

## Billing rules that only show up in the docs

Four rules live in ScraperAPI's documentation and pricing fine print rather than in any marketing copy, and all four affect real budgets:

1. **Credits don't roll over.** They reset at each renewal and the leftover balance disappears. Annual plans can renew early for a fresh batch, which is one way to avoid wasting credits, but budgeting for the full allowance every month is the safer default.
2. **Pay-as-you-go overage only exists from Scaling up.** On Hobby, Startup or Business, when credits run out scraping pauses until renewal — unless you've opted into auto-upgrade, which moves you to the next plan automatically. If your volume spikes unpredictably, that's an argument for Scaling ($475/mo) rather than Business.
3. **A 404 counts as a delivered request.** You pay for HTTP 200s and 404s alike, plus anything you cancel within the 70-second window. Dead product pages on a monitored catalog will quietly eat credits.
4. **Hitting the concurrency cap returns HTTP 429.** The request is rejected, not queued, and it costs nothing. But it's rejected — a job that needs 300 threads won't wait politely on a Hobby plan's 20.

None of these are dealbreakers once you know them. All of them surprise people who budgeted off the credit number alone.

## What ScraperAPI gets you beyond the proxy layer

The 2026 product has grown well past the "simple proxy API" reputation. All paid plans include structured data endpoints that return parsed JSON for Amazon, Walmart, eBay, Home Depot, Google (Search, News, Jobs, Shopping, Maps), Redfin, and AI answer engines like ChatGPT, Perplexity and Gemini — so when a site redesigns, the vendor fixes the parser, not you. DataPipeline runs low-code scheduled jobs of up to 100,000 URLs, keywords or ASINs per project with webhook delivery. There's a crawler that follows links from a seed URL, an Async API for batch jobs, and integrations including an MCP server (works with Claude Code), LangChain, LlamaIndex, n8n and Zapier.

In 2026 the company also acquired Traject Data, folding the Rainforest and SerpWow SERP and e-commerce APIs into the same credit system — worth knowing if those tools were on your stack separately.

You pay per request, not per GB, and bandwidth is unlimited. The IP pool is advertised at over 40 million addresses across residential, datacenter and mobile networks in 50+ countries.

New accounts can kick the tires before paying anything: 👉 [Claim the 7-day trial with 5,000 credits](https://www.scraperapi.com/?fp_ref=coupons)

## Who should look elsewhere

Being straight about the fit saves everyone time:

- **Hard targets at volume.** LinkedIn costs 30 credits per request, and ultra-premium routing on heavily protected e-commerce can end up pricier than a bandwidth-billed residential proxy plan. If your whole project is LinkedIn or Instagram scraping, a dedicated provider fits better.
- **Long-lived sessions.** Sticky sessions hold for about 15 minutes, and session persistence tops out around an hour. Ad verification or account workflows that need the same IP for days need a different tool category.
- **Fine-grained IP control.** You choose country, session and IP tier, but never a specific IP, ASN or city. That's by design; if you need it, buy raw proxies.
- **No-code users.** You can schedule and configure jobs through DataPipeline, but there's no marketplace of ready-made scrapers like Apify runs — you're still expected to write or assemble the logic.
- **Geotargeting outside US/EU on a budget.** Country-level targeting beyond the US and EU starts at Business ($299/mo).

For pure price monitoring against ordinary e-commerce sites, plain HTML requests at 1 credit are genuinely cheap — roughly $0.10–0.15 per 1,000 pages from Startup up. The "expensive" reputation comes from rendered and protected pages, which is a target-site problem, not a plan problem.

## FAQ

**Does ScraperAPI have a free plan?**
Yes — 1,000 free API credits per month with a maximum of 5 concurrent connections, plus a 7-day trial with 5,000 credits that requires no credit card. It's enough to test your target sites, not enough to run anything in production. Support can grant extra testing credits if you ask.

**Can I get a refund?**
Paid plans come with a 7-day no-questions-asked refund, and you can cancel from the dashboard at any time. Between that and the free trial, the cost of finding out it doesn't work for your targets is close to zero.

**What happens when I run out of credits mid-month?**
Scraping pauses by default until renewal. Hobby through Professional can enable opt-in auto-upgrade to jump to the next plan automatically; Scaling and above can keep scraping on pay-as-you-go at a fixed per-credit rate, capped by a monthly spend limit you set.

**How fast are responses?**
Simple pages return in seconds. Protected domains can take up to 60 seconds — the docs recommend a 70-second client timeout — which is what the Async API is for at volume.

**Do I need to know how to code?**
For the core API, yes — it's a single GET endpoint, so basic HTTP skills are the floor. DataPipeline lowers the bar for scheduled jobs, but if you want zero code at all, an Actor marketplace platform is a better fit than this product category.

## Picking your plan, in one pass

Plain-HTML scraping of e-commerce or typical sites under ~80,000 pages a month → Hobby at $49 covers it, and the free tier will confirm your targets clear before you pay. SERP tracking or Google-targeted work → do the 25-credit math first; most likely you land on Startup or Business. Unpredictable or spiky volume, or you want overage protection → Scaling is the floor for pay-as-you-go. Anything with Cloudflare/DataDome-class protection on every page → price out the 20–30× multiplier honestly before committing, because a bandwidth-billed proxy provider might undercut it.

Whatever you land on, start with the free 5,000 credits, run your Domain Cost Estimator check, and only then commit to a tier. 👉 [Set up your account and test your targets free](https://www.scraperapi.com/?fp_ref=coupons)
