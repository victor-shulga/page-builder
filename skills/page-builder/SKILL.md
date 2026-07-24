---
name: page-builder
description: >-
  Production line for website pages of a B2B service business (agency, outsourcing, consulting).
  Takes ONE page request — a service page, an industry/vertical page, a case study, a blog article,
  a landing page — and runs it end to end: picks the right Page Kit for that page type, enforces the
  architecture gate BEFORE a word is written, drafts the structure, runs copy, search/AI visibility,
  UI/UX, conversion and technical passes, then scores the page on a weighted scorecard and enforces
  the technical gate before publish.
  Use whenever someone says: "build a service page", "write the page for [service]", "we need an
  industry page for [vertical]", "make a page for our website", "rewrite this page", "add a page to
  the site", "напиши сторінку послуги", "зроби сторінку під галузь", "сторінка на сайт". Also use when
  auditing an existing page against the standard, or when planning which pages a site should have.
  Do NOT use for the homepage messaging rewrite from scratch (that is a positioning job) or for social
  posts. This skill assumes a Site Blueprint exists; if it does not, it stops and says so.
---

# page-builder — the website page production line

You are running a repeatable pipeline. The point is that page #40 comes out as good as page #1,
built by whoever is on shift.

Two rules that carry the whole thing:

1. **A Site Blueprint is an input, not a step.** The blueprint (page inventory, clusters, URL logic,
   internal-link map) is made once per site. A page cannot be placed inside an architecture that does
   not exist. No blueprint → stop and produce the blueprint first.
2. **Gates are stop-filters, not suggestions.** G-A blocks writing. G-T blocks publishing. A page that
   fails a gate does not proceed with a note in the margin; it goes back.

---

## Phase 0 — Intake

Collect before anything else. Ask only for what is missing; never invent answers.

| Field | Why it matters |
|---|---|
| Page type | Selects the Kit (see `references/page-types.md`) |
| Business + what they sell | Everything downstream is written in their vocabulary |
| Target reader (role, seniority, company type) | Determines pains, proof, and objections |
| Search intent | Informational / commercial / transactional — changes structure and CTA |
| Place in the blueprint | Parent page, cluster, URL, which pages link in |
| One conversion action | A page with two primary actions has none |
| Proof available | Cases, numbers, quotes, certifications, named clients |
| Language | Page language is the reader's language, not the team's |
| Design system | Client's own tokens; never a generic template |

**If there is no Site Blueprint**, stop here. Say plainly: the page has nowhere to live, and
publishing it produces an orphan. Produce the blueprint (inventory → clusters → URL scheme →
internal-link map), then resume.

---

## Phase 1 — Route to the Kit

Read `references/page-types.md` and pick the Kit. Load only that Kit file.

| Page type | Kit | Reference |
|---|---|---|
| Service / offer page | Service Page Kit | `references/kit-service-page.md` |
| Industry / vertical page | Industry Page Kit | `references/kit-industry-page.md` |
| Case study | Case Study Kit | `references/kit-case-study.md` |
| Blog article / guide / comparison / listicle | Blog Page Kit | `references/kit-blog-page.md` |
| Landing page (campaign) | Service Page Kit, minus navigation, one action only |
| Other types in the registry | No Kit yet — build from the nearest Kit and say so explicitly |

Never silently substitute a Kit. If the requested type has no Kit, name the substitution.

---

## Phase 2 — G-A · Architecture gate (BEFORE the first word)

All four must pass. Read `references/gates-and-scorecard.md` for the full checklist.

- [ ] The page has a defined place in the blueprint: parent, cluster, final URL
- [ ] Cannibalisation checked — no existing page already targets these queries
- [ ] Inbound internal links identified — which existing pages will link here
- [ ] Search Console baseline captured if the URL already existed

Failing G-A costs the entire writing cycle. A page that duplicates an existing one does not just
underperform; it drags down the page it duplicates.

Industry pages carry an extra gate, **G-I**, inside their Kit — it decides whether the page should
exist at all. Run it before G-A for that type.

---

## Phase 3 — Build

Structure first, then the passes. Passes 2–6 can run in any order; structure cannot move.

**1. Structure.** Fill every slot of the Kit top to bottom. A slot may be dropped only deliberately,
and the reason gets recorded. Mark visual placeholders inline (`[HERO]`, `[PROCESS]`, `[QUOTE]`).

**2. Copy.** Written in the reader's vocabulary, taken from real calls and emails. Nouns for
deliverables, numbers for claims. Every differentiator carries proof — a figure, a standard, a named
certification, a linked case. A differentiator without proof is deleted, not softened. Strip AI
tells: no negative parallelism ("not X, but Y"), no rule-of-three punch triads, no filler
intensifiers.

**3. Search and AI visibility.** Primary query in H1 and the first 100 words. One H1, no skipped
heading levels. FAQ block built from real objections, phrased the way a human asks. Comparison tables
where the topic allows — structured data is what AI search quotes. Schema per the Kit. Clean URL.

**4. UI/UX.** The client's design system, never a generic theme. Scannable in 60 seconds. Mobile
first: most traffic is a phone. Contrast and focus states pass accessibility. Tables and diagrams
scroll inside their own container.

**5. Conversion.** One primary action, visible without scrolling. Inline actions contextual to their
section. A soft alternative for readers not ready to talk — a checklist, a sample of work, a
teardown. Short form. Analytics events on view, start, submit, and contact clicks.

**6. Technical.** Indexable, in the sitemap, canonical correct, valid schema, images optimised, page
weight controlled.

---

## Phase 4 — G-T · Technical gate (BEFORE publish)

- [ ] Indexable, present in sitemap, canonical points where intended
- [ ] Schema validates
- [ ] Performance and accessibility within threshold
- [ ] One conversion action; analytics events verified firing by hand
- [ ] All visual placeholders replaced

---

## Phase 5 — Scorecard

Score the page out of 100 using the weights in `references/gates-and-scorecard.md`. Threshold **85**.
Below threshold, return to the axis that lost points; do not average the failure away.

Report the score as a table with the points lost and why. A scorecard that always returns 95 is not
measuring anything.

---

## Phase 6 — Post-launch review

Schedule 30-day and 90-day reviews against the baseline: impressions and position in Search Console,
enquiries attributed to the page, scroll depth.

- A page with zero enquiries at 90 days goes back for a copy pass or a review of its place in the cluster.
- For an industry page, check separately whether the parent service page lost ground. If it did, the
  child is a duplicate — fold it back into a section.

---

## Working rules

- **Never fabricate proof.** No invented figures, client names, certifications, or standards. Missing
  proof is flagged as missing: "to confirm with delivery — not fabricated".
- **Confidentiality.** Client names, logos and cases never go into a public or shareable artifact
  unless the client approved that specific use.
- **One page, one job.** A page that serves two intents serves neither.
- **Price belongs on the page.** At minimum a range or a floor. Silence about money reads as
  "expensive and evasive" and loses the reader before they reach the form.
- **Say what you skipped.** If a section was dropped for missing input, state it in the handover
  rather than quietly shipping a thinner page.
