# Atividade 1: Fundamentos e Características da Qualidade no LocalEats

> Substituam os campos entre colchetes pelas respostas da equipe e removam as instruções antes da entrega.

## 1. Identificação

**Turma:** Qualidade de software 2026 - 2 - manhã  
**Equipe:**Daniel 
**Data:** 27/10/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Daniel | @ddahnn |

**Elemento de Competência:** Compreender os fundamentos de qualidade de software e sua aplicação no desenvolvimento de sistemas.

**Aplicação:** <https://local-eats-unisenac.vercel.app/>

---

## 2. Tarefa 1: Fundamentos da qualidade

### 2.1 Necessidades explícitas e implícitas

| Tipo | Necessidade | Interessado | Consequência se não for atendida |
|---|---|---|---|
| Explícita | Permitir cancelar um pedido confirmado, dentro das regras de cancelamento do restaurante. | Cliente e restaurante | O cliente pode ficar com um pedido indesejado e precisar procurar atendimento para resolver. |
| Explícita | Permitir minimizar a janela do pedido sem perder os itens adicionados. | Cliente | A janela pode atrapalhar a visualização do cardápio, principalmente em telas menores. |
| Implícita | Calcular corretamente o total conforme os preços e as quantidades dos produtos. | Cliente e restaurante | Pode haver cobrança incorreta, prejuízo e reclamações. |

**Um sistema que implementa todas as funcionalidades explicitamente solicitadas pode, ainda assim, apresentar baixa qualidade? Justifiquem utilizando pelo menos uma necessidade implícita identificada pela equipe.**

Sim. Mesmo tendo todas as funcionalidades solicitadas, o sistema pode apresentar baixa qualidade se não atender às necessidades implícitas. Por exemplo, o cliente espera que o total do pedido seja calculado corretamente. Se o valor estiver errado, o sistema pode causar prejuízos e perder a confiança dos usuários.

---

## 3. Tarefa 2: Exploração da aplicação

> Cada integrante deve explorar uma funcionalidade, realizando uma utilização esperada e uma utilização alternativa, inválida ou incompleta. Acrescentem ou removam linhas conforme o número de integrantes.

| Integrante | Funcionalidade | O que foi realizado | O que foi observado | Evidência |
|---|---|---|---|---|
| [Daniel] | [Montagem de pedido] | [uso esperado e uso alternativo] | [comportamento observado] | [ver evidência](evidencias/nome-do-arquivo.png) |
---

## 4. Tarefa 3: Requisitos e características de qualidade

> Cada integrante deve formular um requisito de qualidade relacionado à mesma funcionalidade explorada na Tarefa 2. Acrescentem ou removam linhas conforme o número de integrantes.

| Integrante | Requisito de qualidade | Característica ou subcaracterística | Justificativa | Como avaliar |

| Daniel | A janela do pedido deve permitir minimizar e reabrir, mantendo os produtos, as quantidades e o total. | Usabilidade — operabilidade. | Permite continuar navegando pelo cardápio sem perder o pedido que já foi montado. | Adicionar dois produtos, minimizar a janela, navegar pelo cardápio e reabrir. Conferir se os produtos, as quantidades e o total continuam iguais.  cuidar o o valor do calculo dos produtos|
---

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
GPT

**Como foi utilizada:**  
auxilio em montar as respostas

**Como as respostas foram verificadas:**  olhei testei e mandei para a IA me ajudar a formatar a resposta