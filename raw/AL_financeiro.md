---
title: "Financeiro — Amigos da Luz"
type: domain-doc
status: to-do
scope: "Contas bancárias, cartões de crédito, receita e despesas da produtora"
updated_by: "Claude"
created: 2026-04-20
updated: 2026-06-06
related:
  - AL_portfolio
  - AL_metricas
tags: [financeiro, contas, cartoes, receita, despesas]
---

# Financeiro

Dados financeiros operacionais — contas, cartões, receita e despesas.

---

## 1. Contas Bancárias

Registro das contas da produtora. Preencher com dados reais de cada conta ativa.

### 1.1 Template de registro

| Campo | Dado |
| --- | --- |
| **Apelido da conta** | *(ex: Conta principal, Conta investimento)* |
| **Banco** | *(nome e número)* |
| **Agência** | *(número + dígito)* |
| **Conta** | *(número + dígito)* |
| **Tipo** | Corrente · Poupança · Investimento · PJ · PF |
| **Titular** | *(razão social ou CPF)* |
| **Saldo atual** | *(data de referência)* |
| **PIX cadastrado** | *(chaves PIX associadas)* |
| **Finalidade** | *(receitas, despesas operacionais, reserva, folha, etc.)* |
| **Observações** | *(limites, tarifas, gerente, acesso)* |

### 1.2 Contas ativas

*(a completar)*

---

## 2. Cartões de Crédito

### 2.1 Template de registro

| Campo | Dado |
| --- | --- |
| **Apelido do cartão** | *(ex: PJ principal, PF pessoal)* |
| **Bandeira** | Visa · Mastercard · Amex · Elo · outros |
| **Emissor** | *(banco ou fintech)* |
| **Titular** | *(razão social ou nome)* |
| **Final do cartão** | *(últimos 4 dígitos)* |
| **Limite** | R$ *(a completar)* |
| **Vencimento da fatura** | *(dia do mês)* |
| **Fechamento da fatura** | *(dia do mês)* |
| **Finalidade** | *(assinaturas, produção, viagens, emergência)* |
| **Observações** | *(anuidade, benefícios, travamentos)* |

### 2.2 Cartões ativos

*(a completar)*

---

## 3. Receita

### 3.1 Fontes recorrentes

| Fonte | Canal/Plataforma | Periodicidade | Observações |
| --- | --- | --- | --- |
| **YouTube AdSense** | Google | Mensal | *(valor médio a completar — ver `docs/AL_metricas.md` para série histórica)* |
| **Membros do canal** | YouTube Memberships | Mensal | *(base ativa a completar)* |
| **Apoiadores / Doações** | *(plataforma a completar)* | Variável | *(campanhas pontuais + recorrência)* |

### 3.2 Fontes transacionais

| Fonte | Canal | Observações |
| --- | --- | --- |
| **Bilheteria de espetáculos** | Casa de Cultura + tours | *(temporadas e médias a completar)* |
| **Locação do espaço** | Casa de Cultura | *(estúdios e salas — ver `docs/AL_casa_cultura.md`)* |
| **Cursos e oficinas** | Oficina de Criação | *(em estruturação)* |
| **Venda de conteúdo pago** | Espiritismo.tv (filmes/webséries) | *(royalties/rateio a completar)* |

### 3.3 Receita consolidada

*(a completar com totais mensais/anuais de exports do Meu Dinheiro + contabilidade)*

---

## 4. Despesas

### 4.1 Estrutura fixa

| Categoria | Itens | Observações |
| --- | --- | --- |
| **Folha e colaboradores** | Pró-labore, pagamentos a elenco, colaboradores, freelas | *(valores a completar)* |
| **Casa de Cultura** | Aluguel, IPTU, condomínio, manutenção, limpeza | Rua Campos da Paz, 105 |
| **Utilidades** | Energia, água, internet, telefonia | *(a completar)* |
| **Impostos e contabilidade** | DAS, FGTS, INSS, honorários Contabilizei | *(a completar)* |

### 4.2 Assinaturas e software

| Serviço | Plano | Vencimento | Valor | Frequência |
| --- | --- | --- | --- | --- |
| **Google Workspace** | Business Standard | *(conferir — estava 08/12/2025)* | R$ 70,00 | Mensal |
| **Wix Studio** | Premium Superior | *(conferir — estava 18/09/2025)* | *(a completar)* | Mensal |
| **Adobe Creative Cloud** | *(a completar)* | *(a completar)* | *(a completar)* | Mensal |
| **mLabs** | *(a completar)* | *(a completar)* | *(a completar)* | Mensal |

### 4.3 Produção

| Categoria | Itens |
| --- | --- |
| **Figurinos e cenografia** | *(médias por produção a completar)* |
| **Locações externas** | *(quando aplicável)* |
| **Transporte e alimentação** | Batidões e viagens de tour |
| **Equipamentos** | Câmeras, áudio, iluminação — aquisição e manutenção |

### 4.4 Marketing e distribuição

| Canal | Investimento | Observações |
| --- | --- | --- |
| **Anúncios pagos** | *(a completar)* | Meta, Google Ads |
| **Produção de divulgação** | *(a completar)* | Cortes verticais, artes |

### 4.5 Despesa consolidada

*(a completar com totais mensais/anuais de exports do Meu Dinheiro + contabilidade)*

---

## 5. Manutenção

- Atualização recomendada: **mensal** com base em exports do Meu Dinheiro e contabilidade
- Revisão de saldos, limites e vencimentos: **trimestral**
