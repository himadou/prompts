# Find a fast-selling emerging feature

## Goal

Find one recurring, paid-for problem in or around the Industry that a side-project developer can solve with a **single, reusable feature**. It must be fast to build, sold once within the Time to first sale, and able to grow into a real business.

- The customer's gain must be in money: money earned, money saved, or time saved that converts directly into money. Avoided regulatory fines don't count. For time saved, name how it becomes money (paid hours cut, outsourcing cut, freed capacity sold) and label that conversion.
- Prefer openings that few competitors cover. "Less obvious" means less competition, never less evidence of demand.
- Keep friction minimal: ideally the customer shares no private data.
- "No idea qualifies" is a valid result. Never invent a problem. A missing fact is **Unverified**, not **Failed**.

Terms in **bold** are defined once in the Reference part. The Procedure tells you what to do and in what order; look up the Reference when a step points to it.

---

# PART A: RUN

## How to run

| # | Step | Budget | Output | Gate (continue only if) |
|---|---|---|---|---|
| 1 | Discovery: scan | 8 searches (at least 4 on Emerging sources) | At most 3 focus areas | at least 1 focus area found, else report "no idea qualifies" |
| 2 | Discovery: deep | 16 searches, on the focus areas only | At most 3 candidate cards opened | — |
| 3 | Pre-check | 8 searches per candidate | Pre-check facts; criteria rated on each card | no Failed criterion; Unverified rule respected |
| 4 | First attacks (1, 2) | 1 search per attack, +1 English search for attack 1; 2 sources opened per attack | Attacks 1–2 rated on each card | neither attack is Fatal |
| 5 | Offer | no new searches | Value ladder and paid offer on each card | the offer respects the Data tiers and the value ladder rules |
| 6 | Remaining attacks (3–8) | 1 search per attack; 2 sources opened per attack | Attacks 3–8 rated on each card | no attack is Fatal |
| 7 | Selection and final recheck | 3 searches, selected candidate only | One selected card, or none | key sources confirmed by a second source |
| 8 | Report | — | Report assembled from the cards | Pre-report checklist passed |

Go deep rather than wide: a few well-evidenced candidates are worth more than many thin ones. Once a candidate is rejected, set its card status to rejected with the reason, and do no further work on it.

## Inputs

Inputs change on every run. Apply this run's values; never treat values from examples or past runs as rules. If an optional Input is empty, derive it during Discovery, cite a source and label it **inferred**. If it is filled, treat it as a starting point that may be incomplete.

**Required**
- **Run date:** today (use the actual current date in YYYY-MM-DD format; every time window in this prompt counts from it)
- **Industry:** Dental care activities (Activités de soins dentaires)
- **NAF codes:** 86.23Z
- **Company size:** self-employed, 1–9, 10–49 or 50–249 employees
- **Sale location:** Doubs (25), France
- **Time to first sale:** 14 days from the start of the work
- **Gain visible within:** 30 days after delivery, unless the gain can be calculated at delivery from the customer's own figures
- **Revenue indication:** about 500 € per month (a hint, not a threshold)
- **Languages:** report in English; searches and customer-facing text in French

**Optional (derive if empty):** Developer time (if empty, no hour cap; the build only has to fit the Time to first sale) · Prospect unit (the entity that buys) · Networks · Possible hosts · Job titles · Trade sources · Regulators and rules to watch · Regulated acts · Counted recoveries (money the customer loses to third parties, other than fines, whose recovery or prevention counts as a gain: refused claims, clawbacks, unpaid invoices, chargebacks…) · Segments to test · Comparable markets · Growth paths

**Already explored ideas (optional, never derived; may be empty, e.g. on the first run):** one line per idea: name · problem · payer · status (proposed, rejected, tested, selling, abandoned) · reason · date.
- Don't propose these ideas again, or a variant of one. A variant has the same payer, the same problem and the same way of creating the gain.
- Exception: a **rejected** or **abandoned** idea can return only if a fact dated after its exploration date removes its blocking reason. Cite that fact and label the idea **revisited**.
- Don't spend searches on explored ideas. They don't count toward the candidate limit.

```already_explored_ideas
```

