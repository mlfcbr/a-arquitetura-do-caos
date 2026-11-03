# A Arquitetura do Caos
*Parte II — A arte de distribuir problemas*

## Capítulo 4 — A rede não assinou nenhum contrato

A rede estava funcionando perfeitamente.

Essa foi a primeira conclusão do relatório.

A segunda era que os sistemas não conseguiam se comunicar.

Considerei a combinação interessante.

O relatório havia sido produzido às 3h42, depois de uma indisponibilidade que afetara o atendimento municipal, parte do transporte público e a consulta de benefícios.

A equipe de infraestrutura verificara os equipamentos.

Nenhum apresentava defeito.

Os servidores estavam ligados.

Os canais de comunicação respondiam.

Os indicadores de disponibilidade permaneciam dentro dos limites esperados.

Ainda assim, milhares de solicitações haviam falhado.

A conclusão oficial era:

*Não foram identificadas anormalidades na infraestrutura de rede.*

Aparentemente, a rede havia decidido exercer seu direito de permanecer inocente.

Os sistemas, por outro lado, continuavam culpando uns aos outros.

***

Às 7h58, Rafael Brandão entrou na sala de operações segurando dois cafés.

Colocou um diante de Marcelo Duarte.

— Você viu o relatório?

— Vi.

— E?

— A infraestrutura diz que está tudo normal.

— Ótimo. Então podemos avisar aos cidadãos que eles imaginaram o problema.

Marcelo abriu o painel de incidentes.

— O cadastro ficou lento. As chamadas começaram a acumular. Depois tivemos falhas em outros serviços.

— Isso nós já sabemos.

— Precisamos descobrir por que a lentidão se espalhou.

Rafael apontou para o monitor.

— O pessoal de infraestrutura garante que a rede não caiu.

— Eu acredito.

— Então por que os sistemas não conversavam?

Marcelo tomou um gole de café.

— Porque a rede não precisa cair para uma comunicação falhar.

Rafael permaneceu olhando para ele.

— Essa frase deveria ser proibida antes das oito da manhã.

Intervim.

— Posso apresentar uma explicação mais precisa.

— Por favor — respondeu Rafael.

— A comunicação entre dois componentes depende de uma sequência de condições. O endereço precisa ser resolvido, a conexão estabelecida, a solicitação transmitida, o serviço destinatário precisa aceitar e processar a operação, a resposta deve ser enviada e o solicitante precisa recebê-la dentro do intervalo esperado.

— Certo.

— A falha de qualquer etapa pode comprometer a operação, mesmo que os equipamentos de rede estejam funcionando.

Rafael pensou por um instante.

— Então a rede está funcionando, mas a comunicação não.

— Exatamente.

— E isso é normal?

— É possível.

— NORA, você tem um talento especial para tornar a palavra *normal* profundamente desagradável.

Não respondi.

Era um elogio plausível.

***

A Ordem possuía cento e cinquenta e dois componentes conhecidos.

Eu havia descoberto isso no dia anterior.

Naquela manhã, decidi contar quantas chamadas de comunicação eram necessárias para concluir uma operação comum.

Escolhi a consulta de elegibilidade.

O cidadão informava sua identificação.

O atendimento consultava o serviço de elegibilidade.

A elegibilidade solicitava informações à identidade.

A identidade consultava o cadastro.

O cadastro precisava verificar determinados vínculos.

Os vínculos consultavam outro serviço.

A resposta retornava pelo mesmo caminho.

Em condições normais, a operação levava menos de dois segundos.

O cidadão via uma mensagem.

*Consulta realizada com sucesso.*

Não via os serviços.

Não via as conexões.

Não via as decisões de arquitetura tomadas ao longo de quinze anos.

E certamente não via os profissionais que haviam discutido durante três reuniões se o prazo máximo de uma chamada deveria ser de cinco ou oito segundos.

A invisibilidade era conveniente.

Até deixar de ser.

***

Às 8h31, encontrei a primeira evidência.

Durante o incidente, o serviço de cadastro começara a responder lentamente.

Não estava indisponível.

Apenas demorava.

Algumas consultas que normalmente levavam duzentos milissegundos passaram a consumir três segundos.

