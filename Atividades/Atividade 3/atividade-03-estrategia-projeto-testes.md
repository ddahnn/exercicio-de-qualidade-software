# Atividade 3: Estratégia e Projeto de Testes do LocalEats

## 1. Identificação

**Turma:** Qualidade de Software 2026 – 2 – manhã  
**Equipe:** Daniel — trabalho individual  
**Data:** 27/10/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Daniel Bortolin | @ddahnn |

**Elemento de Competência:** Planejar e projetar testes selecionando técnicas adequadas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

## 2. Tarefa 1: Planejamento dos testes

### 2.1 Objetivo dos testes

Verificar se o LocalEats calcula corretamente o valor do pedido ao adicionar produtos, alterar suas quantidades e remover itens. Também será verificado se o sistema impede a confirmação de um pedido vazio.

Os casos serão planejados nesta atividade e executados futuramente. O relato anterior de erro no cálculo será usado para priorizar os testes.

### 2.2 Escopo

#### Funcionalidades incluídas

| Integrante | Funcionalidade incluída | O que será verificado |
|---|---|---|
| Daniel | Fazer pedido. | Cálculo do subtotal e do total, atualização dos valores ao alterar os itens e bloqueio da confirmação de pedido vazio. |

#### Funcionalidade não incluída

| Funcionalidade não incluída | Justificativa |
|---|---|
| Favoritar e desfavoritar restaurantes. | Não faz parte das regras de montagem e cálculo do pedido escolhidas para este planejamento. |

### 2.3 Abordagem

| Item | Decisão da equipe | Justificativa |
|---|---|---|
| Níveis de teste | Teste de sistema. | O comportamento será verificado pela interface da aplicação, incluindo a montagem do pedido e os valores apresentados. |
| Tipos de teste | Testes funcionais. | O objetivo é verificar o cumprimento das regras de cálculo e de validação do pedido. |
| Perspectiva caixa-preta ou caixa-branca | Caixa-preta. | Serão consideradas as entradas e as respostas da aplicação, sem depender do acesso ao código-fonte. |
| Técnicas de teste | Particionamento de equivalência e transição de estados. | A primeira técnica ajuda a selecionar composições representativas do pedido. A segunda verifica o comportamento ao remover o último produto e tentar confirmar um pedido vazio. |

### 2.4 Ambiente e responsabilidades

| Item | Definição |
|---|---|
| Ambiente necessário | Aplicação LocalEats disponível, computador com Chrome ou Edge atualizado, conexão com a internet e conta de teste cadastrada e autenticada. Deve existir um restaurante com dois produtos disponíveis, com preços visíveis, e controles para adicionar e remover itens. As quantidades serão alteradas pelos controles disponíveis na interface. Uma calculadora será usada para conferir os valores. |
| Responsáveis pelo planejamento | Daniel Bortolin. |
| Responsáveis pela especificação dos casos | Daniel Bortolin. |
| Responsáveis pela futura execução | Daniel Bortolin. |

**Preparação dos dados e regra de comparação:**

- Escolher dois produtos do mesmo restaurante, identificados como A e B.
- Registrar os nomes e os preços exibidos no cardápio: PA para o produto A e PB para o produto B.
- Usar os preços vigentes no momento da execução, mantendo-os estáveis durante cada caso.
- Realizar os casos sem aplicar cupons ou descontos.
- Calcular o subtotal somando o preço de cada produto multiplicado pela quantidade.
- Se houver taxas, registrar separadamente o valor informado pela aplicação em cada etapa. Nos resultados esperados, T representa a soma dessas taxas naquela etapa; se não houver taxas, T será zero.
- Comparar o total com o subtotal mais T. Qualquer acréscimo deve estar identificado na interface.

Os símbolos PA, PB e T serão substituídos pelos valores registrados na futura execução. Assim, o planejamento não depende de preços fictícios ou de uma taxa presumida.

### 2.5 Critérios

Os critérios abaixo orientarão a execução futura dos casos.

| Critério | Definição da equipe |
|---|---|
| Entrada | Aplicação acessível, conta de teste autenticada, restaurante e produtos disponíveis, preços visíveis e dados de entrada preparados. O pedido deverá estar no estado indicado na pré-condição de cada caso. |
| Saída | Os três casos deverão ser executados, com resultados registrados e defeitos encontrados documentados. A aprovação do fluxo dependerá do cálculo correto em todas as verificações e do bloqueio da confirmação do pedido vazio, após correção e nova verificação de eventuais falhas. |
| Suspensão | Interromper os testes se a aplicação ficar indisponível, o acesso à conta falhar, os produtos necessários não estiverem disponíveis, os preços mudarem durante um caso ou uma falha impedir a montagem do pedido. Retomar quando a condição necessária estiver restabelecida. |

## 3. Tarefa 2: Riscos e técnicas de teste

### 3.1 Análise dos riscos

As classificações são estimativas qualitativas para priorizar os testes. O R01 considera o erro relatado na exploração anterior; o R02 é um risco a verificar na execução futura.

