# DESIGN.md Protocol

Use `DESIGN.md` as the persistent design contract for Codex UI work.

## Source Priority

1. User-provided reference or explicit brand rules.
2. Existing repo `DESIGN.md`.
3. Existing code tokens, global CSS, component library, and screenshots.
4. A concrete reference family selected for the surface.
5. Inferred style, only when no stronger source exists.

When sources conflict, preserve repo truth unless the user asked for a redesign. If `DESIGN.md` conflicts with live UI, mention the conflict and choose the safer path for the requested task.

## How To Consume DESIGN.md

- Find candidate files with `rg --files | rg '(^|/)DESIGN\\.md$|(^|/)design\\.md$'`.
- Read `DESIGN.md` before choosing colors, fonts, radius, spacing, shadows, motion, cards, nav, or CTA styling.
- Treat YAML frontmatter tokens as normative values.
- Treat markdown prose as rationale, usage rules, and constraints.
- If token values and prose disagree, prefer tokens for implementation and note the prose mismatch if it matters.
- Use token names directly in reasoning. Avoid paraphrasing token roles when exact names exist.

## When To Create Or Update DESIGN.md

Create or update `DESIGN.md` only when one of these is true:

- The user explicitly asks for it.
- The task is greenfield UI with more than one screen or a reusable visual system.
- The task is a broad redesign that should persist across sessions.
- The repo has inconsistent UI and no design source of truth.
- The task uses an external reference family that should be reused later.

Do not create or update `DESIGN.md` for a tiny component fix unless the user asks.

## Minimal DESIGN.md Shape

Keep the file compatible with the Google Labs alpha spec:

```md
---
version: alpha
name: Product Design System
colors:
  primary: "#111111"
typography:
  body-md:
    fontFamily: Geist
    fontSize: 16px
    fontWeight: 400
    lineHeight: 1.5
rounded:
  sm: 4px
spacing:
  md: 16px
components:
  button-primary:
    backgroundColor: "{colors.primary}"
    textColor: "#ffffff"
---

## Overview

Describe the specific visual world, audience, density, and emotional register.

## Colors

Explain each palette role and where it must not appear.

## Typography

Define the type hierarchy and usage rules.

## Layout

Define spacing, max widths, density, and responsive behavior.

## Elevation & Depth

Define shadows, borders, tonal layers, or the explicit absence of depth.

## Shapes

Define radius and shape consistency.

## Components

Define buttons, inputs, cards, nav, tables, charts, and states that matter.

## Do's and Don'ts

List practical guardrails that prevent generic AI output.
```

## Validation

Run the linter when `DESIGN.md` is created or changed:

```bash
npx @google/design.md lint DESIGN.md
```

Use lint findings as actionable QA:

- `broken-ref`: fix token references before continuing.
- `contrast-ratio`: adjust foreground and background pairs.
- `missing-primary` or `missing-typography`: add the missing source tokens.
- `section-order`: reorder sections into the spec sequence.
- `orphaned-tokens`: remove unused tokens or attach them to components.

When exporting tokens, choose the smallest useful target:

```bash
npx @google/design.md export --format css-tailwind DESIGN.md > theme.css
npx @google/design.md export --format json-tailwind DESIGN.md > tailwind.theme.json
npx @google/design.md export --format dtcg DESIGN.md > tokens.json
```

## External References

Use these sources for task-specific lookup, not as vendored content:

- Google Labs spec: `https://github.com/google-labs-code/design.md/blob/main/docs/spec.md`
- Google repo: `https://github.com/google-labs-code/design.md`
- Google blog: `https://blog.google/innovation-and-ai/models-and-research/google-labs/stitch-design-md/`
- getdesign.md: `https://getdesign.md/`
- Awesome DESIGN.md: `https://github.com/VoltAgent/awesome-design-md`

If using getdesign.md or Awesome DESIGN.md, fetch only the reference needed for the task. Do not copy brand claims, logos, trademarks, or private assumptions. Use the analysis as a visual language reference and keep the output original.
