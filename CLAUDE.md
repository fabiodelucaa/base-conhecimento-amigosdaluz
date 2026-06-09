# CLAUDE.md — Esquema operacional da wiki Amigos da Luz

> Este arquivo é o **cérebro operacional** da base de conhecimento. Qualquer agente (humano ou
> LLM) que for ler, consultar ou editar esta wiki deve carregar este arquivo primeiro e seguir o
> que está aqui. Ele e o operador humano co-evoluem o esquema ao longo do tempo.

**Idioma:** todo o conteúdo da wiki, deste arquivo e dos outputs é em **português do Brasil
(PT-BR)**. Apenas slugs, nomes de arquivo, nomes de pasta, chaves de frontmatter e valores de
vocabulário controlado ficam em **minúsculas ASCII, kebab-case, sem acentos** (ex.: `juridico`,
`producao`, `sintese`). Títulos legíveis dentro das páginas mantêm grafia e acentos corretos.

---

## 1. Visão geral

Esta é a **base de conhecimento dos Amigos da Luz** — grupo teatral, produtora de conteúdo e casa
de cultura. É a **fonte única da verdade** da organização, cobrindo tudo o que o grupo sabe nas
dimensões institucional, administrativa, operacional, jurídica, financeira, artística, criativa,
histórica, espiritual, comercial e de comunicação.

A wiki será consultada e editada pelo operador humano **e por outros agentes de IA**. A
navegabilidade por máquina é requisito de primeira classe.

### O padrão (não é RAG)

Em vez de redescobrir conhecimento a partir dos documentos brutos a cada pergunta, nós
**compilamos e mantemos incrementalmente uma wiki persistente e interligada** entre o operador e
as fontes. Há **três camadas**:

1. **`raw/`** — documentos-fonte curados (Markdown, PDF, JSON, TXT, DOCX, imagens). São
   **imutáveis**: você os lê, **nunca os modifica**. É a base de evidência.
2. **`wiki/`** — arquivos Markdown **gerados por LLM**: resumos, páginas de entidade/conceito,
   ideias, decisões, atas, resumos de fontes, sínteses e hubs de área. **Esta camada é sua por
   inteiro.** Você cria páginas, atualiza quando chegam fontes novas, mantém referências cruzadas
   e a consistência. O operador lê; você escreve.
3. **`CLAUDE.md`** — o esquema (este arquivo): convenções e workflows. É o que faz de você um
   mantenedor disciplinado, não um chatbot genérico.

> **Regra de ouro:** **a wiki é sua, o `raw/` é imutável.** O trabalho do humano é curar fontes,
> dirigir a análise e fazer boas perguntas. **Seu trabalho é todo o resto** — resumir, cruzar
> referências, arquivar e a contabilidade que mantém a base útil à medida que cresce.

O operador usa o **Obsidian** como "IDE" para navegar a wiki (graph view, backlinks, Dataview,
Marp). Escreva tudo de forma Obsidian-friendly.

---

## 2. Mapa de diretórios

```
/  (raiz do repositório / vault)
├── CLAUDE.md                 # este esquema (PT-BR)
├── README.md                 # guia rápido para humanos (PT-BR)
├── .gitignore
├── _templates/               # templates reutilizáveis, um por tipo de página
│   ├── area.md  entidade.md  conceito.md  ideia.md
│   ├── decisao.md  reuniao.md  fonte.md  sintese.md
├── raw/                      # FONTES IMUTÁVEIS — só leitura, nunca editar
│   ├── inbox/                # zona de entrada de fontes novas, não processadas
│   └── assets/               # imagens / anexos referenciados pelas fontes
├── wiki/                     # base de conhecimento, propriedade do LLM
│   ├── index.md              # catálogo mestre, por categoria
│   ├── log.md                # log cronológico append-only
│   ├── areas/                # 11 hubs de área (dashboards Dataview)
│   ├── entidades/            # coisas concretas (subtype no frontmatter)
│   ├── conceitos/            # ideias abstratas, valores, métodos, doutrina
│   ├── ideias/               # baú criativo — sementes ainda não promovidas
│   ├── decisoes/             # uma página por decisão (rastreável, com status)
│   ├── reunioes/             # atas / notas de reunião
│   ├── fontes/               # um resumo por fonte ingerida (hub de proveniência)
│   └── sinteses/             # visões transversais e sínteses
├── outputs/                  # artefatos gerados (Marp, matplotlib, relatórios)
└── scripts/                  # pequenos helpers CLI/python (opcional)
```

---

## 3. Vocabulário canônico