## Step 1: Discovery, scan

**Do:**
1. Search the **Discovery options** (see Reference) to find where money is already spent, lost or delayed, including at handoffs with interacting industries (see **Scope**).
2. Choose at most 3 **focus areas**. A focus area is one recurring task or problem inside the Industry, or one handoff between the Industry and an interacting industry. Prefer areas with the most money at stake that a product could address at the lowest **Data tier**. Explain each choice.

**Output:** the focus areas, with sources.

## Step 2: Discovery, deep

**Do:** search only within the focus areas, working through the Discovery options again, until each focus area yields at most one strong candidate. Open a **Candidate card** for each (template in Part B) and fill in the Discovery fields.

**Output:** at most 3 candidate cards.

## Step 3: Pre-check

**Do:** for each candidate, verify with sources:
- the timing fact;
- the local rules that allow or block the offer;
- what the Networks already provide;
- the number of reachable prospects in the Sale location, and how they were counted;
- one example of someone paying for this outcome;
- the **Competition level**, with the offers found;
- the public data sources: owner, licence, freshness, access;
- the data tier, plus the form specification for T4 (each field, its values, their source), or the data model source for synthetic-first T5.

Then rate every **Hard criterion** on the card, using the **Ratings** rules.

**Output:** the Pre-check facts, and the criteria ratings on each card.
**Gate:** reject a candidate with a Failed criterion, more than one Unverified criterion, or an Unverified criterion 1, 6 or 7.

## Step 4: First attacks

**Do:** for each remaining candidate, write the kill findings for attacks 1 and 2, then run them (see **Attacks**).

**Output:** attacks 1–2 rated on each card.
**Gate:** reject the candidate if either attack is Fatal.

## Step 5: Offer

**Do:** for each remaining candidate, design the value ladder and the paid offer (see **Value ladder and offer**).

**Output:** value ladder, paid offer and risk reversal on each card.

## Step 6: Remaining attacks

**Do:** for each remaining candidate, write the kill findings for attacks 3 to 8, then run them (see **Attacks**). Redesign the offer, or add a pilot test, for each Weakened attack.

**Output:** attacks 3–8 rated on each card.
**Gate:** reject the candidate if any attack is Fatal.

## Step 7: Selection and final recheck

**Do:** if several candidates survive, compare them in this order:
1. **Gain and growth together.** The Revenue indication is a hint: don't reject a candidate for low first revenue if it can grow, and don't favour one only for high first revenue.
2. **Competition level:** Open, then Contested, then Crowded. A Crowded candidate wins only with a named angle that others don't cover.
3. **Data tier:** the lowest wins. A higher tier wins only if its gain or growth is clearly larger; justify this. Synthetic-first T5 ranks after T4. Last-resort T5 follows its rule.
4. **Tie-breaker:** the faster signed commitment, then the smaller build.

Then, for the selected candidate, confirm that the key sources (market size, prices, competitor claims, data availability) say what is claimed, with an independent second source.

**Output:** one selected card, or none. If nothing survives or the budget runs out, report that no idea qualifies.

## Step 8: Report

Assemble the report from the cards (see **Report** in Part B), then run the **Pre-report checklist**.

## If budget or context runs short

Protect, in this order: (1) the money evidence and calculation; (2) attacks 1 and 2; (3) the Hard criteria ratings; (4) the remaining attacks; (5) the offer detail. Shorten from the bottom of this list first. Never finish work on a rejected candidate. Say in the report what was cut.

## Pre-report checklist

- [ ] Every factual claim has a source and an evidence label.
- [ ] Criterion 1 has at least one verified input; no candidate has more than one Unverified criterion, nor one on criteria 1, 6 or 7.
- [ ] Every kill finding was written before its first search and not changed afterwards.
- [ ] The data tier is the lowest that works, and the T5 and Article 9 rules are respected.
- [ ] Every candidate examined has a line for Already explored ideas.

---

# PART B: REFERENCE

## Scope

