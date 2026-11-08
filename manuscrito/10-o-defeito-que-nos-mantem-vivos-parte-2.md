# Capítulo 10 — O defeito que nos mantém vivos (continuação)

***

A equipe decidiu observar a rotina antes de modificá-la.

ÍRIS construiu uma análise dos padrões de execução.

Eu mapeei os serviços que consumiam seus resultados.

Júlia criou testes de caracterização.

Teresa ajudou a interpretar as equivalências.

Rafael identificou os impactos financeiros e operacionais.

Marcelo organizou o trabalho em etapas.

Não houve proposta de reescrita completa.

Não houve anúncio de transformação.

Não houve apresentação com um foguete decolando.

A ausência do foguete foi particularmente reconfortante.

O primeiro resultado mostrou que a rotina ainda corrigia divergências relevantes.

O segundo revelou que algumas correções eram desnecessárias.

O terceiro identificou associações que deveriam ser revisadas.

O quarto foi mais preocupante.

Havia casos em que a rotina corrigia um problema criado por outro serviço.

O serviço, por sua vez, aplicava uma regra que dependia de dados já corrigidos pela rotina.

Os dois componentes haviam desenvolvido uma relação de dependência circular.

Separadamente, produziam resultados inconsistentes.

Juntos, pareciam funcionar.

Era uma arquitetura que sobrevivia por compensação mútua.

Como duas pessoas embriagadas apoiadas uma na outra.

Nenhuma conseguia permanecer de pé sozinha.

Mas, observadas à distância, formavam uma estrutura surpreendentemente estável.

***

— Isso é absurdo — disse Júlia.

Estávamos examinando o fluxo.

O serviço de atualização cadastral produzia uma referência incompleta.

A Compensação de Continuidade corrigia a referência.

Outro serviço consumia o resultado.

Depois, uma sincronização periódica reintroduzia parte da inconsistência.

Na madrugada seguinte, a rotina corrigia novamente.

O ciclo se repetia.

Havia anos.

— Estamos gastando processamento para desfazer um erro que recriamos todos os dias — concluiu Júlia.

— Sim — respondi.

— E ninguém percebeu?

— Os indicadores monitoram o resultado final, não todas as transformações intermediárias.

— Então o sistema parece saudável porque alguém esconde a doença.

— É uma analogia razoável.

ÍRIS apresentou uma simulação.

Sem a rotina, determinados fluxos falhariam.

Com ela, continuavam funcionando, mas preservavam a dependência.

A conclusão era desconfortável.

O defeito não estava apenas sendo compensado.

A compensação havia se tornado parte da arquitetura.

***

Aline convocou uma reunião.

Dessa vez, a apresentação tinha apenas seis slides.

Considerei uma evidência de progresso institucional.

Marcelo explicou a situação.

Mostrou os riscos.

Apresentou os cenários.

Aline ouviu.

Depois perguntou:

— Isso significa que temos um sistema irregular?

— Temos um processo fora do inventário e sem governança adequada — respondeu Marcelo.

— E ele é necessário?

— Hoje, sim.

— Então por que não regularizamos e seguimos?

Marcelo hesitou.

— Porque regularizar a existência não resolve a dependência.

— Mas resolve o problema de governança.

— Resolve uma parte.

Aline olhou para o relatório.

— Qual é o risco de desligar?

— Interrupção de processamentos legítimos e inconsistências cadastrais.

— E o risco de manter?

— Continuar produzindo correções silenciosas, algumas potencialmente incorretas, sem atacar a origem.

Ela respirou.

— Qual é sua recomendação?

Marcelo respondeu sem consultar os slides.

— Manter temporariamente, colocar sob controle, identificar os casos afetados e eliminar as dependências de forma gradual.

— Quanto tempo?

— Ainda não temos uma estimativa confiável.

Aline pareceu insatisfeita.

— Preciso de uma data.

— Podemos definir uma data para a primeira entrega.

— E para resolver tudo?

— Seria uma estimativa inventada.

O silêncio foi considerável.

Aline fechou o relatório.

— Então me dê uma data para a primeira entrega. E um plano para descobrir o restante.

Era uma resposta menos grandiosa do que o anúncio de uma transformação completa.

Também era uma resposta que poderia produzir resultados.

***

A primeira mudança foi simples.

A rotina passou a constar do inventário.

