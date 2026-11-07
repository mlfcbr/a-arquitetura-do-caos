# Complexidade essencial e acidental

*Por que alguns problemas são difíceis por natureza, enquanto outros se tornam difíceis pelas soluções que criamos?*

Nem toda complexidade em um sistema é consequência de decisões ruins. Algumas dificuldades pertencem ao próprio problema que precisamos resolver. Outras surgem das tecnologias, estruturas e processos escolhidos para resolvê-lo.

Essa distinção foi popularizada por Frederick P. Brooks Jr. no ensaio *No Silver Bullet* (*Não existe bala de prata*), publicado em 1986.

Compreendê-la ajuda a evitar dois erros frequentes: tentar eliminar uma complexidade inevitável e aceitar como inevitável uma complexidade que nós mesmos introduzimos.

## 1. Complexidade essencial — A dificuldade pertence ao problema?

Complexidade essencial (*essential complexity*) é aquela que decorre da natureza do problema, independentemente da tecnologia utilizada.

Um sistema financeiro, por exemplo, pode precisar lidar com regras tributárias, conciliação, autorizações, estornos, auditoria e exigências regulatórias. Essas responsabilidades não desaparecem simplesmente porque a aplicação foi reescrita em uma linguagem moderna.

Da mesma forma, um sistema de benefícios pode precisar administrar diferentes categorias de saldo, restrições de utilização, regras contratuais e exceções operacionais.

A tecnologia pode facilitar a implementação dessas regras, mas não eliminar sua existência.

**Cuidado:** classificar toda dificuldade como essencial pode servir de justificativa para processos ruins, regras redundantes e decisões que nunca foram questionadas.

## 2. Complexidade acidental — A dificuldade foi criada pela solução?

Complexidade acidental (*accidental complexity*) é aquela introduzida pelos meios utilizados para implementar e operar o sistema, e não pela natureza do problema.

Ela pode surgir de integrações desnecessárias, dependências excessivas, duplicação de regras, ferramentas inadequadas, configurações difíceis de compreender ou arquiteturas desproporcionais.

Imagine uma funcionalidade simples de consulta que depende de vários serviços, filas e processos intermediários sem que exista uma necessidade real para essa distribuição.

A dificuldade adicional não pertence necessariamente ao problema de consultar informações. Pode ser consequência da arquitetura escolhida.

**Cuidado:** nem toda complexidade tecnológica é acidental ou dispensável. Distribuição, redundância e controles adicionais podem ser necessários para atender requisitos reais de escala, disponibilidade ou segurança.

## 3. Por que a distinção é importante?

A principal consequência é que os dois tipos de complexidade exigem abordagens diferentes.

| Tipo | Origem | Abordagem |
|---|---|---|
| **Essencial** | Regras, restrições e características do problema | Compreender, modelar e administrar |
| **Acidental** | Ferramentas, estruturas e decisões de implementação | Questionar, simplificar e, quando possível, eliminar |

Uma equipe que confunde os dois tipos pode investir em uma grande migração tecnológica esperando resolver problemas que, na realidade, pertencem às regras de negócio.

Também pode desperdiçar esforço tentando simplificar um domínio que exige controles rigorosos.

A primeira pergunta deveria ser: **a dificuldade existe porque o problema exige ou porque nossa solução a introduziu?**

## 4. A promessa da bala de prata

Brooks argumentou que não existia uma única tecnologia ou técnica capaz de produzir, por si só, uma melhoria de ordem de grandeza em produtividade, confiabilidade e simplicidade no desenvolvimento de software.

Isso não significa que novas tecnologias sejam inúteis ou incapazes de gerar avanços expressivos em situações específicas.

Significa que ferramentas não eliminam automaticamente as dificuldades fundamentais de compreender requisitos, modelar comportamentos, coordenar responsabilidades e lidar com mudanças.

Linguagens modernas, computação em nuvem, microsserviços e inteligência artificial podem reduzir determinados custos, mas também introduzir novas dependências e desafios.

A escolha de uma tecnologia precisa ser avaliada pelos problemas concretos que resolve, não pela expectativa de que transforme qualquer sistema complexo em algo simples.

## 5. Como reconhecer a complexidade acidental?

Alguns sinais merecem investigação:

- Uma operação simples exige compreender muitos componentes.
- Existem diferentes fontes para a mesma informação.
- Alterações pequenas demandam coordenação excessiva.
- Ferramentas e processos introduzem mais trabalho do que eliminam.
- A arquitetura exige conhecimentos especializados sem benefícios proporcionais.
- Regras simples tornam-se difíceis de localizar ou modificar.

Esses sinais não provam que a complexidade seja desnecessária. Indicam onde uma avaliação pode revelar oportunidades de simplificação.

Também é importante considerar que **complexidade pode ser deslocada, e não eliminada**. Uma interface simples para o usuário pode depender de mecanismos internos sofisticados; um serviço aparentemente simples pode transferir responsabilidades para a infraestrutura ou para a operação.

## 6. Como reduzir a complexidade sem comprometer o sistema?

A abordagem mais segura é compreender primeiro as necessidades reais e distinguir as restrições obrigatórias das decisões que podem ser revistas.

Práticas como modularização, redução de dependências, automação, melhoria de contratos e eliminação de duplicações podem reduzir a complexidade acidental.

Entretanto, simplificar não significa retirar controles necessários nem esconder dificuldades atrás de abstrações que apenas transferem o problema para outro lugar.

**A lição central:** a boa engenharia não promete eliminar toda a complexidade. Ela procura compreender a complexidade inevitável e evitar que nossas próprias soluções acrescentem dificuldades sem benefício suficiente.
