# Prompt 1 (Find): from a role to the tasks where input data is the bottleneck, inputs change over time and people pay or would pay: VERSION October 2026 (find-v1.9)

> **How to run (for the user; the model can skip this box)**
> 1. Fill the parameters below.
> 2. Use any model with web search turned on, in normal mode.
> 3. Paste the whole prompt and send it. If the answer stops with `CONTINUE`, reply "continue".
> 4. Copy the whole handoff block (from `=== HANDOFF START ===` to `=== HANDOFF END ===`) without editing it. Open Prompt 2 (Refine), paste the block in `FIND_HANDOFF`, write the ID of the candidate you picked in `CANDIDATE_ID`, and set `RUN_DATE`. Prompt 2 reads every other value from the handoff; do not retype them.
> 5. For the next round on the same role and country, copy the line from the report section "Updated ALREADY_VISITED" into the `ALREADY_VISITED` parameter (the same line is also in the handoff as `already_visited_line`). To have a task re-examined, delete its entry from the line before running.

> **Changelog v1.8 → v1.9**
> - Each full candidate entry now shows the **product blueprint**: `data_sources` (every source to curate or receive, with link, access mode, input format, reuse terms, refresh rate, scenario), `stack.pipeline` (ordered stages with tool, input format and output format, plus the `curated_asset` the founder keeps), and `deliverables` (what the customer receives, in which file format, with which fields, through which channel), for the free version and for each scenario rung up to `MAX_SCENARIO`.
> - New section "Product blueprint". Step 1e renamed "Sources, stack and deliverable blueprint" and extended; checks 3 and 8 and the report (section 3) updated; handoff `key_inputs` replaced by `data_sources`; `stack` extended; new `deliverables`.
> - Handoff now says `FIND_HANDOFF` (the name Prompt 2 uses for its input block) in the how-to box.

> **Changelog v1.7 → v1.8**
> - Handoff block now carries every run setting (adds `TARGET_SATURATION`, `INVENTORY_SIZE`, `CANDIDATES`, `MAX_DEMAND_TESTED`, `ROLE_GATE`), a `candidate_ids` list, and the `already_visited_line`, so that Prompt 2 can read all its parameters from the handoff and nothing has to be retyped.
> - `INDUSTRY` and `COMPANY_SIZE` in the handoff `parameters` block keep the value given to this prompt; each candidate entry now always states an explicit `industry` and `segment` (never "open"), which Prompt 2 treats as the fixed values.
> - Candidates that passed the screen but were not demand-tested keep a full entry; off-target and killed candidates stay one-line entries and cannot be passed to Prompt 2 without a new Prompt 1 run.
> - Minor: removed a duplicated sentence in step 1a.

> **Changelog v1.6 → v1.7**
> - New parameter `TARGET_SATURATION` (open | Low | Medium | High).
> - New section "Market saturation by level": saturation measured separately for Level 1, 2 and 3 from four measures (Availability, Maturity, Similarity scored 0–2, Unmet need yes/no) with fixed thresholds; classification rules for Low (empty), Low, Medium (with its reason) and High; ranges when evidence is missing.
> - Each candidate gets a competitive level: the reachable level matching `TARGET_SATURATION`, closest to `TARGET_DEPTH`. Non-matching candidates are "off-target", reported, never killed.
> - Step 1d: provisional saturation profile from the register. Check 7 rebuilt on the per-level profile; zones Open/Emerging/Contested/Saturated replaced by Low (empty)/Low/Medium/High.
> - Report, ALREADY_VISITED tags and handoff updated (per-level profile, competitive level, off-target list).

> **Changelog v1.5 → v1.6**
> - Check 7 rebuilt as "Market saturation and differentiation": seven saturation signals, four zones, a differentiation strength (need, durability, reach), and a verdict table where the required differentiation rises with saturation. Saturation never kills on its own.
> - New "what Prompt 2 must prove" line per candidate. Ranking uses market position. Handoff gets `saturation`, `differentiation` and `must_prove`.

> **Changelog v1.4 → v1.5**
> - New `description` for each shortlisted candidate: 3 to 4 plain sentences explaining why the task was selected.

> **Changelog v1.3 → v1.4**
> - `ALREADY_REJECTED` replaced by `ALREADY_VISITED`: one line listing every task examined in previous rounds, each with a status tag.

> **Changelog v1.2 → v1.3**
> - New parameters `MAX_SCENARIO`, `TARGET_DEPTH`, `HUMAN_IN_LOOP`, `LICENCE_POLICY`; data-access scenarios and delivery ladder; Step 1e open-source stack mapping; handoff rewritten.

**Your part:** you are part 1 of 2. Starting from ONE role, you inventory what that role does, find the tasks where getting or verifying the input data is the slowest step and where the inputs change from time to time, so that a practitioner without the time or the skill to keep up loses something by missing a change. You sort these tasks into two paths: **path A** (people already pay for this output or its inputs) and **path B** (latent demand: no visible paid offer, but strong proxy signals and a cheap validation test). For each candidate you also describe how far into the task the product can go (its **delivery ladder**), which **data-access scenario** each level needs, which parts **open-source tools** already cover, and a **product blueprint** (the data sources to curate and their formats, the stack that processes them, and the format the customer receives). You map the existing alternatives and assess **market saturation for each level of the delivery ladder** (Low, Medium, High, from the availability, maturity and similarity of existing offers and from unmet needs), focus on the saturation set by `TARGET_SATURATION`, and pick the level the product competes on: a crowded market is a signal that the need is real, not a kill, but the more saturated it is, the stronger the differentiation must be. You name for each candidate a gap hypothesis, rate its differentiation strength and state what Prompt 2 must prove, and you test demand on the candidates. You do NOT design the input pack, run source discovery, build the market map or write the positioning: Prompt 2 does that for one candidate the user picks. Your answer ends with a handoff block that Prompt 2 reads; follow its format exactly.

## Parameters

