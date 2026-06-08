---
title: "Área — Artístico"
type: area
areas: [artistico]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Espetáculos, repertório, encenação, técnica teatral, direção e elenco dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "artistico") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "artistico") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "artistico") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "artistico") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "artistico") AND (type = "fonte" OR type = "sintese")
```
