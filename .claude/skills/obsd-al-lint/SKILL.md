---
name: obsd-al-lint
description: Health-check completo da wiki dos Amigos da Luz (Obsidian + Claude Code, schema PT-BR) — detecta contradições, páginas órfãs, wikilinks quebrados, frontmatter inválido (type/area/status fora do vocabulário, chaves obrigatórias faltando, updated desatualizado), slugs/tags com acento, conceitos sem página própria, índice desatualizado e lacunas — e produz RELATÓRIO sem auto-corrigir. Use sempre que o usuário pedir "/obsd-al-lint", "lint da wiki", "health-check do vault", "revisar integridade", "escanear erros", ou auditar o estado geral da base. Aplica o workflow LINT descrito em CLAUDE.md.
---

# obsd-al-lint — Health-check da wiki Amigos da Luz

## Quando disparar
- `/obsd-al-lint`, "lint da wiki", "health-check do vault", "revisar integridade", "escanear erros".
- Após ingestões grandes, em manutenção periódica, ou antes de uma entrega/publicação.

**Não confundir:** corrigir/refazer **uma** página específica apontada pelo operador é trabalho direto, não um lint completo.

## Contexto (a régua é o vocabulário canônico)
Leia o `CLAUDE.md` §3–4 antes. A validação se baseia em:
- **Áreas (11):** institucional, administrativo, operacional, juridico, financeiro, artistico, criativo, historico, espiritual, comercial, comunicacao.
- **Tipos (8):** area, entidade, conceito, ideia, decisao, reuniao, fonte, sintese.
- **Subtipos de entidade:** pessoa, projeto, producao, documento, parceiro, evento, personagem, campanha, roteiro.
- **status:** ativo | rascunho | revisar | arquivado. **maturidade** (ideia): semente | em-desenvolvimento | promovida | arquivada. **decisao_status:** proposta | aprovada | rejeitada | revisada.
- Chaves obrigatórias: `title, type, areas, status, created, updated` (+ `subtype` em entidade).

## O que escanear e relatar
Escaneie `wiki/**` e produza um **relatório** (não edite em massa). Categorias:

1. **Contradições** entre páginas (afirmações conflitantes + suas fontes).
2. **Claims obsoletos** superados por fontes mais novas.
3. **Páginas órfãs** (sem links de entrada).
4. **Conceitos importantes** mencionados, mas sem página própria.
5. **Wikilinks quebrados** / referências cruzadas faltando / backlinks não recíprocos.
6. **Frontmatter inválido:** `type` fora dos 8; valor em `areas` fora das 11; `status`/`maturidade`/`decisao_status` fora do vocabulário; chave obrigatória faltando; `subtype` ausente em `type: entidade`; `updated` mais antigo que a última edição real.
7. **Slugs/tags fora do padrão** (com acento ou não-kebab-case ASCII).
8. **Áreas/hubs:** páginas com `areas:` que não batem com nenhuma das 11; hub de área com frontmatter ou bloco Dataview quebrado.
9. **`index.md` desatualizado:** páginas que existem mas não estão no índice (ou entradas do índice sem página).
10. **Lacunas** preenchíveis por web search; **páginas candidatas** e boas perguntas de acompanhamento.

## Como reportar
**Checklist por categoria**, com caminho do arquivo e descrição do problema. Priorize (alto / médio / baixo). **Não corrija nada ainda.**

## Correções (só com OK)
Aplique correções **somente com confirmação** do operador (ou se ele já disse "corrige o que achar"). Ao aplicar:
- Atualize `updated` nas páginas tocadas.
- Anexe em `wiki/log.md`: `## [AAAA-MM-DD] lint | <resumo do que foi corrigido>`.
- `git add -A && git commit -m "lint | <resumo>" && git push` (espelha o log). **Se foi só relatório, sem correções → sem commit.**

## Regras duras
- **Relatório primeiro, sempre.** Nunca edição em massa silenciosa.
- O vocabulário canônico do `CLAUDE.md` é a régua.
- **Nunca editar `raw/`.**

## Por que essas regras existem
Wikis crescem por acreção e degradam em silêncio: links apodrecem, frontmatter diverge, páginas viram ilhas. O lint é o raio-x periódico. O relatório-antes-de-corrigir mantém o operador no controle e evita "consertos" que destroem nuance — por exemplo, apagar uma contradição que na verdade era um achado real a investigar.