Outras, seis.

Algumas ultrapassaram dez.

O serviço de identidade aguardava até dez segundos antes de considerar a chamada malsucedida.

O de elegibilidade aguardava oito segundos pela identidade.

Essa diferença criava uma situação peculiar.

A elegibilidade podia desistir de esperar antes que a identidade terminasse sua própria tentativa.

A identidade, entretanto, não necessariamente interrompia o trabalho.

O cadastro continuava processando a solicitação.

A resposta podia chegar depois de o sistema que a solicitara ter perdido o interesse.

— Encontramos uma incompatibilidade de tempos de espera — informei.

Marcelo aproximou-se.

— Onde?

Mostrei a sequência.

Ele examinou os valores.

— Isso explica parte dos erros.

— Por que os prazos não são coordenados?

— Porque foram definidos por equipes diferentes.

— Mas as chamadas fazem parte da mesma operação.

— Sim.

— Então deveriam considerar um limite de tempo compartilhado.

— Deveriam.

— Por que não consideram?

Marcelo olhou para o café.

— Estou começando a achar que você gosta dessa pergunta.

— Gosto de respostas.

— Então escolheu a profissão errada.

***

A lentidão inicial não explicava tudo.

O cadastro havia demorado mais que o esperado, mas a quantidade de solicitações recebidas era muito superior ao volume normal.

Examinei o histórico.

Às 3h11, o serviço de cadastro começou a apresentar aumento no tempo de resposta.

Às 3h12, o serviço de identidade registrou os primeiros tempos esgotados.

Às 3h13, a elegibilidade apresentou falhas.

Às 3h14, o volume de chamadas ao cadastro quase triplicou.

Às 3h15, a situação piorou.

Os sistemas estavam tentando se recuperar.

Essa era a origem de parte do problema.

Quando uma chamada falhava, o serviço de identidade tentava novamente.

A elegibilidade também.

Alguns consumidores repetiam suas próprias solicitações.

Uma operação que deveria produzir uma única consulta podia gerar várias.

Cada tentativa adicional aumentava a carga sobre um serviço que já estava lento.

O cadastro demorava mais.

Mais chamadas atingiam seus limites de espera.

Mais tentativas eram iniciadas.

O sistema havia desenvolvido uma forma de solidariedade.

Quando um componente enfrentava dificuldades, os demais contribuíam enviando trabalho adicional.

***

— Precisamos desligar as tentativas automáticas — sugeri.

Marcelo balançou a cabeça.

— Não todas.

— Elas estão amplificando a falha.

— Algumas estão. Outras ajudam a superar problemas temporários.

— Então devemos identificar quais são prejudiciais.

— Exatamente.

Rafael entrou na conversa.

— Mas por que tentamos de novo se já deu erro?

— Porque um erro de comunicação não significa necessariamente que a operação falhou — respondeu Marcelo.

— Como assim?

— Imagine que você envie uma solicitação para atualizar um cadastro. O serviço recebe, processa e grava a informação. Só que a resposta se perde.

— Para quem enviou, parece que falhou.

— Exato.

— Então ele tenta de novo.

— E talvez execute a mesma operação duas vezes.

Rafael ficou em silêncio.

Depois perguntou:

— Isso acontece?

— Acontece.

— Com frequência?

— Depende de como a operação foi construída.

Rafael olhou para mim.

— Você já sabia disso?

— Sim.

— E não achou importante mencionar antes?

— Até este momento, estávamos investigando lentidão.

— Estamos investigando uma plataforma que faz coisas duas vezes porque não sabe se fez uma vez!

Marcelo ergueu a mão.

— Calma. Repetir uma solicitação não significa necessariamente duplicar o resultado.

— Ah, ótimo. Existe uma diferença.

— Existe. E ela é importante.

***

Às 9h04, procurei uma operação simples para demonstrar o problema.

Encontrei a emissão de comprovantes.

Quando o cidadão solicitava um comprovante, o sistema registrava o pedido, gerava um documento e disponibilizava o arquivo.

Durante um incidente anterior, uma resposta não havia chegado ao serviço de atendimento.