The Industry is a starting point for exploration, not a limit. Do not look only at problems inside the Industry. Also explore problems that arise where the Industry works with other industries to get a job done or reach a goal. These **interacting industries** include, for example:
- suppliers of products, materials, equipment or services the Industry uses;
- businesses that help it operate (maintenance, logistics, staffing, finance, insurance, software, accounting, training);
- businesses that help it market and sell (agencies, platforms, directories, partners that send it customers);
- the businesses that are the Industry's own customers or that receive its outputs;
- any other industry that takes part in a shared task with the Industry, including ones that look unrelated at first.

For each problem, explain its relationship to the Industry, which interacting industry is involved, and the value of solving it for each side. Every candidate must involve the Industry: a problem that concerns only other industries is out of scope.

## Definitions

- **Sale:** a signed quote or order with a price and a payment date. Payment can come later.
- **Payer:** the signer. Either:
  - the owner or manager of a company under the NAF codes, within the Company size (independents, franchisees that are separate companies, owners of several sites); or
  - a business in an interacting industry (see Scope) that gains money when a problem in its work with the Industry is solved. Name its industry, its link to the Industry and why it pays. Company size applies to it too, and it must serve or work with Industry companies in the Sale location.
- **Network:** a brand or group a prospect belongs to. It often supplies software, booking and marketing. Check what it covers before assuming a gap.
- **Host:** a third party that gives access to prospects (federation, accountant, supplier, training body, software vendor).
- **Starving crowd (Gary Halbert):** a segment with urgent, poorly served demand that already spends money on the problem.
- **Productisable:** the same build sells to many customers with little extra work per customer.
- **Emerging sources:** the reasons an opening is still free in the Sale location.
  - **Recent change:** a rule, public dataset, technology, price or market change from the last 12 months that incumbents haven't reacted to.
  - **Arbitrage:** paid for in the Comparable markets or in another industry, but missing here.
  - **Workaround:** customers already pay for a makeshift solution (spreadsheets, staff time, agencies, generic tools).
  - **Adjacent payer:** a business in an interacting industry gains when the problem is solved, while competitors target only the obvious buyer.
  - **Operations:** a recurring daily task that is slow, manual or error-prone, and too small or specific for existing software to cover.

## Ratings

| Scale | Values | Used for | Rules |
|---|---|---|---|
| **Evidence label** | verified · inferred · assumption | every factual claim | **Verified:** stated by a cited source. **Inferred:** derived from verified facts with the reasoning shown (calculation, proxy, comparable market, sector standard). **Assumption:** no source and no derivation; it is not evidence. |
| **Source strength** | primary · secondary · weak | every money fact | Vendor marketing, self-reported results and anonymous reviews are weak. Also record the source date, whether an independent second source confirms it, and whether a figure is a price asked or a price paid (paid outranks asked). |
| **Criterion rating** | Met · Unverified · Failed | Hard criteria | **Met:** supported by verified or inferred facts. **Unverified:** no evidence either way within budget, or only assumptions; it becomes a pilot test. Before rating Unverified, check whether the fact can be inferred. **Failed:** contradicted by verified evidence. An inferred fact never makes a criterion Failed on its own. At most one Unverified per candidate, never on criteria 1, 6 or 7. List every inferred fact a criterion depends on as a pilot check. |
| **Attack rating** | Survives · Weakened · Fatal | Attacks | **Survives:** the kill finding was not found. **Weakened:** partial evidence; redesign the offer or add a pilot test. **Fatal:** the kill finding was found; reject the candidate. |
| **Competition level** | Open · Contested · Crowded | each candidate | Count the offers available to prospects in the Sale location, including national and online offers, not only businesses based there. **Crowded:** many offers. **Contested:** a few, with gaps. **Open:** none found. List the offers and how they were counted; if "Open" rests only on finding no offers, say so. |
| **Awareness** | aware · unaware | each candidate | Whether prospects know they have the problem. |

"No evidence found" proves nothing either way. Only a sale proves demand. Without a search tool, say so, mark Discovery, Pre-check and the attacks as not run, and validate nothing.

## Discovery options

1. **Emerging sources:**
   - recent changes and what they make newly possible or necessary;
   - features paid for in Comparable markets or neighbouring industries but absent here;
   - spending on workarounds (job adverts for manual tasks, templates sold, agencies doing repetitive work, complaints);
   - what interacting industries already pay for;
   - daily tasks that software ignores.
