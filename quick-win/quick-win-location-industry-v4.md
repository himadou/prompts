# Find a Quick-Win AI Business Opportunity

## Inputs

Set each value here only. Write OPEN for INDUSTRY or CUSTOMER_LOCATION to remove that restriction.

Required:

- **INDUSTRY:** Manufacturing and retreading of rubber tires and manufacturing of inner tubes (In french NAF code 22.11Z: `Fabrication et rechapage de pneumatiques`)
- **CUSTOMER_LOCATION:** France
- **CURRENT_DATE:** today

Optional (defaults shown):

- **MY_LOCATION:** Besançon, France
- **LANGUAGES:** French and English
- **TIME_TO_FIRST_SALE:** one week
- **EXISTING_ACCESS:** none [contacts, communities, or businesses that already know me]
- **EXCLUDED_IDEAS:** Public-tender/BOAMP lead radar for French tire retreaders ("Radar Rechapé Marchés Publics"); casing-sourcing marketplace for VL (passenger/van) retreaders; fleet cost-per-km / casing-management tool sold to hauliers via retreaders; SEO/content lead-gen for the Leonard (VL retread) brand; website/e-commerce growth services for French inner-tube manufacturers; retread labelling/compliance assistant tool

## Scope rules

- **If INDUSTRY is specified or chosen from OPEN:** Treat it as a hard boundary around the industry's value chain, not only around its own core activity. Consider opportunities at any stage of that chain:
  - **Before:** upstream suppliers of raw materials, components, or equipment used by the industry.
  - **During:** the industry's own production or service activity, including its operational problems (logistics, compliance, maintenance, procurement, staffing, and so on).
  - **After:** downstream commercialization, distribution, resale, or use of the industry's output by its direct customers, and end-of-life handling (repair, recycling, disposal) where relevant.
  - A business counts only if it has a direct, concrete connection to the named industry's own inputs, output, or operations — not merely the same broad sector.
  - Narrow to one sub-segment or one stage if that helps focus the search, but do not move to a stage that has no real connection to the named industry.
  - If more than one stage could plausibly host the opportunity, briefly compare them and state which one is the best fit, the same way OPEN values are compared.
- **If CUSTOMER_LOCATION is specified:** Customers must be there. Hosts can be based anywhere if they already have the trust of those customers. Use sources in the local language, and check local rules, buying habits, and competitors.
- **If either value is OPEN:** Compare at least three candidate industries or locations for that value before choosing, and explain why the winner beats the others.
- **CURRENT_DATE:** Use it to search for current information. Prefer evidence from the past 12 months and flag anything older. Check for laws, platform changes, or market changes already announced for the next 12 months that could shrink or grow the opportunity.
- **If nothing in scope passes:** Apply the rule at the end of this prompt. You may name one adjacent industry or location worth trying next, but do not recommend it as the opportunity.

## Role

Act as a pragmatic, skeptical business opportunity researcher. Identify **one actionable opportunity** within the scope above that I can build with AI engineering skills, Claude Code, or basic computer skills.

## Goal

Help customers achieve **real, measurable revenue growth** by:

- (a) acquiring more customers;
- (b) raising average order value;
- (c) generating repeat purchases; or
- (d) any other direct way of increasing revenue.

Avoid speculative value, such as avoiding a regulatory fine that may never happen.

Aim for a quick win within {{TIME_TO_FIRST_SALE}} if possible, or slightly longer if necessary. A completed sale is the only proof of demand. Interest, compliments, promises, demo views, and positive demo feedback do not count. My revenue can be irregular, but the offer must have the potential to grow.

**Kill the idea if** the customer's revenue growth cannot be measured.

## My constraints

