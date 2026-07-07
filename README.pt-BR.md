# UI Anti Slop Codex

UI Anti Slop Codex é uma skill para Codex que força o agente a tratar trabalho de UI como trabalho real de produto. Ela classifica a superfície, cria um contrato visual, respeita tokens em `DESIGN.md` e exige revisão visual com screenshot quando possível.

A documentação principal fica em inglês no [README.md](README.md). Este arquivo é o guia secundário em português.

## O Problema

Agentes de código costumam cair em padrões genéricos:

1. Dashboard que parece landing page.
2. Landing page com gradiente abstrato e sem prova de produto.
3. Grid de cards decorativos que não representa um fluxo real.
4. Screenshot falso feito com retângulos em `div`.
5. Layout mobile, tabelas, gráficos e botões sem verificação visual.

Esta skill força uma etapa de intenção visual antes da implementação.

## Instalação

Via skills.sh:

```bash
npx skills add victorbenazzi/ui-anti-slop-codex
```

Via Codex:

```text
$skill-installer install https://github.com/victorbenazzi/ui-anti-slop-codex
```

Instalação manual:

```bash
git clone https://github.com/victorbenazzi/ui-anti-slop-codex.git
mkdir -p ~/.codex/skills
cp -R ui-anti-slop-codex ~/.codex/skills/ui-anti-slop-codex
```

Reinicie o Codex depois de instalar se a sua sessão não recarregar skills automaticamente.

## Como Usar

Chamada explícita:

```text
Use $ui-anti-slop-codex para redesenhar este dashboard.
```

Ou pelo nome:

```text
Rode ui-anti-slop-codex antes de construir esta landing page.
```

A skill também pode ser acionada automaticamente quando a tarefa envolve UI, frontend, dashboard, landing page, app, admin, editor, checkout, docs, screenshot, `DESIGN.md` ou correção de ai-slop.

## Contrato Visual

Para trabalhos relevantes de UI, o agente deve declarar:

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

Isso evita que o agente comece a codar uma interface genérica sem decidir primeiro que tipo de tela está construindo.

## Dicas

1. Diga qual é a superfície. Exemplo: "admin para fila de leads", não só "dashboard moderno".
2. Diga qual é a frequência de uso. Ferramenta diária precisa de densidade e velocidade.
3. Para landing page, peça prova visual real do produto logo no início.
4. Para plataforma, peça tabela, filtros, ações, estados vazios, loading, erro e permissões.
5. Peça screenshot desktop e mobile antes da resposta final.

## Referências Internas

1. [Protocolo DESIGN.md](references/design-md-protocol.md)
2. [Contratos por Superfície](references/surface-contracts.md)
3. [Famílias de Referência](references/reference-families.md)
4. [Verificação Codex](references/codex-verification.md)

## Licença

MIT. Veja [LICENSE](LICENSE).
