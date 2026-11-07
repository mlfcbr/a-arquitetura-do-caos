# Comunicação síncrona e assíncrona — Quando esperar e quando continuar

*Nem toda operação precisa de uma resposta imediata. Mas toda comunicação precisa lidar com a possibilidade de falha.*

Sistemas precisam trocar informações para executar processos de negócio. Essa comunicação pode ocorrer de maneira síncrona ou assíncrona, dependendo de como os participantes coordenam suas atividades e aguardam resultados.

A escolha influencia o tempo de resposta, o acoplamento, a resiliência e a complexidade operacional.

Nenhuma abordagem é superior em todos os cenários. Muitas arquiteturas combinam as duas.

## 1. Comunicação síncrona — O resultado é necessário agora?

Na **comunicação síncrona (*synchronous communication*)**, uma operação depende da conclusão de outra para prosseguir. O solicitante aguarda o resultado da interação.

Esse modelo é comum em chamadas HTTP a APIs, consultas e validações que precisam fornecer uma resposta durante a execução de uma solicitação.

Sua principal vantagem é a simplicidade de acompanhar uma operação cujo resultado está imediatamente disponível.

Entretanto, o solicitante pode ficar dependente da disponibilidade e do tempo de resposta do serviço chamado.

**Cuidado:** uma sequência longa de chamadas síncronas pode aumentar a latência e fazer com que a falha de um serviço afete toda a operação.

## 2. Comunicação assíncrona — O trabalho pode continuar depois?

Na **comunicação assíncrona (*asynchronous communication*)**, o solicitante não precisa aguardar a conclusão do processamento para continuar sua própria execução.

A operação pode ser encaminhada por mensagens, filas ou outros mecanismos, permitindo que o processamento ocorra posteriormente.

Esse modelo é útil para atividades demoradas, processamento em lote, integração entre sistemas e tarefas que não precisam apresentar um resultado definitivo imediatamente.

Também pode ajudar a absorver variações de carga e reduzir dependências temporais entre componentes.

**Cuidado:** comunicação assíncrona não elimina falhas. Ela introduz desafios como mensagens duplicadas, atrasos, reprocessamento, ordenação e acompanhamento do estado das operações.

## 3. Assíncrono não significa necessariamente orientado a eventos

Embora frequentemente associados, esses conceitos não são equivalentes.

Uma **fila de comandos** pode transportar solicitações de execução assíncrona, como “gerar relatório”.

Já um **evento** normalmente comunica algo que aconteceu, como “relatório gerado”, permitindo que outros componentes reajam ao fato.

Além disso, uma operação pode utilizar comunicação assíncrona sem adotar uma arquitetura orientada a eventos.

Essa distinção é importante porque comandos e eventos expressam intenções diferentes e produzem formas distintas de acoplamento.

## 4. Comparação entre os modelos

| Característica | Síncrona | Assíncrona |
|---|---|---|
| Resposta | Geralmente durante a chamada | Pode ocorrer posteriormente |
| Dependência temporal | Maior | Geralmente menor |
| Tratamento de falhas | Frequentemente imediato | Pode exigir reprocessamento |
| Acompanhamento | Fluxo mais direto | Exige controle de estados |
| Uso comum | Consultas e validações imediatas | Lotes, tarefas demoradas e integrações |

A comunicação assíncrona pode melhorar a resiliência, mas não garante maior desempenho nem menor complexidade. O benefício depende da implementação e das características do processo.

## 5. Falhas, tempo limite e retentativas

Em sistemas distribuídos, uma chamada pode falhar, demorar além do esperado ou ser concluída sem que o solicitante receba a confirmação.

Por isso, a comunicação síncrona frequentemente utiliza **tempo limite (*timeout*)**, que determina quanto tempo uma operação pode aguardar.

Também pode utilizar **retentativas (*retries*)**, que repetem operações após determinadas falhas.

Na comunicação assíncrona, mecanismos semelhantes podem ser aplicados ao processamento e à entrega de mensagens.

Entretanto, repetir uma operação pode gerar efeitos duplicados. Para operações com efeitos relevantes, é necessário considerar **idempotência (*idempotency*)**, propriedade que permite repetir uma solicitação sem multiplicar indevidamente seus efeitos.

**Cuidado:** retentativas indiscriminadas podem sobrecarregar serviços já instáveis. Elas precisam considerar limites, intervalos e quais falhas realmente justificam uma nova tentativa.

## 6. Consistência e acompanhamento do processamento

Na comunicação síncrona, o usuário frequentemente recebe o resultado da operação no mesmo fluxo de interação.

Em processos assíncronos, pode ser necessário informar que a solicitação foi recebida, está em processamento, foi concluída ou apresentou falha.

Isso exige mecanismos de acompanhamento, como consultas de situação, notificações ou eventos de conclusão.

Também é necessário distinguir **aceitar uma solicitação** de **concluir o processamento**. Uma resposta confirmando o recebimento não garante que a operação tenha sido executada com sucesso.

Quando diferentes sistemas atualizam informações em momentos distintos, pode existir um período de inconsistência temporária que precisa ser considerado pelas regras de negócio.

## 7. Quando utilizar cada abordagem?

A comunicação síncrona tende a ser adequada quando a próxima etapa depende imediatamente de uma resposta, como uma autorização que precisa ser confirmada antes de concluir uma operação.

A comunicação assíncrona costuma fazer sentido quando o processamento é demorado, pode ocorrer posteriormente ou precisa absorver picos de demanda.

Em muitos casos, a melhor solução é híbrida: uma chamada síncrona recebe e valida a solicitação, enquanto etapas demoradas são executadas de forma assíncrona.

**A lição central:** a escolha entre comunicação síncrona e assíncrona não deve seguir uma preferência tecnológica. Deve refletir quando o resultado é necessário, quais falhas são aceitáveis e como o sistema acompanhará a conclusão do trabalho.
