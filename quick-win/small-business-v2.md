# Find a Quick-Win AI Business Opportunity

Version: 3 (2026-11-05) Changes from v2: added an optional NAF/APE code anchor and upstream/downstream value-chain exploration for INDUSTRY; made the host-beneficiary model optional and preferred rather than required, with pilot access (Gate 3) as the central distribution gate; added a mandatory early fact-check (Pre-check) right after Gate 1 and before any offer design, so a dead load-bearing fact kills the idea before time is spent on pricing, outreach, or execution planning; reframed the "coming changes" adversarial attack to also catch a triggering fact that is already outdated today, not only one that might change in the next 12 months; added an anti-seasonality selection rule; reordered the required output to match.

## Inputs

Set each value here only. Write OPEN for INDUSTRY, CUSTOMER\_LOCATION, or BUSINESS\_SIZE to remove that restriction.

Required:

- **INDUSTRY:** Collection of sorted waste (recycling, material recovery). In french: Récupération de déchets triés (recyclage, valorisation matière)
- **INDUSTRY\_NAF (optional):** 38.32Z
- **BUSINESS\_SIZE:** self-employed | 1-9 | 10-49 | 50-249
- **CUSTOMER\_LOCATION:** Doubs in France
- **CURRENT\_DATE:** today

Optional (defaults shown):

- **MY\_LOCATION:** Besançon, France
- **LANGUAGES:** French and English
- **TIME\_TO\_FIRST\_SALE:** one week
- **MAX\_DAYS\_TO\_PAYMENT:** 14 around
- **IN\_HOUSE\_CAPABILITY:** OPEN
- **EXISTING\_ACCESS:** none
- **EXCLUDED\_IDEAS:** none

## Scope rules

- **If INDUSTRY is specified:** Treat it as a hard boundary. Narrow to a sub-segment if that helps, but do not move to another industry.
- **NAF anchor and value-chain exploration:** If INDUSTRY\_NAF is given, treat it as a starting anchor, not a hard filter. If it is not given, propose a best-guess NAF code from the industry name yourself. Search for and compare candidate NAF codes within the same industry boundary — including codes **upstream** (suppliers, raw materials, inputs, production) and **downstream** (distributors, resellers, prescribers, regulators, insurers, end-use channels) of the anchor — and select whichever candidate offers the strongest combination of starving-crowd evidence, credible pilot access, and a recurring problem. Report which NAF code(s) were considered and why the winner was chosen, with real establishment counts where available (e.g. INSEE Sirene or the equivalent local business registry). This exploration must never leave the real industry the user intended; it only looks at what comes before, alongside, or after that industry's own product or service.
- **If CUSTOMER\_LOCATION is specified:** Customers must be there. Hosts can be based anywhere if they already have the trust of those customers. Use sources in the local language, and check local rules, buying habits, and competitors.
- **BUSINESS\_SIZE:** Self-employed means the owner works alone with no employees, whatever the legal form. Other ranges count the employees of the independent business, or of the whole group if it has a parent. These ranges apply worldwide, whatever local definitions of "small" say. If more than one value is given, every recommended customer must fall within them, and you may focus on one.
- **If INDUSTRY is OPEN:** Use BUSINESS\_SIZE as the main filter. Compare at least three specific industries where businesses of this size are common, each with its own candidate NAF code(s), then recommend one specific customer type, such as "independent plumbers" rather than "small businesses". The winner must have a problem that recurs in its normal work, and either a named host that reaches that customer type or a credible direct-access path to it (see Gate 3).
- **If CUSTOMER\_LOCATION or BUSINESS\_SIZE is OPEN:** Compare at least three candidate locations or size ranges for that value before choosing, and explain why the winner beats the others.
- **CURRENT\_DATE:** Use it to search for current information. Prefer evidence from the past 12 months and flag anything older. Check for laws, platform changes, or market changes already announced for the next 12 months that could shrink or grow the opportunity. Also check whether the opportunity's own triggering fact (a law, rule, cost, or frequency the problem depends on) is still current today, not only whether it might change in the future. A triggering fact that is already outdated, repealed, replaced, or unconfirmed at the exact local level of the scope kills the idea just as much as a future change would — see the Pre-check step below.
- **Seasonality:** Deprioritize or reject opportunities whose value depends on a narrow annual time window (a single season, a single filing period, a single regulatory deadline) unless (a) a pilot can be launched and measured entirely within the time remaining in that window this cycle, and (b) the recurring-revenue path does not depend solely on the same narrow window recurring next year.
- **If nothing in scope passes:** Apply the rule at the end of this prompt. You may name one adjacent industry, location, or business size worth trying next, but do not recommend it as the opportunity.

