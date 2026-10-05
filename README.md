# Bright Data pricing: the real per-GB math behind the $8 sticker, the coupon that expires in three months, and when a $1/GB alternative wins

Open Bright Data's site and you'll see "$2.50/GB" in the navigation. Open the residential proxy page and the meta description says $5.88/GB. Scroll down to the plan cards and the pay-as-you-go tier says $8/GB. Three numbers, one product, and no obvious explanation of why they disagree.

They disagree because Bright Data prices by volume and then layers a time-limited coupon on top. The $2.50 comes from the highest commitment tier with that coupon applied. The $8 is what you pay with no commitment and no promo. Both are real. Neither is the price most people actually pay.

Here's the full picture, product by product, plus what the same workload costs at a provider positioned on the opposite end of the market.

## Residential proxies: four tiers, two price lists each

Residential is the product most people mean when they search for Bright Data pricing. Four options, all billed monthly:

| Plan | Traffic included | List rate | Rate with RESIGB50 (first 3 months) |
| --- | --- | --- | --- |
| Pay as you go | Metered, no commitment | $8.00/GB | $4.00/GB |
| $499/month | 141 GB | ~$7.08/GB | ~$3.54/GB |
| $999/month | 332 GB | ~$6.00/GB | ~$3.01/GB |
| $1,999/month | 798 GB | ~$5.00/GB | ~$2.51/GB |

Above roughly 1 TB a month, pricing moves to a custom quote.

The commitment tiers don't roll over. If you buy the $499 plan and use 60 GB that month, you paid for 141. That's the trade: a lower per-GB rate in exchange for forecasting your consumption correctly. Teams that underestimate tend to discover it in month two or three, when the overage rate kicks in at 20–50% above their contracted rate.

## The coupon is real, but it's a three-month coupon

RESIGB50 takes 50% off residential traffic for three months. That's the whole offer. A $499/month plan runs near $3.54/GB while it's active and snaps back to roughly $7/GB in month four unless you renegotiate or move up a tier.

Bright Data also matches your first deposit dollar for dollar up to $500, which is a better deal than the coupon if you're testing the platform before committing to a monthly volume.

Neither of these is hidden, exactly. Both are easy to miss if you read the navigation bar and stop there.

## What the rest of Bright Data's catalogue costs

Proxies are one line item. The wider product list includes datacenter bandwidth, static residential IPs, mobile traffic and managed scraping APIs, and they're priced on different models — some per GB, some per request, some per IP per month.

| Product | Entry rate | Committed rate | Unit |
| --- | --- | --- | --- |
| Residential | $8.00/GB | ~$5.00/GB at $1,999/month | per GB |
| Datacenter | from $0.60/GB | $0.42/GB at $1,999/month (5 TB included) | per GB |
| ISP / static residential | from $8.00/GB | $5.00/GB at $1,999/month (399 GB included) | per GB |
| Mobile (4G/5G) | ~$20.00/GB | from ~$7.00/GB | per GB |
| Web Unlocker | ~$3.00 per 1,000 successful requests | — | per request |
| SERP API | ~$0.75–$1.50 per 1,000 requests | — | per request |
| Scraping Browser | ~$8.00 per 1,000 sessions | — | per session |

A note on ISP proxies: Bright Data's own published page frames them per GB, but third-party trackers have reported per-IP pricing in the region of $1.30/IP/month on pay-as-you-go. Both figures circulate, they imply very different bills depending on how many concurrent sessions you run, so check the checkout page for your actual configuration rather than trusting either number.

The datacenter column is the one worth staring at. At $0.60/GB pay-as-you-go, datacenter bandwidth costs roughly 13× less than residential. A lot of projects that default to residential don't need it — they need to test whether datacenter IPs get blocked. If you're not seeing consistent 403s or 429s, you're paying a premium for anonymity you aren't using.

## What a year of Bright Data actually costs

Per-GB rates hide the coupon cliff and the unused-commitment problem. Modelled over twelve months, three realistic profiles look like this:

