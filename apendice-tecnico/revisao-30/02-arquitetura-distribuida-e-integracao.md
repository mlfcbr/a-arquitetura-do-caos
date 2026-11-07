# Apêndice técnico — Engenharia por trás do caos

> **Bloco II — Arquitetura distribuída e integração**
>
> **STATUS: APROVADO PELO AUTOR.** Seleção e redação definitiva dos 32 conceitos aprovadas em 2026-11-07. Complemento independente; não altera a narrativa.

### 7. Monólitos e microsserviços

**O conceito:** Um monólito reúne diferentes funcionalidades em uma mesma unidade de implantação. Microsserviços dividem capacidades em serviços que podem ser implantados e evoluídos independentemente. Nenhuma dessas abordagens garante, por si só, uma boa arquitetura.

**Onde aparece:** Capítulo 3 — *Dividir para complicar*.

**Na história:** A Ordem fragmenta suas aplicações em busca de escalabilidade, autonomia e facilidade de manutenção. Entretanto, algumas divisões produzem serviços excessivamente dependentes e multiplicam a comunicação pela rede.

**Avaliação:** A fragmentação é uma escolha arquitetural legítima, mas foi aplicada sem considerar suficientemente as fronteiras de responsabilidade e os custos de integração.

**Lição:** Um monólito bem organizado pode ser superior a um conjunto de microsserviços fortemente acoplados. Distribuir componentes não significa distribuir responsabilidades corretamente.

### 8. Comunicação síncrona e assíncrona

**O conceito:** Na comunicação síncrona, uma operação aguarda a resposta de outra para prosseguir. Na assíncrona, o processamento pode continuar sem esperar imediatamente o resultado, frequentemente por meio de mensagens ou eventos.

**Onde aparece:** Capítulos 3 e 4.

**Na história:** A Ordem utiliza chamadas diretas entre serviços e filas de mensagens. Uma fila consegue receber solicitações mesmo quando o processamento posterior está indisponível. Entretanto, o recebimento de uma mensagem é confundido com a conclusão da operação de negócio.

**Avaliação:** A comunicação assíncrona oferece vantagens reais, mas exige controle sobre estados intermediários, falhas de processamento e confirmação de resultados.

**Lição:** Assincronia não elimina dependências. Ela modifica o momento e a forma como essas dependências precisam ser administradas.

### 9. Timeouts, retries e Circuit Breaker

**O conceito:** Três mecanismos ajudam a controlar falhas de comunicação:

- **Timeout:** estabelece um limite para aguardar uma resposta, sem necessariamente interromper o processamento remoto.
- **Retry:** repete uma operação após uma falha. Pode utilizar *backoff* (intervalos progressivamente maiores) e *jitter* (variação nesses intervalos) para reduzir sobrecargas.
- **Circuit Breaker:** interrompe temporariamente chamadas a uma dependência degradada, permitindo tentativas controladas de recuperação.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** Serviços da Ordem possuem limites de espera incompatíveis e repetem chamadas automaticamente. Quando a rede apresenta lentidão, as tentativas se acumulam e sobrecarregam componentes que já enfrentam dificuldades.

**Avaliação:** Os mecanismos foram configurados sem uma estratégia coordenada. A equipe reconhece a necessidade de contenção, mas a narrativa não confirma a implantação completa de um Circuit Breaker.

**Lição:** Insistir nem sempre aumenta a disponibilidade. Em sistemas distribuídos, saber quando esperar, repetir ou interromper uma chamada é parte fundamental da resiliência.

### 10. Idempotência

**O conceito:** Uma operação idempotente pode ser repetida sem multiplicar seus efeitos após a primeira execução bem-sucedida. Em APIs, uma chave de idempotência permite reconhecer solicitações equivalentes e recuperar resultados anteriores.

**Onde aparece:** Capítulo 4 — *A rede não assinou nenhum contrato*.

**Na história:** A repetição de uma solicitação produz um segundo comprovante. Em uma operação financeira, o mesmo comportamento poderia provocar uma cobrança duplicada. A Ordem utiliza uma chave de idempotência para reconhecer cobranças já processadas.

**Avaliação:** O mecanismo é bem aplicado no exemplo de cobrança. A duplicação dos comprovantes demonstra o risco de repetir operações sem controlar seus efeitos.

**Lição:** Uma resposta perdida não significa que a operação deixou de acontecer. O sistema precisa lidar com essa incerteza sem executar duas vezes uma consequência que deveria ocorrer apenas uma.

### 11. Consistência eventual e processamento de eventos

**O conceito:** Em sistemas distribuídos, componentes podem apresentar temporariamente versões diferentes de uma informação. A consistência eventual permite essa divergência enquanto mecanismos de propagação buscam a convergência. O processamento de eventos também precisa considerar mensagens duplicadas, atrasadas ou recebidas fora de ordem.

**Onde aparece:** Capítulos 3 e 4.

**Na história:** Um cadastro central contém um endereço atualizado enquanto serviços consumidores ainda utilizam informações antigas. Em outro incidente, uma confirmação de agendamento chega antes do evento de criação. A equipe considera versões crescentes por agendamento e mecanismos de reconciliação para restaurar a coerência.

**Avaliação:** Aceitar divergências temporárias pode ser adequado. O problema está em não definir quais operações toleram dados desatualizados e em presumir que a ordem de chegada das mensagens representa a ordem lógica dos acontecimentos.

**Lição:** Consistência não significa obrigatoriamente atualização instantânea. Significa conhecer as garantias necessárias para que o sistema produza resultados corretos, mesmo diante de atrasos e mensagens fora de ordem.

### 12. Observabilidade e reconciliação de estados

**O conceito:** Observabilidade é a capacidade de compreender o comportamento de um sistema por meio de métricas, registros e rastreamentos. Reconciliação é a comparação e correção de estados divergentes após falhas ou atrasos. Juntas, essas práticas ajudam a distinguir recuperação aparente de recuperação efetiva.

**Onde aparece:** Capítulos 3, 4, 9 e 10.

**Na história:** Serviços da Ordem apresentam indicadores satisfatórios enquanto operações dos cidadãos falham. Após um incidente de rede, os componentes voltam a responder, mas ainda existem mensagens pendentes. Mais tarde, uma rotina crítica é descoberta fora do monitoramento central.

**Avaliação:** A Ordem inicialmente observa componentes isolados e confunde servidores disponíveis com operações concluídas. O acompanhamento dos fluxos completos e a reconciliação dos estados melhoram a capacidade de detectar e corrigir problemas.

**Lição:** Um sistema não está recuperado apenas porque seus servidores voltaram a funcionar. É preciso verificar se as operações foram concluídas e se os dados permanecem coerentes.
