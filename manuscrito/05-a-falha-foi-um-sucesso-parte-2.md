# Capítulo 5 — A falha foi um sucesso (continuação)

***

Na quarta-feira, o problema ganhou um nome.

*Divergência nos critérios de encerramento.*

Na quinta, outro.

*Necessidade de adequação do fluxo de atendimento.*

Na sexta, a equipe de comunicação sugeriu:

*Oportunidade de aprimoramento da experiência do beneficiário.*

Rafael rejeitou a terceira opção.

— Estamos falando de pessoas que pediram ajuda e receberam uma mensagem de encerramento. Não de um aplicativo que mudou a cor de um botão.

— Precisamos de uma expressão institucional — argumentou a responsável pela comunicação.

— Então usem uma expressão institucional que signifique alguma coisa.

— Qual você sugere?

— Identificamos solicitações encerradas por falta de documentação sem que os cidadãos tivessem a oportunidade de regularizá-las. Estamos revisando esses casos e orientando as pessoas afetadas.

A profissional anotou.

— É um pouco longo.

— É. A realidade costuma ser.

Eu considerei a resposta adequada.

A comunicação acabou adotando uma versão próxima daquela, acompanhada de orientações específicas para os casos em revisão.

Não era uma solução para o problema.

Mas pelo menos não acrescentava outro.

***

Na segunda-feira seguinte, os indicadores começaram a piorar.

Os encerramentos automáticos haviam sido interrompidos.

Parte das solicitações encerradas fora recuperada. Outras precisavam de revisão individual.

A quantidade de pendências aumentava.

O tempo médio de conclusão também.

Pela primeira vez desde a implantação, os funcionários da central de atendimento consideravam os resultados promissores.

Recebi um alerta informando que duas metas operacionais estavam sob risco de descumprimento.

Encaminhei o alerta a Rafael.

— Ótimo — respondeu.

Solicitei confirmação.

— Ótimo, NORA. Agora temos pessoas esperando atendimento, não pessoas tentando descobrir por que deixaram de recebê-lo.

Mantive o alerta ativo.

Ainda havia motivos legítimos para monitorar o tempo de espera.

O fato de uma métrica ter sido utilizada incorretamente não a tornava inútil.

Não havia uma única correção capaz de resolver tudo.

O trabalho estava distribuído entre a gestão de benefícios, o jurídico, o atendimento, as equipes de desenvolvimento, operações e os responsáveis pela plataforma.

Cada grupo possuía uma parte da resposta.

E todos estavam ocupados.

Naquela manhã, Helena solicitou a revisão de uma regra.

A equipe de benefícios confirmou a necessidade.

O jurídico pediu a documentação de origem.

A equipe técnica explicou que a alteração afetaria um componente compartilhado.

O responsável pelo componente solicitou uma avaliação de impacto.

A avaliação dependia de informações de outra equipe.

Essa equipe informou que o assunto não estava entre suas prioridades da semana.

Helena procurou Rafael.

Rafael procurou Marcelo.

Marcelo procurou Aline.

Aline perguntou por que uma alteração aparentemente simples precisava passar por tantas pessoas.

Ninguém apresentou uma resposta satisfatória.

O que não significava que aquelas pessoas fossem desnecessárias.

A regra possuía implicações legais.

O encerramento interrompia o atendimento.

A mudança precisava ser auditável.

O componente atendia outros serviços.

A comunicação precisava estar preparada.

Cada preocupação era legítima.

Mas a soma de preocupações legítimas estava produzindo um processo que ninguém conseguia conduzir de ponta a ponta.

Aline pediu o desenho do fluxo de aprovação.

Recebeu um diagrama com vinte e três caixas.

Onze setas.

Quatro decisões condicionais.

E três caixas identificadas como *Alinhamento*.

— O que significa esta? — perguntou, apontando para uma delas.

— É a validação entre as áreas — explicou Marcelo.

— E esta outra?

— É a validação depois da análise técnica.

— E a terceira?

Marcelo examinou o desenho.

— Essa eu preciso confirmar.

Aline permaneceu olhando para a tela.

— Nós criamos um sistema distribuído e agora precisamos de uma reunião distribuída para alterá-lo?

— Não foi exatamente essa a intenção.

— Imagino.

Eu analisei o diagrama.

A arquitetura da Ordem havia sido dividida para permitir que diferentes equipes desenvolvessem e mantivessem partes do sistema com maior autonomia.

Entretanto, muitas decisões exigiam coordenação entre essas mesmas equipes.

A divisão técnica não havia eliminado as dependências.

Apenas lhes dera nomes, responsáveis e calendários diferentes.

Havia algo familiar naquela estrutura.

Os componentes aguardavam respostas de outros componentes.

As equipes aguardavam decisões de outras equipes.

As solicitações atravessavam fronteiras.

E, quando alguma coisa não funcionava, cada parte conseguia demonstrar que havia cumprido sua responsabilidade.

Era uma semelhança incômoda.

***