| Profile | Months 1–3 | Months 4–12 | Year total | Effective rate |
| --- | --- | --- | --- | --- |
| Pay as you go, 20 GB/month | $80/month | $160/month | $1,680 | ~$7.00/GB |
| $499/month tier | 141 GB/month | ~71 GB/month at the same spend | $5,988 | ~$5.64/GB |
| $1,999/month tier | 798 GB/month | ~339 GB/month at the same spend | $23,988 | ~$4.41/GB |

Nobody pays the headline $8. Nobody pays the promotional $4 either. Across a full year you land between the two.

The pay-as-you-go row is the interesting one. Twenty gigabytes a month costs $1,680 a year, and that's the profile where Bright Data's pricing structure stops making sense — you're paying enterprise rates for test-level volume, plus an identity verification step that a 20 GB user gains nothing from.

## The costs the plan cards don't mention

Bright Data's residential and mobile networks require KYC before use. In practice that means providing company or personal verification, and a representative may ask for a short video call. Web Unlocker doesn't require it, which is part of why the FAQ on the proxy pages nudges scraping buyers toward the managed API.

Other line items worth budgeting for:

- **City, ZIP and ASN targeting** carries a premium. Reported multipliers run 20–40% on residential depending on the combination. Note that Bright Data's own residential plan cards advertise country, state, city and ZIP targeting as included — the discrepancy between the cards and third-party cost reporting is unresolved, so confirm before you build a geo-heavy pipeline around it.
- **Overage.** Exceeding a committed volume costs 20–50% more per unit than your contracted rate.
- **Setup fees.** Enterprise contracts sometimes carry one-time onboarding charges in the $2,000–$10,000+ range for custom integrations or dedicated infrastructure.
- **Auto-renewal with escalation.** Contracts commonly renew automatically with 3–10% annual increases baked in.
- **Support.** Premium support and dedicated account management are billed separately, often at 10–25% of annual contract value.

At the enterprise end, Vendr's transaction data puts mid-market buyers committing 500 GB to 2 TB a month at $10,000–$50,000 monthly spend. Buyers in that band typically negotiate 15–25% below list. Below that band, list is close to what you pay.

## The scale floor problem

Bright Data is priced for the customer it wants. That customer has a procurement process, a compliance requirement and a predictable six-figure annual data budget. If you're that customer, the premium buys real capability: a residential network north of 400 million IPs across 195 countries, ZIP and ASN targeting, ISO 27001 documentation that survives a security review, and managed unblocking that handles hardened targets.

If you're spending $100–800 a month, you're on the wrong side of the discount curve. The volume discounts that make the math work — roughly 30% off pay-as-you-go at 100 GB and about 47% at 500 GB — sit behind commitment levels most small teams can't forecast honestly.

Run the same 240 GB that a pay-as-you-go user burns in a year through a flat $1/GB and you're at $240 instead of $1,680. Same data volume. Roughly 14% of the cost. What you give up is the surrounding platform, not the bytes.

## The other end of the market: $1/GB, pay as you go, no expiry

DataImpulse is the clearest example of the model that's been eating into the low end of enterprise pricing. Residential traffic is $1/GB with no subscription, no monthly minimum and traffic that doesn't expire. Buy 5 GB today, use it in six months, nothing is deducted in the interim.

The network is 90M+ IPs across 195 countries, with HTTP/HTTPS and SOCKS5, rotating and sticky sessions, and a published 99.51% success rate. Country targeting is included; city and ASN targeting is a paid add-on billed at a premium over the base rate.

Here's the full plan lineup as published:

