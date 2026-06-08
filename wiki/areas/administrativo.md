---
title: "Área — Administrativo"
type: area
areas: [administrativo]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Gestão interna, papéis e responsabilidades, RH, associados, burocracia e organização do dia a dia dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "administrativo") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "administrativo") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "administrativo") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "administrativo") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "administrativo") AND (type = "fonte" OR type = "sintese")
```
