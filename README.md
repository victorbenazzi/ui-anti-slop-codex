# UI Anti Slop Codex

[![skills.sh](https://skills.sh/b/victorbenazzi/ui-anti-slop-codex)](https://skills.sh/victorbenazzi/ui-anti-slop-codex)

UI Anti Slop Codex is a Codex skill that makes OpenAI coding agents handle UI work like product design work. It forces surface classification, a clear visual contract, `DESIGN.md` token discipline, and screenshot-based verification before delivery.

Primary language: English.

Secondary language: Portuguese. See [README.pt-BR.md](README.pt-BR.md).

## What It Solves

Codex and other agents often default to generic UI patterns:

1. Dashboard screens that look like marketing pages.
2. Landing pages with abstract gradients and no product proof.
3. Decorative card grids with no workflow.
4. Fake screenshots built from styled rectangles.
5. Buttons, charts, tables, and mobile layouts that were never inspected in a browser.

This skill makes the agent slow down just enough to classify the surface, pick the right reference family, implement against a contract, and visually verify the result.

## What The Skill Does

When active, the skill requires the agent to:

1. Inspect existing repo UI before making visual decisions.
2. Classify the surface: landing page, platform app, dashboard, admin, editor, checkout, docs, mobile UI, game, or interactive surface.
3. Load the matching surface contract and reference family.
4. Declare a compact Visual Contract before substantial UI edits.
5. Prefer existing `DESIGN.md`, design tokens, components, fonts, and icon libraries.
6. Keep CRUD browsing and CRUD creation as separate interaction modes unless inline entry is the product behavior.
7. Implement the UI against the contract.
8. Run browser or screenshot verification when feasible.
9. Fix visible issues before the final response.

## Install

### Install With skills.sh

```bash
npx skills add victorbenazzi/ui-anti-slop-codex
```

Restart your agent after installation if your environment does not reload skills automatically.

### Install In Codex With skill-installer

```text
$skill-installer install https://github.com/victorbenazzi/ui-anti-slop-codex
```

Restart Codex after installation.

### Manual Install

Clone the repository and copy it into your skills directory:

```bash
git clone https://github.com/victorbenazzi/ui-anti-slop-codex.git
mkdir -p ~/.codex/skills
cp -R ui-anti-slop-codex ~/.codex/skills/ui-anti-slop-codex
```

Some Codex setups also read personal skills from `~/.agents/skills`:

```bash
mkdir -p ~/.agents/skills
cp -R ui-anti-slop-codex ~/.agents/skills/ui-anti-slop-codex
```

## How To Use

Invoke it explicitly:

```text
Use $ui-anti-slop-codex to redesign this dashboard.
```

Or name it in a prompt:

```text
Run ui-anti-slop-codex before building this landing page.
```

It can also be invoked automatically when the task involves UI design, frontend implementation, dashboards, landing pages, app UI, admin panels, editors, checkout flows, docs UI, visual QA, screenshots, `DESIGN.md`, or anti-slop cleanup.

## Example Prompts

```text
Use $ui-anti-slop-codex to build a landing page for a developer API monitoring tool.
```

```text
Use $ui-anti-slop-codex to make this CRM admin dashboard feel like a real operational tool.
```

```text
Use $ui-anti-slop-codex to review this UI for generic AI patterns, then fix the visible issues.
```

```text
Use $ui-anti-slop-codex and the existing DESIGN.md before touching the frontend.
```

## The Visual Contract

For substantial UI work, the agent should declare this before editing:

```md
Visual Contract
- Surface:
- User job:
- Reference family:
- Design source:
- Density:
- Layout:
- CRUD create mode:
- Required states:
- Forbidden tells:
- Verification:
```

This makes the intended UI direction inspectable before the agent starts writing code.

## CRUD Creation Flow Rule

For admin, dashboard, platform app, and data table surfaces, the skill treats browsing records and creating records as different interaction modes.

Default behavior:

1. Keep the table or list as the primary surface for inspection and row actions.
2. Use a modal, drawer, or dedicated create page for new records.
3. Use a modal for short creation flows that can be completed without losing table context.
4. Use a dedicated page for long, multi-step, permission-heavy, or high-risk creation flows.
5. Use inline creation only for tiny single-field additions or spreadsheet-like workflows.

The Visual Contract must explicitly state whether create happens inline, in a modal, in a drawer, or on a dedicated page, with a short justification based on task complexity and record-scanning needs.

## DESIGN.md Support

The skill treats `DESIGN.md` as a persistent design contract when one exists. It tells the agent to:

1. Read `DESIGN.md` before choosing colors, type, spacing, radius, shadows, components, or motion.
2. Treat frontmatter tokens as normative implementation values.
3. Treat markdown prose as rationale and usage guidance.
4. Create or update `DESIGN.md` only for greenfield UI, broad redesigns, multi-page systems, or explicit user requests.
5. Run the Google Labs linter when `DESIGN.md` changes:

```bash
npx @google/design.md lint DESIGN.md
```

## Tips

1. Give the agent a real surface, not only a vibe. Prefer "admin dashboard for a sales lead queue" over "make it modern".
2. Name a reference family when you know the target. For example, "Linear settings density with Stripe docs clarity".
3. Ask for screenshot verification explicitly when the environment can run a browser.
4. Do not let the agent skip required states. Empty, loading, error, disabled, selected, hover, focus, and mobile states are part of the UI.
5. For landing pages, provide real product screenshots or tell the agent to generate visual assets. Fake product UI is a core AI tell.

## Included References

The skill ships with four reference files:

1. [DESIGN.md Protocol](references/design-md-protocol.md)
2. [Surface Contracts](references/surface-contracts.md)
3. [Reference Families](references/reference-families.md)
4. [Codex Verification](references/codex-verification.md)

## Compatibility

Designed for OpenAI Codex and future OpenAI coding models. It uses the open `SKILL.md` format, so other agents that support agent skills can read it too.

## Repository Page On skills.sh

This repository includes [skills.sh.json](skills.sh.json). According to the skills.sh docs, repository pages are picked up after the repository is seen by the telemetry service, usually after someone installs from the repo with the `skills` CLI.

After publishing, run:

```bash
npx skills add victorbenazzi/ui-anti-slop-codex
```

Then check:

```text
https://skills.sh/victorbenazzi/ui-anti-slop-codex
```

## License

MIT. See [LICENSE](LICENSE).
