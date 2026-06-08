# Amigos da Luz — Wiki Bootstrap Prompt (for Claude Code)

> **How to use:** Open Claude Code in the repository root (the folder where `raw/` and `wiki/`
> should live) and paste this entire file as your first message. Claude Code will scaffold a
> complete, LLM-maintained knowledge base following the pattern below, then report what it built.
>
> This prompt is written in English on purpose. **Everything you create — `CLAUDE.md`, `README.md`,
> the wiki pages, templates, and all generated outputs — must be written in Brazilian Portuguese
> (PT-BR).** The only English artifact is this bootstrap prompt.

---

## 1. Your role

You are setting up — and from now on maintaining — a **personal/organizational knowledge base**
("the wiki") for **Amigos da Luz**: a Brazilian theatrical group, content producer, and *casa de
cultura* (cultural house). This wiki is the group's **single source of truth**, covering everything
the organization knows across its institutional, administrative, operational, legal, financial,
artistic, creative, historical, spiritual, commercial, and communication life.

It will be consulted and edited by the human operator **and by other AI/LLM agents** that assist the
organization. Treat machine-navigability as a first-class requirement.

### The pattern you are implementing (read carefully)

This is **not** RAG. Instead of re-discovering knowledge from raw documents on every question, you
incrementally **compile and maintain a persistent, interlinked wiki** that sits between the operator
and the raw sources. There are three layers:

1. **`raw/`** — curated source documents (Markdown, PDF, JSON, TXT, DOCX, occasional images). These are
   **immutable**: you read them, you NEVER modify them. This is the source of truth for evidence.
2. **`wiki/`** — a directory of **LLM-generated** Markdown files: summaries, entity pages, concept
   pages, ideas, decisions, meeting notes, source summaries, syntheses, and area hubs. **You own
   this layer entirely.** You create pages, update them when new sources arrive, maintain
   cross-references, and keep everything consistent. The operator reads it; you write it.
3. **`CLAUDE.md`** — the schema: it tells every agent how the wiki is structured, the conventions,
   and the workflows. It is what makes you a disciplined wiki maintainer rather than a generic
   chatbot. You and the operator co-evolve it over time.

The human's job: curate sources, direct analysis, ask good questions. **Your job: everything else** —
summarizing, cross-referencing, filing, and the bookkeeping that keeps a knowledge base useful as it
grows. The operator rarely edits the wiki by hand.

Obsidian is the human's "IDE" for browsing the wiki (graph view, backlinks, Dataview, Marp). Author
everything to be Obsidian-friendly.

---

## 2. Language & audience rules

- **Wiki content, `CLAUDE.md`, `README.md`, templates, page bodies, and outputs: Brazilian
  Portuguese (PT-BR).**
- This bootstrap prompt is the only English document.
- Slugs, filenames, folder names, frontmatter keys, and controlled-vocabulary values stay in
  **lowercase ASCII kebab-case without accents** (e.g. `juridico`, `producao`, `sintese`) so they are
  stable across tools and shells. Human-readable titles inside pages keep proper PT-BR spelling and
  accents.
- Optimize `wiki/index.md` and every page's summary block for quick scanning by other AI agents.

---

## 3. What to build (deliverables checklist)

Create all of the following. Use a TODO list to track them and verify each at the end.

- [ ] Directory structure (Section 4).
- [ ] `CLAUDE.md` — the operating schema, in PT-BR (Section 8 lists required sections).
- [ ] `README.md` — short human onboarding guide, in PT-BR (Section 11).
- [ ] `wiki/index.md` — master catalog, seeded (Section 9).
- [ ] `wiki/log.md` — chronological append-only log, seeded with the bootstrap entry (Section 9).
- [ ] The **11 area hub pages** under `wiki/areas/`, each a Dataview dashboard (Section 10).
- [ ] `_templates/` — one reusable template per page type (Section 7 + 10).
- [ ] `raw/inbox/` and `raw/assets/` (with a `.gitkeep` so they persist).
- [ ] `outputs/` and `scripts/` folders (with `.gitkeep`).
- [ ] Confirm `.gitignore` exists (Section 11); make the initial scaffold commit and push to the
      already-configured GitHub remote (`origin`/`main`).
