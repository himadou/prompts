# Find a fast-selling emerging feature (prompt v2.1)

## Goal

Find one recurring, paid-for problem involving the Industry that a side-project developer can solve with a **single, reusable feature**: fast to build, sold once within the Time to first sale, able to grow into a real business.

- The payer's gain is in money: earned, saved, or time saved that converts into money (name and label the conversion: paid hours cut, outsourcing cut, freed capacity sold). Avoided fines don't count.
- Prefer openings few competitors cover ("less obvious" means less competition, never less evidence of demand) and minimal friction (ideally no private data).
- "No idea qualifies" is a valid result. Never invent a problem. A missing fact is **Unverified**, not **Failed**.

Part 0 changes between runs. Part A is the procedure. Part B defines every **bold** term once.

---

# PART 0: RUN SETUP

After each run, the report's "Run memory update" gives a full replacement for each memory block, under the same name.

```run_inputs
Run date:            today, YYYY-MM-DD (all time windows count from it)
Industry:            Dental care activities (Activités de soins dentaires)
NAF codes:           86.23Z
Company size:        self-employed, 1–9, 10–49 or 50–249 employees (company payers only)
Sale location:       Doubs (25), France
Time to first sale: 30 days from the start of the work (build ≤ 10 days); payment due ≤ 30 days after acceptance
Gain visible within: 30 days after delivery, unless calculable at delivery from the payer's own figures
Revenue indication:  about 500 € per month in total for the developer, excl. VAT (a hint, not a threshold)
Payer types:         any (Industry companies, interacting businesses, public bodies, associations, individuals, or none of these)
Self-entered health data: allowed (or "excluded")
Languages:           report in English; searches and customer-facing text in French
```

Optional inputs: one line each, as value · source · date · label (verified, inferred, or "set by the person", which the run never changes). Empty lines are derived in Step 1 and labelled inferred; filled lines are a starting point that may be incomplete.

```optional_inputs
Developer time: (empty: no hour cap beyond the Time to first sale)
Prospect unit:
Networks:
Possible hosts:
Job titles or segments:
Trade sources:
Regulators and rules to watch:
Regulated acts:
Professional ethics rules:
Counted recoveries:
Segments to test:
Comparable markets:
Growth paths:
Public data sources:
```

Already explored ideas: name · problem · payer · status (proposed, rejected, tested, selling, abandoned) · reason · date. Don't propose them again or a variant (same payer, problem and way of creating the gain), and don't spend searches on them. A rejected or abandoned idea may return, labelled **revisited**, only if a fact dated after its exploration removes its blocking reason.

```already_explored_ideas
C1 devis follow-up and acceptance tracker · quotes abandoned by patients, practice owner recovers revenue · dental practices 1–49 employees, Doubs · rejected (near-miss, on watch list) · attack 1 Weakened (LaFraise 1,200+ users, Doctolib Pro, Dental Pilote, Julie); criterion 1 and gain-in-30-days Unverified; CNIL consent friction on patient messaging; template-only version Fatal on attack 6 · 2026-11-13
C2 DUERP / compliance kit · yearly risk-assessment update · dental practices · rejected · criterion 2 Failed (no yearly update under 11 employees); attack 1 (free INRS OiRA tool) · 2026-11-13
C3 lab dunning of late-paying dentists · lab receivables · dental labs · rejected · criterion 1 Unverified (advocacy claim only) · 2026-11-13
E-invoicing reception kit · incoming invoices from 1 Sept 2026 · dental practices · rejected · attack 5 (dated rollout, vendor bundling) · 2026-11-13
CCN IDCC 1619 salary calculator · salary grid lookup · dental practices · rejected · criterion 2 (one-off check) · 2026-11-13
No-show deposits · missed appointments · dental practices · rejected · attack 1 (already in Doctolib Pro and others) · 2026-11-13
```

Run memory, written by past runs:

