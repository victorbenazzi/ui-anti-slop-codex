# Codex Verification

Visual work is not done until the rendered surface has been inspected.

## Browser Loop

Use this loop when the project can run locally or the artifact can be opened:

1. Start or reuse the dev server.
2. Open the UI in a browser or browser automation tool.
3. Capture desktop and mobile screenshots.
4. Compare the screenshots against the Visual Contract.
5. Fix visible defects.
6. Repeat until the output no longer contradicts the contract.

Recommended viewport set:

- Desktop: 1440 by 900.
- Small desktop or tablet: 1024 by 768 when relevant.
- Mobile: 390 by 844.
- Narrow mobile: 375 by 667 when text or nav is risky.

If browser tooling is unavailable, still run static checks and state that visual screenshot verification could not be performed.

## Screenshot Critique Checklist

Check the actual image, not just DOM or code:

- Does the first screen match the classified surface?
- Is the primary user job visible without reading explanatory marketing text?
- Is text readable and contained in its parent?
- Do buttons have visible text, hover or pressed states, and clear hierarchy?
- Are controls stable, or do labels and dynamic states shift the layout?
- Does mobile reflow preserve the core task?
- Is there horizontal scroll?
- Do fixed headers, footers, or sidebars hide content?
- Are tables, charts, forms, and empty states usable?
- Are images real, generated, or explicitly placeholdered, rather than div-based fake screenshots?
- Does the color palette look like one intentional system?
- Are icons from one family and sized consistently?
- Is decorative motion absent or justified by the contract?

## Common AI Tells To Scan

Search code and CSS for likely tells. Treat matches as review prompts, not automatic failures.

```bash
rg -n "linear-gradient|radial-gradient|purple|violet|indigo|blur-3xl|backdrop-blur|shadow-xl|rounded-full|Lorem|John Doe|Acme|transform your|unlock|seamless|next-gen" .
```

Fix when the tell contradicts the Visual Contract:

- Purple, violet, or indigo gradients used by default.
- Beige craft palette reused for unrelated premium consumer work.
- Card grids with no workflow.
- Cards inside cards.
- Fake metrics and fake testimonials.
- Fake product screenshots made from styled divs.
- Oversized hero in an app surface.
- Banners explaining obvious UI.
- Button text with low contrast.
- Mixed radius systems without a rule.
- Mixed icon families.
- Font sizes that scale with viewport width and break long words.

## Accessibility And Interaction Checks

At minimum:

- Normal text contrast should meet WCAG AA, 4.5 to 1.
- Touch targets should be at least 44px on mobile.
- Icon-only buttons need accessible names or visible labels.
- Forms need labels, errors near fields, and recovery actions.
- Loading, empty, disabled, selected, active, hover, focus, and error states should exist when the component can enter those states.
- Motion should respect `prefers-reduced-motion`.
- Charts should include units, labels, legends or direct labels, and not rely on color alone.

## Canvas, 3D, And Game Checks

For canvas, Three.js, WebGL, games, or interactive boards:

- Verify the canvas is nonblank with a pixel or screenshot check.
- Verify the scene is framed correctly on desktop and mobile.
- Verify movement or interaction is visible.
- Verify controls do not overlap the canvas.
- Verify restart, reset, pause, or escape routes when relevant.

## Final Response Requirements

In the final answer, include:

- What changed.
- Which surface contract was used.
- Which visual verification ran.
- Any verification that could not run.

Do not claim the UI was visually verified if no screenshot or rendered inspection happened.
