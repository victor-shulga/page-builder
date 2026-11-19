# UI/UX pass

Phase 3, pass 4. The page already has structure and copy; this pass decides whether a reader can
actually use it on the device they are holding.

---

## The rule that decides every conflict

**The client's design system wins.** Colours, type scale, spacing, radius, component shapes and the
logo lockup come from the client's own tokens — a design-system file in the repo, a Figma library, or
a live style guide. A generic recommendation never overrides them, however good it looks in
isolation. A page that is beautiful and off-brand has failed, because the reader's first judgement is
"is this the same company I was just talking to".

What is genuinely open, and what this pass decides (the checklist below is the whole pass):

| Decided by the design system | Decided by this pass |
|---|---|
| Palette, fonts, type scale | Layout and section rhythm |
| Spacing scale, radius, shadows | Which component carries which slot |
| Button and form styling | Hierarchy and scan path |
| Iconography and imagery style | Accessibility and touch behaviour |
| Logo and brand marks | Motion, loading and empty states |

If the client has no design system, say so in the handover and build one before the page, rather
than inventing tokens page by page and drifting across the site.

---

## Review order — highest cost of failure first

### 1. Accessibility — blocking

- [ ] Contrast at least 4.5:1 for body text, 3:1 for large text and meaningful icons
- [ ] Visible focus ring on every interactive element; focus order matches visual order
- [ ] Alt text on every meaningful image; empty alt on decorative ones
- [ ] `aria-label` on icon-only buttons
- [ ] Every form field has a real `<label>` tied by `for`
- [ ] The page is operable by keyboard alone, including the primary action

A page that fails contrast or keyboard operation fails the pass outright. This is not a polish item;
in several jurisdictions it is a legal exposure for the client.

### 2. Touch and interaction — blocking

- [ ] Touch targets at least 44×44 px, with spacing between adjacent ones
- [ ] Nothing important is revealed only on hover — there is no hover on a phone
- [ ] Submit buttons disable and show state during async work
- [ ] Errors appear next to the field that caused them, in plain language
- [ ] `cursor: pointer` on anything clickable

### 3. Performance

- [ ] Images in a modern format, with `srcset` and lazy loading below the fold
- [ ] Space reserved for async content so nothing jumps as it loads
- [ ] `prefers-reduced-motion` respected
- [ ] Fonts subset and preloaded; no layout shift when they swap in

### 4. Layout and responsive

- [ ] Viewport meta present
- [ ] Body text at least 16 px on mobile
- [ ] No horizontal scroll at 320 px width
- [ ] Tables, code blocks and diagrams scroll inside their own container, not the page
- [ ] A defined z-index scale rather than ad-hoc numbers

### 5. Typography and colour — within the design system

- [ ] Line height 1.5–1.75 for body copy
- [ ] Line length 65–75 characters at desktop width
- [ ] Heading levels used for hierarchy, not for size
- [ ] Colour never the only carrier of meaning

### 6. Motion

- [ ] Micro-interactions 150–300 ms
- [ ] Animate `transform` and `opacity`, not `width` and `height`
- [ ] Loading states are skeletons or spinners, never a blank region

---

## The 60-second scan test

Before signing the pass off, look at the page for one minute the way a stranger would and answer:

1. What does this company do, and for whom?
2. What is the one action this page wants?
3. Why should I believe them — what proof did I actually notice?

If any answer takes longer than the minute, the problem is hierarchy, not copy. Fix it here rather
than sending it back to the writer.

---

## What this pass hands to the blind judge

The judge scores **Design and UX** without opening a browser, so state plainly in the fact sheet:
measured performance, viewport widths checked, contrast results, and whether keyboard operation was
verified by hand. Unverified items are reported as unverified — never as passed.