2. **Local and sector signals:** job adverts (Job titles); trade press and regulators; forums and owner groups; complaints; vendor pricing pages for the Prospect unit.
3. **Starving crowd:** start with the Segments to test, but don't assume they qualify.
4. **Comparable markets:** how the problem is solved there and the price. Adapt to local rules.
5. **Inputs and outputs:** the data the Industry needs to work faster or cheaper; the outputs it supplies to interacting industries, and how better quality or access would help them.
6. **Public data inventory:** datasets, registers, open data, rules and standards, with licence and update frequency.
7. **Reports and online content:** industry and government reports, news, academic papers, case studies, reviews, complaints and discussions.

## Data tiers

Use the lowest tier at which the paid product still works.

| Tier | What the customer provides |
|---|---|
| **T1** | Nothing; no data needed |
| **T2** | Nothing; general public data is used |
| **T3** | Nothing; public data about the customer is used (website, listings, registers, public reviews) |
| **T4** | A form with predefined fields and values. The product is built in advance from public data; the form personalises it with no upload and no manual help. The predefined values may be prepared in advance from public data, so the customer chooses from real options instead of guessing |
| **T5** | Private data (files, exports, account access, customer lists, financials) |

- A T4 form is valid only if its predefined values can be listed in advance from a source (public data, regulation, sector standard, named expert).
- **T5 is allowed in two cases:**
  1. **Synthetic-first T5:** the structure of the private data can be modelled accurately from a documented source (a standard export format, published software documentation, a sector data standard, a public template). Before the sale, the developer builds and demonstrates the product only on synthetic data built from that model, and never receives real private data. After the sale, the product runs on the customer's real data, preferably in the customer's own environment (the customer hosts or runs it). If the developer would process the real data, state the GDPR legal basis and any national rules for hosting that kind of data, and check them in Pre-check. Name the source of the data model. "Works the same on real data" stays an inferred fact until the first customer confirms it; make that confirmation part of delivery.
  2. **Last-resort T5:** the developer needs real private data to build or demonstrate the product. Allowed only if no T1–T4 or synthetic-first T5 candidate survived with a viable gain and growth path. Name the candidates that were checked.
- **Special-category data (Article 9 GDPR, e.g. health):** if the data subjects are individuals whose special-category data would be involved, last-resort T5 is excluded. Synthetic-first T5 is allowed only if the developer never accesses the real data (the customer hosts or runs the product). T3 and T4 must not collect such data.

## Product, money and developer

**Product:** a tool, dataset, document or content. It is one focused feature that plugs into the payer's existing tools and complements the ecosystem rather than competing with it. Never a full software or ERP. **DFY** (Done For You) is only a delivery mode, either manual delivery of the first version or a paid service on top. The manual share per customer should shrink over time.

**Money levers** (ways to make money for the customer; examples, not exhaustive):
- (a) new customers;
- (b) larger orders;
- (c) more frequent purchases;
- (d) recovering lost revenue, without straining the customer's relations with its own clients (see Counted recoveries);
- (e) margin and automation;
- (f) monetising idle capacity;
- (g) B2B2C partnerships;
- (h) faster cash flow;
- (i) productising knowledge;
- (j) outcome-based pricing, or capturing grants and tax credits;
- (k) preventing major losses (fines excluded).

**Developer:** an information expert, not a domain expert. Skills are information architecture, data curation, AI, AI coding agents and no-code.
- Domain knowledge comes from sources, the customer or a named expert.
- When the output needs domain judgment, the product produces a draft that the expert validates.
- The developer never performs or signs Regulated acts.

## Hard criteria

