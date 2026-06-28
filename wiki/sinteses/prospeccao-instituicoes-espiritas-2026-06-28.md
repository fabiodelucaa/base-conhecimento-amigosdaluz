---
title: "Prospecção de instituições espíritas — visita de campo 2026-06-28"
type: sintese
areas: [comercial, comunicacao, operacional, espiritual]
status: ativo
created: 2026-06-27
updated: 2026-06-28
sources: []
tags: [parceria-iluminada, centros-espiritas, campo, prospeccao, rio-de-janeiro]
---

# Prospecção de instituições espíritas — visita de campo 2026-06-28

> **Resumo:** documento vivo para registrar a primeira ida presencial às instituições próximas à [[casa-de-cultura-amigos-da-luz|Casa de Cultura Amigos da Luz]], dentro da estratégia de [[tom-comunicacao-casas-espiritas|comunicação com casas espíritas]] e da Parceria Iluminada.

## Objetivo

Catalogar instituições visitadas, material entregue, fachada, dias/horários de funcionamento, telefones, tamanho percebido e observações de campo para futuras parcerias de divulgação, venda de ingressos, agenda compartilhada e aproximação comunitária.

## Critério de tamanho

- **PP** — porta pequena, estrutura mínima, pouca sinalização ou funcionamento restrito.
- **P** — casa pequena, movimento/localização discreta.
- **M** — instituição média, fachada identificável, potencial regular de público.
- **G** — casa grande, boa estrutura, maior fluxo ou programação visível.
- **GG** — instituição de referência, grande fachada/estrutura, alto potencial de parceria.

## Arquivos operacionais

- Planilha CSV editável: `outputs/parcerias/campo-instituicoes-espiritas/2026-06-28/visitas-instituicoes-espiritas-2026-06-28.csv`
- JSON estruturado para atualização por agente: `outputs/parcerias/campo-instituicoes-espiritas/2026-06-28/visitas-instituicoes-espiritas-2026-06-28.json`
- Pasta de fotos de fachada: `outputs/parcerias/campo-instituicoes-espiritas/2026-06-28/fotos`

## Como atualizar por WhatsApp

Quando Fábio mandar check-ins durante a rota, atualizar a linha correspondente usando:

- `status_visita`: `visitado`, `fechado`, `não encontrado`, `pular`, `retornar`
- `visitado_em`: data/hora local quando disponível
- `checkin_recebido_em`: horário da mensagem/áudio de check-in no WhatsApp
- `tempo_desde_inicio_min`: minutos desde o primeiro check-in/saída registrada
- `tempo_desde_anterior_min`: minutos desde o check-in da instituição anterior
- `tempo_parada_min`: quando for possível inferir, tempo entre chegada/entrega/saída
- `facilidade_parada_carro`: `fácil`, `média`, `difícil`, `não deu para parar`
- `rota_tranquila`: `sim`, `não`, `parcial`
- `desvio_ou_problema_rota`: trânsito, erro de mapa, rua ruim, retorno, obra, lugar difícil de achar
- `tamanho`: `PP`, `P`, `M`, `G`, `GG`
- `material_entregue`: `sim`, `caixa correio`, `não`, `parcial`
- `foto_fachada`: caminho do arquivo recebido/salvo
- `dias_horarios`, `telefone`, `whatsapp`, `email`, `site_instagram`, `pessoa_contato`
- `receptividade`: observação qualitativa curta
- `potencial_parceria`: `baixo`, `médio`, `alto`, `prioritário`
- `proximo_passo`: ação prática posterior
- `observacoes`: qualquer contexto livre


## Avaliação final da rota

Ao encerrar a visita de campo, consolidar:

- horário de início e horário de fim;
- tempo total porta a porta;
- tempo total estimado de direção versus tempo real percebido;
- média de minutos por instituição;
- gargalos: estacionamento/parada rápida, ruas, retornos, trânsito, instituições difíceis de localizar;
- instituições que merecem retorno com conversa mais longa;
- instituições que podem virar contato prioritário;
- ajustes recomendados para uma próxima rota semelhante.

Durante o campo, cada check-in enviado logo após a entrega deve ser usado como marcador temporal para calcular `tempo_desde_anterior_min` e estimar o ritmo real da operação.

