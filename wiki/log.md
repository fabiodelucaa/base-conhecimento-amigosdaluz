# Log — Wiki Amigos da Luz

> Log cronológico **append-only**. Mais novo embaixo. Cada entrada começa com
> `## [AAAA-MM-DD] <tipo> | <título>`. Tipos: `ingest`, `query`, `lint`, `ideia`, `setup`, `schema`.
> A mensagem de commit espelha a entrada correspondente (ver [[CLAUDE]] §10).

## [2026-06-08] setup | Bootstrap da wiki Amigos da Luz
- Estrutura criada: `_templates/` (8 templates), `wiki/areas/` (11 hubs), `wiki/{entidades,conceitos,ideias,decisoes,reunioes,fontes,sinteses}/`, `raw/{inbox,assets}/`, `outputs/`, `scripts/`.
- Esquema: `CLAUDE.md` (PT-BR) — vocabulário canônico (11 áreas, 8 tipos de página, subtipos de entidade), contrato de frontmatter e workflows INGEST / QUERY / LINT / IDEA.
- Guia humano: `README.md`. Catálogo: `wiki/index.md`.
- Notas: `raw/` começa vazio (só `inbox/` e `assets/`); a wiki cresce a partir de fontes reais. Skills `obsd-*` (de outro vault, schema diferente) foram realocadas para fora deste vault para evitar conflito.

## [2026-06-08] setup | Skills /adl-ingest e /adl-lint
- Criadas em `.claude/skills/` (escopadas a este vault): operacionalizam os workflows INGEST e LINT do `CLAUDE.md` como comandos `/`.
- `/adl-ingest` cobre todos os formatos (PDF/DOCX/MD/TXT/JSON/imagem) + expansão de fonte já existente + triagem leve de notas do inbox.
- QUERY e IDEA permanecem conversacionais (sem skill dedicada, por escolha de escopo).

## [2026-06-08] schema | Tipo de log "ideia" + commit em captura/promoção de ideia
- Adicionado o tipo de entrada `ideia` ao log (§7.2).
- §10: captura e promoção de ideia agora disparam `commit+push` (fecha lacuna identificada — antes só ingest/query/lint commitavam).
- §6.4 e a cola rápida atualizadas.

## [2026-06-08] setup | Skills renomeadas: /adl-* → /obsd-al-*
- `/adl-ingest` → `/obsd-al-ingest`; `/adl-lint` → `/obsd-al-lint` (conteúdo + diretórios).
- Prefixo unificado `obsd-` (família de wikis Obsidian) com `al` para Amigos da Luz. Sem colisão com as `obsd-*` do vault irmão (escopos de projeto separados).
- Docs atualizadas: README, CLAUDE.md (nota de skills em §6), memória do projeto.

## [2026-06-08] setup | Política de versionamento do .obsidian/
- Escolha do operador: ignorar binários de plugin, versionar config.
- `.gitignore`: adicionados `.obsidian/plugins/` e `.obsidian/cache` (`workspace*` já estava).
- Versionados: `.obsidian/{app,appearance,core-plugins,community-plugins,graph}.json`. Dataview instala-se via README.

## [2026-06-08] setup | obsd-al-lint: relatório por severidade + verificação via web search
- Portadas 2 ideias do lint do vault irmão: modelo de relatório por severidade (🔴🟠🟡🟢) e protocolo de web search para claims `⚠️ não verificado` (verificado / contradito / inconclusivo).

## [2026-06-08] schema | Novos subtipos de entidade: organizacao, lugar
- Motivo: a primeira ingestão (institucional) exigiu modelar a própria produtora e a sede.
- `organizacao` (a produtora / organizações) e `lugar` (espaços físicos — substitui o `espaco` antes previsto). `CLAUDE.md` §3.3 atualizado.

