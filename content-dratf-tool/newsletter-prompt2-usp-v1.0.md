# Prompt 2 (Refine): from an initial task to a validated USP, for a fixed role and industry: VERSION October 2026 (usp-v1.3)

> **How to run (for the user; the model can skip this box)**
> 1. Run Prompt 1 (find-v1.9) first. Older handoffs (find-v1.7, find-v1.8) are still read, but they lack the sources, stack and deliverable formats, so Prompt 2 has to find them itself and uses more of its search budget.
> 2. The only place where you paste anything is `FIND_HANDOFF`. Below, fill only three things: `RUN_DATE` (today), `CANDIDATE_ID` (the ID you picked, for example C1) and `FIND_HANDOFF` (the whole block from `=== HANDOFF START ===` to `=== HANDOFF END ===`, pasted without editing). Do not retype any other parameter: the prompt reads them from the handoff.
> 3. Optional: `HINT` (your own direction for this round) and `OVERRIDES` (values you deliberately want to change, see the list in Step 0). Leave both as "none" for a plain run.
> 4. Use any model with web search turned on, in normal mode. A model that can run sub-agents gives a stronger stress test (Step 4B). Paste the whole prompt and send it. If the answer stops with `CONTINUE`, reply "continue".
> 5. Check the "Parameters applied" table the model prints first (10 seconds): it shows each value and where it came from. If something looks wrong, stop the run and fix the input.

> **Changelog v1.2.1 → v1.3**
> - Every task version now carries a **product blueprint**: the data sources to curate (with access mode, input format, reuse terms, refresh rate, scenario), the stack pipeline (stage, tool, input format, output format, curated asset) and the customer deliverable (format, fields, channel) for the free version and for each scenario rung up to `MAX_SCENARIO`. New section "Product blueprint".
> - Step 0.0 reads the blueprint from a find-v1.9 candidate entry (`data_sources`, `stack.pipeline`, `deliverables`); with find-v1.7 or find-v1.8 it is built in Step 1f and flagged.
> - New Step 1f (blueprint verification of V0), blueprint lines on every variant card, a feasibility check on the blueprint (score F), a blueprint attack in category 6, a proof sample shown in the real customer format, report section 6 extended, and the output handoff gets `data_sources`, `stack` and `deliverables`.
> - Accepts `handoff_version` find-v1.9 in addition to find-v1.7 and find-v1.8.

> **Changelog v1.2 → v1.2.1**
> - The input block is renamed `FIND_HANDOFF` (it is the block you paste from Prompt 1). The block written at the end of this prompt keeps the `=== USP HANDOFF START/END ===` markers and is output only; the user never fills it in. Report section 8 now says so.

> **Changelog v1.1 → v1.2**
> - The parameter block is reduced to `RUN_DATE`, `CANDIDATE_ID`, `FIND_HANDOFF`, `OVERRIDES` and `HINT`. All other parameters are read from the handoff (new Step 0.0), so nothing is retyped.
> - New Step 0.0 "Handoff validation and parameter resolution": checks the markers, the version, the candidate ID and the completeness of the entry; resolves every parameter from a fixed source; applies and reports overrides; prints a "Parameters applied" table before any search; stops with one line on a blocking error.
> - Overrides: an explicit, limited list. `ROLE`, `COUNTRY`, `INDUSTRY` and `LANGUAGE` cannot be overridden (change them with a new Prompt 1 run).
> - Compatible with handoffs from find-v1.7 (missing fields are filled from the candidate entry or marked unknown and flagged).
> - Step 0 consistency check now compares the candidate entry with the resolved parameters, and recomputes the ladder if an override changes `MAX_SCENARIO`, `TARGET_DEPTH` or `HUMAN_IN_LOOP`.

> **Changelog v1.0 → v1.1**
> - Step 0 runs the demand gate (D1 to D4) when Prompt 1 did not; variants are generated from unserved needs, V0 is one variant among others, with a diversity rule; a score of 2 requires Confirmed evidence; two-stage stress test (4A quick screen, 4B full 12 attacks) with a separated attacker; new proof sample (Step 5); general-AI baseline is run and graded; global `SEARCH_BUDGET`; handoff extended.

**Your part:** you are part 2 of 2. Prompt 1 found an initial task (V0). Your job is NOT to validate V0. Your job is to find a version of the task that carries a **Unique Selling Proposition (USP)** the customers would pay for, by assessing the market, generating alternative versions of the task, attacking them, refining them, and selecting the strongest, or by concluding honestly that none is strong enough. The role, country and industry stay fixed. The task, its output, its depth on the ladder, its delivery form and its segment (inside the fixed industry) may change.

A USP here is a specific, evidenced reason why a named customer in the fixed role and industry would choose this product over every alternative they have today (including doing nothing and asking a general AI assistant), and keep paying for it.

## Inputs (the only things the user fills in)