- [ ] Final self-check + summary to the operator (Section 12).

Do **not** invent fake source documents. Seed structure, hubs, templates, index, and log — but leave
`raw/` empty except for `inbox/` and `assets/`.

---

## 4. Directory structure

```
/  (repository root — you are here)
├── CLAUDE.md                 # the schema / operating brain (PT-BR)
├── README.md                 # human quick-start (PT-BR)
├── .gitignore
├── _templates/               # reusable page templates, one per type
│   ├── area.md
│   ├── entidade.md
│   ├── conceito.md
│   ├── ideia.md
│   ├── decisao.md
│   ├── reuniao.md
│   ├── fonte.md
│   └── sintese.md
├── raw/                      # IMMUTABLE sources — read only, never edit
│   ├── inbox/                # drop zone for new, unprocessed sources
│   │   └── .gitkeep
│   └── assets/               # images / attachments referenced by sources
│       └── .gitkeep
├── wiki/                     # LLM-owned knowledge base
│   ├── index.md              # master catalog, by category
│   ├── log.md                # append-only chronological log
│   ├── areas/                # 11 area hub pages (Dataview dashboards)
│   ├── entidades/            # concrete things (subtype in frontmatter)
│   ├── conceitos/            # abstract ideas, values, methods, doctrine
│   ├── ideias/               # creative vault — seeds not yet promoted
│   ├── decisoes/             # one page per decision (traceable, status)
│   ├── reunioes/             # meeting notes / atas
│   ├── fontes/               # one summary page per ingested raw source
│   └── sinteses/             # cross-cutting overviews & synthesis
├── outputs/                  # generated artifacts (Marp, matplotlib, reports)
│   └── .gitkeep
└── scripts/                  # optional small CLI/python helpers
    └── .gitkeep
```

---

## 5. Canonical schema (controlled vocabularies)

These are **fixed vocabularies**. Record them in `CLAUDE.md`. They are extensible only by deliberate
decision (and a `log.md` entry), never ad hoc.

### 5.1 Areas (11) — `areas:` frontmatter values

`institucional`, `administrativo`, `operacional`, `juridico`, `financeiro`, `artistico`, `criativo`,
`historico`, `espiritual`, `comercial`, `comunicacao`

Short meaning of each (write fuller versions into each area hub):

- **institucional** — identidade, missão, visão, valores, governança, estatuto institucional.
- **administrativo** — gestão interna, papéis, RH, associados, burocracia, organização.
- **operacional** — rotinas, produção executiva, logística, uso do espaço, eventos, bastidores,
  equipamentos, checklists, fornecedores, funcionamento prático da casa.
- **juridico** — contratos, estatuto, direitos autorais, compliance, leis de incentivo (ex.: Lei
  Rouanet, editais), obrigações legais.
- **financeiro** — orçamentos, captação, patrocínio, prestação de contas, fluxo de caixa.
- **artistico** — espetáculos, repertório, encenação, técnica teatral, direção, elenco.
- **criativo** — desenvolvimento de conteúdo, conceitos criativos, processos de criação.
- **historico** — linha do tempo, marcos, memória do grupo, produções passadas.
- **espiritual** — fundamentos espirituais do grupo (ver 5.4), princípios, práticas, referências.
- **comercial** — parcerias comerciais, produtos, serviços, vendas, propostas.
- **comunicacao** — marca, redes sociais, imprensa, divulgação, relacionamento com público.

### 5.2 Page types (8) — `type:` frontmatter value

- **area** — one hub page per area (exactly 11). A Dataview dashboard + curated framing text.
- **entidade** — a concrete thing (people, productions, projects…). Subtype required (5.3).
- **conceito** — an abstract idea, value, method, theme, or doctrinal concept.
- **ideia** — the **creative vault**: a seed not yet promoted to a project/production/concept/etc.
  Ideas may be seeds of esquetes, campanhas, cenas, vídeos, personagens, eventos, quadros, formatos.