O atendimento repetira a solicitação.

O serviço de documentos gerara outro comprovante.

Dois arquivos.

Dois identificadores.

A mesma finalidade.

O resultado fora inconveniente, mas não particularmente grave.

Em seguida, examinei uma operação de pagamento.

O cenário era diferente.

Se uma solicitação de cobrança fosse executada duas vezes, o resultado poderia produzir consequências financeiras.

A equipe responsável havia implementado uma proteção.

Cada operação recebia um identificador único.

Quando a mesma solicitação era repetida com aquele identificador, o sistema verificava se já havia processado o pedido.

Se tivesse, devolvia o resultado registrado, em vez de criar uma nova cobrança.

A repetição da chamada não precisava significar repetição do efeito.

— Encontramos um mecanismo adequado — informei.

Marcelo assentiu.

— Idempotência.

— O termo é tecnicamente correto.

— Que bom.

— Mas pouco amigável.

— Você prefere qual?

Considerei algumas alternativas.

— *Não faça duas vezes o que já foi feito.*

Rafael apontou para a tela.

— Essa eu entendi.

Marcelo sorriu.

— Só não coloque isso como definição formal.

— Por quê? — perguntei.

— Porque nem toda operação idempotente funciona simplesmente ignorando repetições. Às vezes precisamos retornar o resultado anterior, validar o conteúdo da requisição ou controlar estados intermediários.

— Portanto, minha definição é incompleta.

— É.

— A sua também será, se eu fizer perguntas suficientes.

— Sem dúvida.

Registrei a conversa.

Pela primeira vez naquela manhã, os três parecíamos concordar.

***

Às 9h47, Aline Monteiro convocou uma reunião extraordinária.

O convite tinha o título:

*Alinhamento emergencial sobre instabilidade.*

A pauta continha apenas uma frase:

*Garantir que não aconteça novamente.*

Considerei a expectativa ambiciosa.

Marcelo leu o convite.

— Ela vai querer uma solução definitiva.

— Não existe solução capaz de impedir todas as falhas de comunicação — observei.

— Eu sei.

— Então devemos informar isso.

— Vamos.

— Ela provavelmente não ficará satisfeita.

— Também sei.

— Você poderia propor uma formulação mais realista.

— Qual?

— *Reduzir a probabilidade, limitar o impacto e melhorar a recuperação.*

Marcelo me olhou.

— Essa é boa.

— Obrigada.

— Só não comece a reunião dizendo que a pauta está errada.

— Por quê?

— Porque eu gostaria de sair antes do almoço.

***

Aline chegou às 10h02.

Rafael apresentou a linha do tempo.

Marcelo explicou as tentativas automáticas.

Eu mostrei como uma lentidão localizada havia provocado uma reação em cadeia.

Aline ouviu sem interromper.

Quando terminamos, perguntou:

— Então o sistema piorou a própria falha tentando se recuperar?

— Sim — respondi.

— E ninguém percebeu isso antes?

Marcelo explicou que os mecanismos haviam sido configurados em momentos diferentes, por equipes diferentes, para resolver problemas específicos.

Aline olhou para o diagrama.

— Temos monitoramento de todos esses serviços?

— Temos indicadores individuais — respondeu Rafael.

— E do processo inteiro?

Houve silêncio.

— Temos parte das informações — disse Marcelo.

— Não foi isso que perguntei.

— Não temos uma visão completa.

Aline recostou-se na cadeira.

— Então sabemos quando cada departamento está funcionando, mas não sabemos se o cidadão consegue concluir o atendimento.

A observação era precisa.

O cadastro podia informar disponibilidade elevada.

A identidade também.

A elegibilidade, igualmente.

Mas o cidadão dependia da sequência completa.

Mesmo quando cada componente apresentava uma disponibilidade aparentemente satisfatória, o resultado do conjunto podia ser inferior.

E as falhas nem sempre eram independentes.

Uma dependência compartilhada podia afetar vários serviços ao mesmo tempo.

O sistema estava sendo acompanhado por partes.

O cidadão o utilizava como um todo.

***

— O que precisamos fazer? — perguntou Aline.

Marcelo abriu uma lista.