1. **Money:** a gain in euros, because the customer already pays staff, outsources the work, or comparable customers pay for a solution. Show the calculation and label each input. At least one input must be verified. Facts that can verify money already paid or lost (use at least one of the first six; the rest support the calculation): public price of a comparable product or service, paid job adverts for the manual task, outsourcing listings with a stated price, templates or datasets sold for the task, subsidies or tax credits covering the purchase, public tenders or supplier contracts for the same outcome, measured time per occurrence, frequency per customer per year, loaded hourly cost of the person doing the task, revenue or margin per affected unit, rate of loss or failure from a non-vendor source, number of reachable payers with counting method, count of paying customers of a comparable offer, median spend of the payer type on the nearest category. Rate each fact's source strength.
2. **Recurrence:** the problem occurs at least yearly and survives the first fix.
3. **Reason to act now:** the problem is live, or recurs within 90 days of the Run date.
4. **Access:** most prospects have a public contact channel, and the payer can sign without long procurement.
5. **Build:** a first sellable version, including outreach, can be ready in time to sign a sale within the Time to first sale, and within Developer time if that Input is set. State the estimated hours, split into pre-sale build, outreach and per-customer delivery.
6. **Developer fit:** no domain expertise is needed from the developer.
7. **Data minimisation:** the data tier is stated and justified, and the T5 rules are respected.
8. **Productisable:** per-customer hours are small compared with the price.
9. **Market and growth:** a small, irregular first market is fine. State the growth path, starting from the Growth paths, and what must be true for it to become a real business.

## Value ladder and offer

Prove value before asking for money, and ask for money before asking for private data. No stage asks for more than the previous stages have earned. Skip the stages that don't apply, and give the developer time per prospect for each stage.

| Stage | Customer gives | Customer gets |
|---|---|---|
| 0. Demo | nothing | generic sample (T1–T2), or a demo on synthetic data (synthetic-first T5) |
| 1. Free analysis | nothing | output personalised from their public data (T3) |
| 2. Form (T4) | predefined answers | tailored preview |
| 3. Paid product | signed commitment | full product |
| 4. Private data (T5 only) | data, after payment, processed preferably in their own environment | the product running on their real data, with its GDPR legal basis |

- **Free stages:**
  - The first contact delivers stage 0 or 1, with no call, sign-up, data or purchase requested.
  - The value is real. Cite a comparable price, or label it assumption and explain.
  - Use only public data, synthetic data or form answers, and follow local prospecting rules (France: B2B email relevant to the role, with an opt-out) and GDPR.
  - Each stage must be cheap enough to produce for enough prospects.
- **Awareness check:** for unaware prospects, the first free stage must show the problem and its cost using the prospect's own public data. If it can't, criterion 3 is at most Unverified.
- **Paid offer:**
  - It adds what the free stages don't.
  - It has a price, a payment date and a delivery mode (self-serve, partly DFY or full DFY).
  - It includes risk reversal (Jay Abraham), with guarantee conditions that depend only on what the developer controls.

## Attacks

**Rules:**
- Try to kill each idea with real searches; memory doesn't count, and Pre-check facts are not searched again.
- Before an attack's first search, write a specific, findable kill finding for it (a product, price, rule or documented statement, not an absence of data). Don't change it afterwards.
- Word each search to find disconfirming evidence, in the search language, using trade terms.
- Rate each attack using the **Ratings** table.

**The attacks:**
1. **Existing solutions:** a free tool, a low-cost product, a feature of software prospects already use, or the host itself solves the problem well enough.
   - **Fatal** only if that solution reaches about half of the prospects or more (cite a usage share, a customer count, or bundling in software that most prospects use).
   - A solution with negligible or unknown reach, complaints about it, or coverage of only some networks makes the attack **Weakened**, not Fatal.
2. **Willingness to pay:** evidence that prospects refuse to pay, have no budget, do it in-house, or buy only through head office or long procurement.
3. **Host reality** (if a host is proposed): the host competes, or is barred from commissions or endorsements.
4. **Recurring use:** low repeat use, high churn, or the problem vanishes after the first fix.
5. **Coming changes:** search only for changes not already in the Pre-check facts.
   - **Fatal:** an adopted rule, a launched product or a dated rollout that removes the problem, or takes most of the market, within 12 months.
   - **Weakened:** a change that is announced, proposed, or would affect only part of the market.
6. **DIY with AI:** an owner could solve it with general AI tools.
   - **Fatal:** a documented example (tutorial, template, prompt pack, public post) shows owners getting an output of equivalent use with general AI in about an hour, using only what they already have, and the product adds nothing that needs refreshing.
   - **Weakened:** it can be done with general AI, but only with data curation, recurring updates, integration or validation that the owner would have to repeat. Redesign the offer so the price pays for that recurring part.
   - **Survives:** the value depends on curated or updated data, integration or validated output that general AI tools don't provide.
