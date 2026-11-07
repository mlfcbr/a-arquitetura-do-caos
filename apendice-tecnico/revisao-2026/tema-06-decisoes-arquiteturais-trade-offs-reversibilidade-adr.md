# Decisões arquiteturais, trade-offs, reversibilidade e ADR

*Uma boa decisão de arquitetura não é aquela que parece perfeita. É aquela cujas consequências foram compreendidas.*

Arquitetura de software envolve escolhas que influenciam a estrutura, a evolução e a operação de um sistema. Essas escolhas podem determinar tecnologias, formas de integração, distribuição de responsabilidades, armazenamento de dados e características como desempenho, segurança e disponibilidade.

Raramente existe uma solução superior em todos os aspectos. Uma arquitetura que facilita a escalabilidade pode aumentar os custos operacionais. Uma solução que acelera a entrega pode limitar a flexibilidade futura.

Por isso, decisões arquiteturais exigem compreender os compromissos envolvidos, avaliar a dificuldade de reversão e preservar o raciocínio que levou à escolha.

## 1. Decisões arquiteturais — O que realmente merece ser decidido?

Uma decisão arquitetural é uma escolha com impacto relevante sobre a estrutura, as características de qualidade ou a evolução de um sistema.

Nem toda decisão técnica possui esse alcance. Escolher o nome de um método normalmente não exige o mesmo cuidado que definir como diferentes sistemas compartilharão informações.

A relevância depende do contexto. Uma escolha aparentemente pequena pode se tornar arquitetural quando afeta segurança, contratos públicos, persistência de dados ou vários componentes.

**Cuidado:** tratar todas as decisões como arquiteturais cria processos pesados. Ignorar decisões importantes, por outro lado, faz com que compromissos de longo prazo sejam assumidos sem avaliação suficiente.

## 2. Trade-offs — Toda escolha envolve renúncias

*Trade-off* é o compromisso entre objetivos que não podem ser maximizados simultaneamente em determinado contexto. Em português, podemos falar em **compensações ou escolhas com perdas e ganhos**.

Uma solução pode favorecer simplicidade e velocidade de entrega, mas oferecer menos flexibilidade para determinados cenários. Outra pode proporcionar maior isolamento entre componentes, exigindo mais infraestrutura, monitoramento e coordenação.

Não existe uma regra segundo a qual microsserviços sejam sempre melhores que monólitos, nem que consistência imediata seja sempre preferível à consistência eventual.

A escolha depende dos requisitos e das restrições reais.

| Decisão | Possível benefício | Possível custo |
|---|---|---|
| Centralizar uma regra | Consistência e manutenção concentrada | Maior dependência do componente central |
| Distribuir serviços | Autonomia de implantação e isolamento | Complexidade de comunicação e operação |
| Adotar uma solução gerenciada | Menor esforço de infraestrutura | Dependência do fornecedor |
| Criar uma abstração | Flexibilidade diante de variações reais | Complexidade adicional |

**Cuidado:** trade-offs não devem servir para justificar qualquer escolha. É preciso demonstrar quais benefícios são relevantes e quais custos são aceitáveis.

## 3. Reversibilidade — Quanto custa mudar de ideia?

A reversibilidade representa a facilidade de modificar ou abandonar uma decisão depois de implementada.

Algumas escolhas são relativamente simples de alterar, como substituir uma biblioteca isolada. Outras podem exigir migração de dados, mudanças contratuais, reestruturação de integrações ou coordenação entre várias equipes.

Quanto maior o custo de reversão, maior deve ser o cuidado na avaliação inicial.

Isso não significa tentar prever todos os cenários futuros. Significa reconhecer decisões que podem comprometer opções importantes e preservar flexibilidade quando o custo for justificável.

**Cuidado:** projetar tudo para ser substituível pode criar complexidade sem benefício. Nem toda dependência precisa ser eliminada ou abstraída antecipadamente.

## 4. ADR — Registrar o motivo, não apenas a escolha

ADR significa *Architecture Decision Record*, ou **Registro de Decisão Arquitetural**.

É um documento curto que preserva o contexto de uma decisão relevante, as alternativas consideradas, a escolha realizada e suas consequências.

Um ADR pode conter:

| Elemento | O que registrar |
|---|---|
| **Contexto** | Qual problema ou restrição motivou a decisão? |
| **Decisão** | O que foi escolhido? |
| **Alternativas** | Quais opções relevantes foram consideradas? |
| **Justificativa** | Por que esta opção foi preferida? |
| **Consequências** | Quais benefícios, custos e riscos são esperados? |
| **Situação** | A decisão está proposta, aceita ou foi substituída? |

O principal valor de um ADR não está em documentar a tecnologia adotada, mas em preservar **por que ela fazia sentido naquele momento**.

Isso evita que decisões antigas sejam interpretadas como erros simplesmente porque o contexto mudou.

**Cuidado:** ADR não deve se transformar em um processo de autorização para cada alteração. Registros extensos, desatualizados ou escritos apenas para cumprir uma formalidade tendem a perder utilidade.

## 5. Decisões reversíveis e irreversíveis exigem tratamentos diferentes

Decisões de baixo impacto e fácil reversão podem ser tomadas rapidamente, acompanhadas de observação e ajustes.

Já decisões com consequências amplas ou difíceis de desfazer merecem análise mais cuidadosa, validação de hipóteses e envolvimento das pessoas afetadas.

Isso não exige consenso absoluto nem aprovação centralizada para tudo. A governança deve ser proporcional ao risco e ao alcance da decisão.

Uma equipe pode ter autonomia para escolher detalhes de implementação dentro de limites compartilhados, enquanto decisões que afetam contratos entre sistemas ou exigências corporativas demandam alinhamento mais amplo.

**O objetivo é estabelecer critérios e limites claros sem transformar cada decisão em uma fila de aprovações.**

## 6. Quando revisar uma decisão arquitetural?

Uma decisão não deve ser considerada eterna.

Ela merece revisão quando os requisitos mudam, os custos se tornam desproporcionais, surgem novas restrições ou evidências demonstram que as premissas originais deixaram de ser válidas.

Revisar não significa que a decisão anterior estava errada. Uma escolha adequada para um sistema pequeno pode deixar de ser a melhor alternativa após seu crescimento.

Também é importante evitar mudanças motivadas apenas por tendências tecnológicas. Substituir uma arquitetura funcional exige benefícios que justifiquem os riscos e custos da transição.

**A lição central:** arquitetura é a prática de fazer escolhas conscientes diante de restrições. Bons registros preservam o raciocínio; bons trade-offs tornam os custos explícitos; e a atenção à reversibilidade evita transformar decisões de hoje em limitações desnecessárias amanhã.
