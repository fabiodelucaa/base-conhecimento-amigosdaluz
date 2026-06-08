---
name: adl-ingest
description: Processa uma fonte nova (arquivo em raw/ ou raw/inbox/) e a transforma em páginas estruturadas na wiki dos Amigos da Luz (Obsidian + Claude Code, schema PT-BR). Use sempre que o usuário pedir "ingest", "ingerir", "processar esta fonte", "adicionar este PDF/artigo/ata/contrato/edital/vídeo/imagem à wiki", "/adl-ingest", ou apontar um arquivo em raw/ ou raw/inbox/ e pedir para incorporar ao grafo. Cobre QUALQUER tipo de dado (PDF, DOCX, MD, TXT, JSON, imagem) — a leitura muda por formato, o workflow é o mesmo. Aplica o workflow INGEST descrito em CLAUDE.md.
---

# adl-ingest — Ingestão de fonte nova na wiki Amigos da Luz

## Quando disparar
- `/adl-ingest` ou "ingerir/processar <arquivo>".
- O operador aponta um arquivo em `raw/` ou `raw/inbox/` e pede "adicionar à wiki", "extrair conceitos", "incorporar ao grafo".
- Vale para **qualquer formato** (PDF, DOCX, MD, TXT, JSON, imagem). Só a forma de **ler** (passo 1) muda; o resto é idêntico.

## Contexto de operação (schema)
Roda na raiz do vault Amigos da Luz, que segue o `CLAUDE.md`. **Leia o `CLAUDE.md` antes** — o schema pode ter evoluído. Resumo:

- `raw/` — fontes **imutáveis** (nunca editar; única exceção: mover um arquivo já processado para fora de `raw/inbox/`).
- `wiki/fontes/ entidades/ conceitos/ ideias/ decisoes/ reunioes/ sinteses/` — páginas mantidas por você.
- `wiki/areas/` — 11 hubs Dataview. **NÃO crie páginas aqui**; os hubs se populam sozinhos a partir de `areas:` no frontmatter das outras páginas.
- `wiki/index.md` — catálogo mestre. `wiki/log.md` — log append-only.
- **Áreas (11):** institucional, administrativo, operacional, juridico, financeiro, artistico, criativo, historico, espiritual, comercial, comunicacao.
- **Tipos (8):** area, entidade, conceito, ideia, decisao, reuniao, fonte, sintese. **Subtipos de entidade:** pessoa, projeto, producao, documento, parceiro, evento, personagem, campanha, roteiro.
- Templates em `_templates/`.

## Workflow

### 1. Ler a fonte por completo — varia por formato
- **PDF:** Read com o parâmetro `pages` em blocos de até 20; cubra o documento todo.
- **DOCX / TXT / MD / JSON:** Read sem truncar; arquivos longos, em partes até cobrir tudo.
- **Markdown com imagens inline:** leia o texto primeiro; depois visualize à parte as imagens referenciadas em `raw/assets/`.
- **Imagem (cartaz, flyer, foto de documento):** visualize e descreva o relevante.

O objetivo é sempre o mesmo: entender a fonte o suficiente para resumi-la e conectá-la.

### 2. Fonte nova ou expansão?
Já existe uma página `fonte` para este material em `wiki/fontes/`?
- **Não →** ingestão nova (siga).
- **Sim (novos capítulos/partes/versão expandida) →** **expanda** a `fonte` existente e enriqueça as páginas conectadas; **não duplique**. Atualize o escopo e `updated`.

### 3. Discutir os takeaways com o operador
Antes de escrever, apresente: 3–5 takeaways em PT-BR; a lista de páginas a criar/atualizar (slugs kebab-case ASCII); as `areas:` que serão marcadas. **Aguarde confirmação** (`sim`/`pode`/`ok`), salvo se mandaram processar em lote/silêncio. O operador pode ajustar escopo ou vetar páginas.

### 3b. Nota crua e rasa? (triagem leve)
Se o "arquivo" for uma nota curta de `inbox/` sem densidade para virar fonte própria, **não** crie uma `fonte`: proponha **mesclar** o conteúdo numa página existente ou **descartar**. Decida com o operador.

### 4. Criar (ou expandir) a página `fonte`
`wiki/fontes/<slug>.md`, base no template `_templates/fonte.md`. Frontmatter com `type: fonte`, `areas:` corretas, `sources: ["raw/..."]` (caminho real do arquivo), `status: ativo`, `created/updated`. Corpo: metadados da fonte, resumo (3–5 parágrafos), pontos-chave, "páginas que esta fonte alimenta".

### 5. Integrar — criar/atualizar 10–15 páginas
Em `entidades/` (com `subtype`), `conceitos/`, `ideias/`, `decisoes/`, `reunioes/`, `sinteses/`. Cada uma: frontmatter completo (contrato do `CLAUDE.md` §4) + **resumo no topo** + corpo pelo template. **Incremental:** se já existe página do tema, enriqueça em vez de duplicar.

### 6. Áreas + backlinks bidirecionais
Defina `areas:` em cada página para que os hubs certos a capturem. Para cada `[[wikilink]]`, garanta que o destino existe (ou será criado nesta ingestão) e adicione o link recíproco.

### 7. Sinalizar contradições
Se a fonte contradiz uma página existente, registre **ambas** as afirmações + suas fontes — não sobrescreva em silêncio.

### 8. Proveniência e rigor
Fatos remetem a uma `fonte` (via `sources:` e `([[fonte-...]])` inline). Distinga: **fato com fonte** × **interpretação do grupo** × **sua inferência**. Em conteúdo doutrinário (espírita/kardecista), use terminologia correta e respeitosa. Sem suporte em `raw/` nem web → marque `> ⚠️ não verificado`.

### 9. Mover o arquivo de `inbox/`
Se a fonte veio de `raw/inbox/` e foi processada, mova-a para `raw/` (fora de `inbox/`, mantendo dentro de `raw/`) com `git mv` e atualize `sources:` para o novo caminho. Nunca edite o conteúdo do arquivo.

### 10. Atualizar `wiki/index.md`
Adicione cada página nova na seção da categoria certa: `- [[slug]] — resumo de uma linha`.

### 11. Anexar em `wiki/log.md`
```
## [AAAA-MM-DD] ingest | Título da Fonte
- Fonte criada/expandida: [[fonte-...]]
- Páginas tocadas: [[...]], [[area-...]], ...
- Notas: contradições sinalizadas, escopo, etc.
```

### 12. Commit + push
`git add -A && git commit -m "ingest | <título>" && git push` (a mensagem **espelha** a entrada do log). **Exceção:** se o operador pedir para acumular ("mando mais arquivos, commita depois"), pule o commit; o staging acumula até liberar.

## Regras duras
- **PT-BR** no conteúdo; **kebab-case ASCII sem acentos** em nomes de arquivo, slugs e tags.
- **Nunca editar `raw/`** (só mover arquivo processado para fora de `inbox/`).
- Nunca inventar fatos.
- **Toque muitas páginas (10–15)** — uma fonte rica conecta várias áreas.
- Sinalize contradições, não sobrescreva.
- **Commit E push** ao fim (este vault é versionado no GitHub — difere de vaults que não dão push).

## Por que essas regras existem
O valor do vault está na **confiabilidade do grafo**: backlinks recíprocos evitam ilhas, `areas:` corretas alimentam os hubs Dataview, a proveniência torna tudo rastreável, e commit+push é a âncora reversível. A pausa do passo 3 existe porque o operador conhece o domínio melhor que o agente e pode redirecionar antes do trabalho pesado.
