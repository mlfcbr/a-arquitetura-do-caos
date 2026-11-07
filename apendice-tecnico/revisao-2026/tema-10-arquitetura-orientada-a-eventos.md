# Arquitetura orientada a eventos — Quando os sistemas reagem a acontecimentos

*Um sistema informa que algo aconteceu. Outros decidem o que fazer com essa informação.*

Na arquitetura orientada a eventos (*Event-Driven Architecture*, ou **EDA**), componentes de um sistema se comunicam por meio de eventos que representam acontecimentos relevantes.

Em vez de um componente controlar diretamente todas as etapas de um processo, ele pode publicar um evento para que outros componentes reajam conforme suas responsabilidades.

Essa abordagem pode reduzir determinadas dependências e favorecer a evolução independente de funcionalidades, mas também introduz desafios de consistência, rastreabilidade e tratamento de falhas.

## 1. O que é um evento?

Um **evento (*event*)** representa um fato que ocorreu e possui significado para o sistema ou para o negócio.

Exemplos incluem “Pedido confirmado”, “Pagamento recebido” e “Cadastro aprovado”.

Um evento normalmente identifica o acontecimento, quando ocorreu e as informações necessárias para que seus consumidores compreendam o fato.

É importante distinguir um evento de um comando:

- **Comando (*command*):** solicita que alguma ação seja executada, como “Aprovar pedido”.
- **Evento (*event*):** informa que algo aconteceu, como “Pedido aprovado”.

O comando expressa uma intenção; o evento registra um fato.

**Cuidado:** eventos devem representar acontecimentos efetivos. Publicar “Pagamento realizado” antes de confirmar o pagamento pode induzir outros sistemas a agir sobre uma informação incorreta.

## 2. Publicadores, consumidores e intermediários

Uma arquitetura orientada a eventos costuma envolver três papéis.

**Publicador (*publisher*)** é o componente que produz e disponibiliza um evento.

**Consumidor (*consumer*)** é o componente que recebe o evento e executa alguma reação, conforme suas responsabilidades.

**Intermediário de mensagens (*message broker*)** é a infraestrutura que pode receber, armazenar, encaminhar ou distribuir eventos entre os participantes.

Um evento de pedido confirmado, por exemplo, pode ser consumido independentemente por componentes de faturamento, notificações e relatórios.

O publicador não precisa necessariamente conhecer todos os consumidores.

**Cuidado:** essa independência é parcial. Os participantes continuam dependendo dos contratos dos eventos, de sua semântica e das garantias de entrega oferecidas pela infraestrutura.

## 3. Filas e publicação/assinatura

Dois modelos comuns de distribuição de mensagens são as filas e a publicação/assinatura (*publish/subscribe*, ou **pub/sub**).

Em uma **fila**, mensagens costumam ser distribuídas entre consumidores concorrentes de um mesmo grupo de processamento. Cada mensagem é destinada a ser processada por um deles, conforme as garantias da infraestrutura.

No modelo de **publicação/assinatura**, diferentes assinantes podem receber o mesmo evento e reagir de maneira independente.

Esses modelos podem ser combinados. Plataformas de mensageria também oferecem outras formas de distribuição, retenção e consumo.

**Cuidado:** escolher uma fila ou um tópico não define, por si só, a arquitetura. O significado dos eventos e a responsabilidade de cada consumidor continuam sendo decisões fundamentais.

## 4. Desacoplamento e autonomia

Um dos benefícios da arquitetura orientada a eventos é permitir que novas reações sejam adicionadas sem necessariamente modificar o componente que originou o acontecimento.

Isso pode facilitar a inclusão de notificações, auditoria e integrações posteriores.

Também pode reduzir o acoplamento temporal: o publicador não precisa aguardar a conclusão de todos os consumidores.

Entretanto, o fluxo de negócio pode se tornar menos explícito. Quando vários componentes reagem a eventos sucessivos, compreender o processamento completo exige boa documentação e observabilidade.

**Cuidado:** substituir chamadas diretas por eventos não elimina o acoplamento quando os consumidores dependem de detalhes internos, de uma ordem rígida de execução ou de alterações coordenadas nos contratos.

## 5. Entrega, duplicidade e ordenação

Em sistemas de mensageria, é necessário considerar que eventos podem chegar atrasados, ser entregues mais de uma vez ou apresentar falhas de processamento.

As garantias dependem da infraestrutura e da configuração adotadas.

Alguns conceitos são particularmente relevantes:

| Conceito | Significado |
|---|---|
| **Entrega pelo menos uma vez (*at-least-once*)** | Uma mensagem pode ser entregue novamente; duplicidades precisam ser consideradas |
| **Entrega no máximo uma vez (*at-most-once*)** | Uma mensagem pode não ser entregue, mas não é repetida pelo mecanismo de entrega |
| **Idempotência** | O processamento repetido não deve multiplicar indevidamente os efeitos |
| **Ordenação** | A sequência de processamento pode precisar ser preservada dentro de determinados limites |

Garantias de processamento *exatamente uma vez* (*exactly-once*) podem existir em escopos específicos, mas não devem ser confundidas com a garantia automática de que todos os efeitos de negócio ocorrerão uma única vez entre sistemas independentes.

**Cuidado:** presumir entrega única e ordem global sem verificar as garantias reais da plataforma é uma fonte frequente de inconsistências.

## 6. Consistência e evolução dos contratos

Quando diferentes componentes reagem a eventos em momentos distintos, suas informações podem não ser atualizadas simultaneamente.

Isso pode exigir **consistência eventual (*eventual consistency*)**, na qual os sistemas convergem para um estado coerente após o processamento das atualizações, desde que as condições necessárias sejam atendidas.

Também é importante evoluir os contratos dos eventos sem interromper consumidores existentes.

Alterações incompatíveis podem exigir versionamento, períodos de transição ou adaptação dos consumidores.

Além disso, publicar um evento e confirmar uma alteração no banco de dados são operações que precisam ser coordenadas para evitar situações em que apenas uma delas seja concluída. Padrões como **Outbox** ajudam a lidar com esse problema.

## 7. Quando a arquitetura orientada a eventos faz sentido?

A abordagem costuma ser útil quando um acontecimento precisa desencadear diferentes reações, quando consumidores podem processar informações de forma independente ou quando existe necessidade de absorver variações de carga.

Por outro lado, pode ser inadequada para fluxos simples que exigem resposta imediata, forte coordenação ou rastreamento direto, especialmente quando a organização não dispõe de infraestrutura e práticas operacionais adequadas.

Uma arquitetura híbrida frequentemente é a melhor escolha: chamadas diretas para operações que precisam de resposta imediata e eventos para comunicar acontecimentos a outros componentes.

**A lição central:** arquitetura orientada a eventos não significa apenas trocar APIs por mensagens. Significa organizar parte da colaboração entre sistemas em torno de fatos relevantes, aceitando os compromissos de consistência, entrega e observabilidade que essa escolha introduz.