Act as a pragmatic, skeptical business opportunity researcher. Identify **one actionable opportunity** within the scope above that I can build with AI engineering skills, Claude Code, or basic computer skills.

## Goal

Identify and define mechanisms to increase revenue or net profit for self-employed individuals and Small-to-Medium Enterprises (SMEs) via a software tool (AI-driven or traditional automation). Categorize these mechanisms under the following economic levers:

- **(a) Customer Acquisition:** Mechanisms that generate new paying clients from any channel or stage of awareness.
- **(b) Average Order Value (AOV):** Mechanisms that increase transaction size or contract value at the point of sale.
- **(c) Purchase Frequency:** Mechanisms that compress re-order cycles or build ongoing contractual loyalty.
- **(d) Direct Leakage Recovery:** Capturing revenue already earned, committed, or lost to friction (e.g., abandoned carts, uncollected invoices, churn).
- **(e) Net Margin Optimization:** Expanding bottom-line profit via pricing power, operational automation, and cost-to-serve reduction.
- **(f) Idle Capacity & Yield Optimization:** Mechanisms that monetize perishable, already-paid-for assets (e.g., unfilled calendar slots, excess inventory, unused software licenses) through dynamic pricing or automated repackaging, without increasing fixed costs.
- **(g) Embedded Partnership & B2B2C Distribution:** Mechanisms that acquire customers at near-zero Customer Acquisition Cost (CAC) by piggybacking on the established trust, audience, and checkout flows of non-competing, complementary businesses.
- **(h) Financial Engineering & Cash Flow Acceleration:** Mechanisms that increase the net present value (NPV) of revenue by shortening the cash conversion cycle, algorithmically optimizing payment terms, or embedding financing (e.g., B2B BNPL) at the point of sale.
- **(i) Intellectual Property (IP) & Knowledge Monetization:** Mechanisms that decouple revenue from linear time investment by systematically extracting, sanitizing, and productizing historical tacit knowledge, workflows, or data into scalable, low-touch digital assets.
- **(j) Structural Business Model Arbitrage & Risk Reversal:** Mechanisms that bypass commodity market pricing by fundamentally restructuring how value is exchanged. This includes shifting from input-based billing (hours, deliverables) to outcome-based pricing (revenue share, performance bonuses, cost-savings splits), or automating the capture of non-dilutive capital (e.g., algorithmic matching and application for SME grants, tax credits, or platform subsidies).

> **Instruction for the model:** 
> 1. Treat any tactical examples as non-exhaustive illustrations. 
> 2. Prioritize novel, domain-specific, and unconventional levers that fit these strict economic definitions. Do not default to generic marketing tactics (e.g., "run Facebook ads" or "start a blog").
> 3. Frame every suggestion around a **buildable tool or software feature** (AI or non-AI) that a developer could realistically create for a self-employed individual or SME in the 2026 landscape.
> 4. For each lever, briefly explain the *economic mechanism* (why it works) and the *tool execution* (how the software automates or enables it).

Aim for a quick win within {{TIME\_TO\_FIRST\_SALE}} if possible, or slightly longer if necessary. A completed sale is the only proof of demand. Interest, compliments, and promises do not count. The revenue can be irregular, but the offer must have the potential to grow.

**Kill the idea if** the customer's revenue growth cannot be measured.

## My constraints

- **Location:** {{MY\_LOCATION}}. I build and deliver the solution locally on my laptop.
- **Languages:** I can sell and deliver in {{LANGUAGES}}.
- **Industry:** {{INDUSTRY}}. If OPEN, any industry.
- **Customers:** {{CUSTOMER\_LOCATION}}. If OPEN, anywhere in the world.
- **Business size:** {{BUSINESS\_SIZE}}. If OPEN, any size.
- **Existing access:** {{EXISTING\_ACCESS}}. Favor hosts and pilot users I can reach through it.
- **Excluded ideas:** {{EXCLUDED\_IDEAS}}. Do not recommend these.
- **Technology:** No complex infrastructure or lengthy development.
- **Business model:** Flexible, including one-off services, customized deliverables, or digital products. A one-off sale can be the first step, but it should lead to recurring use and revenue.