## [2026-06-08] ingest | Institucional Amigos da Luz
- Fonte criada: [[fonte-al-institucional]] (`raw/AL_institucional.md`).
- Páginas criadas: [[amigos-da-luz]], [[casa-de-cultura-amigos-da-luz]], [[fabio-de-luca]], [[fabio-oliviere]], [[humor-espirita]], [[missao]], [[visao]], [[valores]].
- Áreas tocadas (via frontmatter): institucional, juridico, comercial, comunicacao, operacional, espiritual, criativo, artistico, administrativo.
- Stubs a enriquecer: sócios e Casa de Cultura (pendentes de `AL_equipe_dados` / `AL_casa_cultura`).
- Notas: sem contradições (vault estava vazio).

## [2026-06-08] setup | Entidade central renomeada + push delegado ao auto-sync
- `amigos-da-luz-produtora` → [[amigos-da-luz]] — passa a ser referenciada pelo nome mais conhecido (nó central do vault). Título, links, arquivo e índice atualizados.
- Removida a instrução de `git push` do `CLAUDE.md`, README e skills `obsd-al-*`: o **push** fica por conta do **auto-sync do Obsidian (Git plugin)**; o agente só **commita**.

## [2026-06-08] schema | Novo subtipo de entidade: canal
- Motivo: o canal do YouTube (principal vitrine) precisava de tipo próprio. `CLAUDE.md` §3.3 atualizado (`canal` agora canônico).

## [2026-06-08] ingest | Documentos institucionais (lote de 21 fontes)
- 20 páginas `fonte` novas (proveniência) — todos os docs `AL_*` de `raw/inbox/` (institucional já existia).
- Conteúdo criado/enriquecido: 15 pessoas (com dados cadastrais — PII liberada pelo operador para este vault privado), 10 produções, 3 personagens, [[canal-youtube-amigos-da-luz]], [[campanha-sos-amigos-da-luz]], [[espiritismo-tv]]; conceitos [[identidade-de-marca]] e [[identidade-visual]] (+ [[humor-espirita]] enriquecido); 12 sínteses (história, portfólio, público, circulação, produção, oficinas, ferramentas, financeiro, métricas, imprensa, citações, academia); ideia [[escola-de-artes-espiritas]]; hubs [[amigos-da-luz]] e [[casa-de-cultura-amigos-da-luz]] enriquecidos.
- Áreas tocadas: todas as 11.
- Fontes movidas de `raw/inbox/` para `raw/`.
- Notas: transcrições de entrevistas (`imprensa/`) e datasets de esquetes (`audiovisual/`) ficam para a próxima rodada. Vários campos "a completar" nas fontes originais permanecem como tal.

## [2026-06-08] ingest | Entrevistas (14 transcrições integrais)
- 14 páginas `fonte` novas (`fonte-entrevista-*`); transcrições movidas de `raw/inbox/` para `raw/imprensa/`.
- Nova pessoa: [[leopoldo-machado]] (educador espírita; referência formativa de [[fabio-de-luca]] e [[thiago-brito]], via Colégio Leopoldo).
- Enriquecidas: [[cobertura-de-imprensa]] (links das 14 fontes), [[fabio-de-luca]], [[sidney-grillo]].
- Notas: aprofundam/validam o que já havia em [[cobertura-de-imprensa]] e [[citacoes-chave]]. Esquetes individuais e figuras externas citadas (Divaldo, Aroldo, Rossandro) ficaram só mencionados. Datasets de esquetes (`audiovisual/`) ficam para depois.