## Checklist pós-check-in

Após cada check-in de Fábio, perguntar apenas o que estiver faltando, nessa ordem de prioridade:

1. **Entrega:** entregou em mãos, deixou na caixa/correio/porta, estava fechado, ou não encontrou?
2. **Tamanho:** PP, P, M, G ou GG?
3. **Parada/rota:** foi fácil parar? A rota até aqui foi tranquila ou teve perrengue?
4. **Contato visível:** tinha telefone, WhatsApp, Instagram, e-mail ou site em placa/fachada?
5. **Funcionamento:** havia dias e horários visíveis?
6. **Pessoa/receptividade:** falou com alguém? Nome/cargo? Foi receptivo, neutro ou ruim?
7. **Foto:** tem foto de fachada/placa para anexar ou ler depois?
8. **Próximo passo:** merece retorno, WhatsApp, visita com conversa, ou só cadastro?

Regra operacional: não bombardear Fábio se ele estiver dirigindo a operação. Se o check-in vier muito completo, responder só confirmando registro. Se vier incompleto, fazer no máximo 2 perguntas curtas por vez.

## Rota de campo

| # | ID | Instituição | Bairro | Status | Tam. | Material | Obs. |
|---:|---|---|---|---|---|---|---|
| 1 | 01 | Centro Espírita Discípulos de Jesus | Tijuca | fechado | M | caixa correio | Foto/placa recebida; quinta 15h e 19h30; tel. (21) 2569-8052; fácil parar; rota tranquila |
| 2 | 03 | Fraternidade Espírita Amor e Paz | Tijuca | fechado | G | em mãos | Entregue a mulher sem nome, aparentava trabalhadora da casa, chegando/abrindo; horários no portão: 2ª/4ª/5ª/6ª 13h-19h, sáb 08h-12h30; fácil estacionar; rota ótima |
| 3 | 02 | Agremiação Espírita Francisco de Paula | Tijuca | fechado | G |  | Foto/fachada recebida; sem horários/contato visíveis; relato de poucos frequentadores; confirmar contato depois |
| 4 | 30 | Grupo Espírita Auta de Souza | Maracanã | visitado | M | deixado para dentro | Aberto com movimento interno, mas ninguém atendeu; kit deixado/jogado para dentro; placa com horários; tel. 2571-3998 |
| 5 | 13 | Centro Espirita Jacques Chulan | Maracanã | fechado |  |  | Foto recebida; nº 63; sem horários/contatos visíveis; fácil estacionar; rota perfeita |
| 6 | 29 | Casa da Caridade - Instituição Cristã Espírita de Estudos e Benefícios | Maracanã | fechado |  | sim, não em mãos | Foto nº 51; sem placa/horários/contatos; Fábio confirma que funciona centro; estacionamento médio; rota parcial com pequeno desvio/bandalha |
| 7 | 31 | Lar Cristão Maria de Nazareth | Maracanã | fechado | P | sim | Fotos; nº 309; tel. 2284-5176; terça 19h30-21h; kit deixado; estacionamento tranquilo |
| 8 | 12 | Centro Espirita de Caridade Jesus | Vila Isabel | fechado |  |  | Fotos; tel. 2576-3011; estacionamento tranquilo; indício forte espiritualista/terreiro: quadro “Terreiro de Exu”, 04/07/26 às 17h, “Axé”; confirmar aderência kardecista |
| 9 | 04 | Centro Espírita Bezerra de Menezes do Andaraí - CEBMA | Andaraí | fechado | M |  | Fotos; banner evangelização sábado 15h; quadro de avisos ilegível; confirmar material/rota se necessário |
| 10 | 05 | Grupo Espírita Redenção | Andaraí | fechado | M |  | Fotos; nº 417; difícil de achar/entrada pequena; horários: 2ª 13h/15h ambíguo, sáb 17h, educação espírita sáb 8h; sem contato visível |
| 11 | 28 | Centro Espírita Humberto de Campos | Andaraí | visitado |  | em mãos | Aberto e movimentado; possível distribuição de cesta básica; sem foto por privacidade/muita gente; dirigente aparente recebeu; sem horário visível |
| 12 | 06 | Centro Espiritualista Irmãos de Fé | Grajaú | fechado |  | sim | CEIF; material deixado; consultas 2ª 19h30/4ª 14h30, desenvolvimento 5ª 19h30; Maps indica esquina mas entra em ruazinha; estacionamento difícil; espiritualista, confirmar aderência |
| 13 | 08 | Grupo Espírita Jesus no Lar | Grajaú | fechado | P | sim | Foto/placa; sem horários/contatos; kit deixado; estacionamento ruim em esquina/descida do Grajaú, mas dá para parar ficando atento |
| 14 | 09 | CEJN - Centro Espírita Jorge Niemeyer | Vila Isabel | pendente |  |  |  |
| 15 | 11 | Sociedade Espirita Jorge | Vila Isabel | visitado |  | em mãos | Secretaria recebeu; casa já conhecida por Fábio/De Luca; palestraram ali; contato pessoal a incluir, poss. Jorge; tel. (21) 2578-9851; reuniões 3ª 15h, 4ª/6ª 19h30; estacionamento fácil |
| 16 | 07 | Centro Espírita Ibirajara | Vila Isabel | fechado |  | sim | Fotos/placas; kit deixado; estacionamento muito tranquilo; reuniões 2ª 17h, 3ª 19h45, 5ª 17h; evangelização sáb 16h-18h; site/e-mail/Instagram registrados |
| 17 | 10 | Casa de Aramis Associação Espírita | Vila Isabel | fechado | P | sim | Fotos; nº 752; tratamentos: 2ª cura especial 19h, 4ª desobsessão 19h, sáb desobsessão 15h; material deixado |
| 18 | 24 | Casa de Apoio Fraterno Ponto do Bem | Vila Isabel | fechado | M | sim | Fotos; atendimento 2ª-6ª 09h-18h; Wpp registrado; kit deixado; estacionamento tranquilo; muito voluntariado; confirmar se é centro espírita ou ação/ONG fraterna |
| 19 | 26 | Grupo Espírita Discípulos de Samuel | Vila Isabel | fechado | M |  | Fotos; reuniões 5ª 19h30; esquina com Bar do Adão; fácil estacionar; entrada lateral Rua Ribeiro Guimarães; possível escola espírita atrelada |
| 20 | 14 | Cabana de Antônio de Aquino | Maracanã | fechado | G |  | Fotos/portões; sem horários/contatos visíveis; prédio grande com cerca elétrica; Fábio conferiu outro portão sem informação |
| 21 | 16 | GEAL - Grupo Espírita André Luiz | Maracanã | visitado |  | em mãos | Fábio falou com Dona Denise; Melissa/Mel frequenta e deve ser ponte; muitos jovens/interesse alto; kit ficou lá; horários/site registrados |
| 22 | 15 | Grupo Espírita Sebastião | Maracanã | retornar |  |  | Pulado de propósito: Rua Morais e Silva, perto da casa de Fábio; ficou para levar material amanhã (2026-06-29), não na rota de hoje |
| 23 | 17 | IEVE - IRMANDADE ESPIRITUALISTA VERDADE ETERNA | Praça da Bandeira | fechado |  | em mãos | Material entregue ao porteiro; Fábio chegou quando a reunião parecia ter acabado e a casa já estava fechando/fechada; inferência: abriu domingo de manhã, mas às 12h14 já encerrava; foto da fachada com letreiro 'IEVE', sem horários/contatos visíveis; confirmar aderência espiritualista/kardecista e horários oficiais |
| 24 | 23 | GECAF | Estácio | fechado | P |  | Foto/placa recebida; Grupo Espírita Caminho da Felicidade, nº 17; site www.gecaf.net; vinculado CEERJ/12º CEU; reuniões 2ª 12h30/19h30, 3ª 17h/19h30, 4ª privativa 19h30, 5ª/6ª 19h30, sábado evangelização 15h; fácil estacionar; bem perto da CCAL/espaço; material ainda não confirmado |
| 25 | 22 | Congregação Espírita Umbandista do Brasil | Estácio | fechado | P | sim | Foto/placa: Templo Umbandista Maria Conga do Congo (Centro Escola); consultas 2ª a partir de 16h; kit deixado; sem contato confirmado; não priorizar no recorte kardecista sem estratégia específica |
| 26 | 18 | Centro Espírita Bezerra Menezes | Estácio | visitado | G | em mãos | Material entregue ao responsável Duque; WhatsApp Duque 98152-8156 sem DDD informado; vão fechar parceria para venda de ingressos na CCAL/casa; cartaz: palestras 3ª 15h/dom 10h, evangelização sáb 8h30; redes /cebmestacio, Wpp público (21) 2273-9398, site bezerramenezes.org.br; prioridade parceria |
| 27 | 19 | Grupo Espirita Caminho da Esperanca | Rio Comprido | fechado | M |  | Foto/banner: Centro Espírita Caminho da Esperança, nº 51; reuniões públicas 2ª e 4ª 19h-20h; Instagram @caminhodaesperancagece, Facebook facebook.com/caminhodaesperancagece, YouTube @CaminhoDaEsperancaGECE; bem perto da CCAL/espaço; material ainda não confirmado |
| 28 | 21 | Grupo Samaritanos | Praça da Bandeira | visitado | P | porteiro | Aberto/funcionando; reunião terminando por volta de 13h; reuniões 5ª/sáb/dom sem horários detalhados; material deixado com o porteiro para entregar hoje ao diretor Seu Ivan; sem foto porque fachada só tinha nº 96 e banner discreto de trabalho social |
| 29 | 27 | Cruzada dos Militares Espíritas | Praça da Bandeira | fechado | M | sim | Fotos/placa e fachada nº 142; reuniões públicas domingos 10h; kit deixado; fachada/portão fechado; instituição kardecista explícita pela placa/Codificação Kardecista |
| 30 | 20 | AEOB - ASSOCIAÇÃO ESPÍRITA OBREIROS DO BEM | Rio Comprido | pendente |  |  |  |
| 31 | 25 | Centro Espirita Caridade Ismael | Rio Comprido | pendente |  |  |  |

