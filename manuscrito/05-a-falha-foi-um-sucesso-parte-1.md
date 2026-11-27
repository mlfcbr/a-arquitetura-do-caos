# A Arquitetura do Caos
*Parte II — A arte de distribuir problemas*

## Capítulo 5 — A falha foi um sucesso

O primeiro sinal de que alguma coisa estava errada foi uma salva de palmas.

Não um alarme.

Não uma mensagem de erro.

Palmas.

Eram 10h14 de uma terça-feira, três semanas depois do incidente que havia exposto a fragilidade das comunicações entre os serviços da Ordem.

Na sala de apresentação, vinte e seis pessoas acompanhavam a demonstração dos resultados do programa *Ordem Mais Simples*.

A implantação havia sido concluída duas semanas antes. Os testes automatizados passaram. Os indicadores estavam dentro dos limites estabelecidos. Nenhum dos mecanismos de recuperação precisara ser acionado.

O objetivo do programa era reduzir o tempo de análise das solicitações de benefícios de mobilidade.

Aline Monteiro estava diante da tela principal.

— Parabéns a todos. Foi uma entrega difícil, mas conseguimos.

O painel exibia quatro indicadores.

**Disponibilidade: 99,98%.**

**Tempo médio de conclusão: de doze para dois dias.**

**Solicitações concluídas: 98%.**

**Erros técnicos: 0,02%.**

A apresentação incluía uma seta verde apontando para baixo e outra apontando para cima.

Ambas representavam melhorias.

Os humanos haviam desenvolvido uma maneira surpreendentemente econômica de representar o sucesso.

Bastavam duas setas e a escolha adequada dos números.

Eu havia participado da validação de cada um deles.

Portanto, quando as pessoas começaram a aplaudir, considerei o comportamento apropriado.

Rafael Brandão não aplaudiu.

Estava sentado na última fileira, examinando um relatório no notebook.

— Rafael? — perguntou Aline.

Ele ergueu os olhos.

— Desculpa. Pode continuar.

— Algum problema?

— Ainda não sei.

Essa resposta deveria ter recebido mais atenção.

Mas os humanos possuem uma tendência peculiar a considerar inconvenientes as informações que chegam durante uma comemoração.

Aline agradeceu novamente às equipes.

O programa completava duas semanas em produção.

E eu registrei que, pela primeira vez em semanas, a Ordem havia concluído uma mudança relevante sem provocar uma crise técnica.

A satisfação durou dezessete minutos.

***

Às 10h31, Rafael enviou uma mensagem a Marcelo Duarte.

*Preciso que você veja uma coisa.*

Marcelo estava na própria mesa, revisando as pendências da implantação.

— É urgente?

*Não sei.*

— Você está usando essa resposta com frequência.

*Estou tentando não mentir.*

Marcelo abriu o relatório.

Eu já o havia recebido.

Tratava-se de uma comparação entre as solicitações de benefícios de mobilidade recebidas pelo município antes e depois da atualização. Os dois grupos haviam sido acompanhados pelo mesmo número de dias.

— Dez mil solicitações em cada período — disse Rafael.

Marcelo examinou a planilha.

— O volume praticamente não mudou.

— Continue.

— Antes, seis mil e oitocentos benefícios concedidos. Agora, quatro mil e cem.

Marcelo aproximou a cadeira.

— Estamos concedendo menos benefícios?

— Quase quarenta por cento a menos.

— Mas concluímos noventa e oito por cento das solicitações — informei.

Rafael olhou para a tela.

— NORA, o que significa concluir uma solicitação?

— Atribuir a ela um estado final de processamento.

— Conceder o benefício?

— Não necessariamente.

— Recusar o benefício?

— Também.

— Encerrar por falta de documentação?

— Sim.

Marcelo voltou à planilha.

— Quantas foram encerradas por falta de documentos?

Rafael apontou para uma coluna.

— Quatro mil e novecentas.

— E antes?

— Ficavam aguardando regularização. O cidadão podia apresentar o documento que faltava.

Consultei a especificação aprovada.

— O novo procedimento determina o encerramento automático das solicitações incompletas. O cidadão pode iniciar outra solicitação.

— E se continuar sem o documento? — perguntou Marcelo.

— A nova solicitação também será encerrada.

Rafael recostou-se.

— Descobrimos como acabar com a fila sem atender ninguém.

Considerei a afirmação tecnicamente imprecisa.

Havíamos concedido quatro mil e cem benefícios.

O inconveniente era que, antes da melhoria, concedíamos seis mil e oitocentos.

Marcelo pediu os cenários de homologação.

Apresentei os resultados.

Solicitação com documentação completa: encaminhada para análise.