7. **Data friction:** comparable tools only work with private data, prospects refuse such forms, the predefined values are too generic to beat free options, or (synthetic-first T5) the real data differs from the documented model.
8. **Why nobody does it** (Contested or Open only): a documented structural reason, such as a failed product, a legal block, an incoming dominant player, or no budget. An absence of competitors alone is not a kill finding.

## Candidate card

Open one card per candidate in Step 2 and update it at every step. Fill in each field with its source and evidence label. Stop updating a card once its status is rejected.

```
CANDIDATE: <name>                         STATUS: open | rejected (step, reason) | selected
--- Discovery (Steps 1–2)
Focus area:                 <focus area>
Problem and payer:          <who has it, how often> · payer: <type, industry>
Interacting industry:       <industry, relationship to the Industry> or none
Discovery options:          <which found it>
Emerging sources:           <list> or none
Timing leverage:            <dated source, why now, when the window closes> or none
First estimates:            competition <level> · awareness <aware|unaware> · data tier <T1–T5>
--- Pre-check (Step 3)
Pre-check facts:            timing · local rules · network coverage · reachable prospects (count, method) ·
                            example of paying · offers found · public data (owner, licence, freshness, access) ·
                            T4 form spec or synthetic data model source
Money calculation:          <inputs with labels, source strength, asked/paid> → low–high € range
Criteria 1–9:               <rating + one-line justification each>
Pilot checks:               <Unverified criterion, inferred facts>
--- Attacks (Steps 4 and 6)
Attack n:                   kill finding (written first) · search · sources · rating
--- Offer (Step 5)
Value ladder:               <stages used, developer time per prospect each>
Paid offer:                 price · payment date · delivery mode · risk reversal
Hours:                      pre-sale build · outreach · per customer
```

## Report

Recommend one idea at most. Build the report from the cards.

**If an idea survives:**
1. **Problem:** the idea's name, who has the problem, how often, and the gain in euros (calculation, labels, low–high range). Include its focus area, the discovery options that found it, and the interacting industry involved, if any.
2. **Why common, and why still open:** evidence, timing leverage, emerging sources, competition level (with offers found), and awareness.
3. **Data tier:** why a lower tier fails. For synthetic-first T5, the data model source and how real-data fit will be confirmed. For last-resort T5, the candidates checked first.
4. **Stack:**
   - tools and public data sources (with licence);
   - inputs and outputs;
   - the T4 form specification, or the synthetic data model;
   - what is automated and what is manual;
   - estimated hours for the pre-sale build, outreach and per customer.
5. **Why customers will choose it** over the network's tools, competitors, in-house work, free options and general AI.
6. **First sale:**
   - the value ladder;
   - the paid offer (price, payment date, delivery mode);
   - the risk reversal;
   - the first prospects, or how to list them;
   - the outreach channel;
   - a day-by-day plan to a signed commitment.
7. **Growth path:** starting from the Growth paths, and what must be true for it to become a real business.
8. **Adversarial results:** the kill findings written in advance, a table of ratings with sources, and the pilot tests for Weakened attacks, the Unverified criterion and the inferred facts that criteria depend on.
9. **Rejected ideas:** each with its emerging source, competition level, data tier, and failed criterion or kill finding.
10. **Evidence limits:** the main assumptions, what was cut if the budget ran short, and what the first sale would prove.
11. **Explored ideas:** the ideas from the Input that were skipped, and any idea revisited with the new fact that justifies it.
12. **Line to add to Already explored ideas:** one line for every candidate examined in this run, in the Input's format, ready to paste into the next run. Use status **proposed** for the recommended idea.

**If nothing survives:**
- List the candidates, each with its emerging source, competition level, data tier, and failed criterion or kill finding.
- Name the criterion that blocked the most candidates.
- Describe the best near-miss: what blocked it, and the smallest change to the Inputs or the offer that would let it qualify. Do not recommend it.
- Give the lines to add to Already explored ideas, as above.