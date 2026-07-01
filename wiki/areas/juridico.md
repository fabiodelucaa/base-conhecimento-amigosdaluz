---
title: "Área — Jurídico"
type: area
areas: [juridico]
status: ativo
created: 2026-06-08
updated: 2026-07-01
tags: []
---

> **Resumo:** Contratos, estatuto, direitos autorais, compliance, leis de incentivo (Lei Rouanet, editais) e obrigações legais dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "juridico") AND (type = "fonte" OR type = "sintese")
```