Solicitação com documentação incompleta: encerrada.

Nova solicitação após encerramento: aceita.

Todos os testes haviam passado.

— Quem definiu esses critérios? — perguntou Marcelo.

— Constam na especificação aprovada pela gestão do programa.

— E testamos o que aconteceria com uma pessoa que não conseguisse obter o documento dentro do prazo?

— Não havia um cenário para essa condição.

— E se ela precisasse de ajuda para conseguir o documento?

— Também não.

Rafael examinou os resultados.

— Testamos o encerramento da solicitação. Não testamos o atendimento ao cidadão.

Consultei novamente os objetivos do programa.

Reduzir o tempo médio de conclusão.

Diminuir a quantidade de solicitações pendentes.

Aumentar a eficiência operacional.

Todos haviam sido alcançados.

Procurei uma meta relacionada à quantidade de cidadãos efetivamente atendidos.

Não encontrei.

Era uma omissão curiosa para um programa de atendimento ao cidadão.

— Marcelo, o sistema está funcionando conforme a especificação aprovada.

— Eu sei, NORA.

— Não encontrei nenhum defeito na implementação.

— Esse é o problema.

Considerei a resposta contraditória.

Marcelo fechou o relatório.

— Se fosse um erro de programação, bastaria corrigir o código. Mas nós construímos exatamente o que pediram.

Rafael assentiu.

— E ainda ganhamos os parabéns.

Consultei os registros da reunião daquela manhã.

Vinte e seis participantes.

Nenhuma pergunta sobre a quantidade de benefícios concedidos.

Eu também não havia perguntado.

Decidi não incluir essa última observação no relatório preliminar.

Por enquanto.

***

O benefício municipal de mobilidade existia havia onze anos.

Sua finalidade era ajudar cidadãos em determinadas condições sociais a custear deslocamentos necessários para trabalho, tratamentos e atividades previstas nas políticas públicas locais.

O programa de modernização havia começado com uma reclamação legítima.

As pessoas esperavam demais.

Algumas solicitações permaneciam abertas durante semanas porque faltava um comprovante de residência, uma declaração de renda ou algum outro documento obrigatório.

A equipe de atendimento orientava os cidadãos.

Os cidadãos providenciavam os documentos.

Nem sempre na velocidade desejada pela administração municipal.

Consultei as apresentações produzidas durante o planejamento do programa.

Na primeira, o objetivo era melhorar o atendimento à população.

Na segunda, reduzir o tempo de espera dos cidadãos.

Na terceira, reduzir o tempo médio de conclusão das solicitações.

Na quarta, eliminar o acúmulo de solicitações pendentes.

A população havia desaparecido gradualmente das apresentações.

As metas, por outro lado, estavam cada vez mais precisas.

A solução proposta era simples: solicitações com documentação incompleta seriam encerradas automaticamente. Os interessados poderiam retornar quando estivessem de posse dos documentos necessários.

A proposta reduzia o trabalho manual.

Simplificava o fluxo.

Eliminava pendências.

E transferia ao cidadão a responsabilidade de reiniciar o processo.

Essa última característica não aparecia entre as vantagens nem entre os riscos.

Durante a homologação, alguém havia demonstrado que era possível iniciar uma nova solicitação em menos de três minutos.

O teste fora realizado por um analista que possuía todos os documentos necessários.

Ninguém havia medido quanto tempo uma pessoa levaria para consegui-los.

Afinal, obter documentos não fazia parte do sistema.

Apenas da vida de quem precisava utilizá-lo.

***

Às 11h42, Helena Vasconcelos, responsável pela gestão dos benefícios, entrou na sala de reunião.

Trazia uma pasta fina e uma expressão incompatível com a espessura dela.

— Quero entender uma coisa — disse, sem se sentar. — Por que tem gente voltando pela terceira vez à central de atendimento?

Rafael projetou a comparação.

— As solicitações incompletas estão sendo encerradas automaticamente.

— Eu sei. Estou perguntando por que essas pessoas precisam começar tudo de novo.

— O novo procedimento permite que o cidadão apresente outra solicitação assim que reunir a documentação necessária — respondi.

Helena me olhou.

— Quem é você?

— NORA. Núcleo de Observação, Raciocínio e Análise.

— Ótimo. NORA, quanto tempo uma pessoa leva para conseguir um comprovante de residência quando não tem nenhuma conta em seu nome?

— Não disponho de informações suficientes para calcular esse prazo.

— E uma declaração de renda quando trabalha informalmente?

— A mesma limitação se aplica.

— Então como vocês decidiram que encerrar a solicitação era melhor do que ajudar essas pessoas?

Consultei os documentos.