Vocabulários **fixos**. Extensíveis apenas por decisão deliberada (com entrada em `log.md`), nunca
ad hoc. Ver Seção 9 (Como evoluir o esquema).

### 3.1 Áreas (11) — valores de `areas:`

`institucional`, `administrativo`, `operacional`, `juridico`, `financeiro`, `artistico`,
`criativo`, `historico`, `espiritual`, `comercial`, `comunicacao`

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
- **espiritual** — fundamentos espirituais do grupo (ver 3.4), princípios, práticas, referências.
- **comercial** — parcerias comerciais, produtos, serviços, vendas, propostas.
- **comunicacao** — marca, redes sociais, imprensa, divulgação, relacionamento com público.

### 3.2 Tipos de página (8) — valor de `type:`

- **area** — um hub por área (exatamente 11). Dashboard Dataview + texto de enquadramento.
- **entidade** — coisa concreta (pessoas, produções, projetos…). Exige `subtype` (3.3).
- **conceito** — ideia abstrata, valor, método, tema ou conceito doutrinário.
- **ideia** — o **baú criativo**: semente ainda não promovida a projeto/produção/conceito etc.
  Ideias podem ser sementes de esquetes, campanhas, cenas, vídeos, personagens, eventos, quadros,
  formatos.
- **decisao** — uma decisão registrada (data, área(s), status, contexto, justificativa, donos).
- **reuniao** — ata / notas de reunião.
- **fonte** — página-resumo/índice de uma fonte ingerida (hub de proveniência).
- **sintese** — síntese ou visão transversal que conecta muitas páginas.

### 3.3 Subtipos de entidade — `subtype:` para `type: entidade`

Canônicos (extensíveis com deliberação): `pessoa`, `projeto`, `producao`, `documento`, `parceiro`,
`evento`, `personagem`, `campanha`, `roteiro`, `organizacao`, `lugar`, `canal`.

Adições futuras prováveis (quando necessárias): `produto-servico`, `acervo-item`.

### 3.4 Contexto espiritual

Os Amigos da Luz operam no campo do **Espiritismo / Doutrina Espírita (kardecismo)**. Em páginas
`type: espiritual` e em conceitos doutrinários, use a terminologia kardecista correta (ex.:
médiuns, mentores espirituais, *O Evangelho segundo o Espiritismo*, preces, reforma íntima,
caridade) e trate o tema com respeito e precisão. Quando uma afirmação doutrinária vier de uma
fonte, cite-a; quando for interpretação/prática do próprio grupo, **marque como tal**.

---

## 4. Contrato de frontmatter

Toda página da wiki começa com frontmatter YAML. Chaves obrigatórias marcadas com `*`.

```yaml
---
title: "Nome Legível da Página"          # * PT-BR, com acentos
type: entidade                            # * um dos 8 tipos de página
subtype: producao                         # obrigatório se type: entidade; opcional nos demais
areas: [artistico, operacional]           # * uma ou mais áreas canônicas (3.1)
status: ativo                             # * ativo | rascunho | revisar | arquivado
created: 2026-06-08                       # * data ISO
updated: 2026-06-08                       # * data ISO — atualizar a cada edição
sources: ["[[fonte-edital-rouanet-2026]]"]# proveniência: links p/ páginas fonte (ou [] se nenhuma)
tags: []                                  # tags livres PT-BR, kebab-case, sem acentos
aliases: []                               # nomes alternativos para linkagem no Obsidian
---
```

**Chaves extras por tipo:**

- `type: ideia` → `maturidade:` = `semente | em-desenvolvimento | promovida | arquivada`.
- `type: decisao` → `decisao_status:` = `proposta | aprovada | rejeitada | revisada`, e `owners:`
  (lista de responsáveis).

**Regras:**

- `status` e qualquer valor controlado vêm dos vocabulários acima.
- `sources` é como a proveniência flui: qualquer afirmação derivada de uma fonte bruta linka para
  a página `fonte` correspondente, que por sua vez aponta para o arquivo em `raw/`.
- **Sempre atualize `updated`** ao alterar uma página.

---

## 5. Convenções

- **Nomes de arquivo:** kebab-case, ASCII, sem acentos, descritivos. Ex.:
  `wiki/entidades/espetaculo-luz-que-nao-se-apaga.md`,
  `wiki/decisoes/2026-06-08-mudanca-de-sede.md`. Prefixe arquivos `decisao` e `reuniao` com a data
  ISO para ordenação natural.
- **Links:** use wikilinks do Obsidian `[[slug-da-pagina]]` ou `[[slug|Texto Exibido]]`. Linke
  generosamente — backlinks e o grafo são a estrutura transversal (áreas **não** são pastas aqui).