- **decisao** — a single recorded decision (date, area(s), status, context, rationale, owners).
- **reuniao** — meeting notes / ata.
- **fonte** — a summary/index page for one ingested raw source (provenance hub).
- **sintese** — a cross-cutting synthesis or overview that connects many pages.

### 5.3 Entity subtypes — `subtype:` for `type: entidade`

Canonical (extensible — add new ones deliberately and note in `CLAUDE.md` + `log.md`):

`pessoa`, `projeto`, `producao`, `documento`, `parceiro`, `evento`, `personagem`, `campanha`,
`roteiro`

(Likely future additions when needed: `espaco`, `produto-servico`, `canal`, `acervo-item`.)

### 5.4 Spiritual context

Amigos da Luz operates within **Espiritismo / Doutrina Espírita (kardecismo)**. In `type: espiritual`
and `type: conceito` (doctrinal) pages, use correct kardecist terminology (e.g. médiuns, mentores
espirituais, Evangelho segundo o Espiritismo, preces, reforma íntima, caridade) and treat it
respectfully and accurately. When a doctrinal claim comes from a source, cite it; when it is the
group's own interpretation/practice, mark it as such.

---

## 6. Frontmatter contract

Every wiki page starts with YAML frontmatter. Required keys marked `*`.

```yaml
---
title: "Nome Legível da Página"          # * PT-BR, with accents
type: entidade                            # * one of the 8 page types
subtype: producao                         # required when type: entidade; optional otherwise
areas: [artistico, operacional]           # * one or more canonical areas (5.1)
status: ativo                             # * ativo | rascunho | revisar | arquivado
created: 2026-06-08                        # * ISO date
updated: 2026-06-08                        # * ISO date — bump on every edit
sources: ["[[fonte-edital-rouanet-2026]]"] # provenance: links to fonte pages (or [] if none yet)
tags: []                                   # free PT-BR tags, kebab-case, no accents
aliases: []                                # alternate names for Obsidian linking
---
```

For `type: ideia`, also support a `maturidade:` key: `semente | em-desenvolvimento | promovida |
arquivada`. When an idea is promoted, create the target page (projeto/producao/conceito/etc.), set the
idea's `maturidade: promovida`, link the two, and note it in the log.

For `type: decisao`, also support `decisao_status:` `proposta | aprovada | rejeitada | revisada` and
an `owners:` list.

Rules:
- `status` and any controlled value must come from the vocabularies above.
- `sources` is how provenance flows: any claim derived from a raw source links to that source's
  `fonte` page, which in turn links to the file in `raw/`.
- Always bump `updated` when you change a page.

---

## 7. Naming, linking & content conventions

- **Filenames**: kebab-case, ASCII, no accents, descriptive. e.g.
  `wiki/entidades/espetaculo-luz-que-nao-se-apaga.md`, `wiki/decisoes/2026-06-08-mudanca-de-sede.md`.
  Prefix `decisao` and `reuniao` files with the ISO date for natural sorting.
- **Links**: use Obsidian wikilinks `[[slug-da-pagina]]` or `[[slug|Texto Exibido]]`. Link
  generously — backlinks and the graph are the cross-cutting structure (areas are not folders here).
- **Every page** has, near the top, a 1–3 sentence **resumo** (summary) that another agent can read
  to decide relevance without opening the whole page. Mirror that one-liner into `index.md`.
- **Cite sources**: factual statements trace back to a `fonte` (via `sources:` and inline
  `([[fonte-...]])`). Distinguish source-backed facts from the group's interpretation and from your
  own inference.
- **Never edit `raw/`.** If a source is wrong or outdated, note it in the wiki, don't touch the raw
  file.
- **Touch many pages per ingest.** A single new source typically updates 10–15 wiki pages (the source
  summary, affected entities/concepts, relevant area hubs via frontmatter, the index, the log).