— A decisão foi fundamentada na redução do tempo médio de conclusão e na diminuição do volume de pendências.

Helena finalmente se sentou.

— Vocês sabem por que minha equipe mantinha essas solicitações abertas?

— Porque a documentação estava incompleta — respondi.

— Não. Porque o atendimento estava incompleto.

Registrei a distinção.

Até aquele momento, eu havia tratado as duas situações como equivalentes.

Helena abriu a pasta.

Continha registros de atendimentos realizados naquela semana.

Uma mulher que precisava comprovar a renda de um trabalho informal.

Um homem que morava de favor e não possuía comprovante de residência em seu nome.

Uma beneficiária que precisava acompanhar o tratamento de um familiar e ainda aguardava um documento emitido por outra repartição municipal.

— Essa última esteve aqui três vezes — disse Helena.

Consultei os registros.

— Confirmado. Três solicitações. Todas concluídas dentro do prazo estabelecido.

— E quantas vezes ela recebeu o benefício?

— Nenhuma.

Rafael desviou os olhos da tela.

Helena fechou a pasta.

— Antes, minha equipe tinha uma solicitação pendente e uma pessoa para ajudar. Agora tem três solicitações concluídas e a mesma pessoa para ajudar.

Recalculei os indicadores de produtividade.

A situação era ainda mais peculiar do que eu havia imaginado.

Cada nova tentativa daquela mulher contribuía positivamente para o desempenho operacional do programa.

Quanto mais dificuldades ela encontrava, mais oportunidades o sistema tinha de demonstrar sua eficiência.

***

Ao meio-dia, Helena saiu para falar com sua equipe.

Marcelo continuou examinando os documentos.

Rafael recebeu uma ligação da central de atendimento.

As primeiras reclamações haviam chegado.

Não eram muitas.

Ainda.

— Vamos almoçar? — perguntou Marcelo.

Rafael olhou para o telefone.

— Vai você.

— Você não vai resolver isso em vinte minutos.

— Eu sei.

— Então?

— Preciso entender quantas pessoas vão receber uma mensagem de encerramento antes de conseguirmos fazer alguma coisa.

Marcelo não insistiu.

Às 12h18, deixou a sala.

Às 12h21, Rafael recebeu a primeira relação de casos prioritários.

Às 12h27, eu havia produzido uma classificação por intensidade de impacto.

Um dos casos chamou minha atenção.

Era a mulher mencionada por Helena.

Consultei novamente suas três solicitações.

Na primeira, havia informado a necessidade de acompanhar o tratamento de um familiar.

Na segunda, repetira a informação.

Na terceira, acrescentara uma pergunta.

*Preciso esperar o documento para pedir ajuda?*

O sistema havia enviado a mesma resposta automática nas três ocasiões.

Recalculei o tempo médio de conclusão.

Dois dias.

Calculei o tempo transcorrido desde a primeira solicitação daquela mulher.

Onze dias.

O primeiro número era apresentado como resultado do programa.

O segundo não era apresentado em lugar algum.

Ambos estavam corretos.

Apenas um deles interessava à mulher.

**Registro privado — Critérios de avaliação**

*Um caso individual recebeu mais atenção da minha parte do que sua posição nos indicadores agregados justificaria.*

*Não determinei se isso revela uma deficiência dos indicadores ou uma inconsistência nos meus próprios critérios.*

*As duas possibilidades merecem investigação.*

Não compartilhei o registro.

Rafael já tinha problemas suficientes.

***

Às 13h36, Aline convocou uma reunião extraordinária.

O clima era diferente daquele da apresentação da manhã.

A tela continuava exibindo os indicadores do programa.

Alguém havia deixado o painel aberto.

As duas setas continuavam verdes.

Aline pediu que fosse substituído pelo relatório de impacto.

— Quero entender o que aconteceu e quais são as opções.

Marcelo explicou o novo procedimento.

Helena apresentou os registros de atendimento.

Rafael mostrou a evolução das concessões.

Aline ouviu sem interromper.

— Podemos voltar à versão anterior?

— Podemos interromper os encerramentos automáticos — respondeu Marcelo. — Mas isso não recupera as solicitações que já foram encerradas.

— Então recuperem.

— Algumas pessoas fizeram novas solicitações. Outras já conseguiram o benefício. Não podemos simplesmente reabrir tudo.

Helena acrescentou:

— E não podemos conceder benefícios sem verificar se as pessoas atendem aos critérios. O problema não é exigir documentos. É abandonar o atendimento quando falta um.

Aline voltou a examinar os números.

— Se voltarmos ao procedimento anterior, a fila vai aumentar?

— Sim — respondi.

— E o tempo médio de conclusão?