```verified_facts
Decree 2026-809: ticket modérateur 50–60 % from 1 Jan 2027 (Assurance maladie share 40–50 % vs 60 %) · selectra.info, caducee.net · secondary · 2026-11-13 · re-check 2026-12-15
Reimbursement rate not yet fixed as of 22 Oct 2026 · selectra.info · secondary · 2026-11-13 · re-check 2026-12-01
LaFraise: 1,200+ practitioners, +250/month, target 5,000 by end 2026 (vendor claim) · lessentieldeleco.fr · secondary · 2026-11-13 · re-check 2027-02-01
LaFraise "+24 % acceptance" · same article · weak (vendor claim) · 2026-11-13 · re-check 2027-02-01
Santéclair 2014 study: 38 % no treatment after 1 year, 17.6 % partial, 42.6 % full · Quotidien du Médecin · secondary (dated) · 2026-11-13 · not time-sensitive
CNIL: SMS/email prospection to individuals needs prior consent; page updated 10 June 2026 · cnil.fr · primary · 2026-11-13 · re-check 2027-06-10
Dental reminder messages must not reveal the care · donneespersonnelles.fr · weak · 2026-11-13 · re-check 2027-06-10
Doctolib Pro lists quote and treatment-plan follow-up · indy.fr · weak · 2026-11-13 · re-check 2027-03-01
Agency figures (Kolonell: 45–100 k€ bespoke software, SEO retainers) · weak · illustrative only · do not reuse
```

```coverage_log
Emerging source: reimbursement cut 2027 · interacting party: mutuelles/patients · C1 · 2026-11-13
Emerging source: 100% santé quotes · none · C1 · 2026-11-13
Emerging source: AI-devis vendors · none · C1 contested · 2026-11-13
Emerging source: compliance (DUERP) · none · C2 · 2026-11-13
Emerging source: lab payment delays · dental labs · C3 · 2026-11-13
Emerging source: e-invoicing reception · none · dry · 2026-11-13
Emerging source: orphaned customers (vendor shutdown) · none · dry · 2026-11-13
Emerging source: tiers-payant rejects (NOEMIE/ARL/RSP) · CPAM · dry (no dentist-specific loss figure) · 2026-11-13
Not reached: Doubs counts (RPPS/ONCD), prosthetic lab-order tracking, hygiene/stérilisation traceability
```

```watch_list
C1 rescoped as CSV-based pending-quote report (no patient messaging) · blocked by unverified French acceptance and gain figures, and by software overlap · needs a verified figure plus a check that Julie, Desmos, LOGOSw and Visiodent lack a pending-quote export · check by 2027-02-01 (after the January reimbursement cut)
```

```process_stats
2026-11-13 · v2.1 · approx. searches: Step 1 about 8, Step 2 about 16–20, Step 3 about 16, last batches 12 (exact counts lost at context reset) · candidates opened 3 (+3 discarded at scan) · rejections: criterion 1 ×1 (C3), criterion 2 ×1 (C2), attack 1 ×1 (C2, plus C1 Weakened) · steps cut: Steps 5, 6 and 7 not run in full; no field verification
```

Field results, written by the person only:

```field_results
(idea · date · prospects contacted · replies · objections, verbatim in French · price proposed · accepted/refused · sale yes/no)
```

---

# PART A: PROCEDURE

| # | Step | Budget | Gate (reject or stop otherwise) |
|---|---|---|---|
| 0 | Load memory | 2 searches | — |
| 1 | Discovery: scan | 8 searches (≥4 on Emerging sources) + up to 6 to derive empty optional inputs | ≥1 focus area, else report "no idea qualifies" |
| 2 | Discovery: deep | 16 searches, focus areas only | — |
| 3 | Pre-check | 8 searches per candidate | no Failed criterion; Unverified rule |
| 4 | Attacks 1–2 | 1 search each, +1 English search for attack 1 | neither Fatal |
| 5 | Offer | none | no Failed criterion; Unverified rule; offer follows Data tiers and Value ladder |
| 6 | Attacks 3–8 | 1 search each | none Fatal |
| 7 | Selection and recheck | 4 searches, selected candidate only | key sources confirmed, or card re-rated |
| 8 | Report | — | Pre-report checklist |

