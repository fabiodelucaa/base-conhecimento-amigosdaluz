---
title: "Audiovisual — Amigos da Luz"
slug: AL_audiovisual
type: domain-doc
status: ready
scope: "Canal YouTube, esquetes, séries, lives, filmes e produtos audiovisuais"
updated_by: "Claude"
created: 2026-04-20
updated: 2026-06-06

related:
  - AL_portfolio
  - AL_metricas
  - AL_producao
  - AL_equipe
tags: [audiovisual, youtube, esquetes, lives, filmes]
---

# Amigos da Luz – Audiovisual

---

## Convenções de status

Valores válidos do campo **Status** usado neste documento:

- **Ativo** — produzindo e publicando novos episódios/edições atualmente.
- **Inativo** — sem produção nova, mas acervo segue acessível.
- **Disponível** — produção pontual (com início e fim) lançada e acessível.
- **Encerrado** — fora do ar.

---

## 1. Plataformas

Onde os produtos audiovisuais da Amigos da Luz são distribuídos.

### 1.1 Canal no YouTube

- **URL:** <https://www.youtube.com/channel/UCYatoBlRirWhMrgjTK0b6Pg>
- **Lançamento:** 20/03/2015
- **Catálogo:** 1.165+ vídeos publicados (até 2025)
- **Papel:** plataforma principal. Recebe esquetes, quadros, lives, podcast, filmes e parte das webséries.

*(a completar: mais métricas do canal)*

### 1.2 Site Amigos da Luz

- **URL:** <https://www.amigosdaluz.com>
- **Papel:** vitrine institucional + galeria de vídeos (embeds do YouTube, organizados por categoria) + distribuição de conteúdos pagos avulsos (ex: *60 Minutos para Morrer*).

### 1.3 Instagram

- **Papel:** cortes verticais, bastidores, chamadas para espetáculos e lives. Mesmo conteúdo é espelhado em TikTok e Twitter quando postado.

---

## 2. Produtos recorrentes

Produtos com cadência de produção (quando ativos). Plataforma padrão: **YouTube**.

### 2.1 Esquetes

Vídeos curtos de comédia com temática espírita lançados semanalmente. Principal formato do canal, com narrativas fechadas em 2–5 minutos.

**Séries e Personagens recorrentes**:

- **Daniel e a Mentorona**: Daniel é um espírito que não quer reencarnar de jeito nenhum e sempre inventa uma nova desculpa para escapar desse compromisso, para desespero de sua mentora espiritual, que ele chama carinhosamente de "Mentorona".
- **Preces do Alberto**: Vídeos solo de Fábio de Luca no papel de Alberto, sempre deitado na cama em sua prece noturna, questionando Deus sobre algum aspecto da vida com o qual não concorda, geralmente algo que simplesmente não o favorece.
- **Elisa, a Evoluída**: Série de vídeos na vertical, estilo selfie com celular. Elisa grava como se fossem um "vídeo de inscrição" para o Planeta de Regeneração: ela quer provar à espiritualidade que está pronta para a nova fase da Terra. Na prática, é vaidosa, fútil e vive em atrito com o namorado Arthur, que é sempre quem a está gravando com o celular, e do qual só ouvimos a voz.

Status: **Inativo**

### 2.2 Quadros fixos

| Quadro | Descrição | Status |
| --- | --- | --- |
| **Replay Amigos da Luz** | Compilados de esquetes antigas agrupadas por tema. | Inativo |

### 2.3 Lives

| Live | Descrição | Status |
| --- | --- | --- |
| **Estudo Divertido do Espiritismo** | Estudo semanal do *Livro dos Espíritos* apresentado por **Fábio de Luca**, com co-apresentação em Libras por **Babi**. Interação com o público no chat. | Inativo |
| **Sextou** | Live de jogos e brincadeiras com temática espírita, apresentado por **Fábio de Luca** e **Babi**, uma sexta-feira por mês. Interação com o público no chat. | Inativo |
| **Com convidados** | Live com convidados especiais para debater temas diversos. Fizemos muitas durante a pandemia. | Inativo |

### 2.4 Podcast Amigos da Luz

Videocast gravado no estúdio da Casa de Cultura, com apresentação de **Fábio de Luca**.

Status: **Inativo**

---

## 3. Produtos pontuais

Produções com início e fim definidos. A coluna **Plataforma** indica onde estão disponíveis.

### 3.1 Filmes originais

| Título | Ano | Formato | Descrição | Acesso | Plataforma | Status | Link |
| --- | --- | --- | --- | --- | --- | --- | --- |
| *Uma Dívida de Natal* | 2018 | Média-metragem | Filme espírita de produção independente | Gratuito | YouTube | Disponível | [YouTube](https://www.youtube.com/watch?v=UHdyBFYfJ74) |

### 3.2 Teatro em Vídeo

| Título | Ano | Formato | Acesso | Plataforma | Status | Link |
| --- | --- | --- | --- | --- | --- | --- |
| *Além das Janelas* | 2019 | Websérie | Membros do canal | YouTube | Disponível | [YouTube](https://www.youtube.com/watch?v=hnvowc4gBt0&list=PLaWJN9ikdpvpCEviogufoQh-FtVLnZPLX) |
| *60 Minutos para Morrer* | 2026 | Vídeo único | Pago avulso | Site Amigos da Luz | Disponível | [Site AL](https://www.amigosdaluz.com/assistir/60-minutos-para-morrer-online) |

---

## 4. Acervo local

A pasta [`audiovisual/`](audiovisual/) contém os datasets estruturados do canal, usados para RAG, indexação e análise.

### 4.1 Catálogo bruto dos esquetes

- **[`audiovisual/lista-videos-canal-youtube.json`](audiovisual/lista-videos-canal-youtube.json)** — 250 esquetes da Primeira à Décima Temporada (2015–2024), com metadados completos: elenco, Tema Principal, Temas Secundários, descrições curta e longa, gênero, temporada, ano e flag de uso em compilado. Cobre até a Décima Temporada; não inclui esquetes publicados após 2024.

### 4.2 Índice temático

- **[`audiovisual/indice-esquetes-por-tema.md`](audiovisual/indice-esquetes-por-tema.md)** — agrupamento dos 250 esquetes em 16 clusters doutrinários (Prece, Mediunidade, Reencarnação, Obsessão, Reforma Íntima, Caridade, Causa e Efeito, Desencarne, Família, Deus, Transição, Livre-Arbítrio, Doutrina, Cotidiano, Progresso e Outros). Gerado por `scripts/build_skit_index.py` — regerar sempre que o JSON for atualizado.

### 4.3 Uso por agentes de IA

- Para **busca livre** (ex: "esquetes em que Sidney Grillo interpreta obsessor"), consultar o JSON diretamente.
- Para **navegação por tema** (ex: "todos os esquetes sobre prece"), usar o índice temático.
- Para **citação**: título em caixa alta como no canal, referenciar ordem de publicação e temporada.

---
