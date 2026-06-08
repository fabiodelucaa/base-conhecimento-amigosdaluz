---
title: "Área — Financeiro"
type: area
areas: [financeiro]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Orçamentos, captação de recursos, patrocínio, prestação de contas e fluxo de caixa dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "financeiro") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "financeiro") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "financeiro") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "financeiro") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "financeiro") AND (type = "fonte" OR type = "sintese")
```