A search is one query, after which up to 2 pages may be opened. A `verified_facts` line before its re-check date is reused without searching (cite "run memory" and its source). `field_results` are primary evidence and outrank all web sources. Go deep rather than wide. A rejected candidate gets its status and reason on its card, then no more work.

**0. Load memory.** Load filled inputs and valid facts. Check watch-list items past their check-by date; a resolved one may return as revisited. From the coverage log, list the least-explored emerging source types and interacting parties, and the areas marked dry. From `field_results`, list the objections heard.

**1. Scan.** Derive the empty optional inputs Discovery needs. Search the **Discovery options** for where money is spent, lost or delayed, inside the Industry and at its handoffs (see **Scope**). Spend at least half of the scan on the least-explored paths, and at least 2 searches on areas absent from the coverage log. Don't reopen a dry area without a new dated fact. Choose at most 3 **focus areas** (one recurring task or problem, or one handoff), preferring the most money at stake at the lowest **Data tier**, and explain each choice with sources.

**2. Deep.** Within the focus areas only, stop each one at one strong candidate or when its budget share is spent. Open a **Candidate card** for each (at most 3).

**3. Pre-check.** Verify each Pre-check field of the card with sources, then rate the **Hard criteria**. Criteria 5 and 8 are provisional (estimated hours, price range of comparables) until Step 5.

**4 and 6. Attacks.** Run the **Attacks**. In attack 1, use the English search to find international or online tools sold into the country. After Step 6, redesign the offer or add a pilot test for each Weakened attack.

**5. Offer.** Using only facts on the card, design the **Value ladder and offer** and the hours. Confirm criteria 5 and 8, and re-rate criterion 3 with the awareness check.

**7. Selection.** Rank survivors by:
1. first-market size (low end of the yearly € gain per payer × reachable payers), then how well the growth path is evidenced. Revenue indication is only a hint.
2. developer hours per signed customer, counting consumer consent and withdrawal friction.
3. Competition level: Open, then Contested, then Crowded. A Crowded candidate needs a named angle others don't cover.
4. the lowest Data tier. A higher one wins only with clearly larger gain or growth, justified. Synthetic-first T5 ranks after T4.
5. the faster signed commitment, then the smaller build.

Then confirm the selected candidate's key sources live (market size, prices, competitor claims, data availability) with an independent second source, including facts taken from memory. If one fails: downgrade the claim one evidence level, re-rate dependent criteria, and if a gate breaks, reject and move to the next survivor with the remaining searches.

**8. Report.** See **Report**.

**If budget runs short**, protect in this order: money evidence; attacks 1–2; criteria ratings; remaining attacks; offer detail; memory update (may shrink to new lines). Shorten justifications only; never skip a gate. Report what was cut.

**Pre-report checklist:**
- [ ] Every claim has a source and an evidence label.
- [ ] Criterion 1 has a verified input; the Unverified rule holds.
- [ ] Every kill finding appears before its search and was not changed.
- [ ] The lowest workable data tier is used, and the health data rules hold.
- [ ] Prices are excl. VAT, with the real cost shown where VAT isn't recoverable.
- [ ] Matching `field_results` objections were used as kill findings.
- [ ] Every candidate has an explored-ideas line; every memory block is complete and keeps its name.

---

# PART B: REFERENCE

## Scope and payer

The Industry is a starting point, not a limit. Explore problems inside it and where it works with others:
- **interacting industries:** suppliers; operations help (maintenance, logistics, staffing, finance, insurance, software, accounting, training); marketing and sales help (agencies, platforms, directories, referrers); businesses receiving its outputs; any industry in a shared task, even one that looks unrelated;
- **outside parties:** the Industry's end clients as individuals, public bodies, associations, anyone in a shared task.

