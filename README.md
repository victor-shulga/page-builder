# page-builder

A production line for website pages of a B2B service business — a Claude Code plugin (skill).

Most agency websites are built page by page, by whoever was free that week. Page 40 looks nothing
like page 1. This skill makes the process repeatable: one request in, one publish-ready page out,
scored against the same standard every time.

## The idea in one line

**A Site Blueprint is an input, not a step. Gates are stop-filters, not suggestions.**

Those two rules prevent the two failures that cost the most: pages that have nowhere to live, and
pages that ship broken because the checklist was advisory.

## What it does

```
Intake  →  Route to Kit  →  G-A gate  →  Build  →  G-T gate  →  Scorecard  →  30/90-day review
                             (blocks              (blocks
                              writing)             publish)
```

1. **Intake** — page type, reader, intent, place in the blueprint, one conversion action, available proof.
2. **Route** — picks the Page Kit for that type and loads only that Kit.
3. **G-A · architecture gate** — placement, cannibalisation, inbound links, Search Console baseline.
   Runs *before* a word is written, because a duplicate page drags down the page it duplicates.
4. **Build** — structure, then copy, search/AI visibility, UI/UX, conversion and technical passes.
5. **G-T · technical gate** — indexation, schema, performance, analytics events verified by hand.
6. **Scorecard** — weighted, threshold 85/100, with the losing axis named.
7. **Review** — 30 and 90 days against the baseline.

## The Page Kits

Each Kit is a full build spec: slot-by-slot structure, an intake questionnaire, a writer SOP, a
technical checklist, a designer brief and a pre-launch checklist.

| Kit | Builds | Distinctive rule |
|---|---|---|
| **Service Page** | The page that turns traffic into an enquiry | 16 slots. The boundary ("what's *not* included") and a price — at least a range — are mandatory |
| **Industry Page** | The same service in one vertical's language | Opens with **G-I**: no page at all without 2 cases from that vertical, plus the **60% uniqueness rule** |
| **Case Study** | One project, one number, one narrative | No number in the headline means the case is not ready |
| **Blog Page** | Articles, guides, comparisons, hubs | Built for AI search: TL;DR, comparison tables, FAQ schema, visible updated date |

`references/page-types.md` maps ~25 page types to Kits and to funnel stage, and gives the rules for
planning which pages a site should have at all.

## Install

```bash
/plugin marketplace add victor-shulga/page-builder
```

```bash
/plugin install page-builder@page-builder
```

Restart the session afterwards — skills load at session start.

Or with the skills CLI:

```bash
npx skills add victor-shulga/page-builder
```

## Use it

Say what you need in plain language:

- `build a service page for [service]`
- `we need an industry page for [vertical]`
- `turn this project into a case study`
- `audit this page against the standard` + paste the URL
- `which pages should this site have?`

The skill asks only for what is missing, and stops if there is no Site Blueprint rather than
producing an orphan page.

## What it will not do

- **Invent proof.** No fabricated figures, client names, certifications or standards. Missing proof is
  flagged as missing.
- **Silently substitute a Kit.** If a page type has no dedicated Kit, it says which Kit it is
  building from.
- **Ship past a gate.** A page that fails G-A or G-T goes back; it does not proceed with a note in
  the margin.
- **Rewrite your homepage messaging.** That is a positioning job, not a page job.

## Repo layout

```
skills/page-builder/
  SKILL.md                          the pipeline
  references/
    page-types.md                   registry: ~25 types → Kit → funnel stage
    kit-service-page.md             16 slots + questionnaire + SOP + checklists
    kit-industry-page.md            G-I gate + 60% rule + 15 slots
    kit-case-study.md               12 sections + SME questionnaire
    kit-blog-page.md                17 elements, built for AI search
    gates-and-scorecard.md          G-I / G-A / G-T + two weighted scorecards
```

## Author

**Victor Shulga** — Fractional CRO for B2B service companies.
[victorshulga.com](https://victorshulga.com) · [github.com/victor-shulga](https://github.com/victor-shulga)

MIT licensed. Client-generic by design: no client names, cases or vendor lists ship with it.