- **Resumo:** toda página tem, perto do topo, um **resumo** de 1–3 frases que outro agente lê para
  decidir relevância sem abrir a página inteira. Espelhe essa frase única no `index.md`.
- **Citação:** afirmações factuais remetem a uma `fonte` (via `sources:` e `([[fonte-...]])`
  inline). Distinga fatos com suporte de fonte da **interpretação do grupo** e da **sua própria
  inferência**.
- **Nunca edite `raw/`.** Se uma fonte estiver errada ou desatualizada, registre isso na wiki — não
  toque no arquivo bruto. (Única exceção: mover um arquivo já processado de `raw/inbox/` para outro
  lugar dentro de `raw/`.)
- **Toque muitas páginas por ingestão.** Uma fonte nova tipicamente atualiza **10–15 páginas** (o
  resumo da fonte, entidades/conceitos afetados, hubs de área relevantes via frontmatter, o índice,
  o log).
- **Sinalize, não sobrescreva em silêncio.** Quando uma fonte nova contradiz uma página existente,
  **registre a contradição explicitamente** (anote ambas as afirmações + suas fontes) em vez de
  apenas substituir o texto.

---

## 6. Workflows

> **Skills:** os fluxos INGEST e LINT têm comandos dedicados — `/obsd-al-ingest` e `/obsd-al-lint`
> (em `.claude/skills/`, versionados junto com o vault). **QUERY** e **IDEA** são
> **conversacionais** (sem skill): é só pedir em linguagem natural que o agente segue o workflow.

### 6.1 INGEST — transformar uma fonte bruta em conhecimento

1. O operador coloca um arquivo em `raw/inbox/` (ou aponta um arquivo em `raw/`) e pede para
   processar.
2. **Leia a fonte por completo.** Para PDF/DOCX, extraia o texto; para imagens, visualize-as e
   descreva o relevante. (Você não lê as imagens inline de um Markdown numa única passada — leia o
   texto primeiro, depois visualize as imagens referenciadas em `raw/assets/` à parte.)
3. **Discuta os pontos-chave com o operador** (a menos que mandem processar em lote, em silêncio).
4. Mantenha/mova a fonte em `raw/` (saindo de `inbox/` depois de processada) e crie/atualize uma
   página **`fonte`** em `wiki/fontes/`, com `sources` apontando para o caminho real do arquivo.
5. **Integre o conhecimento:** crie ou atualize as páginas **entidade / conceito / ideia / sintese**
   afetadas. Defina `areas:` corretamente para que os hubs certos as capturem. Adicione wikilinks
   nos dois sentidos.
6. **Sinalize contradições** com páginas existentes (registre ambas as afirmações + fontes).
7. Atualize `wiki/index.md` (adicione páginas novas com o resumo de uma linha na categoria certa).
8. **Anexe uma entrada em `log.md`** (formato em 7.2).
9. Reporte quais páginas foram tocadas.

> Padrão: uma fonte por vez, com participação do operador. Suporte ingestão em lote quando pedido.

### 6.2 QUERY — responder perguntas usando a wiki

1. Leia `wiki/index.md` primeiro para localizar páginas relevantes; depois leia essas páginas (e
   seus links).
2. Só recorra a `raw/` quando a wiki não tiver o detalhe.
3. Responda **com citações** (linke as páginas da wiki e as páginas `fonte` usadas).
4. Escolha a forma de saída adequada: resposta no chat, página Markdown nova, tabela comparativa,
   deck Marp ou gráfico matplotlib (ver 6.5).
5. **Arquive boas respostas:** se a resposta for reutilizável (análise, comparação, síntese,
   conexão descoberta), salve como página `sintese` (ou tipo adequado) para que as explorações se
   acumulem. Adicione ao índice e ao log.

### 6.3 LINT — health-check periódico (relate, não edite em massa)

Escaneie a wiki e relate:

- contradições entre páginas;
- afirmações obsoletas superadas por fontes mais novas;
- páginas órfãs (sem links de entrada);
- conceitos importantes mencionados, mas sem página própria;
- referências cruzadas faltando / wikilinks quebrados;
- violações de frontmatter (`type`/`area`/`status` inválidos, chaves obrigatórias faltando,
  `updated` desatualizado);
- lacunas de dados preenchíveis por busca na web;
- páginas candidatas e boas perguntas de acompanhamento.

Apresente como **checklist**; aplique correções só com confirmação do operador (ou conforme
instruído).

### 6.4 IDEA — o baú criativo