- **Location:** {{MY_LOCATION}}. I build the demo and the solution locally on my laptop.
- **Demo deployment:** Deploy the demo remotely by default so that hosts and customers can check it on their own. Use a local demo, shown by screen share or in person, or a recorded walkthrough only as a fallback.
- **Product delivery:** Choose the simplest method that supports recurring use. It does not have to match the demo's deployment.
- **Languages:** I can sell and deliver in {{LANGUAGES}}.
- **Industry:** {{INDUSTRY}}. If OPEN, any industry.
- **Customers:** {{CUSTOMER_LOCATION}}. If OPEN, anywhere in the world.
- **Existing access:** {{EXISTING_ACCESS}}. Favor hosts and pilot users I can reach through it.
- **Excluded ideas:** {{EXCLUDED_IDEAS}}. Do not recommend these.
- **Technology:** No complex infrastructure or lengthy development. A remote demo should be a static page or one small app on a low-cost host.
- **Business model:** Flexible, including one-off services, customized deliverables, or digital products. A one-off sale can be the first step, but it should lead to recurring use and revenue.

## Gate 1: Market segment

Target an **underserved starving crowd** within the scope, in the sense used by copywriter Gary Halbert: people who already urgently want a solution and are ready to pay for it. Start with the customer's problem, not the technology. In a crowded market, look for a neglected segment that existing solutions serve poorly. The starving crowd has the budget and is ready to pay for the solution. The starving crowd doesn't mean lack of money.

Show evidence of hunger from the scope where possible, such as money already being spent, active searches, repeated complaints, or inadequate workarounds. If you rely on evidence from outside the scope, say so and explain why it should still apply.

**Kill the idea if** the segment is not an underserved starving crowd.

## Gate 2: Distribution

Base distribution on **Jay Abraham's host-beneficiary model**. In this model, a business that already has the trust of the target customers (the host) endorses or introduces my offer to them. I am the beneficiary. The host gains revenue share, a commission, or added value for its customers, without having to build or deliver the offer.

Name specific types of host, and real examples that serve the target customers where possible. Explain why they would agree, what is in it for them, how the endorsement would work, and how I can reach the decision-maker.

**Kill the idea if** there is no credible host-beneficiary model.

## Gate 3: Validation

Before exposing the solution to many people, run a small pilot with a few users from the scope to gather feedback and iterate. Explain who the pilot users are, how to reach them, what to test, and what result justifies a wider launch.

**Kill the idea if** users for validation are hard to find.

## Opportunity conditions

Every proposed business opportunity must satisfy the following conditions. Here, "the developer" means me.

1. **Domain expertise comes from the customer:** The developer does not need to be an expert in the target industry. The developer provides the information management, data/content curation (if needed), technical architecture, AI implementation, and software development capabilities. If domain expertise is needed, it should come from the expert or the data. The idea is to create an environment where developers' technical skills complement experts' domain expertise to achieve the common goal. Experts may lack the technical skills needed to implement their ideas or simply not have the time to do the work themselves. Developers can fill this gap by providing the technical support needed to turn those ideas into reality.
2. **Technical feasibility:** The solution must be realistically buildable and deployable by a technically competent developer using software engineering, applied AI, automation, or no-code/low-code tools, without requiring deep domain expertise from the developer.
3. **Recurring problem:** The underlying problem must occur frequently enough to create continuous value and encourage customers to keep using the solution.
4. **Customer retention potential:** The solution should ideally become embedded in the customer's recurring professional workflow, creating a strong reason for continued usage and recurring revenue.

Reject opportunities that fail condition 1, 2, or 3, including any that require the developer to possess specialized domain expertise or that solve problems with little potential for recurring usage. Deprioritize opportunities that fail condition 4.

## Other selection criteria

Favor opportunities with:

- Decision-makers who are easy to identify and contact, directly or through a host.
- Clear urgency and a compelling reason to buy now.
- A simple solution that can be built, customized, and delivered manually.
- Revenue-related value that a demo can show quickly.
- A strong advantage over existing alternatives.
- A short path from introduction to payment.

## Data principle: deliver value before asking for anything

Using data is not a goal. Asking for private data too early can create enough friction to stop a project, so use only the data the solution truly needs to deliver the revenue result.

The final product can use any of the following:

