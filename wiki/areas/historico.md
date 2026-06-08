---
title: "Área — Histórico"
type: area
areas: [historico]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Linha do tempo, marcos, memória do grupo e produções passadas dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "historico") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "historico") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "historico") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "historico") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "historico") AND (type = "fonte" OR type = "sintese")
```
