# Installation Guide

This guide is in English first. Portuguese follows.

## English

### Install With skills.sh

```bash
npx skills add victorbenazzi/ui-anti-slop-codex
```

This is the recommended public install path. It also helps skills.sh discover and rank the repository through anonymous aggregate telemetry.

### Install With Codex skill-installer

```text
$skill-installer install https://github.com/victorbenazzi/ui-anti-slop-codex
```

Restart Codex after installation.

### Manual Install

```bash
git clone https://github.com/victorbenazzi/ui-anti-slop-codex.git
mkdir -p ~/.codex/skills
cp -R ui-anti-slop-codex ~/.codex/skills/ui-anti-slop-codex
```

Optional personal agents path:

```bash
mkdir -p ~/.agents/skills
cp -R ui-anti-slop-codex ~/.agents/skills/ui-anti-slop-codex
```

### Verify

Ask Codex:

```text
Use $ui-anti-slop-codex to create a Visual Contract for a CRM admin dashboard. Do not implement yet.
```

You should see a Visual Contract with surface, user job, reference family, density, layout, states, forbidden tells, and verification.

## Português

### Instalar via skills.sh

```bash
npx skills add victorbenazzi/ui-anti-slop-codex
```

Este é o caminho recomendado para instalação pública. Ele também ajuda o skills.sh a descobrir e ranquear o repositório por telemetria agregada e anônima.

### Instalar via skill-installer no Codex

```text
$skill-installer install https://github.com/victorbenazzi/ui-anti-slop-codex
```

Reinicie o Codex depois da instalação.

### Instalação manual

```bash
git clone https://github.com/victorbenazzi/ui-anti-slop-codex.git
mkdir -p ~/.codex/skills
cp -R ui-anti-slop-codex ~/.codex/skills/ui-anti-slop-codex
```

Caminho pessoal opcional:

```bash
mkdir -p ~/.agents/skills
cp -R ui-anti-slop-codex ~/.agents/skills/ui-anti-slop-codex
```

### Verificar

Peça ao Codex:

```text
Use $ui-anti-slop-codex para criar um Visual Contract para um dashboard admin de CRM. Ainda não implemente.
```
