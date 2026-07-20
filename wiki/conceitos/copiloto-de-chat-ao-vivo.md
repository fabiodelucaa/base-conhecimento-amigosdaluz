---
title: "Copiloto de Chat ao Vivo"
type: conceito
areas: [operacional, comunicacao]
status: ativo
created: 2026-07-20
updated: 2026-07-20
sources: ["[[fonte-dossie-live-estudo-divertido-2026-07-20]]"]
tags: [chat, automacao, moderacao, live, seguranca, metodo]
aliases: ["Copiloto de Chat", "Modelo seguro de copiloto de chat"]
---

> **Resumo:** Método do grupo para assistir o chat ao vivo com automação **sem** transformar
> frequência de fala em sinônimo de acolhimento. Separa leitura, decisão e envio em três
> responsabilidades distintas, e adota o **silêncio como padrão**.

## Definição

Modelo de operação assistida do chat de uma transmissão ao vivo, formulado para a
[[live-estudo-divertido-do-espiritismo|Live Estudo Divertido]]. Sua premissa é que a capacidade
técnica de falar no chat **não é autorização para falar** — a publicação e qualquer moderação exigem
uma porta humana de segurança.

*(Procedimento interno do grupo, não doutrina espírita.)*

## As três responsabilidades separadas

| Camada | Função | Pode publicar? |
|---|---|---|
| **1. Coletor** | Identifica a Live correta, a fase, mensagens novas, mensagens da equipe e o cursor. | **Não** — somente leitura |
| **2. Decisão editorial** | Recebe contexto recente e escolhe uma intervenção rara ou `SILENT`. | Não — apenas propõe |
| **3. Guard de envio** | Único caminho de publicação. | Sim — **e só** com Live ativa e autorização explícita de [[fabio-de-luca]] |

A separação é o mecanismo: nenhuma camada acumula "ler + decidir + publicar", de modo que uma falha
de julgamento não vira uma mensagem publicada.

## Princípios inegociáveis

- **O silêncio é o padrão.** `SILENT` é uma resposta legítima e esperada.
- **Atividade humana da equipe tem precedência** — se a equipe está respondendo, o copiloto não intervém.
- **Pergunta direta técnica ou logística vem antes de pergunta temática.**
- **Chegada não justifica saudação.** A entrada de um espectador não dispara boas-vindas automáticas.
- Boas-vindas, quando houver, exigem autorização, **identificador estável** e **teto pequeno**.
- **Não banir, silenciar ou aplicar timeout automaticamente** na primeira operação restaurada.
- Ao fim: remover a operação temporária, **desarmar** e **auditar** as mensagens efetivamente enviadas.

## Regra editorial que o sustenta

> **Ler frequentemente não obriga falar frequentemente.** Silêncio é a ação correta quando não existe
> motivo humano e útil para intervir.

Essa regra vale igualmente para operação humana e assistida — é diretriz de chat da Live, não apenas
de automação.

## Como se aplica nos Amigos da Luz

O ambiente dispõe de acesso autenticado ao YouTube com permissões de leitura, Analytics e operações de
canal, incluindo localizar o chat, ler e monitorar mensagens, **enviar**, **excluir** e aplicar
banimento ou timeout.

> **A existência técnica desses comandos não é autorização para usá-los.** O dossiê registra isso de
> forma explícita.

**Estado no corte de 20/07/2026:** não há job persistente dedicado ao chat da Live na automação
recorrente. Isso é **coerente com a política**, não uma lacuna: o modelo prevê criar uma operação
**temporária, pausada e desarmada** para cada transmissão, em vez de deixar um robô recorrente pronto
para falar sem contexto.

## Risco que o método endereça

O dossiê nomeia o risco diretamente: **automatizar chat como se frequência de fala fosse sinônimo de
acolhimento**. Um chat cheio de mensagens automáticas produz ruído e simula presença; o modelo
inverte o default para que a intervenção precise se justificar.

Conecta-se ao princípio editorial mais amplo da Live de **não oferecer orientação individualizada** —
para perguntas pessoais no chat, acolher e devolver o tema ao apresentador, sem orientação médica,
psicológica, jurídica ou mediúnica.

## Métricas de auditoria

Cada intervenção do copiloto, se ativado, é registrada com **motivo e `message_id`** no painel por
edição — ver [[operacao-editorial-da-live]]. A auditoria final responde: o que gerou conversa boa, o
que foi ruído e quando a equipe humana precisou assumir.

## Relações
- [[live-estudo-divertido-do-espiritismo]] — formato onde o método se aplica.
- [[operacao-editorial-da-live]] — painel e auditoria por edição.
- [[fabio-de-luca]] — autoridade que arma o guard de envio.
- [[canal-youtube-amigos-da-luz]] — plataforma. · [[ferramentas-digitais]] — pilha técnica do grupo.

## Fontes
- [[fonte-dossie-live-estudo-divertido-2026-07-20]]