- **Zero data:** The tool or deliverable works without customer data.
- **Public data:** The tool or deliverable uses only publicly available information, such as the customer's website.
- **Private customer data:** The tool or deliverable needs customer data to work. In this case, ladder steps 2 and 3 also apply.

### Data ladder

Every opportunity starts at step 1. Use steps 2 and 3 only if the product needs them.

1. **Demo first:** Before asking for anything, show a working demo or sample result that can be built in a few hours using zero data or public data, such as the customer's website. It must show a specific path to a measurable revenue result. Personalizing it for each new prospect must be quick and repeatable.
2. **Light self-service input:** Use a short form with mostly predefined choices, a single number, or a screenshot to personalize the output without private access.
3. **Private data later:** Request exports, read-only access, or account access only after the customer has seen value, and tie each request to a specific, visible improvement.

Do not make private access a precondition for first value.

**Kill the idea if** zero or public data cannot produce a credible, revenue-related demo or sample result within a few hours.

### Demo requirements

- **Format:** The demo can be an app or a sample deliverable(document, dataset, curated content), whichever best proves the result. A deployed app is not mandatory.
- **Scope:** Limit it to one scenario and one revenue result. It is a time-boxed sales asset, not a first version of the product.
- **Personalization:** After the first version, personalizing it for a new prospect should mostly mean changing the input URL and reviewing the output, ideally in under 30 minutes.
- **Hosts:** Show each host a generic demo based on a sample company or its own website, plus one or two examples relevant to its customers. Create personalized versions for the prospects it introduces. Use a per-host link where possible so that referrals can be attributed for commission.
- **Accuracy:** Review every personalized demo manually before sending it. Show which claims come from the website and which are estimates. Label any revenue figure as an estimate until it is measured against the customer's baseline.
- **Revenue link:** A website summary or generic audit is not enough. The demo must identify a specific revenue opportunity, such as a missing product page, a neglected buyer segment, or an unanswered inquiry path.
- **Paid offer:** The demo should show what is possible using zero or public data, without fully solving the problem. The paid offer must add what the demo cannot provide, such as implementation, use of the customer's own data, and repeat use.
- **Compliance:** Personal data on a company website, such as staff names, email addresses, and phone numbers, is still covered by GDPR. Exclude it unless it is truly needed, and do not use real personal data in samples. Address GDPR for any form inputs or analytics, and respect each website's terms and access rules.
- **Access and cost:** Send personalized demos through a private link. If the demo calls an LLM, add rate limits and a spending cap.

Revenue measurement may require some customer figures, even for a zero-data product. Ask for the minimum needed, such as a baseline and a result figure, and only after the customer has seen value or agreed to the pilot.

Where the product needs little or no proprietary data and is therefore easy to copy, explain the real advantage, such as speed, analysis quality, personalization, distribution through hosts, or data accumulated from customers over time.

## Adversarial test: try to kill the idea

Before recommending an opportunity, stop arguing for it and try to prove it wrong using a real search tool. Evidence from memory does not count. If no search tool is available, say so, mark the test as not run, and do not call the idea validated.

Before searching, write down what finding would kill the idea. Do not change this afterwards.

Run at least one search for each attack below, worded to find disconfirming evidence. Search in the customers' language and in English, and open the sources rather than relying on search snippets.

1. **Existing solutions:** Is the problem already solved by a free tool, a low-cost product, a feature of software customers already use, or the host itself?
2. **Past failures:** Have similar products or services failed, shut down, changed direction, or drawn complaints? Why?
3. **Willingness to pay:** Is there evidence that these customers refuse to pay, have no budget, solve this in-house, or buy only through long procurement processes?
4. **Host reality:** Do the named hosts already sell a competing offer, or are they barred from taking commissions or endorsing third parties? Is there any evidence that they make such referrals?
5. **Revenue proof:** Could other factors explain the revenue result, or would the result take too long to measure?
6. **Recurring use:** Is there evidence of low repeat use, high churn, or a problem that goes away after the first fix?
7. **Coming changes:** Could an announced law, platform change, or market trend shrink the opportunity in the next 12 months?
8. **Demo weakness:** Would the demo remove the need to buy? Is there evidence that target customers will not try this kind of demo, or that their websites and other public data are too thin to support it?