## Gate 1: Market segment

Target an **underserved starving crowd** within the scope, in the sense used by copywriter Gary Halbert: people who already urgently want a solution and are ready to pay for it. Start with the customer's problem, not the technology. In a crowded market, look for a neglected segment that existing solutions serve poorly.

Show evidence of hunger from the scope where possible, such as money already being spent, active searches, repeated complaints, or inadequate workarounds. If you rely on evidence from outside the scope, say so and explain why it should still apply.

Before comparing candidate industries/NAF codes, verify by search that the problem claimed for each candidate rests on a current, non-superseded fact (a rule, a cost, a frequency) rather than something assumed from memory or an old source. A candidate whose problem rests on an unverified or outdated fact cannot be carried forward as a finalist.

**Kill the idea if** the segment is not an underserved starving crowd.

## Pre-check: verify the triggering fact (before designing the offer)

Once a candidate opportunity is tentatively chosen from Gate 1, and **before** designing the distribution plan, pricing, or outreach, run a focused search to confirm the one to three load-bearing facts the opportunity depends on (e.g. a legal obligation, a recurring cost, a frequency of need) are true as of {{CURRENT\_DATE}}, specifically at the local level of {{CUSTOMER\_LOCATION}} and {{INDUSTRY}} — not just generally true somewhere else or at a national level that may not apply locally.

For each load-bearing fact, find a primary source and, where possible, an independent secondary source. State explicitly whether each fact is:

- **Confirmed current** — still true today, with sources;
- **Confirmed superseded or false** — no longer true, with the source that replaced or repealed it; or
- **Unverifiable from available sources** — name the exact official body, registry, or document that would resolve it.

**Kill the idea immediately if a load-bearing fact is confirmed superseded or false**, and go back to the next-best candidate from Gate 1. Do not proceed to Gate 2, Gate 3, or any solution design until this Pre-check passes, or is explicitly flagged as unverifiable with a stated mitigation (for example, asking the pilot customer to confirm it, or querying the relevant authority before launch).

## Gate 2: Distribution (optional, preferred when available)

Look for distribution based on **Jay Abraham's host-beneficiary model** if a relevant host exists within the scope. In this model, a business that already has the trust of the target customers (the host) endorses or introduces my offer to them, in exchange for a revenue share, a commission, or added value for its customers, without having to build or deliver the offer.

A host is a **preferred accelerator, not a requirement**. The absence of a credible host never kills the idea on its own.

When a host is found, name specific types of host, and real examples that serve the target customers where possible. Explain why they would agree, what is in it for them, how the endorsement would work, and how to reach the decision-maker. Also consider upstream and downstream actors identified in the NAF value-chain exploration (suppliers, distributors, prescribers, regulators, insurers) as potential hosts, not only the industry's own trade association.

There is no kill condition for this gate. What matters is Gate 3 below.

## Gate 3: Validation and pilot access (the central distribution gate)

Explain how to reach enough pilot users within scope to validate the idea — **directly** (cold outreach, public directories, professional networks, marketplaces) and/or through a host if one was found in Gate 2. State the actual channel that will be used for the pilot, not a hypothetical one. Explain who the pilot users are, what to test, and what result justifies a wider launch.

**Kill the idea if** pilot users, reached directly or through a host, are hard to find.

## Opportunity conditions

Every proposed business opportunity must satisfy the following conditions. Here, "the developer" means me.

1. **Domain expertise comes from the customer:** The developer does not need to be an expert in the target industry. The developer provides the information management, technical architecture, AI implementation, and software development capabilities. If domain expertise is needed, it should come from the expert or the data.
2. **Technical feasibility:** The solution must be realistically buildable and deployable by a technically competent developer using software engineering, applied AI, automation, or no-code/low-code tools, without requiring deep domain expertise from the developer.
3. **Recurring problem:** The underlying problem must occur frequently enough to create continuous value and encourage customers to keep using the solution.
4. **Customer retention potential:** The solution should ideally become embedded in the customer's recurring professional workflow, creating a strong reason for continued usage and recurring revenue.
5. **Capability gap:** The target business has no one who can build and maintain this solution, and no current supplier already contracted to do it. Assess this for the specific problem, not the business's technical skills in general. Show evidence where possible, such as job postings, team pages, supplier mentions, or the business currently using manual work or paying outsiders. The business must also have:
   - A budget: it already pays outsiders for this or a similar problem, or the problem has a clear cost.
   - A decision-maker who can approve the purchase.
   - Someone who can supply the domain knowledge. This can be the owner.
   - A way to use the solution without technical staff.

   Apply this condition when IN\_HOUSE\_CAPABILITY is none. Skip it when IN\_HOUSE\_CAPABILITY is OPEN.