| ID | Integrante | Funcionalidade | Risco | Consequência | Probabilidade | Impacto | Prioridade | Justificativa |
|---|---|---|---|---|:---:|:---:|:---:|---|
| R01 | Daniel | Fazer pedido. | O total não corresponder aos produtos e às quantidades atuais, incluindo valores desatualizados após uma alteração. | O cliente pode visualizar ou pagar um valor incorreto, e o restaurante pode receber um valor diferente do devido. | Alta | Alto | Alta | Já houve relato de erro no cálculo, e uma cobrança incorreta prejudica o cliente, o restaurante e a confiança na plataforma. |
| R02 | Daniel | Fazer pedido. | O sistema permitir confirmar o pedido depois da remoção de todos os produtos. | O restaurante pode receber um pedido sem itens, causando confusão e retrabalho para o cliente e para o estabelecimento. | Média | Médio | Média | Remover produtos é uma situação possível durante a montagem, e o estado vazio exige validação. A ocorrência ainda deverá ser verificada. |

### 3.2 Aplicação das técnicas

#### Análise 1: Particionamento de equivalência

**Integrante:** Daniel  
**Funcionalidade:** Fazer pedido.  
**Riscos relacionados:** R01 e R02.  
**Técnica escolhida:** Particionamento de equivalência.

**Por que a técnica foi escolhida:**  
A composição do pedido pode ser dividida em classes com características semelhantes. Isso permite selecionar situações representativas para verificar a soma dos preços, a multiplicação pelas quantidades e a validação do pedido vazio.

**Aplicação da técnica:**

Para os pedidos não vazios, serão consideradas quantidades inteiras positivas. As classes abaixo não pressupõem um limite máximo de itens.

| Classe | Situação | Representante escolhido | Comportamento esperado | Casos derivados |
|---|---|---|---|---|
| E01 — válida | Um único produto com uma unidade. | A com quantidade 1. | Subtotal igual a PA e total igual a PA + T. | CT01, na primeira adição. |
| E02 — válida | Dois ou mais produtos diferentes, todos com uma unidade. | A com quantidade 1 e B com quantidade 1. | Subtotal igual a PA + PB e total igual a PA + PB + T. | CT01, após adicionar B. |
| E03 — válida | Pedido com pelo menos um produto com mais de uma unidade. | A com quantidade 2 e B com quantidade 1; depois, somente A com quantidade 2. | Calcular as quantidades atuais e retirar da soma os produtos removidos. | CT02. |
| E04 — inválida para confirmação | Pedido sem produtos. | Pedido vazio após remover o último item. | Impedir a confirmação do pedido. | CT03. |

**Casos derivados:** CT01, CT02 e CT03.

#### Análise 2: Transição de estados

**Integrante:** Daniel  
**Funcionalidade:** Fazer pedido.  
**Risco relacionado:** R02.  
**Técnica escolhida:** Transição de estados.

**Por que a técnica foi escolhida:**  
O comportamento esperado muda quando o pedido passa de um estado com produtos para um estado vazio. A técnica permite verificar se o sistema reconhece essa mudança e bloqueia uma tentativa de confirmação.

**Aplicação da técnica:**

Para este recorte, os estados usados no modelo são “Com produtos” e “Vazio”. Esses nomes descrevem a situação do pedido em montagem e não dependem de rótulos exibidos pela aplicação.

| Estado inicial | Ação | Estado esperado | Regra verificada |
|---|---|---|---|
| Com produtos, contendo somente A com quantidade 1. | Remover o último produto. | Vazio. | O item deve desaparecer do pedido e o subtotal dos produtos deve ser R$ 0,00. |
| Vazio. | Tentar confirmar o pedido. | Permanecer vazio, sem confirmação. | A tentativa deve ser bloqueada e nenhum pedido deve ser enviado ao restaurante. |

**Casos derivados:** CT03.

## 4. Tarefa 3: Casos de teste e rastreabilidade

### 4.1 Casos de teste

Os casos abaixo especificam ações e resultados esperados para execução futura.

### CT01: Calcular o valor ao adicionar produtos diferentes

**Integrante responsável:** Daniel  
**Funcionalidade:** Fazer pedido.  
**Risco ou requisito relacionado:** R01 — cálculo incorreto do valor do pedido.  
**Técnica utilizada:** Particionamento de equivalência, classes E01 e E02.

**Pré-condição:**  
Conta de teste autenticada, pedido vazio e restaurante com dois produtos disponíveis. Os preços deverão permanecer estáveis durante o caso, sem aplicação de cupons ou descontos.

**Dados de entrada:**

| Dado | Valor |
|---|---|
| Produto A | Um produto disponível no restaurante, com preço registrado como PA. |
| Produto B | Outro produto do mesmo restaurante, com preço registrado como PB. |
| Quantidade de A | 1. |
| Quantidade de B | 1. |
| Taxas | T, conforme os valores informados pela aplicação em cada etapa; zero se não houver taxas. |

**Passos:**

1. Acessar o cardápio do restaurante e registrar os nomes e os preços dos produtos A e B.
2. Adicionar uma unidade de A ao pedido e consultar o resumo.
3. Conferir se o subtotal corresponde a PA e se o total corresponde a PA + T.
4. Adicionar uma unidade de B ao mesmo pedido e consultar novamente o resumo.
5. Calcular manualmente PA + PB e comparar com o subtotal. Somar T e comparar com o total exibido.