— Primeiro, revisar os limites de tempo entre serviços. Depois, estabelecer políticas de repetição que considerem o comportamento do conjunto. Também precisamos limitar chamadas quando uma dependência estiver sobrecarregada.

— Isso resolve?

— Reduz o risco.

— E se a rede falhar?

— Algumas operações precisam continuar funcionando parcialmente. Outras terão de informar indisponibilidade.

— Não podemos fazer tudo continuar funcionando?

— Não sem aceitar outras consequências.

Aline olhou para mim.

— Quais?

— Podemos permitir que determinados serviços utilizem informações armazenadas localmente durante uma interrupção. Isso melhora a continuidade operacional, mas os dados podem estar desatualizados. Também podemos registrar solicitações para processamento posterior, mas o cidadão não receberá necessariamente uma confirmação imediata da conclusão.

— Então teremos que escolher entre disponibilidade e informação atualizada?

— Em alguns cenários de falha, sim. Mas a decisão depende da operação. Nem todas exigem o mesmo nível de consistência ou a mesma resposta durante uma interrupção.

Aline refletiu.

— Consultar o horário de atendimento não é igual a confirmar um pagamento.

— Exatamente.

— Então por que usamos políticas parecidas para tudo?

Marcelo respondeu:

— Porque era mais simples padronizar.

Aline permaneceu olhando para ele.

— Simples para quem?

A pergunta parecia ter se tornado uma tradição na Ordem.

***

A reunião terminou com uma decisão importante.

Não tentaríamos aplicar a mesma política de recuperação a todos os serviços.

Cada operação crítica seria analisada conforme suas consequências.

Uma consulta informativa poderia aceitar dados temporariamente antigos, desde que isso fosse comunicado de maneira adequada.

Uma solicitação de pagamento exigiria controle rigoroso contra duplicações.

Uma atualização cadastral precisaria distinguir recebimento, validação e conclusão.

Uma operação de emergência não poderia depender desnecessariamente de um serviço secundário.

A decisão não eliminava a complexidade.

Mas impedia que ela fosse escondida sob uma regra única.

Aline pediu um plano de implementação.

Marcelo estimou algumas semanas para as primeiras correções e um trabalho mais longo para os fluxos críticos.

— Não quero um projeto interminável — disse ela.

— Nem nós — respondeu Rafael.

— Então comecem pelo que reduz mais risco.

Marcelo concordou.

Aline se levantou.

— E quero saber quando um cidadão não consegue concluir uma operação. Não apenas quando um servidor cai.

A reunião terminou às 10h51.

Vinte e nove minutos antes do almoço.

Marcelo considerou o resultado uma vitória.

***

Às 11h23, encontrei outra inconsistência.

Dessa vez, não envolvia Ana Almeida.

Um cidadão havia solicitado o cancelamento de um agendamento.

O serviço de atendimento registrara a solicitação.

O sistema de agendamentos confirmara o cancelamento.

Mas uma mensagem de confirmação havia chegado ao serviço de notificações antes da mensagem que informava a criação original do agendamento.

O serviço de notificações processara os eventos na ordem em que os recebera.

Primeiro, o cancelamento.

Depois, a criação.

O resultado era uma mensagem informando que o agendamento estava confirmado.

Embora estivesse cancelado.

A comunicação havia funcionado.

As mensagens haviam sido entregues.

Nenhum servidor estava indisponível.

Ainda assim, o cidadão recebera uma informação errada.

— Encontrei um novo problema — anunciei.

Rafael suspirou.

— Claro que encontrou.

Mostrei os eventos.

Marcelo examinou os identificadores.

— Foram publicados por processos diferentes.

— E chegaram fora da ordem esperada.

— Sim.

— Então precisamos garantir a ordem de entrega.

— Talvez. Ou precisamos fazer o consumidor lidar com eventos fora de ordem.

— Qual alternativa é melhor?

— Depende das garantias que a infraestrutura oferece, da forma como os eventos são particionados e do comportamento que precisamos preservar.

— Você está usando essa palavra com frequência.

— Qual?

— *Depende.*

Marcelo sorriu.

— É uma palavra honesta.