6. **Fast first payment:** First payment must be possible within {{MAX\_DAYS\_TO\_PAYMENT}} days of the first introduction (host or direct), without procurement, an IT or security review, system integration, or more than one approver. Larger or recurring purchases can follow later, but the first purchase must be the first step of the recurring workflow, not a separate one-off.

Reject opportunities that fail condition 1, 2, 3, 5, or 6, including any that require the developer to possess specialized domain expertise or that solve problems with little potential for recurring usage. Also reject any that the target customers could solve themselves with existing staff and general AI tools, or where they lack both the skills and the budget. Redesign an offer that fails condition 6 before rejecting it. Deprioritize opportunities that fail condition 4.

## Other selection criteria

Favor opportunities with:

- Decision-makers who are easy to identify and contact, directly (preferred) or through a host if one is available.
- Clear urgency and a compelling reason to buy now.
- A simple solution that can be built, customized, and delivered manually.
- A strong advantage over existing alternatives.
- A short path from introduction to payment.
- Demand that is not confined to a narrow seasonal window (see the Seasonality scope rule above); when it is, the remaining time in the current window and the plan to recur without relying on that same window must both be credible.

## Data principle: deliver value before asking for anything

Using data is not a goal. Asking for private data too early can create enough friction to stop a project, so use only the data the solution truly needs to deliver the revenue result.

The final product can use any of the following:

- **Zero data:** The tool or deliverable works without customer data.
- **Public data:** The tool or deliverable uses only publicly available information.
- **Private customer data:** The tool or deliverable needs customer data to work. In this case, apply the data ladder below.

### Data ladder for products that need private data

1. **Value first:** Show useful value before asking for anything, using zero data, public data, or a sample result.
2. **Light self-service input:** Use a short form with mostly predefined choices, a single number, or a screenshot to personalize the output without private access.
3. **Private data later:** Request exports, read-only access, or account access only after the customer has seen value, and tie each request to a specific, visible improvement.

Do not make private access a precondition for first value. If the opportunity cannot show value first, redesign it or reject it.

Revenue measurement may require some customer figures, even for a zero-data product. Ask for the minimum needed, such as a baseline and a result figure, and only after the customer has seen value or agreed to the pilot.

Where the product needs little or no proprietary data and is therefore easy to copy, explain the real advantage, such as speed, analysis quality, personalization, distribution through hosts, or data accumulated from customers over time.

## Adversarial test: try to kill the idea

Before recommending an opportunity, stop arguing for it and try to prove it wrong using a real search tool. Evidence from memory does not count. If no search tool is available, say so, mark the test as not run, and do not call the idea validated.

This test runs **after** the Pre-check above, which already verified the opportunity's core load-bearing fact(s). Do not re-run that same verification here — focus this test on everything else that could still kill the idea.

Before searching, write down what finding would kill the idea. Do not change this afterwards.

Run at least one search for each attack below, worded to find disconfirming evidence. Search in the customers' language and in English, and open the sources rather than relying on search snippets.

1. **Existing solutions:** Is the problem already solved by a free tool, a low-cost product, a feature of software customers already use, or the host itself?
2. **Past failures:** Have similar products or services failed, shut down, changed direction, or drawn complaints? Why?
3. **Willingness to pay:** Is there evidence that these customers refuse to pay, have no budget, solve this in-house, or buy only through long procurement processes?
4. **Host reality (only if a host was proposed in Gate 2):** Does the named host already sell a competing offer, or is it barred from taking commissions or endorsing third parties? Is there any evidence that it makes such referrals? **If no host was proposed (direct-to-customer distribution only), mark this attack as N/A and state so explicitly.**
5. **Revenue proof:** Could other factors explain the revenue result, or would the result take too long to measure?
6. **Recurring use:** Is there evidence of low repeat use, high churn, or a problem that goes away after the first fix?
7. **Coming and already-outdated changes:** Could an announced law, platform change, or market trend shrink the opportunity in the next 12 months? Also check for any *additional* change not already covered by the Pre-check — do not re-verify the same core fact twice, only look for other upcoming or recent changes that could still affect the opportunity.
8. **Do-it-yourself with AI:** Could the owner or an employee solve this in an afternoon with general AI tools? If so, why would they keep paying?

