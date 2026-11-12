# Maintaining the "Find a fast-selling emerging feature" prompt

This file is for you, not for the model. Don't paste it into a run.

## Between two runs (about 5 minutes)

1. In `run_inputs`, change only what you want to change. Dates count from the Run date automatically.
2. From the last report's section 13, replace each Part 0 block with the block of the same name: `optional_inputs`, `already_explored_ideas`, `verified_facts`, `coverage_log`, `watch_list`, `process_stats`.
3. If you pitched an idea, add a line to `field_results` and update its status in `already_explored_ideas` (tested, selling, abandoned).
4. To lock an optional input, label it "set by the person"; runs will no longer change it.
5. Read section 14 (suggested prompt changes). Apply one only if you agree, following the rules below.

## Changing the rules (Part A or B)

- Each term is defined once, in Part B. Change it there only.
- If you add, remove or rebudget a step, update the table and the step's paragraph in Part A, and the Pre-report checklist if it checks that step.
- If you add an Input, put it in `run_inputs` or `optional_inputs`, and reference it where it's used.
- Change one thing at a time, and compare `process_stats` before and after, so runs stay comparable.
- Bump the version on the prompt's first line and add a line below.

## Change history

- 2.1 (2026-11-12): compressed by about 40% with no rule removed: step sections no longer repeat the table; the Pre-check list lives only in the candidate card; the report refers to the card; emerging sources are defined once; maintenance notes and history moved to this file.
- 2.0 (2026-11-12): Part 0 with named blocks and run memory; Step 0 and discovery rotation; payer opened to any type, with consumer law, B2C prospecting, self-entered health data, VAT and procurement rules; criteria 5 and 8 confirmed after the offer; Step 5 gate; Step 7 failure action and ranking; search counting defined; Gain visible window tied to criterion 1; risk reversal limited to deliverables; levers (a) fixed and (l) added; Professional ethics rules in Pre-check.
- 1.0: initial version.