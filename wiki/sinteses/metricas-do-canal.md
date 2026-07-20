---
title: "Métricas do Canal"
type: sintese
areas: [comunicacao, comercial]
status: ativo
created: 2026-06-08
updated: 2026-07-20
sources: ["[[fonte-al-metricas]]", "[[fonte-dossie-live-estudo-divertido-2026-07-20]]"]
tags: [metricas, kpi, youtube, receita]
aliases: []
---

> **Resumo:** Leitura dos KPIs do [[canal-youtube-amigos-da-luz|canal]] (2015–2025) — crescimento, picos, monetização e sinais de atrito.

## Consolidado (2015–2025)
45,4M visualizações · 435.215 inscritos líquidos · 1.165 vídeos · ~R$ 175.334 de receita estimada · RPM médio R$ 3,86.

## ⚠️ Dado não confiável — tempo de exibição acumulado

O arquivo histórico `raw/AL_metricas.md` registra **2.447.221.274** como tempo de exibição acumulado,
rotulado em **"horas"**. Esse rótulo **não fecha** com o resto da série:

> 45,4M views × duração média de 3min13 ≈ **2,44 milhões de horas** — não 2,44 **bilhões**.
> A ordem de grandeza do rótulo está errada por ~1000×.

O valor deve ser tratado como **não confiável até reconciliação da unidade e da origem do export** —
provavelmente minutos rotulados como horas, mas isso não está confirmado. **Não usar em propostas,
prestação de contas ou material de patrocínio** enquanto não for reconciliado.
([[fonte-dossie-live-estudo-divertido-2026-07-20]])

## ⚠️ Três superfícies, três números

No corte de 20/07/2026 o mesmo canal retornou:

| Superfície | Views | Inscritos | Vídeos |
|---|---:|---:|---:|
| `raw/AL_metricas.md` (06/06/2026) | 45.446.089 | 435.215 | 1.165 (total) |
| YouTube Data API (público) | 46.388.270 | 445.000 | 751 (públicos) |
| YouTube Analytics API | 46.863.706 | — | — |

As diferenças são **parcialmente explicáveis** por data, escopo (público × total) e definição de
superfície — mas não integralmente. **Falta uma fonte oficial única de reporting** para decisões
executivas. Enquanto ela não existir, toda citação de número do canal deve vir com data e superfície
explícitas.

## Série anual (destaques)
- **2015:** 3,7M views, 49 vídeos, +86k inscritos (lançamento).
- **2018:** pico de produção — 305 vídeos; 6,0M views.
- **2020:** pico de visualizações — 7,3M (pandemia, 276 vídeos).
- **2021→2024:** queda de 5,3M → 1,7M views.

## Leituras-chave
- **Monetização:** RPM cresceu de R$0,16 (2015) a R$10,59 (2023) — maturação do público; **queda abrupta em 2024** (R$1,13) a investigar.
- **Fidelidade:** duração média subiu (2:24 → 3:50); porém razão perda/ganho de inscritos chegou a ~100% em 2024 — **atrito alto**.
- Possível saturação do formato esquete / mudança de algoritmo a partir de 2022.

## Recorte por formato
- **Lives:** a série [[live-estudo-divertido-do-espiritismo|Estudo Divertido]] acumula ~980 mil views ≈ **2,11%** das views públicas do canal, com retenção média de 13,04%. Detalhe em [[metricas-live-estudo-divertido-2026-07-20]] — inclui o alerta de que vídeo longo tem consumo, vida útil e função de relacionamento diferentes de esquete, e não deve ser comparado no mesmo critério.

## Conexões
- Perfil da base: [[publico-alvo]]. Receita no contexto geral: [[estrutura-financeira]]. Motiva a [[campanha-sos-amigos-da-luz]].

## Lacunas
- Atualização trimestral via YouTube Studio; investigar a queda de RPM 2024.
- **Reconciliar a unidade** do tempo de exibição acumulado (ver alerta acima) — pendência aberta.
- **Definir a fonte oficial única de reporting** do canal, encerrando a divergência de três superfícies.
- **Impressões, CTR e espectadores únicos** não são obteníveis pela API de Analytics usada (identificadores recusados) — exigem export do YouTube Studio.

## Fontes
- [[fonte-al-metricas]] · [[fonte-dossie-live-estudo-divertido-2026-07-20]]
