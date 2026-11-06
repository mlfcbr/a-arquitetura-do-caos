# Apêndice técnico — Engenharia por trás do caos

> **Parte II — Arquitetura distribuída e integração**
>
> **STATUS: APROVADO PELO AUTOR.** Complemento independente. Não altera a narrativa.

## 10. Monólitos e microsserviços

**O conceito:** Um monólito reúne funcionalidades em uma unidade de implantação. Microsserviços dividem capacidades em serviços que podem ser implantados e evoluídos independentemente, desde que suas fronteiras e dependências sejam adequadamente definidas.

**Onde aparece:** Capítulo 3 — *Dividir para complicar*.

**Na história:** A Ordem fragmenta aplicações para obter escalabilidade, autonomia e facilidade de manutenção. Entretanto, algumas divisões criam serviços excessivamente dependentes e multiplicam a comunicação pela rede.

**Avaliação:** Trade-off legítimo, prejudicado pela fragmentação excessiva e pela falta de fronteiras claras.

**Lição:** Microsserviços não são uma evolução obrigatória dos monólitos. Um monólito modular pode ser mais simples e adequado, dependendo das necessidades do sistema.

## 11. Comunicação síncrona e assíncrona

**O conceito:** Na comunicação síncrona, uma operação depende da resposta de outra para prosseguir. Na comunicação assíncrona, o processamento pode continuar sem aguardar imediatamente o resultado, frequentemente utilizando mensagens ou eventos.

**Onde aparece:** Capítulos 3 e 4.

**Na história:** A Ordem utiliza chamadas entre serviços e filas de mensagens. Uma fila permite receber solicitações mesmo quando o processamento posterior está indisponível, mas a confirmação de recebimento não garante que a atualização de negócio tenha sido concluída.

**Avaliação:** A comunicação assíncrona é uma escolha legítima. O problema surge quando os componentes confundem entrega de mensagens com conclusão da operação.

**Lição:** Assincronia não elimina dependências; altera como elas se manifestam e precisam ser controladas.

## 12. Timeouts — limites de espera

**O conceito:** Um timeout estabelece quanto tempo uma operação aguardará antes de considerar que não recebeu uma resposta dentro do prazo esperado. Ele não garante que o processamento remoto tenha sido interrompido.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** Serviços possuem limites de espera incompatíveis. Um componente desiste de aguardar enquanto outro continua processando a solicitação, consumindo recursos e ampliando a sobrecarga.

**Avaliação:** Configuração inadequada dos limites de espera entre serviços dependentes.

**Lição:** Os timeouts precisam considerar a operação completa, suas dependências e o tempo disponível para entregar o resultado.

## 13. Retries, backoff e jitter

**O conceito:** Retry é a repetição de uma operação após uma falha. Backoff aumenta o intervalo entre tentativas, enquanto jitter introduz variação para evitar que muitos clientes repitam chamadas simultaneamente.

**Onde aparece:** Capítulos 3 e 4.

**Na história:** Diferentes serviços repetem automaticamente suas chamadas. Quando uma conexão apresenta lentidão, as tentativas se acumulam e ampliam a carga sobre componentes que já estão sobrecarregados.

**Avaliação:** Violação de uma estratégia coordenada de recuperação. As tentativas são configuradas localmente sem considerar seus efeitos sobre o conjunto.

**Lição:** Repetir uma operação pode aumentar a disponibilidade em falhas transitórias, mas também pode transformar uma lentidão em uma indisponibilidade generalizada.

## 14. Circuit Breaker — disjuntor de chamadas

**O conceito:** Circuit Breaker é um padrão de resiliência que interrompe temporariamente chamadas a uma dependência quando identifica falhas ou degradação acima de determinados critérios. Após um período, pode permitir tentativas controladas para verificar a recuperação.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** A equipe reconhece a necessidade de limitar chamadas quando uma dependência está sobrecarregada, em vez de permitir que todos os consumidores continuem insistindo.

**Avaliação:** O princípio é considerado como medida de contenção. A narrativa não demonstra uma implementação completa do padrão; portanto, não é possível afirmar que o Circuit Breaker foi efetivamente implantado.

**Lição:** Em sistemas distribuídos, interromper temporariamente chamadas pode proteger o conjunto. Persistir indefinidamente nem sempre é a opção mais resiliente.

## 15. Idempotência

