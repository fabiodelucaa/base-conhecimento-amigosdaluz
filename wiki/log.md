# Log — Wiki Amigos da Luz

> Log cronológico **append-only**. Mais novo embaixo. Cada entrada começa com
> `## [AAAA-MM-DD] <tipo> | <título>`. Tipos: `ingest`, `query`, `lint`, `setup`, `schema`.
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