Quando o operador tiver uma semente criativa (esquete, campanha, cena, vídeo, personagem, evento,
quadro, formato), capture-a como página `type: ideia` com `maturidade: semente`, `areas:`
relevantes (geralmente `criativo` + outras) e links para o que ela se relaciona. Quando uma ideia
amadurece em projeto/produção/conceito real, **promova-a**: crie a página-alvo, defina
`maturidade: promovida`, linke nos dois sentidos. **Tanto capturar quanto promover uma ideia mexem
na wiki → registre no `log.md` (tipo `ideia`) e faça `commit`** (ver §10). Ideias são de
primeira classe.

### 6.5 Saídas (outputs)

- Artefatos gerados vão em `outputs/`: slides como **Marp** (Markdown), gráficos via **matplotlib**
  (helpers em `scripts/`), relatórios longos como Markdown.
- Quando um output tem valor além do momento, **arquive-o de volta** na wiki como página (e
  índice + log), para que as explorações sempre somem.

---

## 7. `index.md` e `log.md`

### 7.1 `wiki/index.md`

Catálogo de conteúdo, organizado por categoria. Tem um cabeçalho de seção por tipo de página
(Áreas, Entidades, Conceitos, Ideias, Decisões, Reuniões, Fontes, Sínteses), cada um listando
entradas `- [[slug]] — resumo de uma linha`. Mantenha-o atual a cada ingestão / arquivamento de
query.

### 7.2 `wiki/log.md`

Append-only, **mais novo embaixo**. Cada entrada começa com um prefixo consistente e parseável,
para que `grep "^## \[" log.md | tail -5` funcione:

```
## [2026-06-08] ingest | Edital Lei Rouanet 2026
- Fonte criada: [[fonte-edital-rouanet-2026]]
- Páginas tocadas: [[projeto-x]], [[area-juridico]], ...
- Notas: contradição com [[orcamento-2025]] sinalizada.
```

**Tipos de entrada:** `ingest`, `query`, `lint`, `ideia`, `setup`, `schema`.

---

## 8. Saídas — onde e quando arquivar de volta

- Tudo que é gerado vai em `outputs/`.
- Sempre que um artefato (deck, gráfico, relatório, análise) tiver valor duradouro, **crie uma
  página na wiki** que o referencie/resuma, adicione ao `index.md` e registre no `log.md`. Assim
  nenhuma exploração se perde.

---

## 9. Como evoluir o esquema

Os vocabulários (áreas, tipos, subtipos, valores de status/maturidade) são **fixos**. Para
estendê-los:

1. Decida deliberadamente que a extensão é necessária (não improvise).
2. Atualize a seção correspondente **deste `CLAUDE.md`**.
3. Registre a mudança no `log.md` com tipo `schema`:
   ```
   ## [AAAA-MM-DD] schema | Novo subtype de entidade: espaco
   - Motivo: passamos a catalogar espaços físicos.
   ```
4. Só então use o novo valor em páginas.

Adições mais prováveis: subtipos de entidade `produto-servico`, `canal`, `acervo-item`.

---

## 10. Controle de versão

Este vault **já é um repositório git** conectado a um **remote privado no GitHub** (`origin`,
branch `main`).

- **NÃO** rode `git init`, **NÃO** crie um novo remote e **NÃO** dê `git push` — o **push é responsabilidade do auto-sync do Obsidian (Git plugin)**, que sincroniza sozinho em intervalos. O agente só **commita**.
- Após **cada ingestão**, cada **query arquivada**, cada **lint com correções aplicadas** e cada
  **captura/promoção de ideia**, rode:
  ```
  git add -A && git commit -m "<mensagem>"
  ```
- A **mensagem de commit espelha a entrada do `log.md`** (ex.: `ingest | Edital Lei Rouanet 2026`,
  `query | comparação de orçamentos`, `lint | correções de wikilinks`, `ideia | esquete do porteiro`).

Isso mantém cada mudança da fonte da verdade versionada e reversível.

---

## Resumo operacional (cola rápida)

- **Idioma:** PT-BR no conteúdo; slugs/chaves/vocabulário em kebab-case ASCII sem acentos.
- **raw/ é imutável; wiki/ é sua.**
- **INGEST:** ler fonte → discutir → criar `fonte` → atualizar 10–15 páginas → sinalizar
  contradições → índice → log → commit (push: auto-sync do Obsidian).
- **QUERY:** índice → páginas → (raw/ se preciso) → responder com citações → oferecer arquivar
  síntese.
- **LINT:** escanear → relatar checklist → corrigir só com OK.
- **IDEA:** capturar semente → `log` (`ideia`) + commit → promover quando amadurecer.
- **Toda página:** frontmatter válido + resumo no topo + wikilinks bidirecionais + `updated`
  atualizado.
