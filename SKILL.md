---
name: ui-anti-slop-codex
description: "Codex UI anti-slop workflow for frontend design and implementation. Use automatically when Codex builds, reviews, fixes, styles, redesigns, or improves user interfaces: landing pages, dashboards, app UI, admin panels, editors, checkout and pricing flows, docs, mobile UI, visual QA, screenshots, DESIGN.md design systems, or when the user says ai-slop, anti-slop, visual contract, make it look better, less generic, or invokes $ui-anti-slop-codex / ui-anti-slop-codex."
---

# UI Anti Slop Codex

Force Codex to treat UI work as a product design task, not a generic screen fill task. Route the surface, lock a visual contract, use repo design truth, implement, then verify the rendered UI before final delivery.

## Workflow

Follow this sequence for every UI task unless the user explicitly asks for discussion only.

1. **Ground in repo truth**
   - Inspect existing UI files, routes, global styles, component libraries, icon libraries, package manager, screenshots, design docs, and `DESIGN.md`.
   - Prefer existing design systems and local components over new visual systems.
   - If a `DESIGN.md` exists, read it before visual decisions. If the task creates or edits a `DESIGN.md`, load `references/design-md-protocol.md`.

2. **Classify the surface**
   - Classify the work as one or more of: landing, marketing site, platform app, dashboard, admin or internal tool, editor or creator, checkout or pricing, docs or devrel, mobile UI, game or interactive surface.
   - Load `references/surface-contracts.md` for the matching surface.
   - If the surface or audience is still genuinely ambiguous after repo inspection, ask one highest-leverage question and recommend an answer. Do not ask for facts that the repo can answer.

3. **Choose the reference family**
   - Use explicit user references first.
   - Otherwise choose a family from `references/reference-families.md` that matches the surface, audience, business job, and density.
   - Treat references as design vocabulary, not cloning permission.

4. **Declare a Visual Contract before editing UI**
   - Keep it compact and operational:

```md
Visual Contract
- Surface:
- User job:
- Reference family:
- Design source:
- Density:
- Layout:
- Required states:
- Forbidden tells:
- Verification:
```

   - `Design source` must say whether the source is existing repo UI, `DESIGN.md`, user reference, generated reference, or an inferred family.
   - `Forbidden tells` must be specific to this surface, not a generic list.

5. **Implement against the contract**
   - Build the actual usable surface first. Do not ship a landing page when the task is a platform screen, and do not ship a product cockpit when the task is a public landing page.
   - Use existing components, tokens, fonts, icon sets, chart libraries, routing, and state patterns when available.
   - Add new visual language only when the repo has no usable design source or the user asked for a redesign.

6. **Verify visually before final delivery**
   - Load `references/codex-verification.md`.
   - Run the app or open the artifact when feasible.
   - Capture desktop and mobile screenshots when browser tooling is available.
   - Critique the rendered output against the Visual Contract, then fix visible issues before final response.

## Core Rules

- Surface first. Visual style follows the job of the screen.
- Tokens first. If `DESIGN.md` or design tokens exist, they are the design source of truth.
- Product proof beats decoration. Use real product UI, real media, real data states, or explicit placeholders. Avoid div-based fake screenshots.
- Density must match usage frequency. Daily tools need scan speed. Public pages need offer clarity and proof.
- One visual system per surface. Do not mix unrelated palettes, icon families, radius systems, shadows, and typography voices.
- No silent generic defaults. Ban default purple gradients, decorative cards, fake metrics, nested cards, vague copy, invisible button text, and unexplained large whitespace unless the contract justifies them.
- Verification is part of the task. Do not finish while text overlaps, mobile breaks, charts are unreadable, buttons lack contrast, or the design contradicts the contract.

## Reference Routing

- Load `references/design-md-protocol.md` when `DESIGN.md` exists, the user mentions `DESIGN.md`, the work creates a reusable design system, or a broad redesign needs persistent visual rules.
- Load `references/surface-contracts.md` for surface classification and required UI behavior.
- Load `references/reference-families.md` when choosing a visual reference family or when the user names a product or brand as inspiration.
- Load `references/codex-verification.md` before finalizing any visual UI implementation or review.

## Output Discipline

- Before code edits for substantial UI work, state the Visual Contract.
- During implementation, keep user updates short and tied to the contract.
- In the final response, report the key UI changes, verification performed, and any checks that could not be run.