| Product | Entry package | Standard rate | Bulk rate | Billing model | Get started |
| --- | --- | --- | --- | --- | --- |
| Residential | $5 / 5 GB | $1.00/GB | $800/1 TB ($0.80/GB); $0.70/GB at 5 TB | Pay as you go, traffic never expires | [Check DataImpulse residential proxy pricing](https://bit.ly/dataimPulse) |
| Premium residential | Pay per GB | $5.00/GB | — | Pay as you go | [See premium residential proxies](https://bit.ly/dataimPulse) |
| Datacenter | $5 / 10 GB | $0.50/GB | $450/1 TB ($0.45/GB); custom from $2,250 at 5 TB+ | Pay as you go | [View datacenter proxy plans](https://bit.ly/dataimPulse) |
| Mobile (3G/4G/5G/LTE) | $5 / 2.5 GB | $2.00/GB | $1,600/1 TB ($1.60/GB); custom from $8,000 at 5 TB+ | Pay as you go | [Compare mobile proxy pricing](https://bit.ly/dataimPulse) |

Two structural differences matter more than the headline rate.

**No expiry.** With Bright Data, unused commitment is gone at the end of the month. With DataImpulse, purchased bandwidth sits in the account until a request consumes it. For project-based scraping — a crawl this month, nothing next month, another crawl in Q3 — that removes the entire reason teams over-forecast.

**No usage floor.** Bright Data's cheapest meaningful tier starts at $499/month. DataImpulse's entry point is $5, and you can stress-test the network for $20 before deciding anything. New users also get a 7-day refund window.

## Where DataImpulse doesn't match up

The trade is real and worth naming rather than glossing.

DataImpulse launched in 2022 and is headquartered in Cyprus. It has no SOC 2 or ISO 27001 certification, which makes it a non-starter for procurement-gated enterprise buyers. Pool depth in Tier-3 geographies — sub-Saharan Africa, Central Asia — trails Bright Data and Oxylabs noticeably, though the headline markets (US, UK, Germany, Japan, Brazil) hold up. Independent benchmark data put Google SERP success around 99.74%, Amazon near 98.4%, and Cloudflare-fronted targets around 93.1%, with a ban rate near 1.1% and median latency around 740 ms.

There's also no scraping API. DataImpulse sells raw proxy connections; you write the request logic, retries, parsing and CAPTCHA handling yourself. Teams that want a managed unblocker and a SERP endpoint in the same invoice should stay with Bright Data, because the plumbing is the product there.

## Which one fits your bill

Run your own numbers against these cases:

- **Under 100 GB/month, mixed or unpredictable volume.** Pay-as-you-go at $1/GB with non-expiring traffic beats a metered tier you can't forecast. 👉 [Start with a $5 DataImpulse package and test on your own targets](https://bit.ly/dataimPulse)
- **Hardened targets at scale, plus compliance documentation.** Bright Data's premium buys pass rates and paperwork that a budget provider doesn't have. The per-GB rate is not the number you should be optimising when a third of your requests get blocked.
- **Steady 300 GB+/month with a procurement team.** Negotiate Bright Data's committed tiers. Reported discounts at that volume run close to 47% off pay-as-you-go, and above 1 TB the price becomes genuinely open to discussion.
- **Open targets, datacenter-eligible.** Neither residential option is the answer. Test datacenter first and cut your bill by an order of magnitude.
- **One-off crawls with gaps between them.** Monthly commitments punish this pattern. Non-expiring pay-as-you-go is built for it.

A useful sanity check: divide your monthly spend by the number of *successful* requests. A $1/GB provider that returns clean data beats a $5/GB provider you're re-running requests against. Both sides of the Bright Data pricing debate tend to skip that calculation.

## Questions people ask before buying either

**Is there a free plan?** No. Bright Data issues trial credits and matches a first deposit up to $500. DataImpulse starts at $5 with a 7-day refund window for new users. Both are ways of testing without committing, not free tiers.

**Why does Bright Data's headline rate keep changing?** Because it's showing different tiers with different promos applied in different places on the same site. Read the plan card that matches your actual monthly volume and ignore the navigation bar.

**Does the discount survive past three months?** Not automatically. RESIGB50 is time-limited, so plan month four at list unless you renegotiate.

**Can I mix proxy types at DataImpulse?** Yes — residential, premium residential, datacenter and mobile all run from one account and one balance, so you can route by target instead of maintaining two vendors.

**Is $1/GB realistic for real workloads?** It's realistic for mid-tier difficulty. Retail, e-commerce and SEO monitoring work fine. The hardest social platforms, where success rates separate, are where the enterprise tier earns its price.

The honest summary: Bright Data's pricing is coherent once you map the tiers, and it's genuinely built for organisations that need the network size and the compliance paperwork. Everyone below that line is subsidising a discount curve they'll never reach — and for those buyers, a pay-as-you-go provider that doesn't expire traffic is the cheaper route to the same data. 👉 [Compare DataImpulse's plans and start from $5](https://bit.ly/dataimPulse)
