---
title: "Arquitetura do Sistema Amigos da Luz"
type: sintese
areas: [institucional, operacional, administrativo, financeiro, comunicacao, comercial, criativo]
status: ativo
created: 2026-07-04
updated: 2026-07-04
sources: ["[[fonte-arquitetura-do-sistema]]"]
tags: [arquitetura, sistema, governanca, estrutura, camadas]
aliases: ["Arquitetura Organizacional", "Estrutura do Sistema AdL"]
---

# Arquitetura do Sistema Amigos da Luz

> **Resumo:** O Amigos da Luz é organizado como um ecossistema criativo em **5 camadas**, cada uma com função distinta. A marca orienta; as unidades de negócio geram valor; os sistemas operacionais servem transversalmente; os canais distribuem; a infraestrutura digital sustenta. Esta arquitetura é o **modelo mental compartilhado** que permite escala, delegação clara e decisões descentralizadas.

---

## Princípios Fundamentais

O sistema se apoia em 5 princípios que **não devem ser quebrados**:

1. **A marca orienta, não executa**
2. **Toda produção acontece dentro de uma unidade clara**
3. **Processos são compartilhados, produtos não**
4. **Financeiro acompanha tudo, mas não manda em tudo**
5. **Só entra no sistema o que será usado**

---

## Mapa de Camadas

### Camada 0 — Marca & Missão

A marca [[amigos-da-luz]] é o núcleo simbólico e filosófico. Define propósito, valores, tom de linguagem, público e critérios estratégicos. **Não executa tarefas**, não gerencia projetos, não produz conteúdo — ela **orienta**.

Perguntas que a marca responde: *"Isso fortalece o Amigos da Luz?"*, *"Isso dialoga com nossa missão espiritual?"*, *"Isso faz sentido para o nosso público?"*

Ver também: [[missao]], [[visao]], [[valores]], [[identidade-de-marca]].

---

### Camada 1 — Unidades de Negócio

Transformam a missão em **produtos concretos**. Cada unidade tem produtos definidos, gera receita e possui indicadores próprios. Compartilham sistemas operacionais entre si.

| Unidade | Produtos principais |
|---|---|
| 🎭 **Teatro** | Circulação com produtores locais, temporadas no [[casa-de-cultura-amigos-da-luz|Espaço AdL]], temporadas em outros teatros, apresentações online |
| 🎬 **Vídeos** | Esquetes, Reels/Shorts, Podcast, Lives — no [[canal-youtube-amigos-da-luz|YouTube]] e demais plataformas |
| 🏠 **Espaço Cultural** | Aluguel de salas e estúdio, eventos de terceiros, atividades próprias |
| 🎓 **Formação** | Cursos, oficinas, workshops dentro e fora do espaço |
| 🤝 **Comunidade & Relacionamento** | Campanhas de apoio, base de apoiadores, mailing, conteúdo exclusivo |

**Indicadores transversais:** cada unidade acompanha frequência/ocupação, receita, custo e resultado financeiro. Vídeos adicionam métricas de audiência e retenção. Comunidade mede engajamento, recorrência e retenção.

Ver também: [[portfolio-de-negocios]], [[publico-alvo]].

---

### Camada 2 — Sistemas Operacionais

Servem a **todas as unidades**. Não pertencem a uma unidade específica.

#### 🔁 Sistema de Produção (Pipeline Único)
Todo produto passa por: **Ideia → Planejamento → Pré-produção → Execução → Pós-produção → KPI/Avaliação**. Vale para vídeos, espetáculos, eventos, cursos e campanhas.

Ver também: [[producao-workflow]].

#### 📣 Sistema de Comunicação
Planejamento editorial, produção de material, distribuição nos canais e análise de métricas. **A comunicação serve às unidades**, não o contrário.

#### 💰 Sistema Financeiro
Orçamento, custos, receitas, resultado por projeto e por unidade. **Informa decisões**, mas não substitui critérios artísticos ou espirituais.

Ver também: [[estrutura-financeira]].

#### 🧠 Sistema de Gestão & Tarefas
Projetos, tarefas, responsáveis, prioridades e acompanhamento. Regra de ouro: **toda tarefa pertence a um projeto**.

#### 🗂️ Sistema de Documentação & Acervo
Roteiros, assets, documentos, fotos e vídeos. Evita perda de memória institucional e retrabalho.

---

### Camada 3 — Canais & Interfaces

Onde o público encontra o projeto. Os canais **não produzem conteúdo** — recebem e distribuem.

- 🌍 **Site** — institucional, agenda, acervo, cursos, vendas
- 📱 **Redes Sociais** — [[canal-youtube-amigos-da-luz|YouTube]], Instagram, TikTok
- 🎟️ **Plataformas de Evento** — bilheteria, streaming, inscrições

---

### Camada 4 — Infraestrutura Digital

Ferramentas que sustentam o sistema: Monday.com (gestão), banco de dados/Supabase, Storage/Drive, ferramentas criativas e IA.

> **Regra:** as ferramentas **se adaptam à arquitetura**, nunca o contrário.

Ver também: [[ferramentas-digitais]].

---

## Regras de Integridade do Sistema

Estas relações **não devem ser quebradas**:

- **Tarefa** → pertence a → **Projeto**
- **Projeto** → pertence a → **Unidade**
- **Unidade** → responde à → **Marca**
- **Financeiro** → acompanha → **Projetos e Unidades**
- **Comunicação** → serve → **todas as Unidades**

Quando respeitadas: o sistema escala, a delegação funciona, decisões ficam claras, o caos diminui.

---

## Relação com outras páginas

- [[fonte-arquitetura-do-sistema]] — fonte original (`raw/arquitetura-do-sistema.md`)
- [[portfolio-de-negocios]] — detalhamento das 6 verticais de negócio
- [[producao-workflow]] — as 7 fases do pipeline de vídeo
- [[ferramentas-digitais]] — pilha de software que implementa a Camada 4
- [[estrutura-financeira]] — como o sistema financeiro opera na prática
- [[identidade-de-marca]] — aprofundamento da Camada 0
- [[amigos-da-luz]] — nó central do projeto
- [[missao]], [[visao]], [[valores]] — os pilares da Marca