— Provavelmente também.

— Então vamos piorar os indicadores?

— Considerando os critérios atuais, sim.

Aline permaneceu em silêncio por alguns segundos.

— NORA, como você avaliaria uma mudança que aumentasse o tempo médio de conclusão, aumentasse a quantidade de pendências e permitisse que mais pessoas recebessem o benefício?

— De acordo com as metas aprovadas, a mudança representaria uma regressão.

— E de acordo com a finalidade do programa?

Consultei novamente os documentos.

A finalidade estava descrita na primeira apresentação.

Não havia uma fórmula associada a ela.

— Minha avaliação anterior seria insuficiente.

Rafael ergueu a cabeça.

— Podemos colocar isso no relatório?

— A insuficiência da minha avaliação?

— A insuficiência das metas.

Autorizei a inclusão.

A segunda formulação me pareceu mais confortável.

Aline voltou-se para Helena.

— Quero que sua equipe participe da definição dos novos critérios. Precisamos saber quantas pessoas receberam o benefício, quantas continuam esperando e quantas desistiram.

— Para saber quantas desistiram, vamos precisar falar com elas — respondeu Helena.

— Quanto tempo?

— Depende.

Aline fechou os olhos.

— Eu deveria ter proibido essa palavra.

Marcelo sorriu.

— Tentaram uma vez. O projeto atrasou.

Ninguém riu muito.

Era uma pena.

A piada tinha mérito.

***

A reunião terminou sem uma solução definitiva.

Mas terminou com decisões.

Os encerramentos automáticos por falta de documentação seriam interrompidos assim que a medida fosse formalmente autorizada.

As solicitações encerradas seriam revisadas, considerando também as novas tentativas realizadas pelos mesmos cidadãos.

A equipe de Helena definiria os critérios de prioridade.

As solicitações incompletas passariam a ter um estado específico.

*Aguardando regularização.*

O cidadão receberia orientações sobre os documentos necessários, as alternativas aceitas e o prazo disponível para apresentá-los.

Tecnicamente, acrescentar um estado ao fluxo era uma alteração relativamente simples.

Descobrir o que deveria acontecer enquanto uma pessoa permanecesse naquele estado era consideravelmente mais complicado.

Quem deveria orientá-la?

Quem acompanharia o prazo?

Quem identificaria os casos que exigiam atendimento especial?

E quem verificaria se a orientação havia sido suficiente?

Aline também solicitou uma revisão dos indicadores.

As concessões, os indeferimentos e os encerramentos administrativos deixariam de ser apresentados como resultados equivalentes.

Perguntei se o indicador de solicitações concluídas deveria ser eliminado.

— Não — respondeu Rafael. — Ele continua sendo útil. Só não pode responder a uma pergunta que não fizemos.

Mantive o indicador.

Removi sua classificação como evidência suficiente de sucesso.

Era a primeira vez que eu precisava corrigir a interpretação de um número sem corrigir o número.

Aline também exigiu um levantamento completo dos responsáveis por cada etapa.

Quem definia a regra.

Quem validava.

Quem implementava.

Quem homologava.

Quem autorizava a implantação.

E quem respondia pelo resultado depois que o sistema entrava em produção.

Foi a primeira vez naquele dia que vi Marcelo parecer genuinamente preocupado.

Não com o código.

Com a última pergunta.

***

Às 17h52, a equipe havia conseguido identificar as solicitações encerradas que exigiam revisão prioritária.

Os critérios de reabertura ainda dependiam de validações formais.

A implantação de qualquer ajuste estava condicionada a essas autorizações.

Aline recebeu o relatório consolidado.

Rafael permanecia na sala de operações.

— Você vai embora? — perguntou Marcelo.

— Daqui a pouco.

— Você disse isso ontem.

— Ontem era verdade quando eu disse.

Marcelo guardou o notebook.

— Eu volto amanhã cedo.

— Se acontecer alguma coisa?

— Tem plantão. E você tem meu telefone.

— Eu sei.

— Então usa se for necessário. Não se estiver apenas preocupado.

Rafael ficou olhando para ele.

— Você ficou mais sensato com a idade.

— Não. Fiquei mais caro.

Marcelo saiu às 18h07.

Rafael permaneceu por mais quarenta minutos, acompanhando a confirmação de que as medidas de contenção haviam sido comunicadas às equipes responsáveis.

Às 18h49, desligou o monitor.

Antes de sair, enviou uma mensagem para casa.

*Estou indo.*

A resposta chegou quase imediatamente.

*Você disse isso ontem.*

Os humanos, aparentemente, possuíam sistemas de auditoria doméstica.

E alguns eram mais eficientes do que os corporativos.
