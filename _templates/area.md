---
title: "Área — Nome da Área"
type: area
areas: [nome-da-area]
status: ativo
created: AAAA-MM-DD
updated: AAAA-MM-DD
tags: []
---

> **Resumo:** *(uma frase descrevendo o que esta área cobre para os Amigos da Luz.)*

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "nome-da-area") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "nome-da-area") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "nome-da-area") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "nome-da-area") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "nome-da-area") AND (type = "fonte" OR type = "sintese")
```