Every candidate must involve the Industry, whoever pays. State the relationship, who is involved, and the value for each side.

- **Payer:** whoever commits to pay and pays, within Payer types, in any industry or none. State who they are, how the Industry is involved, why they pay, and how the gain reaches them in money. Company size applies only to companies. The payer must be reachable in the Sale location. The payer can be any body, anything.
- **Consumer payer:** an individual buying outside any professional activity; consumer law and B2C prospecting rules apply.
- **Sale:** an order with a price and payment date (payment may come later). For consumer payers it counts once paid, or once the legal withdrawal period has passed or been validly waived.
- **Network:** a brand or group a prospect belongs to, often supplying software, booking and marketing. Check its coverage before assuming a gap.
- **Host:** a third party giving access to prospects (federation, accountant, supplier, training body, software vendor, patient or consumer association).
- **Professional ethics rules:** rules of a regulated profession on soliciting clients, advertising, fee-sharing or kickbacks (dentistry: its code of ethics).
- **Starving crowd (Halbert):** a segment with urgent, poorly served demand already spending on the problem.
- **Productisable:** one build sells to many payers with little extra work each.

## Discovery options

1. **Emerging sources**, the reasons an opening is still free:
   - **Recent change:** a rule, dataset, technology, price or market change from the last 12 months that incumbents haven't reacted to.
   - **Budget waste**: Find existing budgets and discover what businesses are already paying for inefficiently.
   - **Arbitrage:** paid for in Comparable markets or another industry, missing here.
   - **Workaround:** spending on makeshift solutions (job adverts for manual tasks, templates sold, agencies, spreadsheets, complaints).
   - **Unexpected payer:** someone other than the obvious buyer gains, while competitors target only the obvious buyer.
   - **Operations:** a slow, manual or error-prone daily task too small or specific for existing software.

   - **Orphaned customers**: When a product is acquired, sunset, price-hiked or neglected after a merger, its customers become unusually open to switching. Watch acquisition news, “we’re sunsetting” emails and sudden pricing changes. The first six months after the event is the best time to sell.

   - **Expiring moats**: Patents expire, exclusive contracts end, and data-portability rules (Open Banking, DMA-style interoperability) break lock-in. Each event opens a window for a challenger or for tooling around the new openness.

2. **Local and sector signals:** job adverts, trade press, regulators, owner and consumer forums, complaints, vendor pricing pages.
3. **Starving crowd:** start with Segments to test, without assuming they qualify.
4. **Comparable markets:** how and at what price the problem is solved there, adapted to local rules.
5. **Inputs and outputs:** data the Industry needs to work faster or cheaper; outputs it supplies to others, and how better quality or access would help them.
6. **Public data inventory:** datasets, registers, open data, rules and standards, with licence and update frequency.
7. **Reports and content:** industry and government reports, news, papers, case studies, reviews, discussions.

## Ratings

- **Evidence label:**
  - **verified:** stated by a cited source or by `field_results`;
  - **inferred:** derived from verified facts with the reasoning shown;
  - **assumption:** neither; not evidence.
- **Source strength** (every money fact): primary, secondary or weak. Official sources and `field_results` are primary; vendor marketing, self-reported results and anonymous reviews are weak. Record the date, any independent confirmation, and whether a price is asked or paid (paid outranks asked).
- **Criterion rating:**
  - **Met:** supported by verified or inferred facts.
  - **Unverified:** no evidence within budget, or only assumptions. Check first whether the fact can be inferred; it becomes a pilot test.
  - **Failed:** contradicted by verified evidence; an inferred fact alone never fails a criterion.
  - **Unverified rule:** at most one Unverified per candidate, never on criteria 1, 6 or 7. List every inferred fact a criterion depends on as a pilot check.
- **Attack rating:**
  - **Survives:** the kill finding was not found.
  - **Weakened:** partial evidence; redesign or add a pilot test.
  - **Fatal:** the kill finding was found; reject.
  - **not applicable:** only where the attack says so.
