---
title: "Métricas da Live Estudo Divertido — corte 2026-07-20"
type: sintese
areas: [comunicacao, comercial]
status: ativo
created: 2026-07-20
updated: 2026-07-20
sources: ["[[fonte-dossie-live-estudo-divertido-2026-07-20]]"]
tags: [metricas, kpi, live, estudo-divertido, youtube, retencao]
aliases: ["Métricas da Live"]
---

> **Resumo:** Recorte quantitativo da [[live-estudo-divertido-do-espiritismo|Live Estudo Divertido]]
> em 20/07/2026: 146 itens, ~980 mil views acumuladas, 9,2 milhões de minutos assistidos e **13,04%
> de retenção média**. O número que orienta decisão editorial não é a view acumulada — é a distância
> entre 1h11 publicados e 9min24 efetivamente assistidos.

## Pergunta / objetivo

Quanto a Live alcança, como ela retém e quais desses números servem — e quais **não** servem — para
decidir pauta, ritmo e formato.

## Método e distinção entre fontes

Duas superfícies do YouTube foram consultadas em 20/07/2026:

- **YouTube Data API** — métricas públicas atuais de cada item, estatísticas públicas do canal e configuração da Live agendada.
- **YouTube Analytics API** — métricas agregadas para os 146 IDs da playlist, no intervalo 05/04/2016 a 20/07/2026.

> ⚠️ **As duas superfícies divergem por atualização, escopo e definição — e não devem ser somadas
> entre si.** Uma diferença como 980.157 (pública) × 980.078 (Analytics) é normal em snapshots de
> superfícies distintas e defasadas, não sinal de erro.

A consulta **não** retornou agregados confiáveis de impressões nem de espectadores únicos — os
identificadores foram recusados pela API. Por isso esta síntese **não apresenta CTR nem audiência
única**; a fonte correta para esses indicadores é um export do YouTube Studio.

## Alcance acumulado da série

| Indicador | Valor | Observação |
|---|---:|---|
| Itens públicos na playlist | 146 | Nenhum indisponível no recorte |
| Itens com início e fim de live registrados | 132 | Os demais incluem o evento agendado |
| Período do acervo | 05/04/2016 → 20/07/2026 | Último item estava agendado |
| Visualizações públicas | 980.157 | Soma de `viewCount` |
| Visualizações (Analytics) | 980.078 | Superfície distinta — não somar |
| Likes públicos | 81.372 | Soma de `likeCount` |
| Likes (Analytics) | 81.354 | Não somar à pública |
| Comentários públicos | 3.040 | `commentCount` atual |
| Comentários (Analytics) | 51.057 | **Definição histórica de evento** — não é "comentários visíveis hoje" |
| Compartilhamentos (Analytics) | 14.883 | Agregado histórico |
| Tempo assistido estimado | 9.228.661 min | ≈ **153.811,02 horas** |
| Duração média assistida | 564 s | **9min24s** |
| Percentual médio assistido | 13,04% | Agregado da série |
| Inscritos ganhos / perdidos | 3.402 / 1.666 | Atribuídos à série |
| **Saldo líquido de inscritos** | **+1.736** | Ganhos menos perdas |

## Distribuição por episódio

| Indicador público por item | Valor |
|---|---:|
| Média de visualizações | 6.713 |
| Mediana | 5.765 |
| Primeiro quartil | 2.112 |
| Terceiro quartil | 8.291 |
| Máximo | 95.346 |
| Mínimo | 0 |

O **mínimo zero é a transmissão ainda agendada** em 20/07/2026 — não uma Live concluída com
desempenho nulo. Pelo mesmo motivo há um item com duração publicada zero.

**Episódio de maior alcance:** *"DEUS E O INFINITO | Questões 1 a 9 do Livro dos Espíritos"*
(05/04/2016, 95.346 views). Outros destaques históricos: atributos da divindade, princípio das
coisas, espírito e matéria, formação dos mundos e sexo nos Espíritos.

> **Cuidado de leitura:** isso **não** significa que "temas de 2016 são melhores". Esses vídeos
> tiveram muitos anos a mais para acumular visualizações. A comparação útil é por **coorte de
> tempo** — idade do vídeo, tema, formato de título, divulgação e retenção.

## Ciclos de publicação

| Ano | Itens | Views acumuladas no recorte |
|---|---:|---:|
| 2016 | 28 | 442.963 |
| 2017 | 32 | 237.674 |
| 2018 | 11 | 72.651 |
| 2019 | 4 | 33.990 |
| 2020 | 6 | 26.959 |
| **2021** | **0** | **0** |
| 2022 | 6 | 36.424 |
| 2023 | 33 | 87.703 |
| 2024 | 21 | 34.066 |
| 2025 | 2 | 6.295 |
| 2026 (até 20/07) | 3 | 1.432 |

Há **ciclos claros de densidade, pausa e retomada** — 2021 sem nenhum item, 2023 com 33, 2025 com
apenas 2. Isso sustenta a leitura de que a Live precisa ser gerida como **programa recorrente com
calendário**, não como conteúdo eventual. Ver [[live-estudo-divertido-do-espiritismo]].

## Inserção no alcance do canal

No mesmo snapshot o [[canal-youtube-amigos-da-luz|canal]] tinha 46.388.270 views públicas. As
~980 mil da playlist representam ≈ **2,11%** desse total.

> Esse percentual **não mede importância**. Vídeos longos têm consumo, vida útil e função de
> relacionamento diferentes de esquetes. Ele apenas mostra que a série é uma frente específica dentro
> de um canal de grande acervo.

## Conexões descobertas

**1. O verdadeiro indicador editorial é a distância entre duração publicada e duração assistida.**
1h11min23s publicados × 9min24s assistidos (13,04%). Isso é compatível com o padrão de vídeo longo e
com entrada/saída de público em Lives — mas é exatamente o número que pede **análise de retenção por
momento** para orientar abertura, ritmo e cortes. O percentual sozinho não é veredito de sucesso ou
fracasso; precisa ser comparado por tema, época, duração e origem de tráfego.

**2. A série retém mais do que converte em comentário visível.** 51.057 interações históricas de
comentário (Analytics) contra 3.040 comentários públicos hoje — definições diferentes, mas a distância
sugere que boa parte da conversa acontece **no chat ao vivo**, que não sobrevive como comentário no
arquivo. Reforça a tese do dossiê de medir participação, não só visualização.

**3. O saldo de +1.736 inscritos é pequeno diante de 980 mil views** — coerente com um formato de
**relacionamento com a base já fiel**, não de aquisição. Isso é argumento a favor de avaliar a Live
por retorno semanal e vínculo, não por crescimento de canal.

## Lacunas
- **Impressões, CTR e espectadores únicos** — recusados pela superfície de Analytics; obter via export do YouTube Studio.
- **Curva de retenção por minuto** — indispensável para os primeiros 3, 10 e 20 minutos; ainda não coletada.
- **Métricas por edição** — não existe painel comparável edição a edição; é a oportunidade prioritária nº 1 do dossiê. O painel mínimo proposto está em [[operacao-editorial-da-live]].
- **Pico e média de espectadores simultâneos** — não disponíveis neste recorte.
- **Fonte oficial única de reporting** — três superfícies retornam números diferentes para o canal (ver [[metricas-do-canal]]).

## Evidências
- [[fonte-dossie-live-estudo-divertido-2026-07-20]] — todos os números desta página, corte 20/07/2026.
- [[live-estudo-divertido-do-espiritismo]] · [[canal-youtube-amigos-da-luz]] · [[metricas-do-canal]] · [[operacao-editorial-da-live]]