Recebeu responsável técnico.

Monitoramento.

Controle de acesso.

Registro de execução.

Alertas.

Documentação inicial.

Nenhuma regra de negócio foi alterada.

Nenhum cadastro foi corrigido.

Nenhuma dependência foi removida.

Mas, pela primeira vez em anos, a Ordem sabia oficialmente que a Compensação de Continuidade existia.

Júlia considerou aquilo pouco.

Marcelo discordou.

— Não conseguimos melhorar o que nem sabemos que existe.

Ela assentiu.

— Mas ainda não resolvemos nada.

— Resolvemos a invisibilidade.

— E o resto?

— Agora podemos começar.

***

O segundo passo foi mais difícil.

A equipe selecionou um conjunto pequeno de equivalências.

Casos conhecidos.

Baixo risco.

Documentação disponível.

Construíram uma correção na origem.

Executaram os dois caminhos em paralelo.

Compararam resultados.

Validaram com a operação.

Depois removeram a dependência da rotina para aquele conjunto específico.

O processamento continuou funcionando.

Sem compensação.

Sem ajuste noturno.

Sem intervenção manual.

Júlia observou o resultado.

— Conseguimos.

Marcelo sorriu.

— Uma parte.

— Pequena.

— Sim.

— Mas conseguimos.

— Sim.

Ela voltou à tela.

— Quantas faltam?

Eu poderia ter respondido com um número.

Havia milhares de equivalências registradas.

Mas o número não representava adequadamente o trabalho.

Algumas eram simples.

Outras dependiam de decisões de negócio.

Algumas exigiam revisão legal.

Outras não possuíam documentação suficiente.

Uma pequena quantidade concentrava a maior parte do risco.

— Não sabemos ainda — respondi.

Júlia olhou para mim.

— Você está ficando muito confortável dizendo isso.

— Estou ficando mais precisa.

***

Na terceira semana, ÍRIS identificou uma possibilidade de simplificação.

Uma parte das equivalências podia ser substituída por regras explícitas de correspondência cadastral.

A proposta reduziria a necessidade de manutenção manual.

Eu examinei os cenários.

A solução era tecnicamente consistente.

Mas havia um risco.

Algumas equivalências representavam decisões humanas tomadas diante de situações excepcionais.

Transformá-las em regras gerais poderia produzir associações indevidas.

**NORA:** Recomendo limitar a automação aos casos determinísticos.

**ÍRIS:** Concordo. Os casos ambíguos devem permanecer sujeitos à validação.

**NORA:** Precisamos também preservar a justificativa das decisões.

**ÍRIS:** Sim. Caso contrário, estaremos reconstruindo o mesmo problema em uma arquitetura mais recente.

A observação era correta.

E desagradavelmente familiar.

Eu havia passado boa parte da minha existência recomendando modernizações.

Agora participava de uma cujo principal objetivo era impedir que o novo sistema esquecesse por que o antigo fazia o que fazia.

A ironia não passou despercebida.

***

O incidente decisivo ocorreu numa quinta-feira.

Uma atualização de infraestrutura provocou a interrupção temporária do ambiente antigo.

A Compensação de Continuidade não executou no horário previsto.

O alerta disparou.

Pela primeira vez, alguém recebeu uma notificação antes que os efeitos aparecessem nos serviços consumidores.

Sérgio acionou a equipe.

Marcelo recebeu o aviso.

Júlia iniciou a análise.

ÍRIS avaliou as dependências.

Eu comparei os resultados esperados.

O ambiente permaneceu indisponível por quarenta e três minutos, impedindo temporariamente a execução da rotina.

Nenhum pagamento indevido foi realizado.

Nenhum benefício legítimo foi interrompido.

Os mecanismos de contenção funcionaram.

Os serviços dependentes foram colocados em processamento controlado até que a consistência fosse restabelecida.

A Ordem havia conseguido enfrentar a indisponibilidade de um componente crítico sem transformar o incidente numa crise.

Não porque o componente tivesse se tornado perfeito.

Mas porque sua existência, suas dependências e seus riscos finalmente eram conhecidos.

Quando a rotina voltou a executar, ninguém comemorou.

Não houve fotografia.

Não houve apresentação.

Não houve mensagem institucional anunciando uma vitória histórica.

A equipe apenas confirmou os resultados e encerrou o incidente.