## [2026-06-08] ingest | Acervo de esquetes + guia de circulação + conceitos doutrinários
- Fontes: [[fonte-acervo-esquetes]] (250 esquetes / 16 clusters), [[fonte-guia-circulacao]] (guia v2.0), [[fonte-info-pack-turne-sc]]. Arquivos movidos p/ `raw/audiovisual/` e `raw/circulacao/`.
- **12 conceitos doutrinários** criados (reforma-intima, obsessao, prece, mediunidade, reencarnacao, caridade, causa-e-efeito, desencarne, livre-arbitrio, transicao-planetaria, progresso-espiritual, deus) — definição ancorada na Codificação + esquetes de cada cluster; **cruzam-referência às páginas do vault irmão `base-conhecimento`** (não copiadas).
- 2 pessoas: [[kelli-sacalem]], [[isabelle-oliveira]] (produção de circulação — o vault irmão tem páginas delas).
- Enriquecidos: [[canal-youtube-amigos-da-luz]] (acervo), [[circulacao-teatral]] (guia/info-pack).
- Notas: os 250 esquetes **não** viraram páginas individuais — acervo consultável via JSON/índice temático, conforme o próprio doc recomenda.

## [2026-06-09] ingest+manutencao | Figuras espíritas de referência + padronização de tags
- 3 entidades (referência externa, subtype pessoa): [[allan-kardec]] (codificador), [[divaldo-franco]] (orador/incentivador do grupo), [[chico-xavier]] (médium) — citadas no vault e agora com página; cross-ref ao vault irmão `base-conhecimento` (Chico ainda sem página lá).
- Índice: nova linha "Referências espíritas externas" em Pessoas.
- **Tags padronizadas** em 14 páginas (só nas linhas `tags:`): `kardecismo`→`espiritismo`, `doutrina`→`doutrina-espirita`.

## [2026-06-09] setup | Indexação OpenViking do vault AdL
- Recurso criado: `viking://resources/projects/adl-vault/base-conhecimento-amigosdaluz`.
- Escopo: snapshot markdown-only de `README.md`, `CLAUDE.md`, `wiki/**`, `raw/**`, `_templates/**` e `.claude/skills/**`; excluídos `.git/`, `.obsidian/`, `outputs/`, `scripts/` e binários.
- Relatório: `outputs/openviking-index-2026-06-09.md`.
- Verificação: recurso destravado (`isLocked: false`), busca semântica e leitura direta retornaram páginas esperadas.
- Nota de sensibilidade: inclui material interno de equipe/financeiro/contatos/pessoas quando presente; expor PII somente com necessidade operacional explícita.

## [2026-06-09] ingest | Acadêmicos (4) + fenômenos mediúnicos (6) + biografia de Leopoldo
- **6 fontes:** [[fonte-tcc-teatro-humor-espiritualidade]] (Fábio Oliviere/Estácio 2025), [[fonte-dissertacao-religiao-humor]] (Grazyelle Fonseca/UERJ 2019), [[fonte-artigo-espiritismo-humor-youtube]] e [[fonte-artigo-espiritismo-vies-do-riso]] (Alanne Almeida & Robéria Nascimento/UEPB 2019), [[fonte-notas-fenomenos-mediunicos]], [[fonte-biografia-leopoldo-machado]].
- **6 conceitos (fenômenos):** [[psicofonia]], [[clarividencia]], [[desdobramento]], [[bicorporeidade]], [[fenomeno-de-transporte]], [[terapia-pela-oracao]] — satélites de [[mediunidade]], com cross-ref ao vault irmão.
- **3 pesquisadoras:** [[grazyelle-de-carvalho-fonseca]], [[alanne-almeida]], [[roberia-nascimento]].
- **Expandidos:** [[humor-espirita]] (fundamentação acadêmica), [[pesquisa-academica]] (catálogo corrigido — a "tese UERJ 2018" e "Religião e humor" eram o **mesmo** trabalho: a dissertação de Grazyelle, 2019), [[leopoldo-machado]] (biografia + precursor do teatro espírita), [[mediunidade]], [[morrendo-e-aprendendo]], [[fabio-oliviere]], [[historia-amigos-da-luz]] (+conflito 2017).
- **Achados:** origem do nome = "Bairro da Luz" (Nova Iguaçu); **fundação 2008** (estreia de *Morrendo e Aprendendo*) confirmada pelo operador, com articulação/ensaios em 2007; conflito com federação espírita (01/10/2017, grupo manteve posição).
- **Arquivos movidos** e renomeados para kebab-ASCII: `raw/academico/` (4), `raw/doutrina/` (6), `raw/historico/` (1).

