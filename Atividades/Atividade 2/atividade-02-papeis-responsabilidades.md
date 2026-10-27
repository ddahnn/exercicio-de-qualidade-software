# Atividade 2: Organização da Qualidade no LocalEats

## 1. Identificação

**Turma:** Qualidade de Software 2026 – 2 – manhã  
**Equipe:** Daniel  
**Data:** 27/10/2026

### Integrantes

| Nome | Usuário no GitHub |
|---|---|
| Daniel Bortolin | @ddahnn |

**Elemento de Competência:** Identificar papéis, responsabilidades e competências relacionadas às atividades de qualidade e testes.

## 2. Tarefa 1: Diagnóstico da situação

### 2.1 Problemas organizacionais

| Problema identificado | Possível consequência para o produto ou para a equipe |
|---|---|
| Os critérios para considerar uma funcionalidade pronta não estão claros. | Uma funcionalidade pode ser entregue sem que seu funcionamento tenha sido conferido adequadamente, causando dúvidas e retrabalho. |
| Alguns integrantes acreditam que somente o QA deve testar. | A equipe pode deixar de realizar verificações durante o desenvolvimento, aumentando a chance de entregar funcionalidades com defeitos. |
| Os defeitos encontrados nem sempre são registrados ou acompanhados. | A equipe pode esquecer de corrigir problemas ou não saber quais continuam pendentes, prejudicando os usuários. |

### 2.2 Responsabilidade pela qualidade

**A qualidade do LocalEats deve ser responsabilidade exclusiva do profissional de QA? Justifiquem.**

Não. A qualidade deve ser responsabilidade de toda a equipe. O responsável pelo produto esclarece o que precisa ser entregue, o desenvolvedor implementa e testa o código, a liderança técnica revisa as soluções e o QA ajuda a prevenir e identificar problemas. Cada papel contribui para que o sistema funcione corretamente.

## 3. Tarefa 2: Papéis e competências

| Integrante | Papel analisado | Responsabilidades relacionadas à qualidade | Competências técnicas | Competências comportamentais |
|---|---|---|---|---|
| Daniel | Responsável pelo produto | Esclarecer requisitos, definir critérios de aceitação, priorizar defeitos e decidir sobre a liberação da versão. | Conhecimento das regras do negócio, análise de requisitos e priorização. | Comunicação, negociação e tomada de decisão. |
| Daniel | Liderança técnica | Revisar os aspectos técnicos dos requisitos, orientar a implementação e revisar o código e os testes unitários. | Arquitetura de software, revisão de código e estratégias de testes. | Colaboração, pensamento crítico e capacidade de orientar a equipe. |
| Daniel | Desenvolvedor | Implementar funcionalidades, criar testes unitários, registrar defeitos e realizar e acompanhar suas correções. | Programação, Git, testes unitários e investigação de defeitos. | Organização, atenção, comunicação e colaboração. |
| Daniel | QA ou analista de qualidade | Contribuir com critérios de aceitação, planejar e executar testes do sistema, registrar defeitos e organizar o acompanhamento de sua resolução. | Técnicas de testes, elaboração de casos de teste e registro e acompanhamento de defeitos. | Observação, pensamento crítico, organização e comunicação clara. |

## 4. Tarefa 3: Matriz de responsabilidades

- **R:** responsável por executar a atividade.
- **A:** aprovador ou responsável final.
- **C:** consultado antes da execução ou decisão.
- **I:** informado sobre o resultado.
- **A/R:** o mesmo papel executa a atividade e responde pelo resultado final.
- **—:** sem participação definida na atividade.

| Atividade de qualidade | Responsável pelo produto | Liderança técnica | Desenvolvedor | QA |
|---|:---:|:---:|:---:|:---:|
| Definir critérios de aceitação | A/R | C | C | C |
| Revisar requisitos | A | R | C | C |
| Implementar a funcionalidade | I | A | R | C |
| Revisar o código | — | A/R | C | I |
| Criar testes unitários | — | A | R | C |
| Planejar e executar testes do sistema | C | C | C | A/R |
| Registrar e acompanhar defeitos | I | C | R | A/R |
| Priorizar a correção dos defeitos | A/R | C | C | C |
| Aprovar a disponibilização da versão | A/R | C | I | C |

### 4.1 Lacuna ou conflito encontrado

**Lacuna ou conflito:**  
O registro e o acompanhamento dos defeitos poderiam ficar concentrados somente no QA. Para evitar isso, a proposta também coloca o desenvolvedor como responsável por essa atividade, enquanto o QA organiza o acompanhamento.

**Consequência:**  
Se somente o QA registrar e acompanhar os defeitos, essa pessoa pode ficar sobrecarregada. Isso pode atrasar as correções e fazer com que problemas encontrados por outros integrantes não sejam acompanhados adequadamente.

### 4.2 Práticas de QA recomendadas

| Prática recomendada | Problema que ajuda a resolver | Papéis envolvidos |
|---|---|---|
| Definir critérios de aceitação antes do desenvolvimento e uma definição de pronto compartilhada, incluindo revisão do código e aprovação dos testes previstos. | Evita dúvidas sobre o comportamento esperado e sobre o que precisa ser concluído antes de entregar uma funcionalidade. | Responsável pelo produto, liderança técnica, desenvolvedor e QA. |
| Registrar os defeitos em um quadro compartilhado, com descrição, passos para reproduzir, responsável, prioridade e situação atual, revisando o andamento com a equipe. | Evita que defeitos sejam esquecidos e permite acompanhar suas correções e compartilhar informações. | QA, desenvolvedor, liderança técnica e responsável pelo produto. |

## 5. Uso de inteligência artificial

**Ferramenta utilizada:**  
ChatGPT.

**Como foi utilizada:**  
Para ajudar a entender os papéis da equipe, diferenciar responsabilidades e competências, organizar a matriz RACI e revisar a escrita e a formatação da atividade.

**Como as respostas foram verificadas:**  
As sugestões foram comparadas com o enunciado da atividade. A matriz foi revisada para conferir se cada atividade possui pelo menos um R e exatamente um A e se a distribuição está de acordo com as responsabilidades descritas para cada papel.