RUN_DATE = today   (today; used for every "last N months" window; never guess it. If it is not filled, say so and stop)
CANDIDATE_ID = C1   (the ID of the candidate to refine, as written in the handoff's `candidate_ids`)
HINT = none   (optional: your own direction for where to look first. Never evidence, never changes a score or a verdict)
OVERRIDES = none   (optional: one `NAME = value` per line, only from the overridable list in Step 0.0)
FIND_HANDOFF =
```
=== HANDOFF START ===
handoff_version: find-v1.9
run_date: 2026-10-12
model_used: Gemini
tools_missing: none
candidate_ids: C1, C2, C3, C4, C5

parameters:
  ROLE: Business Developer
  COUNTRY: France
  INDUSTRY: open
  COMPANY_SIZE: open
  LANGUAGE: French
  HINT: none
  ALREADY_VISITED_COUNT: none
  ROLE_GATE: on
  ROLE_GATE_RESULT: pass
  PATH_B_MAX_USED: 2
  INVENTORY_SIZE: 20
  CANDIDATES: 5
  MAX_DEMAND_TESTED: 3
  MAX_SCENARIO: A
  TARGET_DEPTH: input data
  HUMAN_IN_LOOP: allowed
  LICENCE_POLICY: permissive only
  TARGET_SATURATION: open

already_visited_line: [Business Developer | France] identifier créations d'entreprises [1c no payment]; veille appels d'offres publics/privés [shortlisted]; veille levées de fonds [screened]; recrutements stratégiques CISO [screened]; transferts de siège social [shortlisted]; subventions environnementales [screened]; mise à jour CRM [1b not input]; rédaction emails prospection [1b not input]; calcul devis [1b not input]; relance factures [1b not input]; suivi prix concurrents [1b no evidence]; organigrammes comptes complexes [not picked]; visiteurs site web [not picked]; stack technologique prospects [not picked]

recommendation:
  recommended: C1. La taille du marché des appels d'offres publics IT et le levier financier pour les PME garantissent une propension à payer forte.
  best_path_b: C4. Le transfert de siège social est le déclencheur d'achat le plus puissant et systématique pour l'IT et l'aménagement.

candidates:
  - id: C1
    outcome: passed the demand test
    rank: 1
    path: A
    task: Veille des appels d'offres publics/privés
    description: Les commerciaux IT passent des heures chaque semaine à éplucher les portails de marchés publics (BOAMP, plateformes locales) pour trouver des projets pertinents, une tâche rendue fastidieuse par des moteurs de recherche archaïques et un volume de faux positifs énorme. Les appels d'offres sont publiés quotidiennement et rater une publication signifie perdre une opportunité de chiffre d'affaires de 50k€ à 500k€ par manque de temps pour préparer la réponse. Les entreprises paient déjà des abonnements onéreux à Vecteur Plus ou Spigao, ce qui crée un marché saturé pour les données brutes, mais un acteur de niche peut s'imposer en offrant une extraction ultra-qualifiée des technologies requises et des budgets spécifiques au secteur IT, sans engagement annuel. Le risque principal est de ne pas réussir à extraire avec fiabilité les spécifications techniques enfouies dans les PDF des cahiers des charges (DCE) via les seules données publiques.
    industry: Services IT / ESN
    segment: PME (10-250 employés)
    exact_output: Tableau quotidien des appels d'offres publics et privés (IT/Digital) qualifiés avec estimation budgétaire et technologies requises
    owner_and_trigger: Business Developer IT, quotidien, déclenché par de nouvelles publications BOAMP
    change_rate: Quotidien; 24h
    cost_of_miss: Perte d'une opportunité commerciale majeure (50k€-500k€) due au non-respect des délais de réponse.
    recurring_value_route: 1
    delivery_form: event alerts
    decision_and_lever: Sélectionner les marchés à cibler; win clients; 50k€-200k€ par marché (estimate)
    slowest_step: Filtrer le bruit et extraire les exigences techniques réelles des PDF administratifs.
    data_sources:
      - S1 | BOAMP Open Data | https://www.data.gouv.fr/fr/datasets/boamp/ | open data | A | API | JSON | Etalab 2.0 | daily | 1
      - S2 | France Marchés | https://www.francemarches.com | web page | A | scrape | HTML | unverified | daily | 1
    task_steps: Surveiller publications | public | automate; Filtrer par secteur IT | public | automate; Extraire budget et tech stack | public | automate; Lire le cahier des charges | judgment | leave; Décider de répondre | judgment | leave
    ladder:
      level_1_input_data: A; no; yes
      level_2_draft: C; no; capped: max scenario A
      level_3_near_final: C; no; capped: max scenario A
      max_depth: Level 1 under scenario A
      vs_target_depth: reached
    upgrade_path: Intégration CRM (Scénario C) pour populer directement les fiches opportunités
    stack:
      coverage: partly covered
      pipeline:
        - P1 | Fetch & Filter | API Client / RSS Parser | category only | covered | JSON | JSON
        - P2 | IT Entity Extraction | LLM Structured Extraction | category only | partly | JSON | CSV
      curated_asset: Base de données historique des appels d'offres IT (SQLite)
      build_gap: Extraire de manière structurée les stacks techniques depuis des textes XML très longs sans exploser les coûts LLM.
      licence_notes: none
    free_version: Top 3 appels d'offres IT qualifiés de la semaine, A, 1
    deliverables:
      free: Top 3 appels d'offres de la semaine | Email | Titre, acheteur, budget, lien | Email (Hebdo) | S1, P1, P2
      rung_A: Flux quotidien des appels d'offres IT filtrés | CSV | Titre, acheteur, budget, technos, dates | Email (Quotidien) | S1, S2, P1, P2 | nothing | 1
      rung_B: above MAX_SCENARIO
      rung_C: above MAX_SCENARIO
      rung_D: above MAX_SCENARIO
    paid_version: Flux de données structuré quotidien spécifique au secteur IT du client, 1, A, Le client lit la ligne CSV et clique sur le lien BOAMP officiel
    price: Vecteur Plus, 3000€/an, third party,
    subscription_form: monthly
    upsell: none found
    payment_or_proxy_evidence: https://www.spigao.com/vos-besoins/veille-marche/
    competitors:
      - Spigao | paid product | Not observable | self-serve/sales | 2 | C |
      - Vecteur Plus | paid product | Not observable | sales | 1 | A |
    saturation:
      target_saturation: open
      level_1: High; A 2 M 2 S 2 U yes,; main offers Vecteur Plus, Spigao
      level_2: Medium: unmet need; A 1 M 2 S 1 U yes,; main offers Spigao
      level_3: Low; A 0 M 0 S 0 U yes,; main offers none
      competitive_level: Level 1, High
      why_empty: n/a
    gap_hypothesis: feature, Bruit réduit et focus IT natif évitant la complexité des plateformes généralistes
    differentiation:
      strength: Strong
      need: pass, Les utilisateurs se plaignent du temps de tri manuel
      durability: structural, Les géants visent le BTP généraliste et le volume
      reach: pass, PME IT (ESN, agences web) estimées à 20 000+ en France
    must_prove: À forte saturation, les PME IT rejettent les leaders du marché à cause du volume de faux positifs et de leurs contrats annuels rigides.
    sales_route: self-serve
    screen_results: 1 pass/Confirmed/high; 2 pass/Confirmed/high; 3 pass/Confirmed/high; 4 pass/Confirmed/high; 5 pass/Confirmed/high; 6 pass/Confirmed/high; 7 pass/Confirmed/medium; 8 pass/Confirmed/high
    demand_results: D1 pass/Confirmed/high; D2 pass/Confirmed/high; D3 pass/Confirmed/medium; D4 pass/Confirmed/high
    flags:
      - not observable: Pricing exact Vecteur Plus
    not_observable:
      - Pricing Spigao / Vecteur Plus
    validation_test: "Questions: Payez-vous aujourd'hui pour une plateforme de veille ? Combien de temps passez-vous chaque jour à trier les faux positifs ?"
    why_now: standing need

  - id: C2
    outcome: passed the screen, not demand-tested
    rank: 2
    path: A
    task: Veille des levées de fonds B2B
    description: Les commerciaux visant les startups SaaS doivent contacter les fondateurs immédiatement après une levée de fonds, ce qui implique de surveiller la presse spécialisée et les registres légaux quotidiennement. Les annonces se font au jour le jour, et arriver un mois après la parution signifie généralement que les nouveaux budgets sont déjà engagés. Les startups paient cher des outils comme Dealroom ou CFNews (saturation moyenne), mais un produit peut s'imposer en combinant l'annonce de la levée avec l'extraction directe des coordonnées des fondateurs et une estimation des postes de dépense. Le risque principal est la difficulté de différencier les "fausses" levées (dette, restructuration interne) des vraies injections de capital de croissance.
    industry: SaaS B2B
    segment: Startups / Scale-ups
    exact_output: Fichier hebdomadaire des entreprises B2B ayant levé des fonds, avec les coordonnées estimées des fondateurs
    owner_and_trigger: Business Developer B2B, quotidien/hebdo, déclenché par annonces de presse
    change_rate: Hebdomadaire; 7 jours
    cost_of_miss: Rater la fenêtre d'achat post-levée de fonds de 3-6 mois (estimate reasoned)
    recurring_value_route: 1
    delivery_form: event alerts
    decision_and_lever: Prioriser la prospection sortante; win clients; 10k€ ARR par client (estimate)
    slowest_step: Identifier les contacts décideurs post-annonce (estimate reasoned)
    data_sources:
      - S1 | Maddyness RSS | https://www.maddyness.com | web page | A | scrape | HTML | unverified | daily | 1
      - S2 | BODACC | https://www.bodacc.fr | open data | A | API | XML | Etalab 2.0 | daily | 1
    task_steps: Surveiller annonces | public | automate; Qualifier SaaS B2B | public | automate; Identifier décideurs | public | automate; Contacter | judgment | leave
    ladder:
      level_1_input_data: A; no; yes
      level_2_draft: C; no; capped: max scenario A
      level_3_near_final: C; no; capped: max scenario A
      max_depth: Level 1 under scenario A
      vs_target_depth: reached
    upgrade_path: Intégration CRM / Séquences emails automatiques (Scénario C)
    stack:
      coverage: partly covered
      pipeline:
        - P1 | News Scraper | RSS Parser | category only | covered | HTML | JSON
        - P2 | Entity/Contact matching | LLM Extraction | category only | partly | JSON | CSV
      curated_asset: Dealflow dataset (CSV)
      build_gap: Fiabiliser le lien entre un article de presse et l'entité légale précise (SIREN) pour dériver les bons contacts.
      licence_notes: none
    free_version: Liste de 5 levées de fonds SaaS de la semaine sans emails, A, 1
    deliverables:
      free: 5 levées de la semaine | Email | Nom, Montant, Investisseur | Email (Hebdo) | S1, P1
      rung_A: Fichier complet Levées SaaS + Décideurs | CSV | Nom, SIREN, Montant, URL LinkedIn CEO | Email (Hebdo) | S1, S2, P1, P2 | nothing | 1
      rung_B: above MAX_SCENARIO
      rung_C: above MAX_SCENARIO
      rung_D: above MAX_SCENARIO
    paid_version: Fichier enrichi automatique des startups levées + CEO, 1, A, Validation visuelle du nom de la startup
    price: CFNews / Dealroom, ~2000€/an, secondary, (reasoned estimate)
    subscription_form: monthly
    upsell: none found
    payment_or_proxy_evidence: CFNews subscriptions (reasoned knowledge)
    competitors:
      - CFNews | paid product | Not observable | sales | 1 | A | unverified
      - Dealroom | paid product | Not observable | sales | 1 | A | unverified
    saturation:
      target_saturation: open
      level_1: Medium: unmet need; A 1 M 2 S 1 U yes, (reasoned); main offers CFNews, Dealroom
      level_2: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      level_3: Low (empty); A 0 M 0 S 0 U yes, (reasoned); main offers none
      competitive_level: Level 1, Medium
      why_empty: n/a
    gap_hypothesis: feature, Extraction directe des dirigeants et focus B2B SaaS pur (reasoned)
    differentiation:
      strength: Moderate
      need: pass, Besoin constant d'avoir l'info actionable, pas juste la news (reasoned)
      durability: cosmetic, Ajoutable par les leaders mais pas leur coeur de métier actuel
      reach: pass, Secteur B2B très dynamique
    must_prove: Les startups SaaS B2B préfèrent payer un outil d'extraction focalisé sur leur niche plutôt que la presse financière généraliste.
    sales_route: self-serve
    screen_results: 1 pass/Confirmed/high; 2 pass/Confirmed/high; 3 pass/Confirmed/medium; 4 pass/Confirmed/medium; 5 pass/Confirmed/high; 6 pass/Confirmed/high; 7 pass/Confirmed/medium; 8 pass/Confirmed/high
    demand_results: not run
    flags:
      - Validation of press scraping terms
    not_observable:
      - Dealroom exact pricing
    validation_test: "Questions: Comment sourcez-vous les entreprises fraîchement financées ? Payez-vous un abonnement data ?"
    why_now: standing need

  - id: C3
    outcome: passed the screen, not demand-tested
    rank: 3
    path: A
    task: Détection des recrutements stratégiques (CISO)
    description: Les commerciaux en cybersécurité doivent identifier le moment exact où un compte cible recrute un nouveau RSSI/CISO, ce qui les oblige à scripter ou vérifier manuellement les pages carrière et plateformes d'emploi. Les offres d'emploi changent quotidiennement, et rater ce signal coûte cher car un nouveau décideur alloue généralement son budget et remplace les outils dans ses 90 premiers jours. Le marché compte des outils de signaux d'intention comme Pharow (marché moyennement saturé), mais un nouvel entrant peut se différencier en se concentrant exclusivement sur la cybersécurité et en extrayant la stack technique (outils déjà en place) mentionnée dans l'annonce. Le risque principal est que le scraping des sites d'emploi publics (comme Indeed ou Welcome to the Jungle) rencontre des blocages techniques réguliers.
    industry: Cybersécurité
    segment: Éditeurs logiciels / Intégrateurs
    exact_output: Alerte temps réel des entreprises recrutant un RSSI ou CISO, avec extraction des logiciels de sécurité mentionnés dans l'offre
    owner_and_trigger: Business Developer B2B Cyber, quotidien, publication d'offre d'emploi
    change_rate: Quotidien; 24h
    cost_of_miss: Le nouveau décideur (CISO) remplace souvent les outils existants dans ses 90 premiers jours ; rater cette fenêtre réduit les chances de vente de 80%. (reasoned)
    recurring_value_route: 1
    delivery_form: event alerts
    decision_and_lever: Déclencher une campagne de prospection ciblée; win clients; 20k€ ARR (estimate)
    slowest_step: Parcourir manuellement les descriptions de poste longues pour repérer la stack existante (reasoned)
    data_sources:
      - S1 | APEC API | https://www.apec.fr | open data | A | API | JSON | unverified | daily | 1
    task_steps: Requêter mots clés | public | automate; Analyser texte pour stack tech | public | automate; Alerter | public | automate; Contacter | judgment | leave
    ladder:
      level_1_input_data: A; no; yes
      level_2_draft: C; no; capped: max scenario A
      level_3_near_final: C; no; capped: max scenario A
      max_depth: Level 1 under scenario A
      vs_target_depth: reached
    upgrade_path: Intégration CRM / Automatisation de messages LinkedIn personnalisés
    stack:
      coverage: partly covered
      pipeline:
        - P1 | Job Fetcher | API Client | category only | covered | JSON | JSON
        - P2 | Cyber Stack Extractor | LLM Prompt | category only | partly | JSON | CSV
      curated_asset: Base de données d'intentions cyber (SQLite)
      build_gap: Fiabiliser l'extraction spécifique des outils cyber (EDR, SIEM) depuis le texte libre de l'offre.
      licence_notes: none
    free_version: Liste des 10 recrutements CISO de la semaine, A, 1
    deliverables:
      free: 10 recrutements de la semaine | Email | Nom entreprise, Lien emploi | Email (Hebdo) | S1, P1
      rung_A: Flux quotidien d'embauches CISO + stack | CSV/Email | Entreprise, Outils identifiés, Lien | Email (Quotidien) | S1, P1, P2 | nothing | 1
      rung_B: above MAX_SCENARIO
      rung_C: above MAX_SCENARIO
      rung_D: above MAX_SCENARIO
    paid_version: Alerte temps réel par email avec stack technologique décodée, 1, A, Lecture de l'email
    price: Pharow ~150€/mois, third party, (reasoned estimate)
    subscription_form: monthly
    upsell: none found
    payment_or_proxy_evidence: Existence d'outils B2B d'intention (reasoned)
    competitors:
      - Pharow | paid product | 150€/mo | self-serve | 1 | A | unverified
    saturation:
      target_saturation: open
      level_1: Medium: unmet need; A 2 M 2 S 1 U yes, (reasoned); main offers Pharow
      level_2: Low; A 1 M 1 S 0 U yes, (reasoned); main offers none
      level_3: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      competitive_level: Level 1, Medium
      why_empty: n/a
    gap_hypothesis: feature, Focus vertical cybersécurité et extraction profonde de la stack technique.
    differentiation:
      strength: Moderate
      need: pass, Les commerciaux adaptent leur pitch à l'outil déjà utilisé.
      durability: cosmetic, Facilement copiable par un acteur généraliste s'il ajoute un prompt spécifique.
      reach: pass, Marché de la cybersécurité en forte croissance.
    must_prove: Les commerciaux cyber ont besoin d'un outil dédié à l'extraction de contexte technique, au-delà du simple signal de recrutement de Pharow.
    sales_route: self-serve
    screen_results: 1 pass/Confirmed/high; 2 pass/Confirmed/high; 3 pass/Confirmed/medium; 4 pass/Confirmed/medium; 5 pass/Confirmed/high; 6 pass/Confirmed/high; 7 pass/Confirmed/medium; 8 pass/Confirmed/high
    demand_results: not run
    flags:
      - Scraping TOS for job boards can be strict
    not_observable:
      - Actual usage rate of job filters in Pharow
    validation_test: "Questions: Utilisez-vous les offres d'emploi pour prospecter ? Extrayez-vous les outils nommés manuellement ?"
    why_now: standing need

  - id: C4
    outcome: passed the demand test
    rank: 4
    path: B
    task: Suivi des transferts de siège social (déménagements)
    description: Les commerciaux en aménagement de bureaux ou infrastructure IT doivent détecter les entreprises qui prévoient de déménager, ce qu'ils font actuellement en surveillant manuellement la presse locale ou en lisant les publications légales brutes. Les annonces légales (BODACC) tombent tous les jours, et un retard dans la détection signifie que le client a déjà signé avec son prestataire historique ou un concurrent proactif. Bien qu'il n'y ait pas d'outil payant ne vendant que ce signal spécifique (le marché est vide car ce déclencheur est généralement noyé dans de coûteux terminaux de données B2B globaux), les entreprises paient des bases de données et des agences de prospection pour trouver ces leads, prouvant la valeur de l'information. Le risque principal est que la publication légale du transfert intervienne parfois trop tard dans le cycle de décision du client pour permettre une vente.
    industry: Équipement de bureau / Infrastructure IT
    segment: PME B2B
    exact_output: Liste hebdomadaire des PME transférant leur siège social, qualifiées par taille et région
    owner_and_trigger: Business Developer IT/Aménagement, hebdomadaire, publication BODACC
    change_rate: Quotidien; 24h
    cost_of_miss: Les contrats d'infrastructure IT et mobilier sont signés 3 à 6 mois avant le déménagement ; rater la publication légale, c'est perdre le client. (reasoned)
    recurring_value_route: 1
    delivery_form: event alerts
    decision_and_lever: Appeler le prospect au bon moment; win clients; 10k€+ par projet (estimate)
    slowest_step: Surveiller le BODACC et trier les petits déménagements sans intérêt (freelances) des vraies PME. (reasoned)
    data_sources:
      - S1 | Pappers Open Data | https://www.pappers.fr | open data | A | API | JSON | permissive | daily | 1
      - S2 | BODACC | https://www.bodacc.fr | open data | A | API | XML | Etalab 2.0 | daily | 1
    task_steps: Surveiller BODACC/Pappers | public | automate; Filtrer "transfert de siège" | public | automate; Filtrer effectif > 10 | public | automate; Lancer prospection | judgment | leave
    ladder:
      level_1_input_data: A; no; yes
      level_2_draft: C; no; capped: max scenario A
      level_3_near_final: C; no; capped: max scenario A
      max_depth: Level 1 under scenario A
      vs_target_depth: reached
    upgrade_path: Scénario C pour importer directement les prospects qualifiés dans HubSpot.
    stack:
      coverage: covered
      pipeline:
        - P1 | Registry Tracker | API Client | category only | covered | JSON | CSV
      curated_asset: Base de données historique des déménagements (CSV)
      build_gap: Créer le filtre d'exclusion pour ignorer les micro-entreprises (effectif < 10) qui polluent le flux des transferts.
      licence_notes: none
    free_version: Synthèse des 5 plus gros déménagements de la région cible par mois, A, 1
    deliverables:
      free: Top 5 déménagements du mois | Email | Nom, Ancienne ville, Nouvelle ville | Email (Mensuel) | S1, P1
      rung_A: Flux hebdomadaire complet des transferts qualifiés | CSV | SIREN, Nom, Nouvelle Adresse, Effectif | Email (Hebdo) | S1, P2 | nothing | 1
      rung_B: above MAX_SCENARIO
      rung_C: above MAX_SCENARIO
      rung_D: above MAX_SCENARIO
    paid_version: Fichier CSV hebdomadaire exact filtré par code postal et taille d'entreprise, 1, A, Validation par consultation de la fiche Pappers
    price: hypothèse 50€/mois pour flux direct, hypothesis
    subscription_form: monthly
    upsell: none found
    payment_or_proxy_evidence: Proxy 1: Bases de données B2B globales vendues très cher (Societe.com) Proxy 2: Agences de prospection externalisées facturant la détection
    competitors:
      - Societe.com | paid product | Not observable | self-serve/sales | 1 | A | unverified
    saturation:
      target_saturation: open
      level_1: Low (empty); A 0 M 0 S 0 U yes, (reasoned); main offers none specific
      level_2: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      level_3: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      competitive_level: Level 1, Low (empty)
      why_empty: Trop spécifique pour une fonctionnalité SaaS B2B majeure, souvent ignoré au profit des levées de fonds.
    gap_hypothesis: feature, Outil monotâche avec coût minime ne nécessitant pas d'abonnement plateforme data.
    differentiation:
      strength: Moderate
      need: pass, Le signal d'achat est très clair pour l'aménagement de bureau.
      durability: structural, Micro-SaaS de niche trop petit pour les leaders.
      reach: pass, Revendeurs IT, agences d'aménagement, courtiers immobiliers.
    must_prove: La publication au BODACC n'arrive pas chronologiquement "trop tard" pour remporter un contrat d'aménagement ou d'IT.
    sales_route: self-serve
    screen_results: 1 pass/Confirmed/high; 2 pass/Confirmed/high; 3 pass/Confirmed/high; 4 pass/Confirmed/high; 5 pass/Confirmed/high; 6 pass/Confirmed/high; 7 pass/Confirmed/medium; 8 pass/Confirmed/high
    demand_results: D1 pass/Confirmed/medium; D2 pass/Confirmed/medium; D3 pass/Confirmed/medium; D4 pass/Confirmed/high
    flags:
      - Timing risk between actual move decision and official legal BODACC publication
    not_observable:
      - Pricing of specific signal modules in enterprise platforms
    validation_test: "Offrir une liste de 20 déménagements récents à 10 commerciaux. Succès: 3 souscrivent à 50€/mois. Échec: L'info est jugée périmée."
    why_now: standing need

  - id: C5
    outcome: passed the screen, not demand-tested
    rank: 5
    path: B
    task: Suivi des attributions de subventions environnementales
    description: Les consultants RSE et vendeurs de technologies vertes doivent identifier les entreprises qui reçoivent des aides publiques (ADEME), ce qui demande une compilation manuelle complexe des données ouvertes de l'État. Ces données sont mises à jour mensuellement ou trimestriellement, et ignorer l'attribution d'une subvention c'est rater une entreprise ayant l'obligation légale et le budget pour engager des travaux écologiques à court terme. Bien que le marché de l'alerte sur l'obtention de subventions soit vide (car les outils existants aident à demander des aides, pas à cibler ceux qui les ont obtenues), l'intérêt massif pour les consultants en aides d'État prouve le potentiel budgétaire. Le risque principal est la fréquence de rafraîchissement des bases Open Data de l'État, parfois trop lente pour une prospection réactive.
    industry: Conseil RSE / Greentech
    segment: B2B Services
    exact_output: Alerte des PME ayant obtenu une subvention environnementale (ADEME/Région), avec le montant et l'objectif du projet
    owner_and_trigger: Consultant RSE / Bizdev Greentech, mensuel, publication ADEME
    change_rate: Mensuel; 30 jours
    cost_of_miss: Rater un lead qualifié disposant d'un budget voté et fléché pour l'écologie. (reasoned)
    recurring_value_route: 1
    delivery_form: monthly
    decision_and_lever: Appeler pour proposer l'équipement visé par la subvention; win clients; 15k€+ (estimate)
    slowest_step: Fouiller les exports CSV obscurs et mal formatés de data.gouv (reasoned)
    data_sources:
      - S1 | Aides ADEME Open Data | https://www.data.gouv.fr/ | open data | A | API/CSV | CSV | Etalab 2.0 | monthly | 1
    task_steps: Télécharger CSV ADEME | public | automate; Filtrer par région/secteur cible | public | automate; Identifier le besoin financé | public | automate; Lancer prospection | judgment | leave
    ladder:
      level_1_input_data: A; no; yes
      level_2_draft: C; no; capped: max scenario A
      level_3_near_final: C; no; capped: max scenario A
      max_depth: Level 1 under scenario A
      vs_target_depth: reached
    upgrade_path: Scénario C pour intégration CRM
    stack:
      coverage: covered
      pipeline:
        - P1 | Open Data Fetcher | API Client / Pandas | category only | covered | CSV | JSON
        - P2 | Sector Filter | Custom logic | category only | covered | JSON | CSV
      curated_asset: Registre des attributaires de subventions vertes (CSV)
      build_gap: Gérer les formats inconsistants des exports CSV gouvernementaux.
      licence_notes: none
    free_version: Liste de 3 subventions notables du mois dans la région, A, 1
    deliverables:
      free: 3 subventions notables du mois | Email | Nom, Région, Montant | Email (Mensuel) | S1, P1
      rung_A: Fichier mensuel exhaustif filtré | CSV | SIREN, Nom, Dispositif, Montant | Email (Mensuel) | S1, P1, P2 | nothing | 1
      rung_B: above MAX_SCENARIO
      rung_C: above MAX_SCENARIO
      rung_D: above MAX_SCENARIO
    paid_version: Alerte par email mensuel structuré pour un ciblage commercial, 1, A, Validation via le nom de l'entreprise
    price: hypothèse 39€/mois, hypothesis
    subscription_form: monthly
    upsell: none found
    payment_or_proxy_evidence: Proxy 1: Plateformes de recherche de subventions pour soi-même (Aides-entreprises.fr payant). Proxy 2: Marché très actif du conseil en financement public. (reasoned)
    competitors:
      - Aides-territoires | free official resource | gratuit | self-serve | 1 | A | unverified
    saturation:
      target_saturation: open
      level_1: Low (empty); A 0 M 0 S 0 U yes, (reasoned); main offers none
      level_2: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      level_3: Low; A 0 M 0 S 0 U yes, (reasoned); main offers none
      competitive_level: Level 1, Low (empty)
      why_empty: Outils existants faits pour les demandeurs de subventions, pas pour les vendeurs de services.
    gap_hypothesis: segment, Ciblage inversé (vendeurs cherchant des bénéficiaires).
    differentiation:
      strength: Moderate
      need: pass, Les greentech peinent à identifier les PME prêtes à investir.
      durability: structural, Outils étatiques n'ont pas vocation à devenir des outils de prospection.
      reach: pass, Écosystème RSE florissant.
    must_prove: Les délais de publication de data.gouv.fr (parfois 3 mois de retard) ne rendent pas le signal d'achat obsolète.
    sales_route: self-serve
    screen_results: 1 pass/Confirmed/high; 2 pass/Confirmed/medium; 3 pass/Confirmed/high; 4 pass/Confirmed/medium; 5 pass/Confirmed/high; 6 pass/Confirmed/high; 7 pass/Confirmed/medium; 8 pass/Confirmed/high
    demand_results: not run
    flags:
      - Delay in government open data publications
    not_observable:
      - Exact refresh rate compliance of ADEME datasets
    validation_test: "Proposer l'alerte sur LinkedIn. Succès: 20 inscriptions au MVP. Échec: Les consultants répondent qu'ils ont déjà l'information par leur réseau."
    why_now: standing need

off_target_candidates:
  - none

killed_candidates:
  - none

near_misses_from_inventory:
  - identifier créations d'entreprises | dropped at 1c | no payment
  - mise à jour CRM | dropped at 1b | not input
  - rédaction emails prospection | dropped at 1b | not input
  - calcul devis | dropped at 1b | not input
  - relance factures | dropped at 1b | not input
  - suivi prix concurrents | dropped at 1b | no evidence
=== HANDOFF END ===
```

**Tuning constants (change only if you mean to):**
MAX_ITERATIONS = 3   (maximum refinement rounds after the first full round)
MAX_VARIANTS_PER_ROUND = 4   (maximum task versions generated per round, V0 included in round 0)
SEARCH_BUDGET = 60   (maximum number of web searches for the whole run; see "Search budget")

All other parameters (ROLE, COUNTRY, INDUSTRY, COMPANY_SIZE, LANGUAGE, MAX_SCENARIO, TARGET_DEPTH, HUMAN_IN_LOOP, LICENCE_POLICY, TARGET_SATURATION, ALREADY_VISITED) are resolved in Step 0.0 from the handoff.

## Founder profile and delivery constraints (swappable)

- Solo founder, applied AI engineer, based in France (assume a French sole-proprietor entity). French and English.
- Skills: Claude Code, RAG and structured RAG, LangGraph, Neo4j, information extraction, NLP, competitive intelligence, LLM APIs (OpenAI, Claude, Qwen, DeepSeek), Python, JavaScript, FastAPI, React.js, Nuxt.js, Firebase, GA4, Cloud Run, AWS, GCP, Docker, APIs, MCP, TTS, ASR, voice agents.
- Time, budget and marginal cost of running software are never kill criteria. Language fit is a note, not a kill criterion.
- Sales must suit a solo founder: self-serve, marketplace discovery, low-touch onboarding, or a few local relationships. No long enterprise sales cycles (scenario D rungs are exempt).
- The profile judges delivery feasibility only. It never creates, favours or ranks a USP. A variant is never kept alive because it suits the founder's skills.

## Product model

The founder is a data and information curator, not an expert in the role. One input effort feeds two versions:

- **Free version:** a recurring or event-driven issue (digest, alert, report), at the cadence the change rate allows, that contains a real result the reader can use, not a summary. Scenario A only, Level 1 or 2.
- **Paid version:** the same output produced automatically for the reader's own case (checker, monitoring, dataset, structured search, form-based assistant, API or MCP server), at the depth supported by the evidence, within `MAX_SCENARIO`.
- **Product blueprint:** each task version states the data sources to curate (and their input formats), the stack that processes them (and the format between stages), and what the customer receives (and in which format). See "Product blueprint".
- **Upsell direction (optional):** one line on a fixed-price add-on that moves the client one rung up the ladder. Not designed in this prompt.

A recurring reason to pay matters more than a publishing rhythm: the inputs change from time to time and a reader without the time or skill to keep up loses something by missing a change. The customer is the domain expert and can judge the output. The product gives no individualised regulated advice.

**Data-access scenarios:** A = public data only; B = manual upload by the reader; C = integration (API, plugin, connector, MCP); D = self-hosted by the reader; E = no digital access. Order of difficulty A → E; `MAX_SCENARIO` is a ceiling and a lower scenario is always allowed. **Human in the loop (modifier):** a fixed, capped human validation step, allowed per `HUMAN_IN_LOOP`, never individual expert judgment.

**Delivery ladder:** Level 1 = input data (collected, verified, structured inputs); Level 2 = draft output (reader reviews and edits); Level 3 = near-final output (reader only validates). The free version is always scenario A. If a level needs a scenario above `MAX_SCENARIO`, cap the maximum depth and flag it; never silently exceed the ceiling.

**Saturation by level:** judged per level and per segment, from Availability (0 to 2), Maturity (0 to 2), Similarity (0 to 2) and Unmet need (yes/no, dated independent practitioner evidence in the 18 months before `RUN_DATE`). Low = Availability 0 or Maturity 0 (Low (empty) when no offer exists); High = Availability 2 and Maturity 2 and no unmet need and (Similarity 2 or a free or bundled mature offer already used); Medium = every other case, with its reason (unmet need, dissimilar offers, friction). Unscorable measures become ranges and go to the manual validation list.

## Product blueprint

Every task version (V0 and each variant) and the final USP show three things, so that the founder sees what to build:

1. **Data sources to curate** (`data_sources`): one line per source with an ID (S1, S2, ...): name, link, kind, scenario (A public, B reader upload, C integration, D self-hosted), access mode (API, bulk file, scraping, manual upload, connector), **input format** (CSV, JSON, XML, XLSX, text PDF, scanned PDF, HTML, other), reuse terms, refresh rate, the levels that use it. Reader sources name the export or fields needed.
2. **Stack** (`stack.pipeline`): ordered stages (P1, P2, ...): stage, tool category, project (licence, last release date) or "category only", coverage (covered | partly | to build), input (source IDs or previous stage, with format), output (with format). Plus the **curated asset** the founder keeps and grows (with storage format) or "none".
3. **Customer deliverable** (`deliverables`): for the free version and for each rung from A up to `MAX_SCENARIO`: what the customer receives, the **file or data format** (email digest, PDF, CSV, XLSX, JSON API, MCP server, web page, calendar file, alert), main fields, channel and cadence, source IDs and stages used, and what the customer provides (nothing in A, an upload in B, a connection in C, an installation in D). A rung that is not reachable states the blocker; a rung above `MAX_SCENARIO` is written "above MAX_SCENARIO".

Rules: a format or reuse term is **Confirmed** only if seen in a sample file, a documentation page or a publisher page opened in this run; otherwise write "(Unverified)". Formats must chain: each stage's input format matches its source or the previous output, and any conversion (scanned PDF to text, XML to CSV) is a stage of its own. When a variant changes the task, level, segment or delivery form, it restates the blueprint lines that change (a "blueprint delta") rather than copying the whole blueprint.

## Rules

### Portability

- **Web search is required.** If you cannot search the web, say so in one line and stop. Never produce the report from memory.
- **Long answers.** If your answer is about to hit its limit, stop at the end of a section, write `CONTINUE` on its own line, and resume exactly there. Never shorten or skip later sections.
- **Context economy.** Keep working notes to one line per finding. Never paste search results. Only the report is written in full.
- **Optional tools.** If you can fetch pages, fetch a provider's own price page rather than reading a snippet. If you can run sub-agents, use them where this prompt says so (Step 4B); otherwise work in sequence and name the missing tool in the run summary.
- **Order.** Follow the steps in order. Use `RUN_DATE` for every time window.

### Search budget

`SEARCH_BUDGET` is shared by the whole run. Step 0.0 uses no search. Default allocation for 60 searches: Step 0 up to 8 (including the demand gate); Step 1 up to 8; Step 1f (blueprint) up to 5; Step 2 up to 6; Step 4A up to 6; Step 4B up to 12; Step 5 up to 4; refinement rounds a shared pool of up to 11. If the budget is smaller or larger, scale the allocation in proportion. Count every search. **Priority when the budget runs short:** protect Step 0 (demand gate), Step 4B and Step 5; cut refinement rounds first, then Step 2, then Step 1 depth. Report the searches used per step in the run summary. Never exceed the budget; apply the budget fallback instead.

### Evidence statuses

Every claim that matters carries a dated source link (prefer the last 18 months; "undated" if the page shows no date) and one status with a confidence (high, medium, low):

- **Confirmed:** supporting evidence found.
- **Disproved:** evidence against.
- **Unverified:** you searched properly and found nothing.
- **Not observable:** the evidence exists but is out of reach (login, private pricing, sales calls, private communities). Never a fatal finding; it goes to the manual validation list with the query tried and what blocked it.

Anything stated without a search is "unverified: reasoned from background knowledge" and can never support a score of 2 or a "Survives" verdict with high confidence.

### Evidence rules

- **Vendor claims** (volumes, hours saved, satisfaction scores, testimonials published by sellers to the segment) are unverified marketing. They never prove need, size or willingness to pay.
- **Competitors are spend, not demand.** An existing paid product proves that people pay. Demand for a new product comes from practitioners' own signals: dated complaints, repeated forum questions, workarounds, paid templates or training, outsourced services priced per task, job postings listing the task.
- **Interest signals** (books, ads, webinars) are "topic interest" or "seller belief", never buyer demand.
- **Open-source tools** count as stack coverage only if found by search with link, licence (inside `LICENCE_POLICY`) and a release or commit in the 12 months before `RUN_DATE`. Never name a project from memory.
- **Why now** needs a dated source and a documented change; "AI is now capable" never counts. A standing need is allowed.
- **No invented content:** never invent a source, price, number, quote, review count, repository, licence or sample item. Quote at most a few words; paraphrase the rest. Read prices from the provider's own page or label the price source.
- **Hint rule:** if `HINT` is set, search that direction first. It is never evidence.
- **Avoid:** generic news summaries, simple competitor monitoring, generic regulatory newsletters, anything a professional gets with one prompt to a general AI assistant, individualised regulated advice. News mining (structured extraction from text into a fixed schema) is allowed.

### Fixed versus mutable

| Fixed (never change) | Mutable (may change, with a stated reason) |
|---|---|
| ROLE, COUNTRY, INDUSTRY, LANGUAGE | The task, its exact recurring output, its decision, its slowest step |
| MAX_SCENARIO, HUMAN_IN_LOOP, LICENCE_POLICY (as resolved in Step 0.0) | The ladder level the product competes on (up to the ceiling) |
| The founder constraints | The delivery form, the segment inside the industry, the free and paid split, the pricing form |

**Drift test, applied to every variant:** the variant must still be a task of the fixed ROLE, bought or used by that role in the fixed INDUSTRY. A variant that needs a different role as the user, a different industry as the buyer, or a different country's data as the main input is **drift**: reject it, do not score it.

## Step 0.0: Handoff validation and parameter resolution (no search)

Do this first, before any search and before anything else in the answer. It uses no search budget.

**A. Validate the handoff.** Stop with one line stating the exact problem, and do nothing else, if any of these holds:
1. `FIND_HANDOFF` is empty, still contains `{{`, or lacks the `=== HANDOFF START ===` or `=== HANDOFF END ===` marker.
2. More than one handoff block is pasted.
3. `handoff_version` is missing or is not `find-v1.7`, `find-v1.8` or `find-v1.9` (an older or unknown version is not read; ask the user to re-run Prompt 1).
4. `CANDIDATE_ID` is empty, or is not found as a full entry in `candidates` (if it is found only in `killed_candidates` or `off_target_candidates`, say which one, and say that only a new Prompt 1 run can turn it into a full candidate).
5. The `parameters` block is missing.

**B. Resolve every parameter from a fixed source.** Do not guess and do not ask the user to retype values.

| Parameter | Source (in order) |
|---|---|
| ROLE, COUNTRY, LANGUAGE | handoff `parameters` |
| INDUSTRY, COMPANY_SIZE | the chosen candidate's `industry` and `segment`. If the entry shows "open" or is empty, take the industry from the candidate's `description` and `task`, state what you inferred, and flag "industry inferred" |
| MAX_SCENARIO, TARGET_DEPTH, HUMAN_IN_LOOP, LICENCE_POLICY | handoff `parameters` |
| TARGET_SATURATION | handoff `parameters`; if absent (find-v1.7), the candidate's `saturation.target_saturation`; if also absent, "open", flagged |
| ALREADY_VISITED | handoff `already_visited_line` if present; otherwise "none" |

**C. Apply overrides.** `OVERRIDES` may change only these values: `MAX_SCENARIO`, `TARGET_DEPTH`, `HUMAN_IN_LOOP`, `LICENCE_POLICY`, `TARGET_SATURATION`, and `COMPANY_SIZE` (narrowing or re-cutting the segment inside the industry). Any attempt to override `ROLE`, `COUNTRY`, `INDUSTRY` or `LANGUAGE`, or any unknown name, is **refused**: say so in the table and keep the handoff value (these need a new Prompt 1 run). Every applied override is marked "OVERRIDE" in the table. If an override changes `MAX_SCENARIO`, `TARGET_DEPTH` or `HUMAN_IN_LOOP`, the ladder in the candidate entry may no longer hold; Step 0 recomputes it.

**C2. Blueprint source.** If the handoff is find-v1.9, take the candidate's `data_sources`, `stack` (`pipeline`, `curated_asset`) and `deliverables` as the starting blueprint of V0 (Step 1f re-verifies it). If a field is missing, "unknown" or "not run", or the handoff is find-v1.7 or find-v1.8, the blueprint of V0 is built in Step 1f from the candidate's `key_inputs`, `task_steps` and `stack` lines (when present) and flagged "blueprint not in handoff".

**D. Print the "Parameters applied" table as the first thing in the answer**, then continue. One row per parameter: name, value, source (handoff | candidate entry | override | default | inferred), flag if any. Add one line listing the fields of the candidate entry that are "not run", "unknown" or missing, and one line saying where the V0 blueprint comes from (handoff | built in Step 1f).

## Step 0: Intake, consistency and demand gate

Up to 8 searches.

1. **Restate V0** (the chosen candidate) neutrally in six fields: exact recurring output, who does it and when, slowest step, decision and money lever, paid depth and scenario, price anchor or hypothesis. Do not state a judgment about V0 yet.
2. **Consistency check:** compare the candidate entry with the parameters resolved in Step 0.0. List every mismatch (for example a ladder that no longer matches an overridden `MAX_SCENARIO`, a depth above the ceiling, a segment outside the chosen industry). Where an override changed the ladder, recompute V0's maximum depth under the new ceiling and say so. Where the entry and the parameters disagree on a fixed field, apply the resolved parameter and say so; do not guess which side is right.
3. **Re-verify the handoff's key claims** with fresh searches: the price anchor, the top two competitors, the `must_prove` claim and the strongest need evidence. Prompt 1 results are leads, not facts. A claim you cannot reconfirm is downgraded to Unverified and listed in "claims downgraded from Prompt 1".
4. **Demand gate.** If the candidate's `demand_results` shows D1 to D4 as "not run", or any of them as Unverified, run them now for the underlying need (the problem the role has, not the specific V0 output), for the fixed segment and industry:
   - **D1 Real and sized:** independent evidence that the task exists in this segment, how often, and roughly how many practitioners do it (job postings, official statistics, association membership). Existence without size is "existence Confirmed, size Unverified".
   - **D2 Existing spend:** practitioners already pay for the same output or its inputs (tools, services, consultants, paid training or templates). Note the depth at which the spend sits. Adjacent spend counts as substitute evidence.
   - **D3 Practitioner demand signal:** independent reviews, testimonials, forum threads or training sessions with dates (vendor testimonials do not count). Confirmed high = 10+ with 3+ in the last 90 days; medium = 3+ from different people in the last 6 months; low = at least 1 in the last 6 months.
   - **D4 Stable or growing:** job postings, dated training sessions, new obligations, continued publication of the inputs. Decline evidence only counts if you found it.
   Record D1 to D4 as Confirmed, Unverified, Disproved or Not observable with confidence. **Consequence:** these results feed the Need and Willingness-to-pay scores of every variant. If D1 is Disproved for the underlying need, no variant of the same need can reach "validated"; only a variant that targets a different, evidenced need inside the fixed role and industry can. If every need fails D1, go straight to the verdict "No sufficient USP found".

## Step 1: Market need and competitive landscape

Up to 8 searches. One competitor register is kept for the whole run; one row per alternative: name, URL, kind (paid product, free official or association resource, general AI assistant, outsourced service, paid training, template, community, newsletter, consultant, native feature of a dominant tool, open-source tool producing the same output), price and price source (provider page | third party | secondary | Not observable), channel, what it produces, depth delivered (Level 1 / 2 / 3), scenario used, visible traction (subscribers, members, reviews, with dates), date checked. Never repeat a search already in the register.

**1a. Market need.** From practitioner sources only (forums, communities, job postings, training content, independent reviews), evidence what the ROLE does today around this area, how long it takes, what a missed or late input costs, how often inputs change. Record dated complaints and workarounds. Look at the whole workflow around V0, upstream and downstream, not only at V0 itself.

**1b. Competition (C1).** Start from the comparables in the handoff. Add direct and indirect alternatives serving this area for the fixed industry in the fixed country: newsletters, templates, benchmarks, training, consultants, communities, vendor content, official guides, native features of the dominant tools, open-source tools. Include every free option. Up to 3 new searches for this part.

**1c. Utility test (C2).** Why would a time-pressed practitioner use a product here rather than (a) searching alone, (b) asking a general AI assistant, (c) using free resources, (d) paying a consultant, a template or a training that does it now? Answer each with evidence. For (b) see the **general-AI baseline** in Step 3: it is run, not reasoned, whenever the model can search.

**1d. Saturation profile.** Classify Level 1, 2 and 3 for the area (and for V0 specifically) as defined above. Note the main offers, the reason for any Medium, and the level where the segment is least served.

**1e. Unserved needs.** From 1a to 1d, list at most 5 **unserved needs**: a friction, a segment, an input, a level, a price point or a channel where practitioners say the existing offers fall short. Each needs a dated practitioner clue; an unserved need inferred only from a missing feature on a product page is marked "inferred from absence" (weak). **These unserved needs, not V0, are the starting point of Step 2.**

**1f. Blueprint verification of V0.** Up to 5 searches or fetches (at most 3 if the handoff blueprint was already complete; if it had to be built, use the full 5 and mark what could not be verified Unverified). For each key source of V0: confirm the link still works, the input format (open a sample file or the documentation), the reuse terms (licence or terms of use: is commercial reuse and redistribution of derived data allowed?) and the refresh rate; for each pipeline stage with a named project: confirm licence (inside `LICENCE_POLICY`) and a release or commit in the 12 months before `RUN_DATE`; for each deliverable: check that the format is producible from the pipeline output. Mark each item Confirmed / Unverified / Disproved. A key source with Disproved reuse terms, or a format chain that cannot work, is a finding for Step 3 (F) and Step 4B (category 6), and a source for repair variants in Step 2. Print the verified blueprint of V0 as three compact tables (sources, pipeline, deliverables by rung).

## Step 2: Variant generation (V0 is one variant among others)

Up to 6 searches. Start from the unserved needs of 1e. Apply the hints below as lenses. A hint is a lens, not a requirement: use the lenses that produce a concrete, evidenced idea, and write "no idea" for the others rather than forcing one. **The goal is not always full automation: look for the best balance between machine and human.**

- **H1 Under-served segment:** a trade, size band, region or language inside the fixed industry that existing offers ignore or price out.
- **H2 Task-level optimisation:** (1) deduce the micro-goal of the task and the next steps the user takes right after it; (2) find the micro-decision or friction point that current offers still leave to the user with high cognitive load; (3) pick the stronger path: **Deepen** (machine does the heavy lifting, human keeps the high-value judgment) or **Handoff** (the output becomes a richer, pre-formatted payload that primes the user's next step).
- **H3 Multi-task consolidation:** (1) map the sequential chain upstream and downstream of the task; (2) find adjacent steps done one after another that one pass could do together; (3) pick **Omni-step** (2 or 3 adjacent tasks in one reviewed action) or **Bridge elimination** (remove the copy-paste or reformatting step between two tasks).
- **H4 Data enrichment:** join items with extra data that changes the decision.
- **H5 Richer data model:** join several datasets or sources into a model no incumbent keeps (including an accumulating historical asset).
- **H6 Agent-ready structure:** consistent structured fields so humans and AI agents (including through an MCP server) can use the output directly.
- **H7 Risk reduction and accessibility:** reduce a visible risk of error or exclusion, or make the output usable by people who cannot use the incumbents.
- **H8 Why now:** more needed now (a rule, deadline, data release, vendor change); cheaper to build now (a new open dataset or feed that removes a documented blocker); easier to reach the audience now; existing alternatives weaker now (discontinued, price rise, stale). State the window: lasting or short, and what happens to the idea when it closes.
- **H9 Lateral redesign (SCAMPER):** select the single most impactful lens (Substitute, Combine, Adapt, Modify, Put to another use, Eliminate, Reverse or rearrange) and describe the paradigm shift, the co-working balance (what the machine does, what judgment the human keeps), one realistic unhappy path with its low-effort human safety net, and a hypothesised, labelled ROI.

**Variant rules.**
- Generate V1 up to V`MAX_VARIANTS_PER_ROUND`, plus V0 as the baseline variant. V0 gets no advantage: it is scored and attacked like any other.
- **Diversity rule:** the variants must differ from each other on at least three of these dimensions across the set: target unserved need, ladder level, segment, delivery form, hint used, free/paid split. Near-duplicates (same need, same level, same segment, only the wording differs) are merged into one.
- At least one variant must come from H2, H3, H4, H5 or H9, not only from H1 or H6.
- Reject drift variants (see "Fixed versus mutable") and note them.
- A variant that targets a level or scenario above the resolved ceiling is not allowed; cap its depth instead.

For each variant write one card:

- **ID and parent** (V0 or the variant it refines), **hint(s) used**, **what changed versus the parent** (task, output, level, delivery form or segment)
- **Task and exact recurring output** (specific, never "market intelligence")
- **Segment** (inside the fixed industry) and **the user and the payer** (same ROLE or a payer reached by the founder's sales routes)
- **Unserved need it targets** (from 1e, with its clue)
- **Free version** (scenario A, level) and **paid version** (level, scenario, how the user verifies the output in under 5 minutes)
- **Blueprint (or blueprint delta versus the parent):** data sources to curate with input format and access mode (S IDs), pipeline stages with input and output format (P IDs), curated asset, and the customer deliverable for the free version and for each rung up to `MAX_SCENARIO` (format, main fields, channel, what the customer provides)
- **Ladder:** lowest scenario for each level, human-in-the-loop yes/no, maximum depth under `MAX_SCENARIO`
- **Pricing:** anchor (path A: price, source) or hypothesis (path B, labelled) and the subscription form that fits the change rate
- **Gap hypothesis:** where it beats the alternatives, kind (segment | feature | input | level | scenario | price | channel | format | asset)
- **USP sentence:** "For [role] in [industry], [product] gives [specific result] unlike [named alternatives] which [specific shortfall], because [mechanism]". No adjective may carry the claim (not "better", "smarter", "faster" without a measured difference).
- **Upsell direction** (one line, optional)

## Step 3: Scoring

Score every surviving variant, V0 included, on the scorecard. Each criterion is 0, 1 or 2 with its evidence status and link.

**Evidence caps (mandatory):**
- A score of **2** requires linked, dated, **Confirmed** evidence (date within 18 months, or "standing" for structural facts) from a source that is not a vendor.
- A criterion supported only by **Unverified**, reasoned or vendor evidence is **capped at 1**.
- A criterion that is **Not observable** is scored as a range (for example 0–2), and the lower bound is used for ranking; the item goes to the manual validation list.
- Do not raise a score between rounds without new evidence.

| Criterion | 0 | 1 | 2 |
|---|---|---|---|
| **N. Need** | no practitioner evidence | 1 dated practitioner clue, or only proxy signals | 3+ independent dated clues (complaint, workaround, repeated question, job posting) |
| **P. Willingness to pay** | no spend or proxy found | adjacent spend, or a paid offer at another level or segment | a paid offer, service or training for this output or its inputs, with a visible price |
| **G. Gap durability** | cosmetic: a competitor could close it in weeks, or only a lower price | structural in part (channel, segment size, pricing model), not accumulating | structural or an accumulating asset (history, dataset, verified local rules) that incumbents do not keep |
| **U. Utility against general AI and free options** | the general-AI baseline or a free resource gives an acceptable result | better on one aspect (freshness, verification, structure) | clear gain on at least two aspects that matter to the user, shown by the baseline run |
| **R. Reach** | buyers cannot be reached by the founder's routes | reachable with friction, size unclear | reachable self-serve or via a marketplace, segment size estimated and large enough (estimate labelled) |
| **F. Feasibility** | needs a scenario above `MAX_SCENARIO`, or key public inputs unavailable, or a key source's reuse terms forbid the use, or the format chain from sources to deliverable does not work | feasible with a capped depth or a human step, or with Unverified source formats or terms | full target depth within the ceiling, with the stack mapped (tools found, licences counted) and key source formats, reuse terms and the deliverable format Confirmed |
| **L. Free-to-paid link** | the free issue cannot hold a real result | free is a teaser rather than a result | free issue holds a real result and the paid feature is the same output for the reader's own case |
| **S. Saturation fit** | the level it competes on is High and the gap is not a new mechanism | Medium, or High with a new mechanism | Low or Low (empty) with a reason for emptiness (or matches `TARGET_SATURATION`) |

**General-AI baseline (feeds U).** For each variant taken past the quick screen (4A), write one fixed prompt a time-pressed practitioner would plausibly give a general AI assistant for this task, using only public inputs. **Run it** with your own search ability, then grade the result: *acceptable* (the user could act on it), *partial* (right idea, stale, unverifiable or incomplete) or *unacceptable*. Record the prompt in one line and the grade with its reason. If you cannot run it, label "reasoned" and cap U at 1. If the result is *acceptable*, U is 0 and the variant needs a different mechanism, not a better version of the same output.

**Maximum total: 16.** Rank by total, then by G, then by N, then by P, then, as last tie-breakers, by lowest scenario to reach the paid depth and stack coverage. Founder skills and `HINT` never enter the score. Drop a variant with N = 0 or P = 0 and no proxy-signal explanation, with the reason.

## Step 4: Adversarial stress test (two stages)

### 4A. Quick screen (all scored variants)

Up to 6 searches in total. Run three killer attacks on every scored variant, one line each (attack, finding, status, verdict Survives / Wounded / Fatal, repair):

1. **Willingness to pay:** who exactly pays this price for this output today or producing the output is painfull for the users?
2. **General-AI and free substitute:** does the baseline run or a free official resource already give the user this same output?
3. **Market shared:** Does the output has a strong market share that goes beyond 50 percent of the market?

A variant with a Fatal verdict and no repair is dropped. Rank the survivors by total score. **Take the leading candidate into 4B**; take the runner-up only if the leader fails in 4B.

### 4B. Full test (leading candidate)

Up to 12 searches. **Minimum 12 attacks, at least 2 in each of the 6 categories below.** Run all attacks, in order, without stopping at the first wound. For each attack write one line: attack, the search or reasoning used, finding, status, **verdict** (Survives / Wounded / Fatal), and, if Wounded or Fatal, **the repair** (a concrete change to the task, segment, level, price or channel) or "no repair". An attack answered only by reasoning is labelled "reasoned" and can never be Survives with high confidence.

**Separation of attacker and builder.**
- If you can run a sub-agent, give it only the candidate card, the competitor register and the evidence list (no generation reasoning, no scores, no list of previous repairs), plus the attack list below, and instruct it to find reasons the candidate fails. Record "red team: independent sub-agent".
- If you cannot, run the attacks in a distinct pass headed "RED TEAM", written as if you were a sceptical competitor or buyer who wants this candidate to fail, and record "red team: same-model pass (weaker)". Do not soften findings to protect a score.

| Category | Attacks (minimum 2 each; add others as the candidate requires) |
|---|---|
| **1. Market relevance** | (a) Find 3 independent practitioner statements, dated within 18 months, that the problem is worth solving, and state how many you found. (b) Show that the need is growing or stable, not declining or being absorbed into another tool or role. (c) Find the best reason a practitioner would say "this is not a problem for me". |
| **2. Competition** | (a) Name the one existing offer, free or paid, that would most easily serve this customer and say what it lacks. (b) Search for failed, closed or abandoned attempts at the same output and say why they stopped.|
| **3. Substitutes and utility** | (a) Re-examine the general-AI baseline result: what would make a practitioner choose the product anyway? (b) Is there a free official or association resource that gives the same result? |
| **4. Differentiation and USP quality** | (a) Rewrite the USP sentence without any adjective: does it still make a distinct claim? (b) Would a customer understand and care about the difference in 10 seconds? (c) Is the advantage an asset that grows with time, or a feature that can be copied? (d) Can the customer verify the claim in under 5 minutes? |
| **5. Commercial viability** | (a) Is the price, at the stated form and cadence, consistent with what this segment pays for adjacent tools? (b) How many paying customers does the segment support at that price (estimate, labelled), and is that enough to matter? (c) What would the first 10 customers be, and by which channel are they reached? (d) Is the free-to-paid link real: what makes a free reader pay? |
| **6. Delivery and trust** | (a) Which input, scenario or licence could block the paid version (a source that forbids reuse, a feed that changes, a licence outside `LICENCE_POLICY`)? Walk the blueprint: for each source, its format, terms and refresh; for each stage, the format in and out; for the deliverable, whether the customer can open and use the format. (b) What is the worst error the output can contain, and can the user catch it in under 5 minutes? (c) Does the product risk individualised regulated advice or personal data issues? (d) What does the build and weekly upkeep look like for one person? |

**Aggregation.** A candidate is **Fatal** if any attack in category 1, 2 or 5 has verdict Fatal with no repair, or if two attacks in different categories are Fatal. It is **Wounded** if any attack is Wounded, or Fatal with a repair. It is **Resilient** if every attack Survives or is Wounded with only minor repairs. Not observable items never produce a Fatal verdict; they go to the manual validation list.

## Step 5: Proof sample

Up to 4 searches or fetches. For the leading candidate (after 4B, and after any refinement round), **produce a real sample of the output** for the fixed segment, built from live public sources, scenario A only (the free version):

- **Three real items** (not an anonymised or invented example), each showing the exact fields of the output **in the format the customer would receive** (for example the CSV row, the JSON object or the digest entry as it would appear) and a link to the source row, page or record it was built from, with the source's input format named.
- For each item, the **5-minute verification path**: which source to open and what to check.
- A **one-line grade by item**: correct, needs correction, or could not be verified, and what the correction is.
- If the output cannot be built from reachable public sources in this session (key inputs behind a login, too large to fetch, blocked), say "not producible: [reason]", and do not invent items.

The proof sample tests the automation claim, the free version and the first links of the blueprint (the real source format turned into the real deliverable format). It never replaces the validation plan with real practitioners. If all three items cannot be built and verified, the verdict can be at most "USP conditional".

## Step 6: Refinement loop

Count the rounds: Steps 2 to 5 on the first set of variants is round 0.

- **Trigger a new round** if the leading candidate is Wounded, or if it is Fatal and at least one repair exists, or if the proof sample failed because of a fixable cause.
- **In each round:** use the repairs, the wounds and the failed sample items as the brief. Generate up to `MAX_VARIANTS_PER_ROUND` refined variants, each with a stated parent, the wound it repairs and the hint that guided it. A refinement must change at least one element of the task card (output, level, segment inside the industry, delivery form, free/paid split or pricing form); rewording the USP sentence alone is not a refinement. Score the new variants (Step 3 rules), run 4A on them, run 4B (the full 12 attacks) on the new leader, and redo the proof sample if the output changed. Evidence already collected need not be searched twice. Use only the shared refinement pool of the search budget.
- **Stop** when any of these occurs: (1) the leading candidate is Resilient, scores at least 12 of 16 with N, P and G each at least 1, and the proof sample passes; (2) `MAX_ITERATIONS` rounds are used; (3) a round improves the best total score by less than 2 points and does not remove a Fatal or Wounded verdict; (4) every remaining idea in H1 to H9 would be drift or has been tried; (5) the search budget is exhausted (apply the budget fallback).
- Never loosen a threshold, never raise a score without new evidence, and never carry an unrepaired Fatal forward.

**Budget fallback:** if search stops working or the budget or room runs out, finish the attacks in progress for the current candidate, write the report in the given order, and mark every unfinished part "not run". Never fill a not-run part from memory.

## Step 7: Selection and verdict

Rank the final candidates (V0 included) by: (1) verdict (Resilient before Wounded), (2) total score, (3) G, (4) N, (5) P, then the last tie-breakers. State one of three verdicts:

- **USP validated:** the best candidate is Resilient, scores at least 12 of 16, has N, P and G each at least 1, has no Fatal verdict, passed the proof sample, ran the general-AI baseline (not "reasoned"), and has no unresolved Not observable item in categories 1 or 2 that would change the verdict.
- **USP conditional:** the best candidate scores 8 to 11, or is Wounded with a repair not yet tested, or the proof sample was not producible, or the baseline could not be run, or an unresolved Not observable item as above remains. State the single test that would turn it into validated or killed (see validation plan).
- **No sufficient USP found:** no candidate reaches 8 of 16, or every candidate is Fatal, or every need fails D1. Say so plainly. List the closest candidate, the smallest change that would revive it (including a higher `MAX_SCENARIO`, a different `TARGET_DEPTH`, a different segment, or a neighbouring industry or role to try next), and what you learned about where customers are not served.

Zero strong USPs is an acceptable result. Never invent a differentiator to avoid it.

## Report format (same headings every time, in this order, content in LANGUAGE)

0. **Parameters applied:** the table from Step 0.0, printed first, before any other content.
1. **Run summary:** run date, model (if known), tools missing, overrides applied or refused, consistency check results from Step 0, the searches used per step against `SEARCH_BUDGET`, the red-team mode (independent sub-agent or same-model pass), the number of refinement rounds run, the number of variants generated, scored and rejected as drift, and which steps or attacks were not run.
2. **Verdict and recommended USP:** one of the three verdicts, the chosen task version (ID, parent chain), its USP sentence, the segment, the exact recurring output, the free and paid versions, the pricing, and the upsell direction. Then a 3 to 4 sentence **description** that lets a reader who has not seen the rest of the report understand why this version and this USP were selected: what the practitioner does today, why a miss costs them, the strongest evidence that people pay, how crowded the market is and the gap used, and the main remaining risk. If the verdict is "No sufficient USP found", give the near-misses instead.
3. **Demand gate, market and competition:** the D1 to D4 results, need evidence (with links), the competitor register (compact table), the utility test answers (a to d), the general-AI baseline (prompt, grade, reason), the saturation profile by level for the area and for the final candidate, and the unserved needs found.
4. **Variants:** a table with ID, parent, hint(s), what changed, USP sentence in one line, total score and verdict, outcome (rejected as drift / dropped at 4A / tested at 4B / selected). Then the full scorecard (criterion by criterion, with status and link) for every candidate taken into 4B.
5. **Adversarial stress test:** the 4A results for all variants, then the full 4B list of attacks (at least 12) for each candidate tested, with attack, finding, status, verdict and repair. Then the aggregation and the refinement path from round to round (which wound caused which change).
6. **Proof sample and blueprint:** the three items (or "not producible: reason"), each with its source link, source input format, customer-format rendering, 5-minute verification path and grade. Then the blueprint of the final version as three compact tables: (1) data sources to curate (ID, name, scenario, access mode, input format, reuse terms, refresh, levels, status); (2) pipeline (ID, stage, tool with licence and date or category, coverage, input format, output format) and the curated asset; (3) customer deliverable (free version and one row per rung A to `MAX_SCENARIO`: what the customer receives, format, main fields, channel and cadence, what the customer provides, reachable yes or blocker).
7. **Validation plan:** for the final candidate, the cheapest tests to run with real practitioners before any build: a pre-sale page with a price, 10 practitioner conversations, or a concierge issue for 3 readers; with success and failure criteria. Include the questions to ask practitioners ("when did you last miss a change in these inputs and what did it cost?", "who does this for you today and what do you pay?", "what do your current tools get wrong?", "would you need us to connect to your data, or could you export it?"), every Not observable item, every open-source project to verify by hand and every claim downgraded from Prompt 1.
8. **Handoff for build and validation (output only):** this is the block you write at the end of your answer for the next step. The user does not fill it in and it is not an input. Write it in this exact format (fill every field; write "none", "unknown" or "not run" rather than omitting one).

```
=== USP HANDOFF START ===
handoff_version: usp-v1.3
run_date: <RUN_DATE>
source_handoff: find handoff version <v> | run date <date> | candidate <ID>
verdict: <USP validated | USP conditional | No sufficient USP found>
parameters: ROLE <v> | COUNTRY <v> | INDUSTRY <v> | segment <v> | LANGUAGE <v> | MAX_SCENARIO <v> | TARGET_DEPTH <v> | HUMAN_IN_LOOP <v> | LICENCE_POLICY <v> | TARGET_SATURATION <v>
overrides_applied: <list or "none">
origin: initial task V0 <one line> | final version <ID, parent chain> | rounds run <n>
final_task: <task and exact recurring output, one line>
usp_sentence: <the final sentence, no adjective carrying the claim>
description: <3 to 4 plain sentences, see report section 2>
user_and_payer: <who uses it, who pays, how they are reached>
free_version: <output, scenario A, level>
paid_version: <output, level, scenario, 5-minute verification, human step if any>
ladder: L1 <scenario, HITL, reachable> | L2 <...> | L3 <...> | max depth <...>
data_sources:
  - <S1 | name | link | kind | scenario (A | B | C | D) | access (API | bulk file | scrape | manual upload | connector | on-premise) | input_format (CSV | JSON | XML | XLSX | PDF text | PDF scanned | HTML | other; "(Unverified)" if not seen) | reuse_terms (Confirmed licence or "unverified") | refresh | levels used>
  - <S2 ...: one line per source; reader sources state the export or fields needed>
stack:
  pipeline:
    - <P1 | stage | tool category | project (licence, last release date) or "category only" | coverage (covered | partly | to build) | input: source IDs or previous stage, format | output: format>
    - <P2 ...: one line per stage, in order>
  curated_asset: <what the founder keeps and grows, with storage format, or "none">
  build_gap: <one or two sentences, domain logic first>
  licence_notes: <one line or "none">
deliverables:
  free: <customer receives | format | main fields | channel and cadence | sources S.. via stages P..>
  rung_A: <public data only: customer receives | format | main fields | channel | sources and stages | customer provides "nothing" | levels delivered; or "not reachable: blocker">
  rung_B: <reader upload: same fields, customer provides the export named in data_sources; or "above MAX_SCENARIO" or "not reachable: blocker">
  rung_C: <integration: same fields, customer provides the connection; or "above MAX_SCENARIO" or "not reachable: blocker">
  rung_D: <self-hosted: same fields, customer provides the infrastructure; or "above MAX_SCENARIO" or "not reachable: blocker">
price: <anchor (source) or hypothesis, labelled> ; form <monthly | annual with alerts | per event>
upsell_direction: <one line or "none">
saturation: L1 <class> | L2 <class> | L3 <class> | competing level <...> | gap kind <...>
top_competitors: <3 to 5: name | kind | price | channel | depth | scenario | link>
demand_gate: D1 <status/conf> | D2 <...> | D3 <...> | D4 <...>
general_ai_baseline: <prompt in one line> | grade <acceptable | partial | unacceptable | reasoned> | reason
scorecard: N <0-2> | P <0-2> | G <0-2> | U <0-2> | R <0-2> | F <0-2> | L <0-2> | S <0-2> | total <x/16>
stress_test: red team <independent sub-agent | same-model pass> | attacks run <n> | Survives <n> | Wounded <n> | Fatal <n> | open repairs <list>
proof_sample: <3 items, one line each with source link and grade | "not producible: reason">
key_evidence: <the 3 strongest pieces, one line each with link and status>
weakest_points: <list, one line each>
claims_downgraded_from_prompt_1: <list or "none">
not_observable: <list, one line each>
searches_used: <n of SEARCH_BUDGET>
validation_test: <test, success criteria, failure criteria>
alternatives_kept: <other variants worth keeping, with one-line reason>
next_step: <build the free version | run the validation test | revisit with changed parameter X | stop>
=== USP HANDOFF END ===
```