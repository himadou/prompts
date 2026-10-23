## Variables (edit these)
- {{CURRENT_DATE}}: 22 October 2026
- {{RESEARCH_SCOPE}}: Russia
- {{LAUNCH_MARKET}}: Amazon France
- {{SAVINGS_LEVEL}}: high
- {{REPURCHASE_FREQUENCY}}: high
- {{NUMBER_OF_TOOLS}}: 10–15
- {{TOP_N}}: 5

---

## Research task: find a proven, lightweight savings tool I can build and monetize with marketplace affiliate links

Today's date is {{CURRENT_DATE}}. Treat this as "now": only include tools, programs, rates and rules that are current as of this date, and flag anything that may have changed.

Context about me: Applied AI engineer and developer, solo, building with Claude Code. Launch market: {{LAUNCH_MARKET}}. Build time is flexible. Assume a low-budget pilot: favor organic, low-cost acquisition over paid ads.

My goal: identify a lightweight, consumer-facing tool to build that helps shoppers save money on a major marketplace and complements it (no own checkout). It can be a website, browser extension or small app, monetized through marketplace affiliate programs such as Amazon Associates. I want recurring commissions from each customer over time, not one-off sales. I am not looking to promote existing tools; I want to study them to find proven categories and gaps.

Research method (mandatory):
- Actively use your web search and page-fetching tools throughout. Do not rely on training data or memory for any current fact: tool existence and status, features, pricing, traction, affiliate commission rates, cookie durations, program rules or terms of service.
- Verify each key claim against at least one current source, preferably official (the tool's site, official affiliate program pages, app/extension store listings, company announcements).
- If you cannot verify something, mark it "unverified" rather than filling the gap from memory.
- Search in the local languages of the research scope, not only in English.
- Express money amounts in the local currency of {{LAUNCH_MARKET}} (convert and note the rate when needed).

Savings level:
Classify every tool's typical customer savings using these definitions:
- HIGH: saves at least 20% of the purchase price on a typical order, OR roughly 50+ per order in local currency, OR an estimated 300+ per customer per year.
- MODERATE: saves 5–20% on a typical order, OR roughly 10–50 per order, OR 100–300 per customer per year.
- LOW: below moderate on all three measures.
Requested level: {{SAVINGS_LEVEL}}. Include only tools at or above this level ("any" includes all).

Repurchase frequency:
Classify how often a typical customer buys the supported products:
- HIGH: monthly or more often (e.g. groceries, diapers, pet food, coffee, cleaning and hygiene products, supplements).
- MODERATE: every 1–6 months (e.g. contact lenses, printer ink, filters, cosmetics, vitamins).
- LOW: yearly or less (e.g. electronics, appliances, furniture).
Requested level: {{REPURCHASE_FREQUENCY}}. Include only tools at or above this level ("any" includes all).

Return trigger:
Because marketplace affiliate cookies are short (check the current duration for each program), a commission is earned only if the customer comes back through my link before each purchase. For every tool, identify what brings the customer back: price-drop or restock alerts, repurchase reminders, email or push digests, a saved list, a browser extension active at checkout, or habit. Rate it:
- STRONG: an automatic trigger that fires before most repurchases (alert, reminder, extension at the point of purchase).
- WEAK: relies on the customer remembering to return.
- NONE: one-time use.

List any notable tools excluded by the savings or frequency filters in one short line each.

Step 1 – Research existing tools.
Research scope: {{RESEARCH_SCOPE}}.
Find existing consumer savings tools used with major marketplaces in this scope (e.g. Amazon, AliExpress, Mercado Libre, Flipkart, Shopee, Jumia, Allegro, Rakuten, Coupang, Cdiscount, Zalando; use those relevant to the scope). Example categories: price trackers, unit-price comparators, deal finders, subscribe-and-save optimizers, repurchase reminders, cashback, coupon extensions. These are illustrations, not preferences. Exclude standalone marketplaces and tools for affiliate marketers. Target {{NUMBER_OF_TOOLS}} tools, grouped by category; flag any shut down or inactive as of {{CURRENT_DATE}}.

For each tool:
1. Name, country/language of origin, link.
2. What it does and the customer problem it solves.
3. Supported marketplaces and 2–3 concrete example products.
4. Savings level (HIGH / MODERATE / LOW) with the numbers behind it: savings per purchase and savings per customer per year (state assumptions).
5. Repurchase frequency (HIGH / MODERATE / LOW) with the typical interval for the example products.
6. Return trigger (STRONG / WEAK / NONE) and how it works.
7. How it makes money (marketplace affiliate, network, own deals, subscription, ads), with source.
8. Estimated affiliate revenue per active customer per year: purchases per year × average order value × commission rate × share of purchases made through the link (state every assumption).
9. Target audience, main acquisition channel, and traction (installs, reviews, users, funding), with source and date.
10. Main weakness or unmet customer need.
11. Signals: tag each tool with any that apply:
   - ★ PROVEN: strong verified traction (e.g. 100k+ users/installs, or funding)
   - ↻ RECURRING: HIGH repurchase frequency AND STRONG return trigger
   - ⚠ RISK: known ToS, policy or reputation problems
   - ◎ GAP: clear unmet need or weak/absent competitor in {{LAUNCH_MARKET}}
   - ✕ INACTIVE: shut down or no longer maintained

Step 2 – Evaluate categories as opportunities for me.
Evaluate each category for {{LAUNCH_MARKET}} specifically, even if the inspiration comes from elsewhere. For each category, state:
- Which marketplace affiliate programs I could use in {{LAUNCH_MARKET}}: commission rates for the relevant product categories (especially recurring-purchase categories, which often have lower rates), cookie duration, approval requirements, payout conditions, and any early-sales requirements to keep the account active or to access product data APIs. Link to official pages and give the date checked.
- Whether the model is allowed under those programs' current terms (e.g. commission-sharing/rebate rules, extension and link-placement rules, price-data display rules, email/link usage rules, API access conditions, scraping restrictions).
- How a new tool in this category would bring customers back before each purchase, and whether that trigger is allowed under the program terms.
- Competition level in {{LAUNCH_MARKET}} and a realistic way to stand out.
- Build effort for a solo developer (data source, MVP scope).

Score each category 1–5 and weight as follows:
customer value 10%, savings level 15%, repurchase frequency 15%, return trigger strength 10%, affiliate revenue per customer per year 15%, ease of acquisition 15%, build/pilot feasibility 10%, platform/ToS risk (inverted) 10%.
Assign each category a tier from its weighted score:
- TIER A (4.0+): strong opportunity, worth piloting
- TIER B (3.0–3.9): viable with a clear angle
- TIER C (below 3.0): not recommended now

Output format:
1. At-a-glance summary (start of the report): a single table of the top {{TOP_N}} opportunities, sorted by weighted score, with columns: rank, category, tier, weighted score, savings level, repurchase frequency, return trigger, estimated revenue per customer per year, signals, best example tool, one-line reason.
2. Full scoring table for all categories.
3. Tool-by-tool details (Step 1), grouped by category, with TIER A categories first.
4. Excluded tools (one line each).
5. Final recommendation.

Rules: use verifiable, current sources and official program pages. Label every figure as fact (with source and date) or estimate (with reasoning).

Final recommendation: the single best quick-win tool for me to build in {{LAUNCH_MARKET}}, including:
- MVP scope, data source, target marketplace, and the affiliate program to use.
- The return trigger to build into the MVP so customers come back through my link before each repurchase.
- A 30-day pilot plan with success metrics (e.g. visitors, affiliate clicks, first qualifying sales, share of users who return within 30 days).
- Where to find the first 50–100 users: name specific communities, forums, subreddits, groups or content niches in {{LAUNCH_MARKET}}, and how to approach them.
- The 2–3 channels most likely to scale distribution afterwards (e.g. SEO, extension store listing, short-form video, deal communities).
- The main risk to watch.