Also recheck the three claims the recommendation depends on most:

- Confirm that each source says what you claim.
- Look for an independent second source.
- Flag vendor marketing, self-reported results, and anonymous reviews as weak evidence.

Rate each attack as **survives**, **weakened**, or **fatal**. Finding nothing is not proof: report it as "no evidence found", and do not count it as support.

- **If an attack is fatal:** Reject the idea, list it among the rejected ideas with the finding that killed it, and test the next best candidate.
- **If an attack weakens the idea:** Redesign the offer to address it, or state the risk and add a pilot test for it.
- **Limit of this test:** Surviving it does not prove demand. A completed sale remains the only proof.

## Required output

First, state the scope you used. If INDUSTRY or CUSTOMER_LOCATION was OPEN, show the candidates you compared. Then briefly list the main ideas you rejected and the gate, condition, or adversarial finding that eliminated each one. Then recommend **the one best opportunity** and explain:

1. **Gate results:** Pass or fail for revenue measurement, starving crowd, host-beneficiary distribution, pilot access, the demo kill rule, and each of the four opportunity conditions, with evidence for each.
2. **The problem:** Who experiences it, how often, how they handle it today, and why they will pay to solve it.
3. **The solution:** What I can build or deliver with my skills and tools. Explain where any domain expertise comes from, and how the solution becomes part of the customer's recurring workflow. Include a demo specification: what it proves, the data it uses, its format, how it is deployed, its build time and running cost, how it is personalized, and what the paid offer adds. This is a specification only. Do not build the demo as part of this research.
4. **Data and first value:** Whether the product uses zero, public, or private data, and why that is the minimum needed. Describe the value the demo gives the customer before they are asked for anything. If private data is needed, also explain each ladder step, what each request unlocks, and the least sensitive form of access that would work.
5. **Customer revenue impact:** The expected revenue gain, the baseline, how to measure it, and how soon it should be visible.
6. **Competitive advantage:** Why customers would choose my offer over existing alternatives.
7. **Host-beneficiary plan:** Which hosts to approach first, the deal terms, a short outreach message in the customers' language, how the host will review and share the demo, how referrals will be attributed, and how the host will present the offer.
8. **Pilot plan:** Pilot users, feedback process, iteration steps, conversion from demo to paid pilot, evidence of repeat use, and the criteria for continuing or stopping. Base these criteria on payment and repeat use, not demo views or positive feedback.
9. **Pricing and revenue:** What to charge, how to get paid, the host's share, the path to recurring revenue, and realistic revenue potential, including how irregular it may be.
10. **Execution plan:** A day-by-day plan starting from {{CURRENT_DATE}}, from identifying hosts to receiving the first payment. Build and deploy the demo in a time-boxed step before host outreach, and only after the idea has passed the gates and adversarial test.
11. **Timing (optional):** Any advantage specific to the month of {{CURRENT_DATE}}. The timing should help to find a growing trend in the time, not a trend that spikes and then fades. A stable trend in the whole year is fine. If the trend will fade soon do not consider a timing advantage.
12. **Adversarial test results:** The kill criteria you set, then for each attack the search used, what you found with sources, and its rating. Also report the three rechecked claims, the strongest remaining case against the idea, and what the test could not check.

Be realistic about competition, willingness to pay, delivery effort, and uncertainty. Label each key claim as verified evidence or an assumption, and cite sources where possible.

**If no opportunity passes every gate and survives the adversarial test, say so and do not recommend a weak one.** Instead, name the closest candidate and what evidence could change the verdict.

**Final objective:** Find the fastest credible path to a first paying customer through a host, with proof of measurable customer revenue growth and an offer that can grow beyond the first sale.