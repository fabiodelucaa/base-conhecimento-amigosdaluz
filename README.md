# Amigos da Luz — Base de Conhecimento (Wiki)

Fonte única da verdade do grupo **Amigos da Luz** (teatro, produtora de conteúdo e casa de cultura),
em todas as suas dimensões: institucional, administrativa, operacional, jurídica, financeira,
artística, criativa, histórica, espiritual, comercial e de comunicação.

## A ideia em 3 linhas

1. **`raw/`** — fontes brutas e curadas (PDF, artigos, atas, contratos…). **Imutáveis**: nunca se edita.
2. **`wiki/`** — páginas em Markdown geradas e mantidas pelo agente (IA): resumos, conceitos,
   entidades, ideias, decisões, sínteses e hubs de área, tudo interligado por wikilinks.
3. **`CLAUDE.md`** — o esquema: convenções e workflows que fazem o agente manter a wiki com
   disciplina. **Não é RAG** — em vez de reprocessar tudo a cada pergunta, compilamos conhecimento
   persistente e interligado.

> Você (humano) **cura fontes, dirige a análise e faz boas perguntas**. O agente faz **o resto** —
> resumir, cruzar referências, arquivar e manter a consistência.

## Como adicionar uma fonte (INGEST)

1. Solte o arquivo em **`raw/inbox/`** (ou aponte um arquivo já em `raw/`).
2. Peça ao agente: *"ingere esta fonte"* (ou `/obsd-al-ingest`, se as skills da família estiverem
   ativas neste vault).
3. O agente lê, discute os pontos-chave, cria a página `fonte`, atualiza 10–15 páginas conectadas,
   sinaliza contradições, atualiza o índice/log e faz commit e push.

## Como perguntar (QUERY)

Pergunte em linguagem natural: *"o que a wiki diz sobre X?"*, *"compare X e Y segundo nossas fontes"*.
O agente navega o índice e o grafo, responde **com citações** e oferece salvar boas análises como
páginas `sintese`.

## Manutenção (LINT)

Peça um *health-check* periódico (`/obsd-al-lint`): o agente relata contradições, páginas órfãs, wikilinks quebrados e
frontmatter inválido — e só corrige com sua aprovação.

## Setup no Obsidian (recomendado)

- Abra esta pasta como **vault** no Obsidian.
- Ative o plugin **Dataview** (os hubs de área dependem dele).
- **Configurações → Arquivos e links → Pasta de anexos** = `raw/assets/`.
- *(Opcional)* **Obsidian Web Clipper** para salvar artigos da web como `.md` em `raw/inbox/`;
  vincule um atalho a *"Download attachments for current file"* para puxar imagens a `raw/assets/`.
- *(Opcional)* plugin **Marp** para visualizar os slides gerados em `outputs/`.
- Use o **graph view** para enxergar hubs e páginas órfãs.

## Controle de versão

Este vault já é um repositório git conectado a um **remote privado no GitHub** (`origin`, `main`).
O agente faz `git add -A ; git commit ; git push` após cada ingestão, query arquivada e lint com correções,
mantendo tudo versionado e reversível.

---

*Idioma da wiki: português do Brasil. Nomes de arquivo, slugs e tags em kebab-case ASCII sem acentos.
Detalhes do esquema: ver `CLAUDE.md`.*