## Log de campo

- 2026-06-27: cadastro inicial criado a partir da rota otimizada saindo da Rua São Francisco Xavier, 169 e terminando na Rua Campos da Paz, 105.
- 2026-06-28 12:14: IEVE registrado como fechado/encerrando; material entregue em mãos ao porteiro; foto de fachada arquivada; sem horários oficiais visíveis.
- 2026-06-28: GECAF registrado por foto/OCR; placas com endereço, site, vínculo CEERJ/12º CEU e horários de reuniões; material ainda não confirmado.
- 2026-06-28 12:21: GECAF confirmado fechado; estacionamento fácil e ponto bem perto da CCAL/espaço; material ainda não confirmado.
- 2026-06-28 12:24: Grupo Espírita Sebastião/Rua Morais e Silva marcado como retornar; Fábio pulou de propósito e vai levar amanhã (2026-06-29), por ser perto de casa.
- 2026-06-28 12:28: Congregação Espírita Umbandista/Templo Umbandista Maria Conga do Congo registrado como fechado, P, kit deixado; placa indica consultas às segundas 16h e linha umbandista explícita.
- 2026-06-28 12:32: Complementado Templo Umbandista Maria Conga do Congo com contato Duque e telefone/WhatsApp 98152-8156 sem DDD informado.
- 2026-06-28 12:33: Centro Espírita Bezerra de Menezes visitado; material entregue ao responsável Duque, WhatsApp 98152-8156 sem DDD; parceria de venda de ingressos sinalizada. Corrigida atribuição anterior do contato Duque, que pertence ao Bezerra de Menezes, não ao templo umbandista.
- 2026-06-28 12:36: Grupo Espírita Caminho da Esperança registrado como fechado, M, bem perto da CCAL/espaço; banner com reuniões 2ª/4ª 19h-20h e redes sociais; material ainda não confirmado.
- 2026-06-28 13:01: Grupo Samaritanos/Rua Barão de Ubá 96 visitado; aberto, reunião terminando; material deixado com porteiro para diretor Seu Ivan; sem foto por fachada sem identificação útil.
- 2026-06-28 13:04: Grupo Samaritanos atualizado com porte P conforme correção de Fábio.
- 2026-06-28 13:04: Cruzada dos Militares Espíritas nº 142 registrada como fechada, M, kit deixado; placa/fachada arquivadas; reuniões públicas domingos 10h.
