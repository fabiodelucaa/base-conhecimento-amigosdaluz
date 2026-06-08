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