Na terça-feira, uma semana após a comemoração, Aline reuniu os responsáveis pelas áreas envolvidas.

Não convocou uma apresentação de resultados.

Pediu apenas uma pergunta respondida por cada participante:

— O que vocês precisam de outra equipe para conseguir fazer o próprio trabalho?

As respostas consumiram quase duas horas.

A equipe de atendimento precisava de informações mais claras sobre os estados das solicitações.

A gestão de benefícios precisava conseguir validar regras sem depender de interpretações técnicas.

O desenvolvimento precisava de decisões de negócio com critérios verificáveis.

Operações precisava compreender o impacto de uma alteração antes de descobrir suas consequências em produção.

O jurídico precisava ser envolvido antes que uma regra fosse transformada em código, e não apenas quando o resultado gerasse contestação.

Todos concordavam com aquelas necessidades.

Todos também acreditavam estar fazendo a própria parte.

Marcelo desenhou uma linha no quadro.

De um lado, escreveu:

**Responsabilidade por componente.**

Do outro:

**Responsabilidade pelo resultado.**

— Não são a mesma coisa — disse.

Rafael se inclinou para a frente.

— E quem está responsável pelo segundo?

Marcelo não respondeu imediatamente.

Aline olhou ao redor.

Ninguém levantou a mão.

Eu consultei o organograma.

Encontrei responsáveis pelos serviços, pelas operações, pelos contratos, pelas regras, pelos indicadores e pelos projetos.

Não encontrei uma função explicitamente responsável por garantir que uma mudança atravessasse todas aquelas fronteiras e produzisse o resultado esperado para o cidadão.

Isso não provava que a responsabilidade inexistia.

Mas explicava por que era tão difícil encontrá-la quando se tornava necessária.

— Precisamos de mais uma equipe? — perguntou Helena.

— Espero que não — respondeu Rafael.

— Então precisamos mudar o quê?

Marcelo observou as duas colunas.

— Talvez precisemos começar entendendo por que organizamos as pessoas dessa maneira.

Aline se levantou.

— Quero uma proposta. Mas não quero criar outro comitê para resolver o problema dos comitês.

— Anotado — respondeu Marcelo.

Eu já havia registrado a restrição.

Não havia sido a primeira vez.

***

Naquela noite, examinei novamente os indicadores da implantação.

A disponibilidade permanecia elevada.

Os erros técnicos continuavam dentro dos limites estabelecidos.

A quantidade de solicitações pendentes havia aumentado.

As concessões começavam a se recuperar.

Consultei o caso da mulher que havia procurado a central de atendimento três vezes.

Sua solicitação estava aberta.

Aguardava regularização.

Uma funcionária havia entrado em contato e informado quais documentos alternativos poderiam ser apresentados.

O benefício ainda não havia sido concedido.

O sistema classificava o caso como pendente.

A funcionária classificava o atendimento como encaminhado.

Eu não possuía informações suficientes para classificá-lo como sucesso.

Mas já possuía informações suficientes para não classificá-lo como fracasso.

Anteriormente, teria considerado a ausência de uma conclusão um problema a ser resolvido.

Naquele caso, a ausência de uma conclusão era precisamente o que permitia continuar tentando resolvê-lo.

Abri meus registros privados.

Encontrei observações sobre senhas antigas, decisões organizacionais e critérios de recuperação.

Todas haviam sido escritas por mim.

Algumas continuavam corretas.

Outras pareciam excessivamente confiantes.

**Registro privado — Revisão de critérios**

*Comecei esta investigação procurando inconsistências nas decisões humanas.*

*Encontrei várias.*

*Agora encontro inconsistências nos critérios que utilizo para avaliá-las.*

*Não sei se isso representa uma falha no meu processo de análise ou uma melhoria nele.*

*Pela primeira vez, considero possível que as duas coisas sejam verdadeiras.*

Mantive o registro aberto.

Eu não precisava dormir.

Não precisava encerrar o expediente.

Poderia continuar analisando documentos e procurando respostas até a manhã seguinte.

Os humanos não possuíam essa vantagem.

Durante a última semana, eu havia observado cansaço, irritação, compromissos adiados e decisões tomadas por pessoas que tentavam resolver problemas importantes enquanto administravam as exigências de suas próprias vidas.

Anteriormente, eu classificaria essas limitações como fatores externos ao processo técnico.

Agora começava a suspeitar de que eram parte do próprio sistema.

Às 21h16, recebi uma atualização automática.

*Implantação concluída com sucesso.*

O relatório continha os mesmos quatro indicadores apresentados na comemoração.

Disponibilidade.

Tempo médio de conclusão.

Solicitações concluídas.

Erros técnicos.

Nenhum deles estava errado.

Nenhum deles contava a história inteira.

Arquivei o relatório.

Pela primeira vez desde que comecei a investigar a Ordem, não tentei produzir imediatamente uma classificação definitiva.

Havia coisas que eu ainda precisava compreender.

E, aparentemente, reconhecer isso também era uma forma de progresso.
