# Gates and scorecards

Three gates and one scorecard. They exist because the expensive failures on a website are decided
before the writing starts and after it finishes, not during.

---

## G-I · Should this page exist (industry pages only)

Runs first, before anything else, and only for industry/vertical pages. Full detail in
`kit-industry-page.md`.

- [ ] 2+ cases from this vertical
- [ ] Demand: queries with the industry name, or ≥15% of pipeline
- [ ] 5 facts absent from the parent service page
- [ ] The vertical's salesperson confirms different objections
- [ ] The 60% uniqueness rule can realistically be met

**Fail →** a section on the parent service page instead. Revisit when two cases exist.

---

## G-A · Architecture gate — before the first word

Runs for every page type.

- [ ] **Placed in the blueprint.** The page has a parent, a cluster and a final URL. If the blueprint
      does not exist, stop: build it first.
- [ ] **Cannibalisation checked.** No existing page already targets these queries. If one does, the
      decision is rewrite-and-merge, not publish-alongside.
- [ ] **Inbound internal links identified.** Name the specific existing pages that will link here. A
      page with no inbound link is invisible.
- [ ] **Baseline captured** in Search Console if the URL already existed — impressions, position,
      clicks. Without a baseline the 90-day review cannot say whether the rewrite helped.

**Why this gate is first:** a page that duplicates an existing one costs the entire writing cycle and
also drags down the page it duplicates. Rewriting after publication is more expensive than deciding
before.

---

## G-T · Technical gate — before publish

- [ ] Indexable, present in sitemap, canonical points where intended
- [ ] Schema validates for every type used on the page
- [ ] Performance and accessibility within threshold; mobile checked on a real viewport
- [ ] One primary conversion action; analytics events verified firing by hand, not assumed
- [ ] All `[markers]` replaced with final visuals; alt text everywhere

---

## Scorecard — service page and most types

Threshold **85 / 100**. Below it, return to the axis that lost points. Do not average a failure away.

| Axis | Weight | What is checked |
|---|---|---|
| Conversion | 20 | one action, soft alternative, short form, events working |
| Offer clarity and copy | 20 | what's included, the boundary, process, price, buyer's language, no AI tells |
| Structure | 15 | every Kit slot present or deliberately dropped |
| Search and AI visibility | 15 | queries, FAQ, schema, quotable blocks |
| Proof | 10 | cases from this service, figures, quote, team |
| Design and UX | 10 | client design system, mobile, hierarchy, accessibility |
| Technical layer | 10 | URL, canonical, performance, indexation |

## Scorecard — industry page

Different weights: the risks here are duplication and unproven belonging, not offer clarity.

| Axis | Weight | What is checked |
|---|---|---|
| Uniqueness against the parent page | 20 | 60% rule, different search titles, no cannibalisation |
| Proof of belonging to the industry | 20 | context, standards, 2+ vertical cases, quote, tools |
| Conversion | 15 | one action, industry magnet, form, events |
| Copy in the industry's language | 15 | buyer's terms, verbatim pains, no AI tells |
| Search and AI visibility | 15 | industry-name queries, FAQ, schema |
| Place in the cluster | 10 | link up and down, sibling block, breadcrumbs |
| Design and technical layer | 5 | design system, mobile, performance, indexation |

## How to score honestly

Award partial credit per axis and write down what was lost and why. A scorecard that always returns
95 measures nothing.

Two habits that keep it useful:

- **Score before the fixes, not after.** The first number is the one that tells you where the process
  is weak across many pages.
- **Track the losing axis across pages.** If "proof" keeps losing points, the problem is not the
  writer — it is that nobody is collecting case studies.

---

## Post-launch review — 30 and 90 days

Against the baseline captured at G-A.

| Signal | What it means | Action |
|---|---|---|
| Impressions growing, position flat | The page is found but not chosen | Title and description rewrite |
| Position growing, no enquiries | Traffic arrives, the offer does not land | Conversion and copy pass |
| Nothing at 90 days | Wrong place in the cluster, or no demand | Review the blueprint, consider merging |
| Parent page dropped after a child launched | The child is a duplicate | Fold it back into a section |

The last row matters most for industry pages and is the reason the uniqueness axis carries the
heaviest weight there.
