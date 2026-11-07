# Resiliência, idempotência e observabilidade — Quando o sistema precisa sobreviver às próprias falhas

*Um sistema pode ter todos os componentes funcionando e, ainda assim, fracassar quando eles precisam trabalhar juntos.*

Em sistemas distribuídos, a confiabilidade não depende apenas de cada componente funcionar isoladamente. Depende também de como o conjunto reage a atrasos, indisponibilidades, mensagens duplicadas e comportamentos inesperados.

Três conceitos ajudam a compreender esses desafios: **resiliência**, **idempotência** e **observabilidade**.

Eles não impedem todas as falhas, mas permitem reduzir seus impactos, evitar efeitos indevidos e compreender o que aconteceu.

## 1. Resiliência — Falhar sem provocar um desastre

A **resiliência (*resilience*)** é a capacidade de um sistema lidar com falhas e perturbações, mantendo ou recuperando suas funções essenciais dentro de limites aceitáveis.

Em uma arquitetura distribuída, um serviço pode ficar indisponível, responder lentamente ou apresentar falhas intermitentes.

Uma aplicação resiliente não pressupõe que todas as dependências estarão sempre disponíveis. Ela considera antecipadamente como reagir quando algo deixa de funcionar.

Alguns mecanismos comuns são:

| Mecanismo | Finalidade |
|---|---|
| **Tempo limite (*timeout*)** | Evitar que uma operação aguarde indefinidamente |
| **Retentativa (*retry*)** | Repetir uma operação quando a falha pode ser temporária |
| **Disjuntor (*Circuit Breaker*)** | Interromper temporariamente chamadas a uma dependência com falhas recorrentes |
| **Isolamento de recursos (*Bulkhead*)** | Evitar que a sobrecarga de uma parte comprometa todo o sistema |
| **Degradação controlada (*graceful degradation*)** | Manter funcionalidades essenciais mesmo com recursos indisponíveis |

Esses mecanismos devem ser aplicados conforme o contexto. Repetir operações indiscriminadamente, por exemplo, pode agravar a sobrecarga de um serviço já instável.

**Cuidado:** resiliência não significa esconder falhas. Significa controlar suas consequências e preservar o comportamento esperado sempre que possível.

## 2. Idempotência — Repetir sem multiplicar o problema

A **idempotência (*idempotency*)** é a propriedade pela qual executar uma operação novamente produz o mesmo efeito relevante que executá-la uma única vez.

Imagine uma solicitação de cobrança enviada a um serviço externo. A cobrança é realizada, mas a confirmação se perde devido a uma falha de comunicação.

O sistema solicitante não sabe se a operação foi concluída e decide tentar novamente.

Sem mecanismos adequados, a nova tentativa pode produzir uma segunda cobrança.

Com idempotência, o serviço reconhece que aquela operação já foi processada e evita repetir seu efeito.

Uma estratégia comum é utilizar um **identificador único da operação**, associado ao resultado do processamento. Novas solicitações com o mesmo identificador são tratadas de acordo com o resultado previamente registrado.

Entretanto, a implementação precisa considerar concorrência, persistência e o período durante o qual esse identificador será reconhecido.

**Cuidado:** idempotência não significa que toda chamada produzirá uma resposta idêntica. O objetivo principal é impedir que repetições indevidas multipliquem os efeitos da operação.

## 3. Observabilidade — Entender o que o sistema está fazendo

A **observabilidade (*observability*)** é a capacidade de compreender o estado interno e o comportamento de um sistema a partir das informações que ele disponibiliza.

Em aplicações distribuídas, uma falha pode envolver vários serviços, bancos de dados e componentes de infraestrutura.

Saber apenas que uma operação falhou costuma ser insuficiente. É necessário compreender onde, quando e por que o problema ocorreu.

Três fontes de informação são especialmente importantes:

| Fonte | O que permite compreender |
|---|---|
| **Logs** | Registros de acontecimentos e operações |
| **Métricas** | Medidas quantitativas, como latência, erros e consumo de recursos |
| **Rastreamento distribuído (*distributed tracing*)** | Percurso de uma operação entre diferentes componentes |

Essas informações se complementam. Uma métrica pode indicar aumento de erros; um rastreamento pode localizar a etapa problemática; os logs podem fornecer detalhes relevantes para investigar sua causa.

**Cuidado:** coletar grandes volumes de dados não garante observabilidade. Informações precisam ser úteis, correlacionáveis e acessíveis, respeitando requisitos de segurança e privacidade.

## 4. Quando tudo funciona separadamente, mas o conjunto falha

Uma dificuldade característica dos sistemas distribuídos é que a disponibilidade individual dos componentes não garante o sucesso de um processo completo.

Uma operação pode depender de diversos serviços, cada um com suas próprias falhas, limites e tempos de resposta.

Mesmo quando todos apresentam bons indicadores isoladamente, a combinação de dependências pode resultar em uma experiência ruim para o usuário.

Por isso, a confiabilidade precisa ser avaliada também **de ponta a ponta (*end-to-end*)**, considerando a conclusão efetiva das operações de negócio.

Não basta medir se os servidores estão disponíveis. É necessário verificar se os usuários conseguem realizar aquilo que o sistema deveria permitir.

## 5. Confiabilidade exige decisões de negócio

Nem todas as operações possuem a mesma criticidade.

Uma falha temporária no envio de uma notificação pode ser tolerável. Uma cobrança duplicada, uma autorização incorreta ou a perda de uma transação podem produzir consequências muito mais graves.

A arquitetura precisa refletir essas diferenças.

Isso envolve definir quais operações podem ser repetidas, quais exigem confirmação, quais podem aguardar processamento posterior e quais precisam ser interrompidas diante de incerteza.

Também envolve estabelecer critérios para recuperação, tratamento de erros e comunicação com o usuário.

**Cuidado:** mecanismos técnicos de resiliência não substituem regras de negócio. Uma retentativa tecnicamente correta pode ser inadequada se provocar um efeito que o negócio não permite repetir.

## 6. O equilíbrio entre proteção e complexidade

É possível tornar um sistema excessivamente complexo tentando protegê-lo contra todas as falhas imagináveis.

Cada mecanismo introduz configurações, estados e comportamentos que também precisam ser compreendidos e mantidos.

A decisão deve considerar a probabilidade da falha, seu impacto e o custo da proteção.

Sistemas críticos podem justificar mecanismos sofisticados. Aplicações simples talvez precisem apenas de limites de tempo, tratamento adequado de erros e monitoramento básico.

**A lição central:** sistemas confiáveis não são aqueles que nunca falham. São aqueles que reconhecem a possibilidade de falha, evitam multiplicar seus efeitos e oferecem informações suficientes para compreender e recuperar o funcionamento esperado.