**Resultado esperado:**  
Na primeira adição, o pedido deve apresentar A com quantidade 1, subtotal igual a PA e total igual a PA + T. Após adicionar B, deve apresentar A e B com uma unidade cada, subtotal igual a PA + PB e total igual a PA + PB + T. Os valores devem coincidir até os centavos, e qualquer taxa deve estar identificada.

---

### CT02: Atualizar o valor ao alterar a quantidade e remover um produto

**Integrante responsável:** Daniel  
**Funcionalidade:** Fazer pedido.  
**Risco ou requisito relacionado:** R01 — cálculo incorreto ou desatualizado após alterações.  
**Técnica utilizada:** Particionamento de equivalência, classe E03.

**Pré-condição:**  
Conta de teste autenticada e pedido em montagem com A e B, uma unidade de cada. Os preços PA e PB deverão estar registrados e permanecer estáveis. Essa preparação pode ser feita diretamente, sem depender da execução do CT01.

**Dados de entrada:**

| Dado | Valor |
|---|---|
| Quantidade inicial de A | 1. |
| Nova quantidade de A | 2. |
| Quantidade inicial de B | 1. |
| Produto a remover | B. |
| Taxas | T, conforme os valores informados pela aplicação em cada etapa; zero se não houver taxas. |

**Passos:**

1. Consultar o resumo do pedido e conferir a presença de A e B, uma unidade de cada.
2. Adicionar mais uma unidade de A pelos controles da interface, deixando A com quantidade 2.
3. Comparar o subtotal com 2 × PA + PB e o total com 2 × PA + PB + T.
4. Remover B do pedido.
5. Consultar novamente o resumo e comparar o subtotal com 2 × PA e o total com 2 × PA + T.

**Resultado esperado:**  
Ao aumentar a quantidade de A, o pedido deve apresentar duas unidades de A e uma de B, com subtotal de 2 × PA + PB. Após remover B, deve apresentar somente A com quantidade 2 e subtotal de 2 × PA. Em cada etapa, o total deve corresponder ao subtotal mais as taxas informadas naquele momento, sem manter valores de itens removidos.

---

### CT03: Impedir a confirmação após remover o último produto

**Integrante responsável:** Daniel  
**Funcionalidade:** Fazer pedido.  
**Risco ou requisito relacionado:** R02 — confirmação de pedido vazio.  
**Técnicas utilizadas:** Particionamento de equivalência, classe E04, e transição de estados.

**Pré-condição:**  
Conta de teste autenticada e pedido em montagem com somente uma unidade de A. Nenhum outro produto deverá estar no pedido.

**Dados de entrada:**  
Remoção da única unidade de A, deixando o pedido sem produtos.

**Passos:**

1. Consultar o resumo do pedido e conferir que existe somente A com quantidade 1.
2. Remover A pelos controles da interface.
3. Verificar se o pedido ficou vazio e se o subtotal dos produtos corresponde a R$ 0,00.
4. Verificar a disponibilidade da ação de confirmar. Se estiver disponível, tentar confirmar o pedido vazio.

**Resultado esperado:**  
Após a remoção, o pedido deve ficar sem produtos e o subtotal deve ser R$ 0,00. O sistema deve impedir a confirmação, seja desabilitando ou retirando a ação, seja apresentando uma validação ao tentar confirmar. Nenhum pedido deve ser enviado ao restaurante, nem deve ser exibida uma confirmação de sucesso ou um novo número de pedido.

### 4.2 Matriz de rastreabilidade

| Integrante | Funcionalidade | Risco ou requisito | Técnica utilizada | Casos de teste |
|---|---|---|---|---|
| Daniel | Fazer pedido. | R01 — cálculo incorreto ou desatualizado. | Particionamento de equivalência, classes E01, E02 e E03. | CT01 e CT02. |
| Daniel | Fazer pedido. | R02 — confirmação de pedido vazio. | Particionamento de equivalência, classe E04, e transição de estados. | CT03. |

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
ChatGPT.

**Como foi utilizada:**  
Para ajudar a organizar o plano, identificar riscos, selecionar e aplicar técnicas de teste, escrever os casos e conferir a relação entre riscos, técnicas e casos.

**Uma sugestão que precisou ser alterada ou rejeitada:**  
As sugestões foram analisadas para evitar criar preços ou limites máximos de quantidade que não foram informados. Os casos foram definidos com os preços que serão lidos do cardápio na futura execução. O cálculo esperado também considera separadamente eventuais taxas informadas, para não confundir um valor identificado com um erro de soma.

**Como as respostas foram verificadas:**  
O planejamento foi comparado com o enunciado. Foram conferidos a seleção de uma funcionalidade, os dois riscos, a aplicação das técnicas e os três casos, além da rastreabilidade entre eles. As fórmulas dos resultados esperados foram revisadas com base nos preços, nas quantidades e nas taxas identificadas. Os resultados reais serão verificados e registrados durante a execução futura.
