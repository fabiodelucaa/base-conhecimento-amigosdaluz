---
title: "Área — Comunicação"
type: area
areas: [comunicacao]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Marca, redes sociais, imprensa, divulgação e relacionamento com público dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "comunicacao") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "comunicacao") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "comunicacao") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "comunicacao") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "comunicacao") AND (type = "fonte" OR type = "sintese")
```
