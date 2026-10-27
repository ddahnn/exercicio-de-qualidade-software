# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

## 1. Identificação

**Turma:** Qualidade de Software 2026 – 2 – manhã  
**Equipe:** Daniel  
**Data:** 27/10/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Daniel | @ddahnn |

**Elemento de Competência:** Compreender os fundamentos de qualidade de software e sua aplicação no desenvolvimento de sistemas.

**Aplicação:** [LocalEats](https://local-eats-unisenac.vercel.app/)

## 2. Tarefa 1: Fundamentos da qualidade

### 2.1 Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | Permitir cancelar um pedido confirmado, dentro das regras de cancelamento do restaurante. | Cliente e restaurante | O cliente pode ficar com um pedido indesejado e precisar procurar atendimento para resolver. |
| Explícita | Permitir minimizar a janela do pedido sem perder os itens adicionados. | Cliente | A janela pode atrapalhar a visualização do cardápio, principalmente em telas menores. |
| Implícita | Calcular corretamente o total conforme os preços e as quantidades dos produtos. | Cliente e restaurante | Pode haver cobrança incorreta, prejuízo e reclamações. |

### 2.2 Questão sobre os fundamentos da qualidade

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade? Justifique utilizando pelo menos uma necessidade implícita identificada pela equipe.**

Sim. Mesmo tendo todas as funcionalidades solicitadas, o sistema pode apresentar baixa qualidade se não atender às necessidades implícitas. Por exemplo, o cliente espera que o total do pedido seja calculado corretamente. Se o valor estiver errado, o sistema pode causar prejuízos e perder a confiança dos usuários.

3. Tarefa 2: Exploração da aplicação

Integrante

Funcionalidade

O que foi realizado

O que foi observado

Evidência

Daniel

Montagem do pedido.

Uso esperado: selecionar produtos para montar o pedido. Uso alternativo: tentar minimizar a janela do pedido para continuar olhando o cardápio.

A janela do pedido não apresentou uma opção para minimizar. Ela ocupou parte da tela e dificultou a visualização dos produtos mais abaixo, principalmente em telas menores. Para fechar a janela, foi necessário finalizar ou cancelar a montagem do pedido.

Ver evidência

Daniel

Cálculo do valor do pedido.

Uso esperado: selecionar produtos e conferir se o total corresponde à soma dos preços multiplicados pelas respectivas quantidades, sem acréscimos.

O total exibido na janela do pedido apresentou erro de cálculo, podendo gerar cobranças incorretas e prejudicar a confiança dos usuários na plataforma.

Ver evidência

4. Tarefa 3: Requisitos e características de qualidade

Integrante

Requisito de qualidade

Característica ou subcaracterística

Justificativa

Como avaliar

Daniel

A janela do pedido deve permitir minimizar e reabrir, mantendo os produtos, as quantidades e o total.

Usabilidade — operabilidade.

Permite continuar navegando pelo cardápio sem perder o pedido que já foi montado.

Adicionar dois produtos e anotar suas quantidades e o total. Minimizar a janela, navegar pelo cardápio e reabrir. Conferir se todos os dados continuam iguais. O total também deve corresponder à soma dos preços multiplicados pelas respectivas quantidades.

Daniel

O sistema deve calcular e atualizar corretamente o total do pedido ao adicionar, remover ou alterar a quantidade dos produtos.

Adequação funcional — correção funcional.

Evita cobranças incorretas e garante que o cliente saiba o valor dos produtos que está pedindo.

Adicionar dois produtos, calcular manualmente os preços multiplicados pelas quantidades e comparar com o total exibido. Depois, alterar uma quantidade e remover um produto, repetindo a comparação. Os valores devem coincidir em todas as etapas.

5. Uso de inteligência artificial

Ferramenta utilizada:
ChatGPT.

Como foi utilizada:
Para ajudar a organizar as observações, montar as respostas e corrigir a formatação da atividade.

Como as respostas foram verificadas:
Acessei o site, testei as funcionalidades e relatei à IA o que observei para que ela ajudasse a organizar a resposta.