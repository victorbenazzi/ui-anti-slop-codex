# Surface Contracts

Classify the UI before choosing style. Use the matching contract to decide density, layout, states, proof, and forbidden tells.

## CRUD Creation Flow Rule

For admin, dashboard, platform app, and data table surfaces, browsing records and creating records are different interaction modes.

Do not place a full create form beside or below the primary table or list by default. A persistent create form competes with scanning, filtering, comparing, and acting on existing records.

Default behavior:

- Keep the table or list as the primary surface for inspection and row actions.
- Use a modal, drawer, or dedicated create page for new records.
- Use a modal for short creation flows that can be completed without losing table context.
- Use a drawer when creation needs supporting context but should not fully leave the record list.
- Use a dedicated page for long, multi-step, permission-heavy, or high-risk creation flows.
- Use inline creation only for tiny single-field additions or spreadsheet-like workflows where inline entry is the core product behavior.

Forbidden tells:

- A sticky "new record" form beside a data table.
- A dashboard split between record management and blank creation fields.
- Empty form controls occupying permanent screen real estate before the user has chosen to create.
- Creation UI that reduces table width, hides row actions, or weakens scan speed.

Visual Contract requirement: when the surface includes CRUD, explicitly state whether create happens inline, in a modal, in a drawer, or on a dedicated page. Justify that choice based on task complexity and record-scanning needs.

## Landing Or Marketing Page

Primary job: convert attention into qualified intent.

Must include:

- First viewport signal: what it is, who it is for, and why it matters.
- Concrete proof: product image, actual screenshot, credible result, customer evidence, demo, or specific mechanism.
- A clear CTA hierarchy with one primary action.
- Sections that answer buyer questions in sequence.
- Real visual assets where the product, place, person, or state can be inspected.

Avoid:

- Generic SaaS hero with vague promise.
- Abstract gradient hero with no product proof.
- Fake dashboard made from div rectangles.
- Invented logos, numbers, testimonials, or social proof.
- Repeated three-card feature grids with no story.

Default density: medium-low. Pages can breathe, but every section must move the sale or explanation forward.

## Platform App

Primary job: help a recurring user complete work efficiently.

Must include:

- Persistent navigation that matches the app hierarchy.
- Primary workflow visible without marketing explanation.
- Clear actions, state, selection, loading, empty, error, disabled, and destructive flows.
- Efficient scanning through tables, lists, panels, or canvases.
- CRUD creation separated from record browsing unless inline entry is the core product behavior.
- Stable layout dimensions for controls and dynamic content.

Avoid:

- Marketing-style hero sections inside the app.
- Oversized decorative KPI cards.
- Persistent create forms competing with the primary list or table.
- Empty whitespace that slows daily operation.
- Banners explaining obvious features.
- Controls that exist only to look complete.

Default density: medium-high. Repeated-use tools should feel quiet, fast, and predictable.

## Dashboard

Primary job: support decisions through comparison, monitoring, and drilldown.

Must include:

- Metrics that answer a decision question.
- Filters, time range, segmentation, or drilldown when data changes the answer.
- Tables or lists for exact inspection, not charts alone.
- Creation flows that preserve monitoring and drilldown context when CRUD exists.
- Clear empty, loading, stale, and error data states.
- Chart legends, labels, units, and accessible color meaning.

Avoid:

- KPI theater with large numbers that do not connect to action.
- Four-card stat rows as the whole product.
- Chart decoration that hides the data.
- Blank create forms that reduce room for comparison or drilldown.
- Color-only meaning.
- Vanity metrics without workflow.

Default density: high, with restrained chrome and strong information hierarchy.

## Admin Or Internal Tool

Primary job: move operational work quickly and safely.

Must include:

- Dense tables with sorting, filtering, pagination, and bulk actions when data volume implies them.
- Clear row actions and destructive action confirmation.
- Create actions routed to a modal, drawer, or dedicated page based on complexity and risk.
- Audit context, ownership, status, permissions, or timestamps where relevant.
- Fast empty and error recovery paths.
- Keyboard and pointer usability.

Avoid:

- Consumer marketing visuals.
- Oversized cards for record management.
- Sticky create forms beside operational tables.
- Hidden critical actions.
- Decorative illustration empty states when users need recovery.

Default density: high. Utility beats expression.

## Editor Or Creator Tool

Primary job: keep the user focused on creating or changing an artifact.

Must include:

- A clear canvas or primary working area.
- Toolbars, inspectors, panels, selection state, undo or redo, save or persistence, and preview where relevant.
- Stable layout while selecting, typing, dragging, resizing, or previewing.
- Clear object state: selected, hovered, locked, invalid, unsaved.

Avoid:

- Instruction panels that steal focus.
- Decorative chrome around the canvas.
- Controls that resize the workspace unexpectedly.
- Hidden persistence or unclear save state.

Default density: medium-high around the canvas, low inside the canvas.

## Checkout Or Pricing

Primary job: help a user choose and complete a commercial action with confidence.

Must include:

- Clear plan, price, billing period, included limits, and primary recommendation.
- Trust signals near risk points.
- Error recovery close to fields.
- Reduced friction for the main path.
- Cancellation, trial, guarantee, or legal details where the business model requires them.

Avoid:

- Confusing plan comparison.
- CTAs that compete at the same hierarchy.
- Hidden fees or ambiguous billing period.
- Unexplained disabled states.
- Visual gimmicks around payment.

Default density: medium. Clarity and trust beat novelty.

## Docs Or Developer Experience

Primary job: help a technical user find, understand, copy, and verify.

Must include:

- Left nav or strong section navigation for multi-page docs.
- Search, examples, code blocks, copy buttons, version or platform context where relevant.
- Clear information architecture and readable measure.
- API warnings, prerequisites, and errors next to examples.

Avoid:

- Marketing layout inside reference docs.
- Decorative code screenshots instead of copyable code.
- Tiny body text or long full-width lines.
- Hidden version compatibility.

Default density: medium-high. Reading and copying should be effortless.

## Mobile UI

Primary job: make the core task reachable and tappable on small screens.

Must include:

- Safe area awareness.
- Touch targets at least 44px.
- Navigation suited to mobile hierarchy.
- Readable 16px body text unless the platform convention requires otherwise.
- Reduced reliance on hover.
- Text scaling and keyboard behavior for forms.

Avoid:

- Desktop sidebars squeezed onto phones.
- Horizontal scroll.
- Tiny icon-only controls without labels.
- Fixed footers that hide content.
- Gesture-only critical actions.

Default density: medium. Prioritize the core job and move secondary detail behind disclosure.

## Game Or Interactive Surface

Primary job: make the play or interaction loop legible and responsive.

Must include:

- The actual playable or interactive surface as the first screen.
- Input feedback, score or progress, reset or restart, and pause where relevant.
- Stable canvas or board dimensions.
- Assets that support the interaction, not generic decoration.

Avoid:

- Landing page before the game.
- Instructions as the main content.
- Static mockups of interaction.
- Canvas or 3D scenes that might render blank without pixel checks.

Default density: task-specific. Prioritize feedback and clear affordances.