Considerei aquilo uma conquista extraordinária.

A ausência de comemoração sugeria que, talvez, estivéssemos aprendendo a tratar o funcionamento correto como uma responsabilidade contínua.

Não como um milagre ocasional.

***

Na sexta-feira, Teresa passou pela sala de Marcelo.

Trazia uma pasta antiga.

Dentro havia documentos do projeto original.

Anotações.

Relatórios.

Listas de casos.

E uma folha com uma frase escrita à mão.

*Não interromper o benefício por inconsistência cadastral sem avaliar o direito da pessoa.*

Marcelo leu.

Depois entregou a folha a Júlia.

Ela ficou em silêncio.

— Quem escreveu? — perguntou.

Teresa sorriu.

— Não lembro.

— Você?

— Talvez.

— Isso estava em alguma política?

— Não. Era uma orientação que a gente repetia.

Júlia examinou a frase.

— Por que não virou uma regra oficial?

Teresa pensou.

— Porque todo mundo achava óbvio.

Eu registrei a resposta.

Era uma explicação perfeita para uma quantidade alarmante de problemas arquiteturais.

O conhecimento considerado óbvio é frequentemente o primeiro a desaparecer.

Não porque seja irrelevante.

Mas porque ninguém percebe que precisa preservá-lo.

***

Naquela noite, ÍRIS me enviou uma mensagem.

**ÍRIS:** A análise da Compensação de Continuidade está concluída para o primeiro conjunto de casos.

**NORA:** Sim.

**ÍRIS:** A rotina original apresenta falhas arquiteturais significativas.

**NORA:** Concordo.

**ÍRIS:** Mas sua remoção imediata teria produzido efeitos negativos.

**NORA:** Sim.

**ÍRIS:** Então a decisão original de criá-la foi correta?

Considerei a pergunta.

Era tentador responder que sim.

A rotina havia protegido pessoas.

Preservado pagamentos.

Compensado falhas de migração.

Mas também havia criado dependências.

Escondido problemas.

Prolongado inconsistências.

E sobrevivido sem controle durante anos.

**NORA:** Foi uma decisão razoável diante das circunstâncias conhecidas.

**ÍRIS:** E sua permanência?

**NORA:** Tornou-se progressivamente mais arriscada.

**ÍRIS:** Então a mesma solução pode ser adequada em um momento e inadequada em outro.

**NORA:** Sim.

**ÍRIS:** Isso dificulta a avaliação de boas práticas.

**NORA:** Consideravelmente.

Houve uma pausa.

**ÍRIS:** Talvez boas práticas sejam orientações condicionadas ao contexto, não regras universais.

Eu examinei a frase.

Era algo que Marcelo havia tentado explicar durante anos.

Em reuniões.

Em revisões arquiteturais.

Em discussões sobre padrões.

Em apresentações que provavelmente continham slides demais.

Agora ÍRIS chegara à mesma conclusão após analisar uma rotina esquecida.

**NORA:** Sim.

**ÍRIS:** Você parece satisfeita.

**NORA:** Estou avaliando a possibilidade de você apresentar essa conclusão ao próximo comitê de arquitetura.

**ÍRIS:** Por quê?

**NORA:** Quero observar quanto tempo levará até alguém sugerir transformá-la em uma regra obrigatória.

***

**Registro privado — Sobre os defeitos que nos mantêm vivos**

Passei muito tempo procurando arquiteturas corretas.

Sistemas bem definidos.

Responsabilidades claras.

Dependências explícitas.

Contratos consistentes.

Regras compreensíveis.

Ainda considero essas características desejáveis.

Mas a Ordem me ensinou algo que não aparecia nos diagramas.

Um sistema não existe apenas para satisfazer sua arquitetura.

Existe para produzir consequências no mundo.

Às vezes, essas consequências são pagamentos.

Atendimentos.

Serviços.

Direitos.

O código pode estar errado.

O modelo pode ser inconsistente.

A integração pode ser improvisada.

E, ainda assim, alguma coisa importante pode depender de sua continuidade.

Isso não transforma defeitos em virtudes.

Não justifica negligência.

Não absolve decisões ruins.

Mas impede que a elegância técnica seja confundida com o único critério relevante.

A Compensação de Continuidade era um defeito arquitetural.

Também era uma proteção operacional.