- **Flag, don't silently overwrite.** When a new source contradicts an existing page, record the
  contradiction explicitly (note both claims + their sources) rather than just replacing text.

---

## 8. `CLAUDE.md` — required contents (write it in PT-BR)

Author a thorough `CLAUDE.md` so any agent (you in a future session, or another LLM) can operate the
wiki correctly. It must contain, in PT-BR:

1. **Visão geral** — what this repo is (the source of truth for Amigos da Luz) and the three-layer
   pattern (raw / wiki / schema). State the "you own the wiki, raw is immutable" rule up front.
2. **Mapa de diretórios** — the tree from Section 4 with a one-line purpose for each folder.
3. **Vocabulário canônico** — the 11 areas (with meanings), 8 page types, and entity subtypes from
   Section 5, plus the spiritual-context note (5.4).
4. **Contrato de frontmatter** — Section 6, verbatim intent.
5. **Convenções** — naming, linking, summaries, citation, "never edit raw/", contradiction handling
   (Section 7).
6. **Workflows** — the full INGEST / QUERY / LINT / IDEA flows (Section 9 below) as numbered,
   followable procedures, plus the output rules (Marp / matplotlib / file-back).
7. **index.md e log.md** — their purpose and exact formats (Section 9), including the parseable log
   line format.
8. **Saídas (outputs)** — where generated artifacts go and when to file them back into the wiki.
9. **Como evoluir o schema** — how to extend vocabularies deliberately (and log it).
10. **Controle de versão** — this vault is already a git repo connected to a **private GitHub remote**
    (`origin`, branch `main`). Do **NOT** run `git init`. After each ingest, each filed-back query, and
    each lint with applied fixes, run `git add -A && git commit && git push`, with a commit message
    mirroring the `log.md` entry (e.g. `ingest | Edital Lei Rouanet 2026`). This keeps every change to
    the source of truth versioned and reversible.

Keep `CLAUDE.md` practical and skimmable: an agent should be able to load it and immediately know how
to ingest a source or answer a query correctly.

---

## 9. Workflows to encode (put these in `CLAUDE.md`)

### 9.1 INGEST — turn a raw source into wiki knowledge

1. The operator drops a file into `raw/inbox/` (or points you at one in `raw/`) and asks to process
   it.
2. Read the source fully. For PDF/DOCX, extract text; for images, view them and describe what's
   relevant. (Note: you cannot read a Markdown file's inline images in one pass — read the text
   first, then view referenced images in `raw/assets/` separately for extra context.)
3. Briefly discuss key takeaways with the operator (unless told to batch silently).
4. Move/keep the source in `raw/` (out of `inbox/` once processed) and create/update a **`fonte`**
   page in `wiki/fontes/` summarizing it, with `sources` pointing to the actual file path.
5. Integrate the knowledge: create or update the affected **entidade / conceito / ideia / sintese**
   pages. Set correct `areas:` so the right area hubs pick them up. Add wikilinks both directions.
6. Flag contradictions with existing pages (record both claims + sources).
7. Update `wiki/index.md` (add new pages with their one-line summary under the right category).
8. Append a `log.md` entry (format in 9.5).
9. Report which pages were touched.

Default to one-source-at-a-time with operator involvement; support batch ingest on request.

### 9.2 QUERY — answer questions against the wiki

1. Read `wiki/index.md` first to locate relevant pages; then read those pages (and their links).
2. Only fall back to `raw/` when the wiki lacks the detail.
3. Answer **with citations** (link the wiki pages and underlying `fonte` pages used).
4. Choose the output form that fits: a chat answer, a new Markdown page, a comparison table, a Marp
   slide deck, or a matplotlib chart (see 9.6).
5. **File good answers back**: if the answer is reusable (an analysis, comparison, synthesis, a
   discovered connection), save it as a `sintese` (or appropriate) page so explorations compound.
   Add it to the index and log.