**O conceito:** Uma operação idempotente pode ser repetida sem multiplicar seus efeitos após a primeira execução bem-sucedida. Em APIs, chaves de idempotência ajudam a identificar solicitações equivalentes e recuperar resultados previamente registrados.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** A repetição de uma solicitação gera um segundo comprovante. Em operações financeiras, o mesmo comportamento poderia causar uma cobrança duplicada. A Ordem utiliza uma chave de idempotência para reconhecer cobranças já processadas e devolver o resultado anterior.

**Avaliação:** Bem aplicada no exemplo de cobrança. A geração duplicada de comprovantes demonstra o risco de repetir operações sem considerar seus efeitos.

**Lição:** Uma resposta perdida não significa que a operação falhou. Sistemas precisam tratar a incerteza sem executar novamente consequências que já ocorreram.

## 16. Consistência eventual

**O conceito:** Em sistemas distribuídos, diferentes componentes podem apresentar temporariamente versões distintas de uma informação. Consistência eventual significa que essas versões tendem a convergir quando as atualizações deixam de ocorrer e os mecanismos de propagação funcionam conforme suas garantias.

**Onde aparece:** Capítulos 3 e 4.

**Na história:** O cadastro central contém um endereço atualizado, enquanto serviços consumidores ainda utilizam informações antigas. A independência dos componentes favorece determinadas operações, mas exige mecanismos para lidar com estados temporariamente divergentes.

**Avaliação:** Trade-off legítimo. O problema não é aceitar diferenças temporárias, mas deixar de definir quais operações podem tolerá-las.

**Lição:** Nem toda informação precisa estar imediatamente sincronizada. Mas o sistema deve conhecer as consequências de utilizar dados desatualizados.

## 17. Ordenação, duplicação e versionamento de eventos

**O conceito:** Sistemas orientados a eventos precisam considerar mensagens duplicadas, atrasadas, ausentes ou recebidas fora de ordem. Identificadores, versões e regras de processamento ajudam a preservar a coerência do estado.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** Uma confirmação de agendamento chega ao serviço de notificações antes do evento que informa sua criação. O consumidor processa as mensagens na ordem de chegada e produz um resultado incorreto. A equipe propõe versões crescentes por agendamento e mecanismos de reconciliação.

**Avaliação:** A implementação inicial viola as necessidades de ordenação do domínio. A proposta de versionamento melhora o controle, mas ainda precisa tratar lacunas e duplicações.

**Lição:** Receber uma mensagem corretamente não significa interpretá-la corretamente. A ordem de entrega não deve ser confundida com a ordem lógica dos acontecimentos.

## 18. Observabilidade ponta a ponta

**O conceito:** Observabilidade é a capacidade de compreender o estado e o comportamento de um sistema a partir de evidências como métricas, logs e rastreamentos. Em sistemas distribuídos, é especialmente importante correlacionar os componentes envolvidos em uma operação completa.

**Onde aparece:** Capítulos 3, 4, 9 e 10.

**Na história:** Os serviços da Ordem apresentam indicadores individuais satisfatórios enquanto operações dos cidadãos falham. Mais tarde, ÍRIS identifica uma divergência contábil que não afetava a soma dos valores, mas comprometia sua classificação. No último capítulo, uma rotina crítica sequer constava do monitoramento central.

**Avaliação:** Inicialmente, a Ordem monitora componentes sem compreender suficientemente os resultados do conjunto. A situação melhora com rastreabilidade, alertas e acompanhamento dos fluxos completos.

**Lição:** Disponibilidade de servidores não é sinônimo de sucesso da operação. É necessário observar o caminho percorrido e o resultado efetivamente produzido.

## 19. Recuperação e reconciliação de estados

**O conceito:** Recuperar um sistema distribuído exige tratar operações pendentes, mensagens acumuladas e possíveis divergências entre componentes. Reconciliação é o processo de comparar estados e corrigir diferenças segundo regras estabelecidas.

**Onde aparece:** Capítulos 4 e 10.

**Na história:** Após o incidente de rede, os servidores voltam a responder, mas ainda existem mensagens pendentes e operações que precisam ser reconciliadas. No capítulo 10, a Compensação de Continuidade demonstra como a reconciliação pode se tornar uma dependência permanente quando os problemas de origem não são resolvidos.

**Avaliação:** A recuperação do capítulo 4 evolui para uma abordagem mais completa. No capítulo 10, a reconciliação é necessária, mas seu uso contínuo revela fragilidade estrutural.

**Lição:** A recuperação termina quando os efeitos relevantes da falha foram tratados, não simplesmente quando os componentes voltam a responder.