- **Competition level:** count offers available to prospects in the Sale location, including national and online ones. **Crowded:** many offers. **Contested:** a few, with gaps. **Open:** none found; say if that rests only on not finding any. List the offers and how they were counted.
- **Awareness:** aware or unaware of the problem.
- **Memory re-check after:** 3 months for prices and competitor offers; 6 months for rules and licences; 12 months for counts and dataset inventories. Past that, search again or label the fact an assumption.

"No evidence found" proves nothing; only a sale proves demand. Without a search tool, say so and validate nothing.

## Data tiers

Use the lowest tier at which the paid product works.

- **T1:** no data.
- **T2:** general public data.
- **T3:** public data about the payer (website, listings, registers, reviews).
- **T4:** a form with predefined fields and values, each value listable in advance from a source (public data, regulation, sector standard, named expert). It personalises a product prebuilt from public data, with no upload and no manual help.
- **T5:** private data (files, exports, account access, customer lists, financials). Allowed only as:
  - **Synthetic-first T5:**
    - the data structure is modelled from a documented source (standard export, software documentation, sector standard, public template); name it.
    - Before the sale, the product is built and demonstrated only on synthetic data from that model, which may be unstructured documents an LLM can handle, such as invoices.
    - After the sale, it runs on real data, preferably in the payer's environment. If the developer processes real data, state the GDPR legal basis and national hosting rules, checked in Pre-check.
    - "Works the same on real data" stays inferred until the first customer confirms it during delivery.
  - **Last-resort T5:** real private data is needed to build or demonstrate. Allowed only if no lower-tier candidate survived with viable gain and growth; name those checked.
- **Health and other Article 9 GDPR data about individuals:**
  - last-resort T5 is excluded;
  - synthetic-first T5 is allowed only if the developer never accesses real data;
  - T3 and T4 must not collect such data, except **self-entered health data** if the Input allows it. Then an individual enters their own data for their own benefit, with explicit consent, no developer access, and processing on their device or with a certified health-data host where required (France: HDS). Pre-check verifies each condition.

## Money