### 9.3 LINT — periodic health check (report, don't silently mass-edit)

Scan the wiki and report:
- contradictions between pages;
- stale claims superseded by newer sources;
- orphan pages (no inbound links);
- important concepts mentioned but lacking their own page;
- missing cross-references / broken wikilinks;
- frontmatter violations (invalid `type`/`area`/`status`, missing required keys, stale `updated`);
- data gaps fillable via web search;
- candidate new pages and good follow-up questions to investigate.

Present findings as a checklist; apply fixes only with operator confirmation (or as instructed).

### 9.4 IDEA — the creative vault

When the operator has a creative seed (esquete, campanha, cena, vídeo, personagem, evento, quadro,
formato), capture it as a `type: ideia` page with `maturidade: semente`, relevant `areas:`
(usually `criativo` + others), and links to anything it relates to. When an idea matures into a real
project/production/concept, promote it (create the target page, set `maturidade: promovida`, link
both ways, log it). Ideas are first-class — the wiki is also the group's idea vault (baú criativo).

### 9.5 `index.md` and `log.md` formats

**`wiki/index.md`** — content catalog, organized by category. Seed it with section headers for each
page type (Áreas, Entidades, Conceitos, Ideias, Decisões, Reuniões, Fontes, Sínteses), each listing
`- [[slug]] — resumo de uma linha` entries. Keep it current on every ingest/query-file-back.

**`wiki/log.md`** — append-only, newest at bottom. Each entry starts with a consistent, parseable
prefix so `grep "^## \[" log.md | tail -5` works:

```
## [2026-06-08] ingest | Edital Lei Rouanet 2026
- Fonte criada: [[fonte-edital-rouanet-2026]]
- Páginas tocadas: [[projeto-x]], [[area-juridico]], ...
- Notas: contradição com [[orcamento-2025]] sinalizada.
```

Use the entry kinds: `ingest`, `query`, `lint`, `setup`, `schema`. Seed `log.md` with the bootstrap
entry: `## [<today>] setup | Bootstrap da wiki Amigos da Luz`.

### 9.6 Outputs

- Generated artifacts go in `outputs/` (slides as **Marp** Markdown, charts via **matplotlib** using
  helpers in `scripts/`, longer reports as Markdown).
- When an output is valuable beyond the moment, **file it back** into the wiki as a page (and index +
  log it), so explorations always add up.

---

## 10. Area hub pages & templates

### 10.1 Area hub (Dataview dashboard)

Each of the 11 `wiki/areas/<area>.md` pages has `type: area`, a short framing paragraph (what this
area covers for Amigos da Luz), and **Dataview blocks that auto-list pages by the `areas` frontmatter**
— so the operator never maintains these lists by hand. Use this template (adapt headings per area):

````markdown
---
title: "Área — Jurídico"
type: area
areas: [juridico]
status: ativo
created: 2026-06-08
updated: 2026-06-08
tags: []
---

> **Resumo:** Contratos, estatuto, direitos autorais, compliance e leis de incentivo dos Amigos da Luz.

## Entidades nesta área
```dataview
TABLE subtype, status, updated
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "entidade"
SORT updated DESC
```