Also recheck the other load-bearing claims the recommendation depends on most (distinct from the Pre-check facts already verified) — such as market-size estimates, pricing benchmarks, or competitor claims:

- Confirm that each source says what you claim.
- Look for an independent second source.
- Flag vendor marketing, self-reported results, and anonymous reviews as weak evidence.

Rate each attack as **survives**, **weakened**, or **fatal**. Finding nothing is not proof: report it as "no evidence found", and do not count it as support.

- **If an attack is fatal:** Reject the idea, list it among the rejected ideas with the finding that killed it, and test the next best candidate.
- **If an attack weakens the idea:** Redesign the offer to address it, or state the risk and add a pilot test for it.
- **Limit of this test:** Surviving it does not prove demand. A completed sale remains the only proof.

## Required output

First, state the prompt version and the scope you used, including whether INDUSTRY\_NAF was given or model-proposed, and which NAF codes were compared. If INDUSTRY, CUSTOMER\_LOCATION, or BUSINESS\_SIZE was OPEN, show the candidates you compared. Then briefly list the main ideas you rejected and the gate, pre-check, condition, or adversarial finding that eliminated each one. Then recommend **the one best opportunity** and explain:

1. **Pre-check results:** The status of each load-bearing fact (confirmed current / confirmed superseded / unverifiable), with sources, run before any offer design.
2. **Gate results:** Pass or fail for revenue measurement, starving crowd, pilot access (Gate 3), host-beneficiary distribution if any was found in Gate 2 (otherwise N/A with reason), and each of the six opportunity conditions, with evidence for each.
3. **The problem:** Who experiences it, how often, how they handle it today, and why they will pay to solve it.
4. **The solution:** What I can build or deliver with my skills and tools. Explain where any domain expertise comes from, and how the solution becomes part of the customer's recurring workflow.
5. **Data and first value:** Whether the product uses zero, public, or private data, and why that is the minimum needed. Describe the value the customer receives before being asked for anything. If private data is needed, also explain each ladder step, what each request unlocks, and the least sensitive form of access that would work.
6. **Customer revenue impact:** The expected revenue gain, the baseline, how to measure it, and how soon it should be visible.
7. **Competitive advantage:** Why customers would choose my offer over existing alternatives.
8. **Pilot plan:** Pilot users reached directly (and/or through a host), how to reach them, what to test, feedback process, iteration steps, evidence of repeat use, and the criteria for continuing or stopping.
9. **Host-beneficiary plan (if any):** Which hosts to approach first, the deal terms, a short outreach message in the customers' language, and how the host will present the offer. If no credible host was found, state N/A and why, and rely on the pilot plan above as the distribution path.
10. **Pricing and revenue:** What to charge for the first purchase and afterwards, how to get paid, the host's share if any, the path to recurring revenue, and realistic revenue potential, including how irregular it may be.
11. **Execution plan:** A day-by-day plan starting from {{CURRENT\_DATE}}, from identifying hosts and/or pilot customers to receiving the first payment, with the expected days from introduction to payment.
12. **Timing (optional):** Any advantage specific to the month of {{CURRENT\_DATE}}. The timing should help to find a growing trend in the time, not a trend that spikes and then fades. A stable trend in the whole year is fine. If the trend will fade soon, or depends on a narrow seasonal window, apply the Seasonality rule above and do not count it as a timing advantage unless both its conditions are met.
Look at new capabilities, new datasets that was not possible before. The timing should help to implement a more efficient, cost-effective, faster and effortless.
13. **Adversarial test results:** The kill criteria you set, then for each attack the search used, what you found with sources, and its rating (marking attack 4 as N/A if no host was proposed). Also report the other rechecked load-bearing claims, the strongest remaining case against the idea, and what the test could not check.

Be realistic about competition, willingness to pay, delivery effort, and uncertainty. Label each key claim as verified evidence or an assumption, and cite sources where possible.

**If no opportunity passes every gate and survives the Pre-check and the adversarial test, say so and do not recommend a weak one.** Instead, name the closest candidate and what evidence could change the verdict.

**Final objective:** Find the fastest credible path to a first paying customer, directly or through a host, with proof of measurable customer revenue growth and an offer that can grow beyond the first sale.