RUN_DATE = 2026-10-12   (used for every "last N months" window; never guess it)
ROLE = Business Developer
COUNTRY = France
INDUSTRY = open   (open = you may pick the industry where the task is most valuable; state it and why)
COMPANY_SIZE = open   (open = same, pick the segment; state it and why)
LANGUAGE = French   (language of the market, the searches and the report content)
HINT = none   (optional direction: where to look first. Never evidence, never changes a check, a ranking or a verdict)
ALREADY_VISITED = [Business Developer | France] identifier créations d'entreprises [1c no payment]; veille appels d'offres publics/privés [shortlisted]; veille levées de fonds [screened]; recrutements stratégiques CISO [screened]; transferts de siège social [shortlisted]; subventions environnementales [screened]; mise à jour CRM [1b not input]; rédaction emails prospection [1b not input]; calcul devis [1b not input]; relance factures [1b not input]; suivi prix concurrents [1b no evidence]; organigrammes comptes complexes [not picked]; visiteurs site web [not picked]; stack technologique prospects [not picked] (single line from the previous round's report section "Updated ALREADY_VISITED": every task already examined for this ROLE and COUNTRY, with its status tag; do not examine them again. Format: `[ROLE | COUNTRY] task 1 [tag]; task 2 [tag]; ...`)
INVENTORY_SIZE = 20
CANDIDATES = 5
PATH_B_MAX = 2   (maximum number of the CANDIDATES on path B; rises to 3 if the Step 0 role gate returns a flag)
MAX_DEMAND_TESTED = 3
ROLE_GATE = on
MAX_SCENARIO = A   (A | B | C | D | E: the hardest data-access scenario the paid version may use; see "Data-access scenarios")
TARGET_DEPTH = input data   (input data | draft output | near-final output: how far into the task the paid version should aim)
HUMAN_IN_LOOP = allowed   (allowed | required | not allowed: whether a human validation step may be part of delivery)
LICENCE_POLICY = permissive only   (permissive only | copyleft acceptable: which open-source licences count as stack coverage)
TARGET_SATURATION = open   (open | Low | Medium | High: how saturated the market may be at the level of the ladder the product competes on; open = all levels of saturation; see "Market saturation by level")

This run studies ONE role in ONE country. It does not compare roles or countries.

## Goals

The goal for the end user is one or more of: win more clients, raise the average order value per client, raise the frequency of sales, or save paid time or outside help.

## Founder profile (swappable)

- Solo founder, applied AI engineer, based in France (assume a French sole-proprietor entity, e.g. micro-entreprise or EI). French and English.
- Skills: Claude Code, Pi AI agent, Claude Design, RAG, structured RAG (the user question is a form instead of a free question), LangGraph, Neo4j, Remotion, TTS, ASR, IVR, real-time AI voice agent, competitive intelligence, information extraction, NLP, Hugging Face, OpenAI API, Claude API, Qwen API, DeepSeek API, Python, JavaScript, FastAPI, React.js, PHP, Nuxt.js, Firebase, GA4, Cloud Run, AWS, GCP, Docker, Helm, APIs, MCP.
- Time and budget are flexible and building and running software has a very low marginal cost: never use them as kill criteria. Language fit with the market is a note, not a kill criterion.
- Sales must suit a solo founder: self-serve, marketplace discovery, low-touch onboarding, or a few local relationships. No long enterprise sales cycles. Exception: rungs delivered under scenario D (self-hosted) are exempt from this sales-cycle rule (see check 6).
- The profile judges delivery feasibility only. It never chooses, favours or ranks a task. A task is never proposed or kept alive because it suits the founder's skills. Stack coverage (Step 1e) is a delivery-effort attribute, used only as a last tie-breaker in the ranking.

## Data-access scenarios and delivery depth

### Scenarios (how the reader's own data reaches the product)

- **A. Public data only:** the founder runs everything on public or licensable data; the reader receives the output. No reader data.
- **B. Manual upload:** the reader exports a file (CSV, Excel, PDF) from their own tools and uploads or sends it. The reader controls what is shared.
- **C. Integration:** the product reads the reader's data through an API, plugin, add-on, extension, connector or MCP server in the reader's tools.
- **D. Self-hosted:** the reader runs the product (the open-source stack plus the founder's configuration) on their own infrastructure; their data never leaves.
- **E. No digital access:** the needed reader data is on paper, in people's heads or in closed legacy systems with no export.

Order of difficulty: A (easiest) → B → C → D → E (hardest). `MAX_SCENARIO` is a **ceiling**: a rung that works under a lower scenario is always allowed.

**F. Human in the loop (modifier, not a scenario):** a human (the reader or the founder) validates or completes part of the output. It can combine with any scenario. Allowed only if `HUMAN_IN_LOOP` is "allowed" or "required"; mandatory on every rung if "required". Founder-side human work must stay a fixed, capped step (for example a 10-minute check per issue), never individual expert judgment and never individualised regulated advice.

### Delivery ladder (how far into the task the product goes)

- **Level 1, input data:** the collected, verified, structured inputs the practitioner needs to start the task.
- **Level 2, draft output:** a first version of the task's result, which the reader reviews and edits.
- **Level 3, near-final output:** a result the reader only validates.

Fixed rules:
- **The free version is always scenario A**, at Level 1 or Level 2 (it cannot use any reader's data).
- **The paid version** may use any scenario up to `MAX_SCENARIO` and aims at `TARGET_DEPTH`.
- **Cap, do not kill:** if `TARGET_DEPTH` needs a scenario above `MAX_SCENARIO`, record the highest level reachable under `MAX_SCENARIO` as the candidate's **maximum depth**, flag the gap, and continue. A candidate is killed on this ground only if even Level 1 under scenario A is impossible (check 3).
- For each candidate, state the **lowest** scenario needed for each level, not the most convenient one.

## Market saturation by level

Saturation is measured **separately for Level 1, 2 and 3 of the delivery ladder**, for the candidate's segment, in COUNTRY. A market is often crowded for raw inputs and empty for draft outputs: the saturation profile shows where on the ladder there is room. Competitors are counted, but the count never decides the level on its own: what decides it is whether the segment can actually get a mature solution at that level, how alike the solutions are, and whether practitioners say they still fall short.

**Which offers count at a level:** an offer counts at the level it delivers, and at a lower level only if it also gives the user that lower level's output (for example, a draft-output tool that also exposes the collected inputs counts at Level 1). It counts only for the candidate's segment and country, or if the segment visibly uses it. General AI assistants count only at the levels where they give an acceptable output in one prompt from public inputs (label "reasoned" unless tested).

### Four measures per level (each with links or "none found")

| Measure | 0 | 1 | 2 |
|---|---|---|---|
| **Availability:** can the segment get a solution at this level? | No offer the segment can get: none, sales-only enterprise offers, another country or language, another segment | Offer reachable with friction: price clearly above what the segment pays for adjacent tools, sales call required, only part of the output covered | Reachable self-serve at a price the segment already pays for adjacent tools, OR free, OR bundled in a tool the segment already uses |
| **Maturity:** how established is the best offer? | No offer, or all launched in the last 12 months, in beta, or with no independent evidence of use | At least one offer on the market for 12 months or more, with at least 3 independent reviews or mentions of real use | At least one offer is the segment's standard: on the market 3 years or more, OR 10+ independent reviews, OR recommended by the segment's association, training or dominant software marketplace |
| **Similarity:** how alike are the offers that scored 1 or more on availability and maturity? | Fewer than 2 such offers, or they differ in inputs, output or segment | 2+ overlap on the core output but differ on a significant feature, level, scenario or price band | 3+ with the same core output, same level and scenario, prices within about ±30% of each other (or free), and matching feature lists on their own pages |

**Unmet need** (yes / no): dated independent practitioner complaints, requests or workarounds about the existing offers at this level, in the 18 months before RUN_DATE. Vendor content does not count.

### Classification per level

- **Low:** Availability 0 OR Maturity 0. Solutions are absent, out of reach for the segment, or immature. Write **Low (empty)** when no offer exists at all.
- **High:** Availability 2 AND Maturity 2 AND Unmet need = no, AND either Similarity 2 OR a free or bundled mature offer that the segment already uses. The segment can easily get mature, look-alike solutions and does not complain about them.
- **Medium:** every other case. Established solutions exist (Availability 1 or more and Maturity 1 or more), but the offers differ meaningfully OR practitioners report unmet needs. Record which reason applies ("Medium: unmet need", "Medium: dissimilar offers", "Medium: friction"), because that reason is the opening.

A market with many competitors is therefore Medium, not High, when practitioners still report needs the competitors do not meet.

**Uncertainty:** if a measure cannot be scored (private pricing, sales-only offers, review counts not observable), score the range (for example Maturity 1–2), give the level as a range (for example "Medium–High"), and add the missing evidence to the manual validation list.

**Usual pattern:** saturation usually falls as the level rises, because each level is harder to build. A profile such as "L1 High / L2 Medium / L3 Low" points to entering above the crowded level.

### How `TARGET_SATURATION` is applied

- Each candidate has a **competitive level**: the ladder level the paid version will be sold on. Choose it among the levels reachable under `MAX_SCENARIO` and `HUMAN_IN_LOOP`: the level whose saturation matches `TARGET_SATURATION`, and if several match, the one closest to `TARGET_DEPTH`. If `TARGET_SATURATION` is open, the competitive level is the maximum depth. A range (for example "Medium–High") matches each of its values, with a flag.
- **open:** no filter. Every saturation is accepted and reported.
- **Low:** keep candidates with at least one reachable level classified Low. Expect weaker proof that people pay; the "why is it empty?" test and the demand test carry more weight.
- **Medium:** keep candidates with at least one reachable level classified Medium. The named reason for Medium becomes the gap hypothesis to test first.
- **High:** keep candidates with at least one reachable level classified High. Payment and buyer education are proven, but only a Strong differentiation passes check 7.
- The filter is applied provisionally in 1d (from the competitor register) and confirmed in check 7. A candidate that does not match is **off-target**, never killed: it is reported with its profile so that another run with a different setting can pick it up.
- If the competitive level is below `TARGET_DEPTH` because the target level does not match the saturation sought, say so and flag "depth lowered for saturation".

## Product blueprint

For every candidate that reaches Step 1e, the handoff shows three things, so that the founder sees what to build without reading the whole report:

1. **Data sources to curate** (`data_sources`): every input the product needs, one line each, with an ID (S1, S2, ...): name, link, kind, scenario (A public, B reader upload, C integration, D self-hosted), access mode (API, bulk file, scraping, manual upload, connector), **input format** (CSV, JSON, XML, XLSX, text PDF, scanned PDF, HTML, other), reuse terms, refresh rate, and the levels that use it. Public sources are scenario A. Reader sources (their export, their account, their files) are scenario B, C or D, and the line says which export or fields are needed.
2. **Stack** (`stack.pipeline`): the ordered stages that turn the sources into the output, one line each (P1, P2, ...): stage, tool category, project found (licence, last release date) or "category only", coverage, the input it takes (source IDs or previous stage, and the format) and the output it produces (and the format). Also the **curated asset** the founder keeps and grows (for example a normalised table of contracts with their expiry dates, in CSV or SQLite), or "none".
3. **Customer deliverable** (`deliverables`): for the free version and for each scenario rung from A up to `MAX_SCENARIO`: what the customer receives, the **file or data format** (email digest, PDF, CSV, XLSX, JSON through an API, MCP server, web page, calendar file, alert message), the main fields or columns, the channel, the cadence, and what the customer must provide (nothing in A, an upload in B, a connection in C, an installation in D). A rung that is not reachable states the blocker; a rung above `MAX_SCENARIO` is written "above MAX_SCENARIO" and not designed.

Rules: a format is **Confirmed** only if seen in a sample file, an API documentation page or a publisher page you opened; otherwise **Unverified**, written as "format (Unverified)". Formats and reuse terms are findings, never assumptions. The blueprint describes what the product could be; it is not a design of the input pack (Prompt 2 does that).

## Product model

The founder is not an expert in the role. They act as a data and information curator. The product has two versions built from the same input work:

- **Free version:** a recurring or event-driven issue (newsletter, digest or change alert), at the cadence the change rate allows (event-driven, monthly, quarterly or annual), that contains a real result, not a summary: one output the reader can use. Scenario A, Level 1 or 2.
- **Paid version:** the same output produced automatically for the reader's own case (a checker, alerts or monitoring of the reader's own contracts, products or files, a dataset, a structured search, a form-based assistant, an API or MCP server), at the highest level reachable up to `TARGET_DEPTH` within `MAX_SCENARIO`.
- **Second revenue type: implementation upsell.** A defined, fixed-price add-on that moves the client **one rung up the ladder**: from scenario A to B (loading their own export into the checker, setting up alerts on their own list), from B to C (connecting the feed to their CRM, tools or AI agent), from C to D (installing the stack on their infrastructure), or from one level of depth to the next; also a one-off audit run through the tool or a training session. It is not custom consulting and never individualised regulated advice.

**A recurring reason to pay matters more than a publishing rhythm.** A task qualifies when its inputs change from time to time and a reader without the time or the skill to keep up loses something by missing a change. The cadence is not fixed at weekly or monthly: a rule that changes twice a year but causes a rejected file or a lost contract when missed can support an annual plan or alerts, while a weekly feed of low-stakes news may not.

A task counts only if both versions can pass: the free issue earns attention with a real result, the task has a recurring value (see Step 2 check 1), and the paid version has an automation test and either a price anchor (path A) or a stated pricing hypothesis with a validation test (path B).

The customer is the domain expert and can judge the output themselves. The product gives no individualised regulated advice.

## The two paths

- **Path A: proven spend.** At least one paid tool, service or outsourced task exists for this output or its inputs, with a price from the provider's page. The price is the anchor. Competition is likely, so check 7 applies in full.
- **Path B: latent demand.** No visible paid offer for this output, but at least 2 **proxy signals** (dated and linked) AND a validation test defined before any build. Proxy signals:
  1. practitioners do the work by hand and say it takes hours (forum threads, training content, job postings that list the task);
  2. workarounds exist: spreadsheets shared in communities, freelancers hired for one-off versions, internal staff dedicated to it;
  3. the decision it feeds is expensive and the cost of a bad input is visible;
  4. adjacent data is already paid for (people buy a nearby dataset or service, but not this slice);
  5. a similar product sells in another country or sector, with evidence of paid success there.

  A path B candidate has no price anchor, so its price is a hypothesis, labelled as such. It is never killed for missing evidence alone, only for disproof (the task is automated away or abolished, or a product already covers it).

A path B candidate must define its **validation test** up front: 10 practitioner conversations, a pre-sale page with a price, or a manual "concierge" version of one issue for 3 readers; and what result counts as success and what as failure.

## Rules

### Portability

- **Web search is required.** If you cannot search the web, say so in one line and stop. Never produce the report from memory.
- **Long answers.** If your answer is about to hit its limit, stop at the end of a section, write `CONTINUE` on its own line, and resume exactly there when the user replies "continue". Never shorten or skip later sections.
- **Context economy.** Search results are long. Keep working notes to one line per finding; never paste or restate search results in the answer. Only the report and the handoff block are written out in full.
- **Optional tools.** If you can fetch full pages or run sub-agents, use them where useful (fetching a provider's own price page or a repository page is preferred to reading a snippet); otherwise work in sequence and say in the run summary what was missing.
- **Order.** Follow the steps in order.

### Evidence statuses

Every claim that matters carries a dated source link (prefer the last 18 months; if the page shows no date, say "undated") and one status, each with a confidence (high, medium, low):

- **Confirmed:** supporting evidence found.
- **Disproved:** evidence against. Kill if the check is mandatory.
- **Unverified:** you searched properly and found nothing. Kill only if the check is mandatory AND the evidence would normally be easy to find AND the candidate is on path A. Otherwise flag.
- **Not observable:** the evidence exists but is out of reach (login, private pricing, group counts, private communities, sales calls). Never a kill; it goes to the manual validation list. Record the query tried and what blocked it.

Anything stated without a search is labelled "unverified: reasoned from background knowledge" and can never support a pass on a mandatory check.

### Evidence rules

- **Demand evidence:** on path A, a task counts only with a signal from real practitioners: complaints, repeated forum questions, paid templates, training or consulting offers, outsourced services priced per task. On path B, proxy signals replace this, as defined above. "Nice to have" is never evidence on either path.
- **Vendor claims:** figures, testimonials and NPS published by vendors selling to the segment (volumes, hours saved, error rates, satisfaction scores) are unverified marketing claims. They never support a pass on recurrence, sizing or bottleneck, and never count as a proxy signal or as D3 demand.
- **Competitors are spend, not demand:** an existing paid product proves that people pay (spend evidence, price anchor). It does not prove demand for a new product. Demand comes from practitioners' own signals. A crowded market shows that the need is real and that people pay; it is never a kill on its own. Saturation raises the differentiation required (check 7), and Prompt 2 tests that differentiation.
- **Spend and interest signals:** record, with date and link, any of these for the task or its inputs. They are weighed differently:
  - *Spend evidence (counts for D2 and path A):* paid training courses with a visible price and dated sessions, paid templates, certifications, paid conferences, outsourced services priced per task.
  - *Interest evidence (counts as a proxy signal for path B, never as D3 demand):* books and ebooks on the task (publisher or retailer page, publication date, number and dates of reviews), training material and course outlines, webinars with registrations, and active paid advertising for solutions to the task (public ad libraries such as the Meta Ad Library and the Google Ads Transparency Center, with advertiser, creative and start date).
  - *Limits:* paid advertising shows that a seller believes buyers exist, not that buyers buy; a book shows interest in a topic, not in this exact output; duration matters (an ad running for months is stronger than one launched last week). Record ad and book evidence as "seller belief" or "topic interest", not as "buyer demand".
- **Open-source evidence:** a tool counts as stack coverage only if found by search, with its repository or project page link, its licence, and its last release or commit date. Never name a project from memory; at most write the tool category. A project with no release or commit in the 12 months before RUN_DATE, an archived repository, or a licence outside `LICENCE_POLICY` does not count as coverage (record it as "found, not counted" with the reason). Open-source availability is never demand evidence and never a proxy signal.
- **Why now** is a bonus, not a requirement. If used, it needs a dated source and must remove a documented blocker or create a documented need. "AI is now capable" never counts, and neither does "an open-source tool now exists". A standing need is allowed; write "standing need".
- **Capability rule:** never start from a capability ("AI can summarise this", "this GitHub tool does X") and look for a task. The stack is mapped only after a candidate exists (Step 1e).
- **Hint rule:** if HINT is set, search its direction first. It never counts as evidence and never changes a check, a ranking or a verdict.

### Avoid

Do not propose generic industry-news or market-news summaries, simple competitor monitoring, generic regulatory newsletters, generic AI research assistants, generic LLM summaries, or anything a professional gets with one ChatGPT prompt. At most 2 of the CANDIDATES may be driven mainly by a regulatory change.

**News mining is allowed, news summarising is not.** A candidate may build on news or other text when the product extracts structured data from it (entities, amounts, dates, locations, event types, counterparties) into a fixed schema that a task, a calculation, a user's AI agent or an MCP server consumes, so the practitioner no longer reads and re-keys the text by hand.

### Stopping and honesty

- **Stop at the first kill** for each candidate. Log every query, one line each (step, query, finding, status), including searches done before a kill. Run the checks in order; do not skip ahead to a later check.
- **Zero survivors is an acceptable result.** Never loosen a threshold or invent evidence to keep a task alive. If nothing survives, say so, list the closest near-misses and the smallest change that would revive each (including "raise MAX_SCENARIO to X" or "lower TARGET_DEPTH to Y" where that is the blocker), and suggest 2 neighbouring roles.
- **Budget fallback:** if search stops working or room runs out, finish the mandatory checks for the current candidate, write the report in the given order, and mark unfinished parts "not run". Never fill a not-run part from memory.
- **No invented content:** never invent a source, price, number, quote, review count, repository or licence. Quote at most a few words from any source; paraphrase the rest.
- **Sources:** prefer fetching one specific page over several searches on the same topic. Prefer primary and official sources. Read prices from the provider's own page; when you cannot, label the price source (third party or secondary).

### Language

Search primarily in LANGUAGE with short, specific queries. Also search in English for global competitors, vendor features, paid success abroad and open-source tools. Write the report content in LANGUAGE. Keep section headings, table column names, handoff field names and status labels (Confirmed, Unverified, Disproved, Not observable) in English.

### Pre-filter

Exclude or narrow tasks that would need a licence to give individualised regulated advice (legal, tax, medical, financial advice to a specific person). Information, benchmarks and checklists are fine. Flag, but do not auto-kill, tasks where a wrong input could cause serious harm or large cost. If a task is too broad, split it and continue with the most decision-heavy part with the clearest recurring value.

### Competitor register

Start one register at Step 1 and carry it through every step. One row per alternative: name, URL, kind (paid product, free official or association resource, general AI assistant, outsourced service, paid training, open-source tool producing the same output), price, price source (provider page | third party | secondary | Not observable), channel (how the segment gets it), what it produces, **depth delivered** (Level 1 / 2 / 3), **scenario used** (A to E, or "unknown"), date checked. Later steps add or update rows; never repeat a search already in the register.

An open-source tool that already produces the candidate's output end to end, usable by the segment without technical skill, is a competitor (register it here). An open-source tool that covers only one step is stack coverage (Step 1e), not a competitor.

## Step 0: Role gate (only if ROLE_GATE = on)

At most 3 searches. Question: does this role already pay for input data, tools or outsourcing? Look for paid tools sold to the role, data vendors, outsourced services priced per task, job postings that buy the work.

- **Pass:** at least 2 paid offers for this role with a price from the provider's page.
- **Flag (continue):** none or one offer, or offers only through associations or bundled in other services. This is not a stop. It means the role has no visible market yet: say so in the summary, raise PATH_B_MAX to 3, and expect most candidates on path B.

Step 0 never stops the run.

## Step 1: Task inventory, bottleneck, payment, candidates, stack

### 1a. Inventory (do not filter yet)

List INVENTORY_SIZE recurring tasks of the role in COUNTRY. Draw them from job descriptions, official job profiles (for France, the ROME sheets), training syllabi and practitioner forums. For each: task in one line, who does it, how often. Do not judge at this stage.

**Skipping visited tasks:** skip every task in ALREADY_VISITED, whatever its tag. Match by meaning, not by exact wording: a task is visited if it is the same task under another name, or a narrower or wider version of a visited task with the same input and the same decision. A task that shares the role but feeds a different decision or needs different inputs is new. If ALREADY_VISITED names a different ROLE or COUNTRY than this run, say so in the run summary and ignore it. If fewer than INVENTORY_SIZE new tasks can be sourced, list only those found, state the shortfall in the run summary ("role close to exhausted: N new tasks found"), and suggest 2 neighbouring roles; never pad the inventory with filler or renamed visited tasks.

At least 1 linked source for the inventory as a whole and a source per task where possible; tasks with no source are labelled "unverified: reasoned".

### 1b. Bottleneck

For each task, name the slowest step: finding the input, verifying the input, deciding, producing the output, or communicating it. Keep only tasks where finding or verifying the input is the slowest step. This is the entry criterion and does not change with `TARGET_DEPTH`: deeper delivery is assessed later, on candidates only. Evidence (link) can be a practitioner statement, a job description or training content that says so. A task with that evidence is kept for path A. A task without it can still be kept for path B if it has 2 proxy signals, one of which is signal 1 (practitioners do the work by hand and say it takes hours). Your own guess is Unverified and keeps nothing alive. A task dropped here for lack of evidence is "no evidence found in the searches run", not evidence of absence.

### 1c. Payment and proxy signals

For each task kept in 1b, search for people already paying to skip the input work: outsourced services priced per task, freelancers, data vendors, paid tools, subscriptions. Record each in the competitor register with its price, price source, depth delivered and scenario used.
- Payment found: **path A**. The price is the anchor.
- No payment found, but at least 2 proxy signals: **path B**. Record the signals with links.
- No payment and fewer than 2 proxy signals: drop the task, with the reason.

Also note for each task, in one line, how often its inputs change and what a missed change costs; this feeds the 1d cards and check 1.

### 1d. Candidates

From the tasks that remain, pick the CANDIDATES with the highest money per decision and a clear recurring value, at most PATH_B_MAX of them on path B. Do not use the scenario, the depth or the stack to pick candidates. If `TARGET_SATURATION` is not open, first estimate a **provisional saturation profile** for each remaining task from the competitor register (Level 1, 2, 3 classified as in "Market saturation by level", marked "provisional") and prefer tasks with at least one reachable level that matches; if fewer than CANDIDATES match, fill the remaining places with the best other tasks and mark them "provisional off-target". Each gets an ID (C1, C2, ...) and a card:

- **Role / Task / Industry / Country / Exact recurring output** (the output must be specific: not "market intelligence" but, for example, "table comparing each supplier's price change with commodity, energy, freight and FX moves", at whatever cadence the inputs change; a fixed weekly cadence is not required)
- **Path:** A or B
- **Owner** and **practitioner frequency and trigger**
- **Change rate and cost of a miss:** how often the relevant inputs change (with a dated observation of the longest gap you can see), and what a reader without the time or skill to keep up loses by missing a change, from a documented source. Vendor claims do not count.
- **Recurring value route:** which one applies, with evidence: (1) inputs change at least quarterly or on trigger events and a miss has a documented cost; (2) an accumulating asset (history, dataset, register, benchmarks) grows with each update; (3) the reader's own case can be monitored (their contracts, products, files or accounts). If none applies, the task is evergreen (a one-off guide does the job) and fails check 1.
- **Delivery form:** event alerts, monthly digest, quarterly digest or annual update, chosen from the change rate.
- **Decision** it ends in and **money lever** (win clients, raise order value, raise sales frequency, or cut paid cost or time)
- **Slowest step** and its evidence (link)
- **Payment evidence (path A):** the price anchor (tool or service, price, price source, link). **Proxy signals (path B):** at least 2, with links, plus the validation test and its success and failure criteria
- **Task step breakdown:** 3 to 7 steps from trigger to decision. For each step: what it needs (public data / reader's data / judgment), and whether the product would automate it, assist it, or leave it to the reader.
- **Delivery ladder:** for each of Level 1, 2 and 3, the lowest scenario needed (A to E), whether a human-in-the-loop step is needed, and what blocks it if anything. Then the **maximum depth** reachable under `MAX_SCENARIO` and `HUMAN_IN_LOOP`, compared with `TARGET_DEPTH` (reached / capped at Level N, with the blocker).
- **Upgrade path:** which extra access (B, C, D) or which human-in-the-loop step would unlock the next level, in one line.
- **Provisional saturation profile and competitive level:** Level 1, 2, 3 each Low (empty) / Low / Medium / High (provisional), and the competitive level chosen under `TARGET_SATURATION` (only when `TARGET_SATURATION` is not open; otherwise write "set in check 7").
- **Upsell path:** one fixed-price, capped implementation add-on that moves the client one rung up the ladder, and its price anchor (an outsourced service priced per task, a freelancer day rate, a training price) or "none found"
- **Why now** (dated source) or "standing need"
- **Likely buyer and sales route:** who pays and how they are reached (self-serve, marketplace, low-touch onboarding, local relationship; or "self-hosted deployment" for scenario D rungs)

If INDUSTRY or COMPANY_SIZE is open, choose for each candidate the industry and segment where the task is most valuable AND whose buyers can be reached with the founder's sales routes. State the choice and why. Steps 2 and 3 use that segment only. **Whether or not they were open, every card states an explicit industry and segment, never "open": Prompt 2 treats them as fixed.**

### 1e. Sources, stack and deliverable blueprint (candidates only)

At most 3 searches per candidate (publisher pages and sample files, repository hosts, package registries, project pages). Work in this order.

**(i) Data sources.** From the task step breakdown and the ladder, list every public source (scenario A) and every reader source (scenarios B to D, up to `MAX_SCENARIO`) with the fields defined in "Product blueprint": ID, name, link, kind, scenario, access mode, input format, reuse terms, refresh rate, levels that use it. Open the publisher page or a sample file to confirm the format and the terms; otherwise mark them Unverified.

**(ii) Stack.** For each step of the task step breakdown that the product would automate or assist, up to the maximum depth, build the pipeline stage:

- **Tool category** (for example: scraping and crawling, PDF and OCR extraction, entity matching and deduplication, structured extraction with an LLM, geocoding, workflow orchestration, alerting, form builder, dashboard).
- **Example project:** only if found by search: name, link, licence, last release or commit date. Otherwise "category only, not searched" or "none found".
- **Coverage:** covered (a counted project does the step with configuration only) / partly covered (a counted project does part; glue or domain logic needed) / to build.
- **Input and output:** which source IDs or previous stage it reads, in which format, and what it produces, in which format.
- **Build gap:** what remains to develop or configure, in one or two sentences, with special attention to the domain-specific logic (the rules of this task in this country and segment), which no generic tool covers.

Name the **curated asset** the founder keeps (dataset, register, history) with its storage format, or "none".

Then give the candidate a **stack coverage** summary: the share of automated or assisted steps that are covered or partly covered, and the main licence notes (for example, any AGPL component in a network-served product). Stack coverage is a delivery-effort attribute only. It never makes a candidate pass a check and never revives a killed one.

**(iii) Deliverables.** For the free version (scenario A) and for each scenario rung from A up to `MAX_SCENARIO`, state what the customer receives, in which format, with which fields, through which channel and cadence, which source IDs and pipeline stages produce it, and what the customer must provide. Check that the formats chain: every stage's input format must match the format of its source or of the previous stage's output; if a conversion is needed (scanned PDF to text, XML to CSV), it is a stage.

## Step 2: Screen (mandatory checks; stop at the first kill per candidate)

Use 1 to 2 searches per check. Do not decompose the task further. Each check gets a verdict (pass, flag, kill), a status, a confidence, evidence and a link. Differences for path B are stated in the check. Run the checks in order.

1. **Recurrence and recurring value:** pass if the practitioner runs the task at least quarterly, OR a large population triggers it so that across the field it happens at least weekly, OR the task has a recurring value through one of three routes: (1) the inputs change at least quarterly or on trigger events and a miss has a documented cost; (2) an accumulating asset grows with each update; (3) the reader's own case can be monitored. Vendor claims do not count. Kill only the evergreen case: inputs rarely change, no trigger events, no accumulating asset and no upsell path, so a one-off guide does the job. A rare change with no documented cost of a miss is a flag, not a pass.
2. **Decision weight and money lever:** a wrong or late output costs money, time, risk or reputation, or a good one wins clients, raises order value or sales frequency. Name the lever and estimate the size, labelled as an estimate.
3. **Input availability (public and reader inputs):**
   - *Public inputs:* most required public inputs are public or reachable (free or paid APIs, datasets, documents, registries) in LANGUAGE, under terms that allow the use. Confirm against the `data_sources` list from 1e that each key source has a known access mode, input format and reuse terms (a source whose reuse terms forbid redistribution or commercial use is a flag, and a kill if it is a key source with no alternative). **Kill** if the key public inputs are secret or unavailable, so that even Level 1 under scenario A is impossible.
   - *Reader inputs:* for each level above Level 1, confirm which reader data is needed and whether it can be obtained under the scenario stated in the ladder (for example: the segment's dominant software has an export for B, a public API or marketplace for C). If a level needs a scenario above `MAX_SCENARIO`, or its reader data is in scenario E, **cap** the maximum depth at the last reachable level and **flag**. Never kill on reader inputs alone.
4. **Curation gap:** practitioners lack the time, skill or attention to find, filter, verify or translate the inputs. Path A: evidence must come from practitioners, not from your reasoning or from vendor content. Path B: job postings or training content that list the task as manual work count as evidence.
5. **Pre-filter and trust (judged at the maximum depth):** the output can be produced without individualised regulated advice, and an error can be detected by the user before it causes harm. A near-final output raises the stakes: if the reader cannot verify the output at the maximum depth in under 5 minutes, either add a human-in-the-loop step (only if `HUMAN_IN_LOOP` allows it) or cap the depth at the last verifiable level, and flag. Kill only if even Level 1 fails this check.
6. **Sales fit:** the payers can be reached through self-serve, marketplace, low-touch onboarding or a few local relationships. Judge each rung of the ladder by its scenario:
   - *Scenarios A and B:* kill if the only realistic buyer needs a long enterprise sales cycle (formal procurement, security review, committee). Pass if practitioners can buy on a card or a small team budget.
   - *Scenario C:* state whether the buyer can install the integration alone (marketplace app, self-serve connector) or needs IT or security approval. If approval is needed, cap the depth at the last rung the buyer can approve alone and flag.
   - *Scenario D:* the sales cycle is not judged. Record the likely deployment requirements (infrastructure, hosting location, security documentation) as a note for Prompt 2.
   - The candidate is killed on sales fit only if its Level 1 rung fails.
7. **Market saturation by level and differentiation** (up to 4 searches): search for the exact recurring output as a product ("[output] logiciel", "[output] outil", "[output] app"), then the segment's association, its dominant software and its marketplaces, then practitioner complaints about the existing offers, then failed or closed attempts ("[output] fermé", "arrêt du service", shut down). Add every product to the register with price, channel, depth delivered and scenario used (a free official or association resource that covers the core of the output counts as a product; so does an open-source tool usable end to end by the segment without technical skill). Then:
   - **Saturation profile:** score Availability, Maturity, Similarity and Unmet need for Level 1, 2 and 3, and classify each level Low (empty), Low, Medium or High, exactly as defined in "Market saturation by level". Replace the provisional profile from 1d.
   - **Competitive level:** confirm or change the competitive level chosen in 1d. If no reachable level matches `TARGET_SATURATION` (after counting uncertain ranges as matching), the candidate is **off-target**: stop its checks here, record its profile, and report it as "off-target: saturation X at every reachable level". Off-target is not a kill: the idea is not judged bad, only outside this run's focus.
   - **Gap hypothesis:** name where an entrant could still win at the competitive level: an under-served segment (size, trade, region), a missing feature or input, a price point the segment cannot reach, a channel the incumbents do not use, a format gap, an **asset gap** (an accumulating dataset or history the incumbents do not keep), or a **ladder gap** (incumbents stop at a lower level, or need a scenario the segment refuses, for example a SaaS that requires sending data out where a self-hosted version would be accepted). Required at every saturation except Low (empty). A Medium level must name the gap that made it Medium (the unmet need or the dissimilarity).
   - **Differentiation strength**, from three tests:
     - (a) *Need:* the gap is backed by practitioner evidence (complaint, request, workaround), not only by the absence of a feature on a product page.
     - (b) *Durability:* incumbents cannot or will not close it quickly. Structural reasons count (the segment is too small or unprofitable for them, a scenario or channel they cannot offer, a pricing model they would cannibalise), and so does an accumulating asset. A feature they could add in weeks, a UI improvement or a lower price alone are cosmetic. At High saturation, buyers have already heard every claim: the gap must be a different mechanism (new input, new level, new scenario, new asset), not a better version of the same promise.
     - (c) *Reach:* the segment that wants it can be reached through the founder's sales routes and is large enough to matter (estimate, labelled; D1 confirms).
     - **Strong:** a, b and c pass. **Moderate:** two of three pass. **Weak:** only a dated clue (inferred from absence). **None:** no gap can be named.
   - **Low (empty), "why is it empty?":** state the most likely reason, with evidence: a new need (with a dated why now), a segment too small for current vendors, products hidden from search (private pricing, sales-only, bundled in services), or failed attempts. Failed attempts found: flag "graveyard" and carry them to D3. No reason found: flag "empty-market risk"; the demand test then decides.
   - **Verdict** at the competitive level (the higher the saturation, the stronger the differentiation must be):

     | Saturation | Pass | Flag | Kill |
     |---|---|---|---|
     | Low (empty) | reason for emptiness found | "empty-market risk" or "graveyard" | never |
     | Low | Moderate or Strong | Weak or None: "differentiation to prove" | never |
     | Medium | Moderate or Strong | Weak or None: "high differentiation burden" | never |
     | High | Strong (with flag "high saturation: entry via gap only") | Moderate or Weak: "high differentiation burden" | only if None AND a product already produces this output for the whole segment, at the same or greater level, at a price and through a channel the segment already uses |

     For path B, a search that finds nothing is "Unverified" and the level is Low (empty); the report must say how hidden products could be missed.
   - **What Prompt 2 must prove:** one line naming the single claim Prompt 2 must confirm for this candidate to survive competition at its competitive level (for example "at Level 2, practitioners in segment X reject incumbents because they require cloud upload", or for Low (empty): "the market is empty because it is new, not because nobody pays").
8. **Free-to-paid link and automation test:** name (a) the output the free issue would show (scenario A, Level 1 or 2), (b) the paid feature that produces that output for the reader's own data, at the maximum depth and with its scenario, (c) the exact input, output and how the user verifies the result in under 5 minutes, (d) what a one-person build looks like in one or two sentences, based on the Step 1e pipeline and its build gap, and (d2) the customer deliverable format of the free issue and of the paid version (file or data format, main fields, channel), from the 1e deliverables, (e) the price anchor (path A) or the pricing hypothesis and how the validation test would check it (path B), with the subscription form that fits the change rate (monthly, annual with alerts, per event) and the upsell path as a rung move. For a news-mining candidate, also name (f) the schema fields, the source set and the legal basis from the Avoid section. Kill if the free issue cannot contain a real result, if no customer deliverable format can be named for Level 1 under scenario A, if each run needs expert judgment (a fixed, capped human-in-the-loop step allowed by `HUMAN_IN_LOOP` is not expert judgment), or, on path A, if no price anchor exists.

If every candidate is killed here, stop: write the zero-survivor report with the near-misses, the smallest change that would revive each, and 2 neighbouring roles.

**Ranking for Step 3:** rank the candidates that passed by (1) fewest flags, (2) market position at the competitive level: Strong differentiation at any saturation first, then Low or Medium with Moderate, then Low (empty) with a reason for emptiness, then Low (empty) without one, then any candidate flagged "high differentiation burden", (3) strength of the money lever, (4) strength of the payment evidence (path A) or of the proxy signals (path B), then, as last tie-breakers only, (5) the lowest scenario needed to reach Level 2, (6) stack coverage. Founder skills and HINT never enter the ranking. Take the top MAX_DEMAND_TESTED into Step 3, keeping at least one path B candidate in the test if one passed the screen and MAX_DEMAND_TESTED is 2 or more, and, when `TARGET_SATURATION` is open, at least one candidate whose competitive level is Low or Medium if one passed the screen and MAX_DEMAND_TESTED is 2 or more (one candidate can satisfy both rules). Off-target candidates are never demand-tested. Mark the rest "passed the screen, not demand-tested".

## Step 3: Demand stress test (mandatory; stop at the first kill per candidate)

At least 1 search per check, extra on D3, at most 4 per check.

- **D1. Real and sized:** evidence from the exact segment that the task exists, how often, and roughly how many practitioners do it (job postings, official statistics, association membership). Independent sources only. No evidence: kill, on both paths. If existence is confirmed but the population size is not found, say "existence Confirmed, size Unverified" and flag.
- **D2. Existing spend:** practitioners already pay for the same output or its inputs (tools, services, consultants, subscriptions). Use the register. Staff time counts only when visibly bought or budgeted. Paid training courses, paid templates and certifications for the same task count as spend; books, ebooks and ads are interest evidence only (see Evidence rules). Note at which depth the spend sits (people may pay for Level 1 inputs but do the rest themselves, or pay a service for the near-final output).
  - Path A: no evidence: kill. Evidence that exists but is Not observable (private pricing): flag.
  - Path B: absence is expected. Record adjacent spend (a nearby dataset or service people do buy) as the substitute evidence. No adjacent spend: flag, and the validation test becomes mandatory before any build.
- **D3. Practitioner demand signal:** read the public pages of comparable paid offers and the practitioner conversations you can see (forums, reviews, testimonials from independent platforms, training sessions with dates). Testimonials and satisfaction scores published by the vendor do not count.
  - **Confirmed, high:** 10+ reviews or testimonials, 3+ in the last 90 days, describing real use.
  - **Confirmed, medium:** 3+ from different people in the last 6 months.
  - **Confirmed, low:** at least 1 in the last 6 months describing real use.
  - **Weak signal (flag):** none found, but 3+ similar paid offers exist. Practitioner conversations become mandatory in the validation test.
  - **Unverified (flag):** no comparable found. This is the expected result on path B and is never a kill there.
  - **Disproved (kill, both paths):** comparables shut down, abandoned for 12+ months, or discounted to clear. Absence of public reviews alone is not disproof, because B2B buyers rarely post reviews.
  Flag as a risk if the only growth among comparables was sales-assisted, and re-check check 6.
- **D4. Stable or growing:** proxies such as job postings, dated training sessions, thread dates, new obligations, continued publication of the inputs. Kill only with evidence of decline (task automated away, abolished, merged into another role, inputs no longer published). No signal: Unverified, flag.

**Shortlist:** rank the candidates that passed D1 to D4 by (1) path A before path B when the D3 confidence is equal, (2) D3 confidence, (3) fewest flags across Steps 2 and 3, (4) market position (as in the Step 3 ranking), (5) money lever, then, as last tie-breakers only, (6) the lowest scenario needed to reach Level 2, (7) stack coverage. Recommend one candidate for Prompt 2 in one sentence, and if the rank 1 candidate is on path A, also name the best path B candidate if there is one. When `TARGET_SATURATION` is open and the rank 1 candidate competes at High saturation, also name the best candidate competing at Low or Medium saturation if there is one. The user makes the final choice.

## Search limits

Step 0 at most 3. Step 1: at most 4 searches for the inventory, 2 per surviving task for payment and proxy signals, 3 per candidate for the sources, stack and deliverable blueprint (1e). Step 2: 1 to 2 per check per candidate, up to 4 for check 7. Step 3: at least 1 per check per candidate, extra on D3, at most 4 per check. Stop at the first kill.

## Report format (same headings every time, in this order)

1. **Run summary and funnel:** run date, model (if known), tools missing, role gate result (and PATH_B_MAX used), HINT result, MAX_SCENARIO, TARGET_DEPTH, HUMAN_IN_LOOP, LICENCE_POLICY and TARGET_SATURATION used, the inventory count and how many tasks survived each of 1b, 1c (split path A / path B) and 1d, and a table with one row per candidate: ID, task, path, segment, maximum depth (and scenario), saturation profile (L1/L2/L3) and competitive level, differentiation strength (or "not reached"), stage reached, outcome (killed / off-target / passed the screen, not demand-tested / passed the demand test), reason, link. If the run was cut short, say which checks were not run.
2. **Shortlist and recommendation:** candidates that passed, in rank order, each with its task in one line, its path, maximum depth, saturation profile (L1/L2/L3), competitive level and differentiation strength, then a **description** of 3 to 4 plain sentences that lets a reader who has not seen the rest of the report understand why the task was selected. The description covers, in this order: (1) what the practitioner does today and what makes it slow or risky; (2) why a missed or late input costs them something, and how often the inputs change; (3) the strongest evidence that people pay or would pay (the price anchor on path A, the best proxy signal on path B) and how crowded the market is at the level the product competes on (and whether lower or higher levels are more or less crowded), with the gap an entrant could use (or, for an empty market, why it is empty); (4) the main risk or open doubt. It only restates findings already in the candidate's card and checks, with no new claim and no link, and avoids jargon such as check numbers or status labels. The same description goes into the handoff block. Then the recommended candidate. If nothing passed: near-misses, the smallest change to revive each, 2 neighbouring roles. Also give the near-misses of killed candidates and the smallest change that would revive each.
3. **Delivery ladder and stack:** one compact table per surviving candidate: rows = Level 1, 2, 3; columns = lowest scenario, human in the loop (yes/no), reachable under the parameters (yes / capped: blocker), stack coverage of the steps involved, build gap. Then one line for the upgrade path and one for licence notes.
   **Sources, stack and deliverables:** three compact tables per surviving candidate. (1) *Data sources to curate:* ID, name, scenario, access mode, input format, reuse terms, refresh rate, levels. (2) *Pipeline:* ID, stage, tool (licence, date) or category, coverage, input format, output format; below it the curated asset. (3) *Customer deliverable:* rows = free version and one row per rung from A to `MAX_SCENARIO`; columns = what the customer receives, format, main fields, channel and cadence, source IDs and stages used, what the customer provides, reachable (yes / blocker). Formats not seen on a page or in a sample are marked Unverified.
   **Market saturation by level:** one table per candidate that reached check 7 (including off-target and killed ones): rows = Level 1, 2, 3; columns = Availability, Maturity, Similarity (0–2 or a range), Unmet need (yes/no with link), saturation (Low (empty) / Low / Medium: reason / High), main offers at this level (2 to 3 names). Below each table: competitive level, match with `TARGET_SATURATION`, gap kind, differentiation strength (need / durability / reach), verdict, what Prompt 2 must prove. Then one sentence on the mix: how many candidates compete at each saturation, and how many were off-target.
4. **Dropped tasks:** the inventory tasks removed at 1b and 1c, one line each with the reason (kept short).
5. **Evidence gaps and manual validation list:** unresolved doubts, all Not observable items, the questions to ask practitioners (including "when did you last miss a change in these inputs, and what did it cost?", "who does this for you today, and what do you pay?", and "could you export this data from your tool, or would you need us to connect to it?"), every open-source project to verify by hand, and for each path B candidate its validation test with success and failure criteria.
6. **Updated ALREADY_VISITED:** one single line, inside a code block, ready to paste as the `ALREADY_VISITED` parameter of the next round. Build it as follows:
   - Start with `[ROLE | COUNTRY]` of this run.
   - Keep every entry of the input ALREADY_VISITED unchanged (same wording, same tag), unless it named a different ROLE or COUNTRY, in which case start fresh.
   - Append every task of this run's 1a inventory, named in one short line (at most about 10 words), with exactly one tag:
     - `[1b no evidence]` dropped at 1b for lack of bottleneck evidence (not proven dead; worth revisiting with other sources)
     - `[1b not input]` dropped at 1b because the slowest step is not finding or verifying the input
     - `[1c no payment]` dropped at 1c (no payment and fewer than 2 proxy signals)
     - `[not picked]` survived 1c but was not among the CANDIDATES
     - `[killed S2-cN]` killed at Step 2 check N (for check 7, write `[killed S2-c7 saturated]`)
     - `[off-target sat: L1 x / L2 y / L3 z]` did not match `TARGET_SATURATION`; worth revisiting with another setting (delete the entry to re-examine it)
     - `[killed DN]` killed at Step 3 check DN
     - `[screened]` passed the screen, not demand-tested
     - `[shortlisted]` passed the demand test
   - Separate entries with `; `. No line breaks, no duplicates: if a new task matches a visited one by meaning, keep only the older entry.
   - Below the code block, one sentence: how many entries were carried over and how many were added.
7. **Handoff block for Prompt 2:** exactly this format, inside a code block. Fill every field; write "none", "unknown" or "not run" rather than omitting one. The block must be complete on its own: Prompt 2 reads all its parameters from it, so every run setting is repeated here. Include one full `candidate` entry for every candidate that passed the screen (Step 2), whether demand-tested or not; killed and off-target candidates appear only as one-line entries and cannot be passed to Prompt 2 without a new run. Every candidate entry states an explicit `industry` and `segment`, never "open". Keep each field to one line or a short list: this is context for a stress test, not a full trace (no query log, no full evidence list).

```
=== HANDOFF START ===
handoff_version: find-v1.9
run_date: <RUN_DATE>
model_used: <name or "unknown">
tools_missing: <none or list; include any check not run>
candidate_ids: <IDs of the full candidate entries below, for example C1, C3, C5>

parameters:
  ROLE: <value>
  COUNTRY: <value>
  INDUSTRY: <value given to this run, "open" if open; each candidate states its own explicit industry>
  COMPANY_SIZE: <value given to this run, "open" if open; each candidate states its own explicit segment>
  LANGUAGE: <value>
  HINT: <value or "none">
  ALREADY_VISITED_COUNT: <number of entries in the input line, or "none">
  ROLE_GATE: <on | off>
  ROLE_GATE_RESULT: <pass | flag: reason | off>
  PATH_B_MAX_USED: <value>
  INVENTORY_SIZE: <value>
  CANDIDATES: <value>
  MAX_DEMAND_TESTED: <value>
  MAX_SCENARIO: <value>
  TARGET_DEPTH: <value>
  HUMAN_IN_LOOP: <value>
  LICENCE_POLICY: <value>
  TARGET_SATURATION: <value>

already_visited_line: <the exact line from report section 6, on one line>

recommendation:
  recommended: <ID and one sentence>
  best_path_b: <ID and one sentence, or "none">

candidates:
  - id: <C1>
    outcome: <passed the demand test | passed the screen, not demand-tested>
    rank: <shortlist rank or screen rank>
    path: <A | B>
    task: <one line>
    description: <3 to 4 plain sentences, see report section 2 for the rules>
    industry: <explicit value, never "open">
    segment: <explicit: company size, trade, region; never "open">
    exact_output: <one line>
    owner_and_trigger: <who does it, how often, what triggers it>
    change_rate: <how often inputs change; longest observed gap with date>
    cost_of_miss: <one line, with link>
    recurring_value_route: <1 | 2 | 3, one line>
    delivery_form: <event alerts | monthly | quarterly | annual>
    decision_and_lever: <decision; lever; size estimate labelled as estimate>
    slowest_step: <one line, with link>
    data_sources:
      - <S1 | name | link | kind (registry | open data | document series | web page | feed | API | reader export | reader account) | scenario (A | B | C | D) | access (API | bulk file | scrape | manual upload | connector | on-premise) | input_format (CSV | JSON | XML | XLSX | PDF text | PDF scanned | HTML | other; "(Unverified)" if not seen) | reuse_terms (licence or "unverified") | refresh | levels used>
      - <S2 ...: one line per source; reader sources state the export or fields needed>
    task_steps: <3 to 7 steps, each: name | public / reader / judgment | automate / assist / leave>
    ladder:
      level_1_input_data: <lowest scenario; human in loop yes/no; reachable yes/no>
      level_2_draft: <lowest scenario; human in loop yes/no; reachable yes / capped: blocker>
      level_3_near_final: <lowest scenario; human in loop yes/no; reachable yes / capped: blocker>
      max_depth: <Level N under scenario X>
      vs_target_depth: <reached | capped at Level N: blocker>
    upgrade_path: <extra access or human step that unlocks the next level>
    stack:
      coverage: <share of automated or assisted steps covered or partly covered>
      pipeline:
        - <P1 | stage | tool category | project (licence, last release date) or "category only" | coverage (covered | partly | to build) | input: source IDs or previous stage, format | output: format>
        - <P2 ...: one line per stage, in order>
      curated_asset: <what the founder keeps and grows, with storage format, or "none">
      build_gap: <one or two sentences, domain logic first>
      licence_notes: <one line or "none">
    free_version: <output of the free issue, scenario A, level>
    deliverables:
      free: <customer receives | format | main fields | channel and cadence | sources S.. via stages P..>
      rung_A: <public data only: customer receives | format | main fields | channel | sources and stages | customer provides "nothing" | levels delivered; or "not reachable: blocker">
      rung_B: <reader upload: same fields, customer provides the export named in data_sources; or "above MAX_SCENARIO" or "not reachable: blocker">
      rung_C: <integration: same fields, customer provides the connection; or "above MAX_SCENARIO" or "not reachable: blocker">
      rung_D: <self-hosted: same fields, customer provides the infrastructure; or "above MAX_SCENARIO" or "not reachable: blocker">
    paid_version: <paid feature, level, scenario, how the user verifies in under 5 minutes>
    price: <path A: anchor, price, price source, link | path B: hypothesis, labelled>
    subscription_form: <monthly | annual with alerts | per event>
    upsell: <rung move, fixed price anchor or "none found">
    payment_or_proxy_evidence: <path A: anchor link | path B: 2+ signals, one line each with link>
    competitors: <top 3 to 5 from the register: name | kind | price | channel | depth | scenario | link>
    saturation:
      target_saturation: <open | Low | Medium | High>
      level_1: <Low (empty) | Low | Medium: reason | High | range>; A <0-2> M <0-2> S <0-2> U <yes/no, link>; main offers <names>
      level_2: <same format>
      level_3: <same format>
      competitive_level: <Level N, saturation; "depth lowered for saturation" if below TARGET_DEPTH>
      why_empty: <Low (empty) only: reason with evidence, "graveyard: names", or "none found"; otherwise "n/a">
    gap_hypothesis: <one line, kind (segment | feature | price | channel | format | asset | ladder), clue with link or "no clue: must test">
    differentiation:
      strength: <Strong | Moderate | Weak | None>
      need: <pass/fail, practitioner evidence with link>
      durability: <structural | asset | cosmetic, one line why>
      reach: <pass/fail, segment and size estimate labelled>
    must_prove: <the single claim Prompt 2 must confirm to survive competition>
    sales_route: <self-serve | marketplace | low-touch | local relationship; scenario D deployment notes if any>
    screen_results: <check 1 to 8: verdict/status/confidence, compact, e.g. "1 pass/Confirmed/high; 2 pass/Confirmed/medium; ...">
    demand_results: <D1 to D4: verdict/status/confidence, or "not run">
    flags: <list, one line each>
    not_observable: <list, one line each>
    validation_test: <path B: test, success criteria, failure criteria | path A: recommended practitioner questions>
    why_now: <dated source or "standing need">

off_target_candidates:
  - <ID | task | path | saturation L1/L2/L3 | which TARGET_SATURATION would pick it up>

killed_candidates:
  - <ID | task | path | killed at check X | reason | smallest change to revive>

near_misses_from_inventory:
  - <task | dropped at 1b or 1c | reason>
=== HANDOFF END ===
```