## [2026-06-09] ingest | Depoimentos do elenco (TCC) nas páginas de pessoas
- Citações do TCC ([[fonte-tcc-teatro-humor-espiritualidade]]) adicionadas a **9 pessoas**: [[carla-guapyassu]], [[alex-moczy]], [[loeni-mazzei]], [[thiago-moreno]], [[ewerton-oliveira]], [[natali-pazete]], [[babi]] (+ alias "Bárbara Barbosa"), [[fabio-de-luca]], [[fabio-oliviere]].
- Fecha a lacuna registrada em [[pesquisa-academica]].

## [2026-06-09] ingest | Espiritismo: gênese histórica + resumo da doutrina (Kardec)
- Fonte: [[fonte-espiritismo-simples-expressao]] (extratos de *O Espiritismo em sua mais simples expressão*).
- **2 conceitos guarda-chuva:** [[espiritismo]] (doutrina + tríplice aspecto, reunindo os conceitos doutrinários) e [[genese-do-espiritismo]] (origem 1848 → Codificação).
- Linkados a [[humor-espirita]] (base doutrinária) e ao índice (novo bloco "Fundamentos").
- Arquivos movidos p/ `raw/doutrina/` (historico-do-espiritismo, resumo-doutrina-espirita), renomeados kebab-ASCII.

## [2026-06-09] lint | Consolidação das citações do TCC em AL_citacoes (remove duplicação)
- Citações do elenco (TCC) movidas das páginas de pessoas → `raw/AL_citacoes.md` (nova §15) para evitar dois lugares com citações. Removida a seção "Depoimento (TCC 2025)" de 9 páginas: [[carla-guapyassu]], [[alex-moczy]], [[thiago-moreno]], [[ewerton-oliveira]], [[natali-pazete]], [[babi]], [[fabio-de-luca]], [[fabio-oliviere]].
- Atualizados [[fonte-al-citacoes]] (escopo ~103) e [[citacoes-chave]] (recorte do elenco). O link [[fonte-tcc-teatro-humor-espiritualidade]] permanece como proveniência nas páginas.
- Nota: editei `raw/AL_citacoes.md` — exceção pontual à imutabilidade de `raw/`, por ser doc-índice mantido por IA (com protocolo de append §17) e a pedido do operador.

## [2026-06-13] ingest | Parceria Centros Vizinhos 2026
- Fonte criada: [[fonte-parceria-centros-vizinhos-2026]] (`raw/parceria-centros-vizinhos-2026.pdf`).
- Páginas criadas: [[parceria-centros-vizinhos]], [[modelo-parceria-centros-vizinhos]].
- Páginas atualizadas: [[amigos-da-luz]], [[casa-de-cultura-amigos-da-luz]], [[portfolio-de-negocios]], [[estrutura-financeira]], [[circulacao-teatral]], [[publico-alvo]], [[humor-espirita]], [[missao]], [[caridade]], [[fabio-oliviere]], [[isabelle-oliveira]], `wiki/index.md`.
- Áreas tocadas: institucional, comercial, operacional, financeiro, espiritual, comunicacao, artistico.
- Notas: o PDF foi movido de `raw/inbox/` para `raw/parceria-centros-vizinhos-2026.pdf`; modelo distinguido da circulação teatral com produtores locais e turnês.

