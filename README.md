# bright data pricing: every plan, per-GB and per-1K rate, and the fine print that changes your real bill

Bright Data doesn't publish one price. It sells around ten products, each metered differently: request-based APIs at $1.50 per 1,000 successful requests, residential proxies at $8 per GB on pay-as-you-go, datacenter proxies from $0.60 per GB, a browser product at $8 per GB, and datasets from $250 per 100,000 records. The $499, $999, and $1,999 figures you'll see on its pricing pages are minimum monthly commitments attached to specific products, and the traffic or request volume included in those tiers is what most review articles get wrong.

This piece walks through every product and rate, then covers the billing rules that live in Bright Data's help docs rather than on the pricing cards. If you mainly want a fixed monthly bill for a scraping project, the short version: Bright Data's costs scale with usage and its commitments don't roll over, while a flat-credit service like ScraperAPI charges the same $49–$475 every month regardless of page weight or retries.

> **Quick take:** for most fixed-budget scraping workloads, ScraperAPI's Hobby plan at $49/month (100,000 credits) covers independent projects, and Startup at $149/month (1,000,000 credits) is the sweet spot for production teams; new accounts can confirm their targets' actual costs on a 7-day trial with 5,000 credits, no credit card needed. 👉 [See ScraperAPI's full plan table and start the free trial](https://www.scraperapi.com/pricing/?fp_ref=coupons) If instead you need raw residential or mobile IPs at thousands of GB, an interactive browser, or managed data pipelines, Bright Data's product range justifies its commitment-based pricing — read the breakdown below before signing anything.

## ScraperAPI plans at a glance

Since this is the service most readers with a predictable workload will land on, here is its current full lineup (all prices USD, monthly billing, 10% off on annual):

| Plan | Monthly / Annual (per month) | Credits per month | Geotargeting | Link |
| --- | --- | --- | --- | --- |
| Free | $0 | 1,000 | — | [Sign up free](https://www.scraperapi.com/?fp_ref=coupons) |
| Hobby | $49 / $44.10 | 100,000 | US & EU | [View Hobby plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Startup | $149 / $134.10 | 1,000,000 | US & EU | [View Startup plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Business | $299 / $269.10 | 3,000,000 | All countries | [View Business plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Scaling | $475 / $427.50 | 5,000,000 | All countries | [View Scaling plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Professional | $975 / $877.50 | 10,500,000 | All countries | [View Professional plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Advanced | $1,975 / $1,777.50 | 21,500,000 | All countries | [View Advanced plan](https://www.scraperapi.com/pricing/?fp_ref=coupons) |
| Enterprise | Custom | 22M+ | All countries | [Contact sales](https://www.scraperapi.com/pricing/?fp_ref=coupons) |

Concurrency scales with the tiers as well: 5 connections on the free plan, 20 on Hobby, 50 on Startup, 100 on Business, 200 on Scaling, 300 on Professional, and 500 on Advanced. Every paid plan includes JS rendering, premium residential and mobile IPs, CAPTCHA and anti-bot bypassing, structured data endpoints for Amazon/Google/Walmart, DataPipeline access, unlimited bandwidth, and a 99.9% uptime guarantee. The standing free plan keeps running at 1,000 credits a month after the trial ends, so you can test indefinitely before paying anything.

Two limits worth knowing before you pick: Hobby and Startup geotargeting covers only the US and EU, so country-level targeting for Southeast Asia or Latin America requires Business or above. And heavily protected social platforms remain hard targets on any service at this price class.

## Bright Data's pricing model: one account, many meters

Now to the product you searched for. Bright Data splits its catalog into two billing families, and you need to know which one you're buying before comparing numbers.

Request-based products (Web Scraper API, Web Unlocker, SERP API, Crawl API, Scraper Studio) bill per 1,000 successful records or requests. If a request fails to deliver, you don't pay for it, which is a real advantage over some competitors that bill any response including 403s.

Bandwidth-based products (Residential proxies, Browser API, and the per-GB datacenter plans) bill by traffic in GB. Every byte counts: heavy pages, images, fonts, and retries all eat your quota whether or not the scrape succeeded. A modern JavaScript-heavy page can weigh 2–5 MB, so a million page loads can burn terabytes.

There's one more wrinkle. Bright Data's navigation menu advertises entry prices that don't match what the product pages actually charge — the menu says "from $1 per 1,000 requests" for Web Unlocker while the product page lists $1.50, and the residential menu's "$2.50/GB" turns out to be the top $1,999 tier with a current three-month promo applied. None of this is hidden, but it means the number to budget with is always the one on the product card, never the menu.

## Request-based API pricing

Here's the full picture for the four request-metered APIs, all in USD, all billed monthly:

| Product | Free each month | Pay-as-you-go | $499/mo plan | $999/mo plan | $1,999/mo plan |
| --- | --- | --- | --- | --- | --- |
| Web Scraper API | Shared 5,000 credits | $1.50 / 1,000 records | 384,000 records | — | — |
| Web Unlocker | Shared 5,000 credits | $1.50 / 1,000 requests | 383,000 requests | 908,000 | 2M |
| SERP API | Shared 5,000 credits | $1.50 / 1,000 requests | 380,000 | 900,000 | 2M |
| Crawl API | None | $1.50 / 1,000 requests | 380,000 | 900,000 | 2M |

Overage rates drop as tiers rise: $1.30 per 1,000 beyond the $499 plan, $1.10 at $999, and $1.00 per 1,000 at the $1,999 tier. Note that the $999 and $1,999 tiers are publicly listed for Web Unlocker, SERP API, and Crawl API, while Web Scraper API shows only the $499 card — anything above it goes through a sales quote.

The math that matters: at the $1.50 pay-as-you-go rate, $499 buys you about 333,000 requests. That's the break-even. Below roughly 333,000 requests a month, paying as you go is cheaper than the commitment; above it, the $499 plan wins.

One caveat buried in the documentation: while failed deliveries aren't billed, records that fail *because your input was wrong* — a dead URL, a bad parameter — still are. Sloppy input lists cost real money at scale.

## Residential, ISP, and datacenter proxy pricing

**Residential proxies** list at $8 per GB pay-as-you-go with no commitment. The monthly tiers are $499, $999, and $1,999 at $7, $6, and $5 per GB respectively on the list rate. Right now the residential page runs a three-month 50% discount, which halves those numbers to $4, $3.50, $3, and $2.50 per GB.

Here's the part most articles state incorrectly: the traffic volumes shown on the plan cards — 141 GB at $499, 332 GB at $999, 798 GB at $1,999 — are calculated at the *promo* rate. At the list price of $7 per GB, the $499 plan includes about 71 GB, not 141. When the promo ends after three months, the per-GB rate roughly doubles while the plan price stays the same. Budget against the list rate and treat the promo as a three-month discount, and you won't get surprised by month four.

Residential and mobile traffic also require identity verification (KYC), which for some accounts includes a video call. Web Unlocker doesn't require this.

**Datacenter proxies** are the cheapest traffic in the catalog at $0.60 per GB pay-as-you-go, dropping to $0.51, $0.45, and $0.42 per GB on $499/1TB, $999/2TB, and $1,999/5TB plans. The same 1.3M IP pool is also sold per IP: shared IPs run $1.40 each at 10 IPs ($14/month entry) down to $0.90 at 1,000 IPs, with dedicated IPs from $2.20 to $1.30. The per-IP plans are advertised as unmetered but carry a fair-use limit of 100 GB per IP per month, calculated across the whole order. If you just need a handful of fixed IPs, ten shared ones at $14 a month is the low-cost entry; per-GB plans only win when you're rotating at scale.

**ISP proxies** bill either $8 per GB or per IP: shared IPs from $1.80 down to $1.30 each per month, dedicated from $3.50 to $2.50.

**Mobile proxies** no longer have public pricing — the old mobile page redirects to the general proxy hub, so you'll need a quote.

## The billing fine print that changes your real bill

These terms come from Bright Data's billing docs, and almost none of the ranking articles mention them. They apply to both the APIs and the proxy tiers above, so read them before you pick a plan:

- **The tiers are minimums.** Each $499/$999/$1,999 plan is a commitment billed on the 1st of every calendar month, prorated for a mid-month start. Unused volume doesn't roll over — an idle $499 plan still costs $499.
- **Wallet mechanics.** You prepay into a balance. Unverified trial accounts cap single top-ups at $100. Your first top-up is matched 1:1 up to $500, but the bonus expires after 90 days and requires at least $5 of monthly activity to stay alive.
- **Zone fees.** Your first 50 proxy/API configurations (zones) are free; each one after that costs $5 per month.
- **Refunds.** Subscription fees are generally non-refundable, promotional credit is never refundable, and a chargeback without cause triggers a $150 fee. Payments run in USD regardless of the currency shown, via card, PayPal, Payoneer, Alipay, Google Pay, wire, or AWS Marketplace.

That last bullet is why the menu-price issue matters: if a promo credit or subscription fee turns out to be different from what you assumed, the practical path back is limited.

## Browser API: the most expensive way to load a page

Browser API gives you a real remote browser (Puppeteer, Playwright, Selenium compatible) with site unlocking built in, metered at $8 per GB pay-as-you-go, or $7/$6/$5 per GB on the $499/$999/$1,999 plans. The cost per thousand pages depends entirely on page weight:

| Page type | Cost per 1,000 pages (pay-as-you-go) |
| --- | --- |
| 500 KB text page | ~$3.81 |
| 2 MB typical modern page | ~$15.62 |
| 5 MB image-heavy listing | ~$49.06 |

Same 2 MB page through Web Unlocker at $1.50 per 1,000 requests costs ten times less, because Unlocker bills per successful request rather than per byte. The rule of thumb: use Browser API only when you genuinely need to click, scroll, or wait for interactions. If you only need the page content, it's an expensive habit — and blocking images and fonts saves more money than negotiating a lower GB rate.

## Datasets and managed services

Datasets (pre-collected data from 600+ domains) start at $2.50 per 1,000 records with a 100,000-record minimum — $250 to get in the door. At 20 million records the rate drops to $0.50 per 1,000. Data Firehose, the continuous HTML stream product, starts at $0.20 per 1,000 pages.

Managed data acquisition is the foggiest corner of the catalog: Bright Data's own pricing page and menu list different starting points ($1,000 versus $1,500 per month), plus a $500 setup fee per scraper and roughly $4 per 1,000 requests. Get a written quote before committing to anything here.

## A worked bill: 1,500 SKUs a month

Say you're tracking 1,500 product SKUs across Amazon and Walmart using pre-built scrapers — 45,000 records a month. On pay-as-you-go at $1.50 per 1,000, after the shared free allowance you're paying roughly **$60 a month**. No commitment, no wallet lock-in.

Now compare the floor cost of the cheapest commitment: $499 every month whether you use 380,000 requests or 50,000. For workloads under a few hundred thousand requests a month, the commitment only makes sense if you're certain your volume is growing into it.

## When a flat-rate alternative fits better

Bright Data's model rewards volume and punishes unpredictability. ScraperAPI takes the opposite approach: one API endpoint, a fixed credit allowance each month (table above), and the same bill whether your target pages weigh 100 KB or 3 MB.

The catch, and it's the mirror image of Bright Data's: ScraperAPI bills in credits with domain multipliers. A standard page costs 1 credit, Amazon costs 5, Google and Bing cost 25, LinkedIn costs 30, and requests through Cloudflare/Datadome/PerimeterX protection add 10 credits each. Fetching 100,000 standard pages fits the Hobby plan; 100,000 Google SERP results would blow through it five times over. The dashboard's Domain Cost Estimator shows the exact cost of any URL before you commit, and you can set a `max_cost` cap per scrape to keep a single request from eating your quota. 👉 [Open the pricing page and run your target URLs through the cost estimator](https://www.scraperapi.com/pricing/?fp_ref=coupons)

Overage behavior differs by tier too. By default, hitting your credit limit pauses scraping until the next cycle — no surprise charges. Hobby through Professional plans can opt into auto-upgrade to bump you to the next tier mid-cycle, and Scaling and above get true pay-as-you-go continuation at a fixed per-credit rate, capped by a monthly spend limit you set. Plans are cancellable anytime from the dashboard with no cancellation fee.

## FAQ

**Does Bright Data have a free plan?**
Sort of. Request-based APIs share a free monthly allowance of 5,000 credits, and proxy products come with a $2 trial credit. It stops when the allowance runs out, doesn't roll over, and disappears once you're on a paid plan.

**Is the $499 Bright Data plan a discount or a minimum?**
A minimum. It's billed on the 1st of each month whether you use the included volume or not, and unused volume doesn't carry forward.

**Why does Bright Data's site say "from $1 per 1,000" when the page shows $1.50?**
The menu shows the best achievable rate — typically a top-tier volume or promotional figure. The product page card is the real entry price. Always budget from the card.

**What's the cheapest way to start with Bright Data?**
Pay-as-you-go. No commitment, and you can set a monthly spending cap on your account. Residential traffic at $8/GB list is the priciest entry point; datacenter at $0.60/GB is the cheapest.

## Which one should you pick

Match the tool to the workload rather than the headline rate:

- **Under ~300,000 requests a month, standard websites, fixed budget:** ScraperAPI Hobby or Startup, $49–$149 a month flat, with the trial confirming your targets' credit costs first.
- **Google/Bing SERP or LinkedIn at volume:** either works, but run the numbers — ScraperAPI's 25–30 credit multipliers versus Bright Data's flat $1.50 per 1,000 change the winner depending on your mix.
- **Raw residential or mobile IPs, thousands of GB:** Bright Data's proxy networks are the point of buying it; just budget at list rates ($7/GB on the $499 plan) and treat any current promo as temporary.
- **Needs a real browser for interactive sites:** Bright Data's Browser API if you're committed to that ecosystem; ScraperAPI's JS rendering (`render=true`) if the content appears without clicks.
- **Wants someone else to build the pipeline:** Bright Data's datasets and managed services, with a written quote given the inconsistent published pricing.

One last check before either checkout: confirm your heaviest target site's actual cost — ScraperAPI's estimator for credits, Bright Data's cost tools for GB — because a single protected domain can shift the math more than any plan tier. 👉 [Compare all ScraperAPI plans and current annual pricing](https://www.scraperapi.com/pricing/?fp_ref=coupons)