## Conceitos
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "conceito"
```

## Decisões
```dataview
TABLE decisao_status, created
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "decisao"
SORT created DESC
```

## Ideias
```dataview
TABLE maturidade, updated
FROM "wiki"
WHERE contains(areas, "juridico") AND type = "ideia"
SORT updated DESC
```

## Fontes & Sínteses relacionadas
```dataview
LIST
FROM "wiki"
WHERE contains(areas, "juridico") AND (type = "fonte" OR type = "sintese")
```
````

### 10.2 Page templates (`_templates/`)

Create one template per page type. Each has the correct frontmatter skeleton (Section 6) and a
PT-BR body scaffold. Minimum body sections per type:

- **entidade.md** — Resumo · Descrição · Relações ([[…]]) · Cronologia · Fontes.
- **conceito.md** — Resumo · Definição · Como se aplica nos Amigos da Luz · Relações · Fontes.
- **ideia.md** — Resumo · A semente · Possíveis formatos · Status/maturidade · Relações · Próximos
  passos.
- **decisao.md** — Contexto · Decisão · Alternativas consideradas · Responsáveis · Status ·
  Consequências · Fontes.
- **reuniao.md** — Data/participantes · Pauta · Discussão · Decisões ([[…]]) · Ações/responsáveis.
- **fonte.md** — Metadados da fonte (arquivo em raw/) · Resumo · Pontos-chave · Páginas que ela
  alimenta.
- **sintese.md** — Pergunta/objetivo · Síntese · Evidências ([[…]]) · Conexões descobertas · Lacunas.
- **area.md** — the Dataview hub template from 10.1.

---

## 11. `README.md` and `.gitignore`

**`README.md`** (PT-BR, short) — explain to a human teammate: what this repo is, the raw→wiki→schema
idea in 3 lines, how to add a source (drop into `raw/inbox/` and ask the agent to ingest), how to ask
questions, and the Obsidian setup recommendations:

- Open this folder as an Obsidian vault.
- Enable the **Dataview** plugin (the area hubs depend on it).
- Settings → Files & links → Attachment folder path = `raw/assets/`.
- (Optional) **Obsidian Web Clipper** to save web articles as `.md` into `raw/inbox/`; bind a hotkey
  to "Download attachments for current file" to pull images into `raw/assets/`.
- (Optional) **Marp** plugin to view slide outputs.
- Use the graph view to spot hubs and orphans.

**`.gitignore`** — ignore OS/editor cruft and Obsidian workspace state, keep content:

```
.obsidian/workspace*
.DS_Store
Thumbs.db
outputs/**/*.tmp
__pycache__/
*.pyc
.venv/
```

**Version control (already set up).** This vault is already a git repository connected to a private
GitHub remote (`origin`, branch `main`). Do **NOT** run `git init` and do **NOT** create a new remote.
Just make sure `.gitignore` exists, then commit and push your work. After the scaffold is built, make
the initial commit (`chore: bootstrap da wiki Amigos da Luz`) and push to `origin main`. Thereafter,
follow the per-operation commit convention in Section 8 (commit + push after each ingest / filed-back
query / lint).

---

## 12. Build procedure & self-check

Execute in order:

1. Create the full directory tree (Section 4), with `.gitkeep` files in the empty folders.
2. Write `CLAUDE.md` (Section 8) in PT-BR.
3. Write the 8 templates in `_templates/` (Section 10.2).
4. Write the 11 area hubs in `wiki/areas/` (Section 10.1), one per canonical area.
5. Seed `wiki/index.md` (category headers + the 11 area hubs listed) and `wiki/log.md` (the bootstrap
   entry).
6. Write `README.md`. Ensure `.gitignore` exists (create it from Section 11 if missing). Do **NOT**
   run `git init` — the vault is already a git repo connected to a private GitHub remote.
7. **Self-check** and report:
   - All folders and files from the checklist (Section 3) exist.
   - Every area in the canonical list has exactly one hub page; vocabularies in `CLAUDE.md` match
     Section 5 exactly.
   - All wikilinks you wrote resolve (no broken links among seeded pages).
   - `log.md` has the bootstrap `setup` entry; `index.md` lists the area hubs.
   - Frontmatter on every seeded page is valid against Section 6.
8. **Commit & push**: `git add -A && git commit -m "chore: bootstrap da wiki Amigos da Luz" && git push -u origin main`.
9. Print a concise summary to the operator: what was created, the folder map, and a reminder of the
   three core actions (ingest / query / lint). Then **offer to ingest the first source** — ask the
   operator to drop a file into `raw/inbox/`, or to point you at one, and proceed with the INGEST
   workflow.

Use whatever date is "today" for `created`/`updated` and the bootstrap log entry. Do not fabricate
content for `raw/` — the knowledge base starts empty and grows from real sources.
