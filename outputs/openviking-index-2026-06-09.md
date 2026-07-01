# Indexação OpenViking — Base de Conhecimento Amigos da Luz

Data: 2026-06-09

## Escopo indexado

Recurso OpenViking:

`viking://resources/projects/adl-vault/base-conhecimento-amigosdaluz`

Snapshot local usado para indexação:

`/tmp/openviking-adl-vault-index`

Fonte editorial original:

`/root/vaults/base-conhecimento-amigosdaluz`

Repositório:

`https://github.com/fabiodelucaa/base-conhecimento-amigosdaluz`

## Conteúdo incluído

Snapshot markdown-only com preservação da estrutura de caminhos:

- `README.md`
- `CLAUDE.md`
- `wiki/**`
- `raw/**`
- `_templates/**`
- `.claude/skills/**`
- `OPENVIKING_INDEX_SCOPE.json` com metadados do snapshot

Excluído do snapshot:

- `.git/`
- `.obsidian/`
- `outputs/`
- `scripts/`
- arquivos não textuais/binários/anexos não Markdown

## Contagem

- 181 arquivos `.md`
- 183 arquivos no snapshot total
- tamanho local aproximado: 2.1 MB

## Sensibilidade

A indexação foi autorizada por Fábio em chat. O snapshot inclui páginas e fontes internas de equipe, finanças, contatos e pessoas quando existentes no vault.

Política operacional: OpenViking é índice semântico derivado. O Obsidian segue sendo fonte editorial. Dados pessoais, financeiros e administrativos só devem ser expostos em respostas quando houver necessidade operacional explícita.

## Verificação

Status do recurso após processamento:

- `isLocked: false`
- diretório criado em `viking://resources/projects/adl-vault/base-conhecimento-amigosdaluz`
- subdiretórios visíveis: `CLAUDE`, `_templates`, `raw`, `wiki`, `README`

Buscas verificadas:

- Consulta sobre Fábio de Luca retornou páginas de `wiki/entidades/Fábio_de_Luca` e fontes de equipe.
- Consulta sobre Escola de Artes Espíritas retornou `wiki/ideias/Escola_de_Artes_Espíritas` e sínteses/oficinas relacionadas.
- Leitura direta de `wiki/ideias/Escola_de_Artes_Espíritas/Escola_de_Artes_Espíritas.md` retornou conteúdo correto.
- Leitura direta de `OPENVIKING_INDEX_SCOPE.json` retornou os metadados do snapshot.

## Observação técnica

Durante o processamento, o painel `ov status` mostrou 1 erro em fila de embedding, com o restante processado. As buscas e leituras diretas funcionaram, então a indexação está operacional. Se aparecer lacuna específica em busca futura, reindexar apenas o caminho afetado, não o vault inteiro por padrão.
