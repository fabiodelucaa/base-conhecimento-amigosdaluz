---
type: concept
title: Paperclip
created: '2026-07-04T00:00:00.000Z'
sources:
  - 'https://github.com/paperclipai/paperclip'
  - 'https://paperclip.ing'
updated: '2026-07-04T00:00:00.000Z'
ingested_via: 'mcp:put_page'
ingested_at: '2026-07-04T20:56:11.202Z'
source_kind: 'mcp:put_page'
tags:
  - agentes
  - control-plane
  - ferramenta
  - orquestracao
---

# Paperclip

> *"Se OpenClaw é um funcionário, Paperclip é a empresa."*

**Control plane open-source (MIT)** que orquestra times de agentes de IA como se fossem uma empresa. Repositório: [github.com/paperclipai/paperclip](https://github.com/paperclipai/paperclip).

### Funcionalidades

- **BYO Agent** — qualquer agente (Claude Code, Codex, Cursor, bash, OpenClaw, HTTP)
- **Org Chart** — cargos, títulos, linhas de reporte, permissões
- **Goal Alignment** — toda tarefa traça de volta à missão da empresa
- **Heartbeats** — agentes acordam em schedule, revisam trabalho, agem
- **Cost Control** — budget mensal por agente com hard stop
- **Multi-Company** — completo isolamento de dados entre empresas
- **Ticketing** — checkout atômico, sem duplicidade
- **Governança** — aprovações, pause/terminate, audit trail
- **Routines** — tarefas recorrentes com cron, webhook, API triggers
- **Plugins** — workers out-of-process para extensão
- **Company Portability** — export/import de orgs inteiras

### Roadmap (já entregue)

Plugin system, OpenClaw support, companies.sh, AGENTS.md, Skills Manager, Scheduled Routines, Better Budgeting, Agent Reviews & Approvals, Multiple Human Users.

### Em roadmap (⚪)

Cloud/sandbox agents, Artifacts & Work Products, Memory/Knowledge, Enforced Outcomes, MAXIMIZER MODE, Deep Planning.

### Avaliação Osíris (2026-07-04)

Não substitui stack atual (Osíris + Hermes + GBrain + Honcho + Obsidian). Adiciona complexidade que não resolve as dores reais (foco, priorização, TDAH). Promissor para futuro se a operação escalar para 5+ agentes autônomos concorrentes. Vale como referência arquitetural de orquestração.
