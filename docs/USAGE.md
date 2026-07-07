# Usage Guide

English first. Portuguese follows.

## English

## When To Use It

Use this skill whenever UI quality matters:

1. New landing pages.
2. Existing page redesigns.
3. SaaS app screens.
4. Admin dashboards.
5. Data dashboards.
6. Editors and creator tools.
7. Checkout and pricing flows.
8. Documentation UI.
9. Mobile UI.
10. Visual QA and screenshot reviews.

## Prompt Patterns

```text
Use $ui-anti-slop-codex before implementing this dashboard. Classify the surface, write the Visual Contract, then build.
```

```text
Use $ui-anti-slop-codex to review this existing UI for AI slop. Run the app, capture screenshots, critique the result, and fix it.
```

```text
Use $ui-anti-slop-codex and the repo DESIGN.md. Do not invent a new style system.
```

```text
Use $ui-anti-slop-codex for this landing page. It should feel like developer tools, not generic SaaS.
```

## What Good Output Looks Like

The agent should produce a Visual Contract before major UI work:

```md
Visual Contract
- Surface: Admin dashboard
- User job: Triage and assign inbound leads quickly
- Reference family: Admin Data Tools plus Operational SaaS
- Design source: Existing repo components and inferred reference family
- Density: High
- Layout: Sidebar, saved views, filter bar, sortable lead table, detail panel
- CRUD create mode: Modal for short lead creation so the table remains the primary scanning surface
- Required states: Loading, empty, error, selected, disabled, bulk selected, permission denied
- Forbidden tells: Marketing hero, decorative KPI cards, fake metrics, hidden row actions
- Verification: Desktop and mobile screenshots, table overflow, focus order, contrast
```

## CRUD Creation Flow Rule

For admin, dashboard, platform app, and data table surfaces, the table or list should remain the primary browsing surface. New records should use a modal, drawer, or dedicated page by default. Inline creation should be reserved for tiny single-field additions or spreadsheet-like workflows where inline entry is the core behavior.

Forbidden patterns include sticky "new record" forms beside tables, dashboards split between record management and blank creation fields, and create UI that reduces scan speed or hides row actions.

## Tips For Better Results

1. Include the real business job of the screen.
2. Say whether the screen is public marketing or repeated-use product UI.
3. Provide existing screenshots or brand references when available.
4. For CRUD, say whether creation should happen in a modal, drawer, page, or inline flow.
5. Ask for states explicitly.
6. Ask for visual verification explicitly.

## Português

## Quando Usar

Use esta skill quando qualidade de UI for importante:

1. Landing pages novas.
2. Redesign de páginas existentes.
3. Telas de SaaS.
4. Admin dashboards.
5. Dashboards de dados.
6. Editores e ferramentas de criação.
7. Checkout e pricing.
8. UI de documentação.
9. UI mobile.
10. Revisão visual e screenshots.

## Padrões De Prompt

```text
Use $ui-anti-slop-codex antes de implementar este dashboard. Classifique a superfície, escreva o Visual Contract e depois construa.
```

```text
Use $ui-anti-slop-codex para revisar esta UI existente contra ai-slop. Rode o app, capture screenshots, critique o resultado e corrija.
```

```text
Use $ui-anti-slop-codex e o DESIGN.md do repo. Não invente um sistema visual novo.
```

## Dicas

1. Diga o trabalho real que a tela precisa fazer.
2. Separe landing pública de produto usado todo dia.
3. Envie screenshots ou referências quando tiver.
4. Para CRUD, diga se a criacao deve acontecer em modal, drawer, pagina ou fluxo inline.
5. Peça estados de loading, vazio, erro, selecionado, desabilitado e mobile.
6. Peça verificação visual antes da resposta final.