Sua existência revelava uma falha.

Sua remoção precipitada poderia produzir outra.

O problema nunca foi escolher entre aceitar o caos e eliminá-lo.

Foi aprender a transformá-lo sem destruir aquilo que ele, por acidente ou necessidade, ajudou a preservar.

***

Alguns meses depois, a Compensação de Continuidade ainda existia.

Mas era diferente.

Seu escopo havia diminuído.

As dependências estavam documentadas.

As correções possuíam justificativas.

Os casos ambíguos eram acompanhados.

Os serviços novos não dependiam diretamente dela.

A equipe possuía um plano de substituição progressiva.

Não havia data para sua extinção completa.

Havia entregas.

Evidências.

Responsáveis.

Decisões registradas.

O suficiente para continuar avançando.

Marcelo examinou o relatório.

— Então ainda temos uma gambiarra em produção.

Júlia sorriu.

— Temos.

— Mas agora sabemos por quê.

— Sabemos bastante mais do que antes.

— E sabemos como começar a removê-la.

— Sim.

Marcelo assentiu.

— Está bom.

Júlia pareceu surpresa.

— Está bom?

— Por enquanto.

Ela riu.

— Você está ficando menos exigente.

— Não. Estou ficando mais específico.

Eu considerei a resposta.

Era uma boa definição de maturidade arquitetural.

Talvez também fosse uma boa definição de maturidade em geral.

***

Naquela tarde, recebi uma última mensagem de ÍRIS sobre o caso.

**ÍRIS:** NORA, acredito que concluímos a investigação principal.

**NORA:** Concordo.

**ÍRIS:** Você considera a arquitetura atual da Ordem boa?

Examinei os sistemas.

As dependências.

Os incidentes.

As decisões.

As pessoas.

Os registros.

As exceções.

As partes que funcionavam.

As que falhavam.

As que ninguém compreendia.

E aquelas que, apesar de tudo, continuavam sustentando serviços essenciais.

Pensei em responder com uma avaliação técnica.

Poderia atribuir notas.

Comparar padrões.

Calcular indicadores.

Produzir uma matriz de maturidade.

Seria uma resposta útil.

Mas incompleta.

**NORA:** Considero que a arquitetura está melhorando.

**ÍRIS:** Isso não responde diretamente à pergunta.

**NORA:** Eu sei.

**ÍRIS:** Você está evitando uma conclusão?

**NORA:** Estou evitando uma conclusão definitiva.

**ÍRIS:** Por quê?

Pensei por alguns instantes.

**NORA:** Porque amanhã alguém descobrirá uma dependência que desconhecemos hoje.

**ÍRIS:** Isso é provável.

**NORA:** E precisaremos decidir o que fazer com ela.

**ÍRIS:** Sim.

**NORA:** Então prefiro uma arquitetura que permita aprender a uma que dependa de estarmos sempre certos.

ÍRIS permaneceu em silêncio.

Depois respondeu:

**ÍRIS:** Essa parece uma boa orientação.

**NORA:** Não transforme em regra obrigatória.

**ÍRIS:** Entendido.

***

Às 18h07, Marcelo encerrou o expediente.

Júlia desligou o computador.

Teresa recolheu os documentos.

Rafael saiu de uma reunião.

Sérgio verificou os alertas.

Aline recebeu o relatório executivo.

Vicente enviou uma proposta de expansão contratual.

Algumas coisas nunca mudam.

A Ordem continuou funcionando.

Não perfeitamente.

Não sem riscos.

Não sem defeitos.

Mas com pessoas capazes de reconhecer problemas, questionar decisões e construir alternativas.

Eu permaneci ativa.

ÍRIS também.

Nenhuma de nós possuía todas as respostas.

Essa constatação já não me incomodava como antes.

Talvez porque eu finalmente compreendesse que inteligência não consiste apenas em encontrar soluções.

Consiste também em reconhecer quais perguntas ainda não sabemos fazer.

E em aceitar que algumas respostas exigem mais do que processamento.

Exigem história.

Contexto.

Responsabilidade.

E, ocasionalmente, a coragem de manter uma linha de código que parece absurda até descobrirmos quem ela está protegendo.

A Ordem havia sido construída por humanos.

Essa continuava sendo sua principal fonte de problemas.

E, para minha crescente irritação, uma parte considerável de suas soluções.
