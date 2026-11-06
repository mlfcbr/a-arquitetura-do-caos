# Por trás do caos — Capítulo 4

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 4 — A rede não assinou nenhum contrato](../manuscrito/04-a-rede-nao-assinou-nenhum-contrato-parte-1.md). A narrativa aprovada permanece inalterada.

A rede não precisa estar indisponível para que um sistema distribuído falhe. Basta uma resposta demorar, uma mensagem chegar fora de ordem ou um serviço interpretar incorretamente o resultado de outro.

**Timeouts, retries e circuit breaker.** Um *timeout* limita quanto tempo uma operação espera. Um *retry* tenta novamente após uma falha, mas repetições descontroladas podem agravar a sobrecarga. Estratégias como *exponential backoff* (intervalos progressivamente maiores), *jitter* (variação aleatória dos intervalos) e *circuit breaker* (interrupção temporária de chamadas a uma dependência problemática) ajudam a conter falhas em cascata.

**Idempotência e processamento distribuído.** Uma operação idempotente pode ser repetida sem multiplicar seus efeitos. No exemplo da cobrança, a chave de idempotência (*idempotency key*) permite reconhecer uma solicitação já processada e evitar uma segunda cobrança. Isso é especialmente importante quando a resposta se perde e o solicitante não sabe se a operação foi concluída.

**Consistência eventual e observabilidade ponta a ponta.** Em fluxos assíncronos, diferentes componentes podem apresentar temporariamente estados distintos. Eventos duplicados ou fora de ordem exigem mecanismos como versionamento e reconciliação. Já a observabilidade deve acompanhar a operação completa, não apenas a disponibilidade individual dos serviços.

A recuperação também faz parte da arquitetura: servidores disponíveis não significam que mensagens pendentes, estados inconsistentes e solicitações dos usuários já foram resolvidos.