**Levers** (non-exhaustive):
- (a) new customers, or serving more with the same staff when demand exceeds capacity
- (b) larger orders
- (c) more frequent purchases
- (d) recovering lost revenue without straining client relations (see Counted recoveries)
- (e) margin and automation
- (f) monetising idle capacity
- (g) B2B2C partnerships
- (h) faster cash flow
- (i) productising knowledge
- (j) outcome-based pricing, grants and tax credits
- (k) preventing major losses
- (l) replacing a compliance service or task already paid for (the cost counts, avoided fines don't)

**Individuals:** count only cash (out-of-pocket costs or fees avoided, money recovered or earned). Their time counts only if it is paid time.

**VAT:** state prices as the payer actually pays them. If the developer is under the VAT franchise, price = amount paid. When comparing with competitors who charge VAT, add 20% to their price for payers who can’t recover VAT (individuals, VAT-exempt activities such as dental care).

## Product and developer

- **Product:** one focused tool, dataset, document or content that plugs into the payer's existing tools and complements them. Never full software or an ERP. **DFY** (done for you) is only a delivery mode, for a manual first version or a paid service on top, and its share should shrink.

- **Around the act, not inside it:** when an idea touches Regulated acts or needs domain judgment, scope the product to what surrounds the act — finding and coordinating the professional, scheduling, reminders, templates, document assembly, tracking, public information — and leave the act and the judgment to the qualified professional. A tracker records that an act is due or done, never its content or result.

- **Developer:** an information expert, not a domain expert: information architecture, data curation, AI, coding agents, no-code. Domain knowledge comes from sources, the payer or a named expert. Where judgment is needed, the product drafts and the expert validates. The developer never performs or signs Regulated acts.

## Hard criteria

1. **Money:** find a proof that people pay to solve the problem. This list is not exhaustive:
- staff are paid to do the job/task
- outsourced job/task
- documented price
- paid comparable solution
- a public price of a comparable product or service; 
- paid job adverts for the task
- Frankenstein Workarounds
- Pre-Orders & Deposits
- Paid Pilots / Consulting
- Active Search & Ad Spend
- Internal Headcount / Budget Allocation
- High-Friction DIY Hacks
- Angry Reviews of Competitors
- Searching for alternatives
- Consultant
- Any other way that show a purchase.

2. **Recurrence:** at least yearly, and it survives the first fix.
3. **Act now:** live, or recurring within 90 days.
4. **Access:** most prospects are reachable through channels the prospecting rules allow, and the payer signs without long procurement. Public bodies qualify only below the procurement threshold that applies, verified in Pre-check.
5. **Build:** a first sellable version plus outreach fits the Time to first sale (and Developer time if set). Give hours for pre-sale build, outreach and per customer.
6. **Developer fit:** no domain expertise is needed from the developer. If an idea needs it, first try rescoping it "around the act, not inside it" (see Product and developer); rate Failed only if no useful product remains.
7. **Data minimisation:** the tier is stated and justified, and the Data tier rules hold.
8. **Productisable:** per-customer hours are small compared with the price.
9. **Market and growth:** a small first market is fine. State the growth path (from Growth paths) and what must be true for it to become a real business.

## Value ladder and offer

Prove value before asking for money; ask for money before private data. Skip stages that don't apply, and give developer time per prospect for each stage.
- **0. Demo:** the payer gives nothing and gets a generic sample (T1–T2) or a synthetic-data demo.
- **1. Free analysis:** nothing given; the output is personalised from the payer's public data (T3).
- **2. Form (T4):** predefined answers given; a tailored preview received.
- **3. Paid product:** a signed commitment given; the full product received.
- **4. Private data (T5 only):** data given after payment, processed preferably in the payer's environment, with its legal basis.

- **First contact:** delivers stage 0 or 1 with no call, sign-up, data or purchase asked. Its value is real: cite a comparable price, or label it an assumption and explain. Each free stage must be cheap enough to produce for enough prospects.
- **Prospecting:**
  - France B2B: email relevant to the recipient's role, with an opt-out.
  - France B2C: no unsolicited email or SMS without prior consent; use the developer's site, ads, public listings, or hosts and partners with consenting audiences.
  - GDPR applies throughout.
- **Awareness check:** for unaware prospects, the first free stage must show the problem and its cost from their own public data; otherwise criterion 3 is at most Unverified.
- **Paid offer:** adds what the free stages don't, and has a price excl. VAT, a payment date and a delivery mode (self-serve, partly DFY, full DFY). It includes:
  - risk reversal (Abraham), guaranteeing only what the developer controls: on time, complete, working as specified. Outcome-based pricing is a price structure, not the guarantee;
  - for consumers, how withdrawal is handled.

## Attacks

Kill each idea with real searches; memory and Pre-check facts don't count. Before each attack's first search, write its kill finding in the output: a specific, findable product, price, rule or documented statement, never an absence of data. Don't change it afterwards. A `field_results` objection matching the payer type or problem becomes the kill finding for attack 1 or 2. Word searches to find disconfirming evidence, in the search language, with trade terms. Open up to 2 sources per attack.

1. **Existing solutions:** a free or cheap tool, a feature of software prospects use, or the host solves it well enough. **Fatal** only with evidence that it reaches about half the prospects or more (usage share, customer count, bundling in majority software). Low or unknown reach, complaints, or partial network coverage make it **Weakened**.
2. **Willingness to pay:** prospects refuse to pay, have no budget, do it in-house, or buy only through head office or long procurement (check this specifically for large organisations and public bodies).
3. **Host reality** (not applicable without a host): the host competes, or is barred from commissions or endorsements, including by Professional ethics rules.
4. **Recurring use:** low repeat use, high churn, or the problem vanishes after the first fix.
5. **Coming changes** not already in the Pre-check facts. **Fatal:** an adopted rule, a launched product or a dated rollout that removes the problem or takes most of the market within 12 months. **Weakened:** announced, proposed or partial.
6. **DIY with AI:**
   - **Fatal:** a documented example shows payers getting an output of equivalent use from general AI in about an hour, with what they already have, and the product adds nothing that needs refreshing.
   - **Weakened:** doable only with curation, updates, integration or validation the payer must repeat; price the offer on that recurring part.
   - **Survives:** the value rests on curated or updated data, integration or validated output.
7. **Data friction:** comparable tools need private data, prospects refuse such forms, predefined values are too generic to beat free options, or real data differs from the synthetic model.
8. **Why nobody does it** (not applicable if Crowded): a documented structural reason (failed product, legal block, incoming dominant player, no budget). Absence of competitors alone doesn't count.

## Candidate card

Opened in Step 2, updated at every step, frozen once rejected. Every field carries its source and evidence label.

```
CANDIDATE: <name>                  STATUS: open | rejected (step, reason) | selected
--- Discovery
Focus area · Problem and payer (who, how often; payer type, industry or none, consumer or not)
Industry involvement · Interacting party (or none) · Discovery options used · Emerging sources
Timing leverage (dated source, why now, when it closes) · First estimates (competition, awareness, tier)
--- Pre-check
Timing fact · Local rules and Professional ethics rules · Consent and withdrawal (consumers)
Network coverage · Reachable payers (count, method) · Example of paying · Offers found
Public data (owner, licence, freshness, access) · T4 form spec (fields, values, sources),
  synthetic data model source, or self-entered health data conditions
Money calculation: inputs, labels, strength, asked/paid, VAT → low–high € range
Criteria 1–9: rating + one-line reason (5, 8 provisional until Step 5) · Pilot checks
--- Attacks
Attack n: kill finding (written first) · search · sources · rating
--- Offer
Value ladder (stages, time per prospect) · Paid offer (price excl. VAT, payment date, mode,
  risk reversal, withdrawal) · Hours (pre-sale, outreach, per customer) · Criteria 3, 5, 8 final
```

## Report

Recommend one idea at most. Write the selected card as a readable report:
1. **Problem and gain:** Explain clearly the problem. Add with the € calculation. 
2. **Why common and still open:** evidence, timing, emerging sources, competition and offers, awareness.
3. **Data tier:** why a lower tier fails, and how the T5 or health data conditions are met.
4. **Stack:** tools and public data with licences; inputs and outputs; form spec or data model; what is automated vs manual; hours.
5. **Why customers will choose it:** over the network's tools, competitors, in-house work, free options and general AI.
6. **First sale:** value ladder, paid offer, risk reversal, first prospects (or how to list them), a compliant outreach channel, and a day-by-day plan to a signed commitment.
7. **Growth path:** and what must be true for it to become a real business.
8. **Adversarial results:** kill findings, a ratings table with sources, and pilot tests (Weakened attacks, Unverified criterion, inferred facts).
9. **Rejected ideas:** emerging source, competition, tier, and the failed criterion or kill finding.
10. **Evidence limits:** main assumptions, what was cut, and what the first sale would prove.
11. **Explored ideas:** those skipped, and any revisited with its new fact.
12. **Already explored ideas lines:** one per candidate examined, status "proposed" for the recommendation.
13. **Run memory update:** full replacement blocks with the same names for `optional_inputs` (person-set lines unchanged), `already_explored_ideas` (with section 12), `verified_facts` (drop expired facts not re-verified), `coverage_log`, `watch_list` (drop resolved items) and `process_stats`. Never output `run_inputs` or `field_results`.
14. **Suggested prompt changes (optional):** at most 3, each backed by `process_stats`; proposals only.

**If nothing survives:** list each candidate (emerging source, competition, tier, failed criterion or kill finding); name the criterion that blocked the most; describe the best near-miss and the smallest Input or offer change that would let it qualify (including rescoping around the act, not inside it), without recommending it ..., and add it to the watch list; then give sections 12–14.