## [2026-06-13] ingest | Dados operacionais da equipe 2026-06-13
- Fonte expandida: [[fonte-al-equipe-dados]] (`raw/dados-operacionais-equipe-2026-06-13.md`).
- Páginas atualizadas: [[fabio-de-luca]], [[fabio-oliviere]], [[alex-moczy]], [[carla-guapyassu]], [[ewerton-oliveira]], [[jean-rizo]], [[loeni-mazzei]], [[mariah-huguenin]], [[natali-pazete]], [[sonia-barbosa]], [[victoria-bastos]], [[babi]], [[thiago-brito]], [[thiago-moreno]].
- Áreas tocadas: administrativo, juridico, artistico, operacional, criativo, comunicacao, institucional.
- Notas: a fonte foi movida de `raw/inbox/`. Por decisão do operador, os dados de `raw/dados-operacionais-equipe-2026-06-13.md` prevalecem sobre registros anteriores em [[fabio-de-luca]], [[loeni-mazzei]] e [[thiago-moreno]]. [[victoria-bastos]] foi mantida como colaboradora por decisão do operador.

## [2026-06-13] lint | Correções pós-health-check
- Corrigidos claims obsoletos sobre produção de circulação e pesquisa acadêmica.
- Atualizados `updated` desatualizados em páginas doutrinárias, figuras espíritas, acervo de esquetes e workflow de produção.
- Backlinks recíprocos recentes adicionados para [[modelo-parceria-centros-vizinhos]], [[producao-workflow]] e relações de equipe.
- Notas: lacunas financeiras, cadastrais e contratuais permanecem pendentes de novas fontes.

## [2026-06-24] decisao | Tom de comunicação com casas espíritas
- Criada a decisão [[tom-comunicacao-casas-espiritas]] para registrar a diretriz de comunicação com centros, casas e instituições espíritas.
- Regra central: valor artístico-cultural e divulgação doutrinária vêm antes; termos comerciais como comissão, venda e repasse podem aparecer de forma clara, mas discreta.
- Índice atualizado em `wiki/index.md`.

## [2026-06-24] modelo | Registro de Parceria Iluminada
- Criado modelo leve para centros/casas/instituições espíritas atuarem como pontos de venda ou divulgação de ingressos: `outputs/modelos/parceria-iluminada/registro-parceria-iluminada-pontos-de-venda.md`.
- Versões geradas: Markdown editável, DOCX editável, HTML e PDF A4 verificado.
- Diretriz aplicada: não usar linguagem de contrato; enfatizar clareza, confiança, ausência de meta obrigatória/custo/exclusividade e garantia de repasse pelos ingressos efetivamente vendidos.

## [2026-06-27] operacional | Prospecção de instituições espíritas — visita de campo 2026-06-28
- Criada a síntese [[prospeccao-instituicoes-espiritas-2026-06-28]] como documento vivo para registrar check-ins, fotos de fachada, horários, contatos, tamanho percebido e observações da primeira visita presencial a 31 instituições.
- Criados artefatos operacionais editáveis em `outputs/parcerias/campo-instituicoes-espiritas/2026-06-28/`: CSV, JSON e pasta `fotos/`.
- Uso previsto: alimentar futuras parcerias da Parceria Iluminada e priorização de relacionamento com casas/instituições próximas à CCAL.
## [2026-06-27] operacional | Métricas de tempo da visita de campo
- Ampliado o cadastro [[prospeccao-instituicoes-espiritas-2026-06-28]] para registrar horário de check-in, tempo desde início, tempo desde a instituição anterior, facilidade de parada, tranquilidade da rota e problemas/desvios.
- Objetivo: produzir avaliação final realista da rota após a primeira ida presencial, comparando estimativa planejada com execução em campo.

## [2026-06-29] operacional | Contatos de leads da Parceria Iluminada
- Atualizados contatos operacionais em `outputs/parcerias/contatos-parceria-iluminada/` com WhatsApp de Ivan (Centro Espírita Samaritanos / Grupo Samaritanos) e Alexandre Coutinho (Grupo Espírita Franciscano Caridade e Amor).
- Complementados [[prospeccao-instituicoes-espiritas-2026-06-28]] e [[parceria-centros-vizinhos]] para manter os próximos passos de follow-up.
