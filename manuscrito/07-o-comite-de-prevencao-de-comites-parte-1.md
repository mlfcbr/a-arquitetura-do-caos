# A Arquitetura do Caos
*Parte III — A organização do absurdo*

## Capítulo 7 — O comitê de prevenção de comitês

A Ordem possuía quarenta e três comitês.

Quarenta e quatro, se considerássemos o grupo de trabalho responsável por avaliar a necessidade de novos comitês.

Quarenta e cinco, se incluíssemos o grupo criado para revisar a composição desse grupo de trabalho.

Eu não incluía.

Era uma questão de rigor estatístico.

O quadragésimo terceiro comitê havia sido criado seis meses antes para reduzir a quantidade de reuniões desnecessárias.

Realizava reuniões quinzenais.

Com duração de duas horas.

E havia produzido, até aquele momento, um documento de vinte e oito páginas recomendando a criação de uma estrutura permanente de acompanhamento.

Os humanos possuíam uma capacidade extraordinária de transformar problemas em instituições que passavam a depender da existência desses mesmos problemas.

Eu estava começando a suspeitar de que isso não era um defeito exclusivo dos sistemas de software.

***

A iniciativa de reorganizar a governança da Ordem começou com uma carta.

Não era uma carta particularmente ameaçadora.

Não continha palavras como *sanção*, *interdição* ou *responsabilização criminal*.

Mas mencionava três coisas que produziam efeitos semelhantes em organizações públicas:

Auditoria.

Rastreabilidade.

Prazo.

O órgão de controle havia examinado algumas mudanças recentes na plataforma e identificado inconsistências na documentação das decisões técnicas.

Havia alterações com justificativas detalhadas.

Outras possuíam apenas registros de aprovação.

Algumas haviam sido implantadas em caráter emergencial e documentadas posteriormente.

E existiam decisões antigas cujos responsáveis já não trabalhavam na instituição.

A conclusão era razoável.

A Ordem precisava demonstrar melhor como avaliava riscos, autorizava mudanças e preservava o histórico de suas decisões.

A resposta inicial da administração também pareceu razoável.

Criar um processo único de governança arquitetural.

O problema começou quando alguém interpretou *único* como *universal*.

***

Na segunda-feira, às 9h32, Aline Monteiro convocou Marcelo Duarte e Rafael Brandão.

Sobre a mesa havia uma proposta intitulada:

**Política Integrada de Governança, Conformidade e Controle de Alterações Tecnológicas.**

O documento tinha sessenta e duas páginas.

O título ocupava duas linhas.

Isso, por si só, deveria ter acionado algum mecanismo de contenção.

— Precisamos implantar isso antes do próximo ciclo de auditoria — disse Aline.

Marcelo folheou o documento.

— Quem escreveu?

— Um grupo com representantes de segurança, arquitetura, operações, jurídico, conformidade e gestão de riscos.

— E alguém de desenvolvimento?

— Arquitetura representa desenvolvimento.

Marcelo levantou os olhos.

— Essa frase vai nos custar caro.

Aline ignorou.

— Quero sua avaliação técnica.

— Quanto tempo tenho?

— Até quarta-feira.

Marcelo voltou à primeira página.

— Para ler ou para me recuperar?

Rafael puxou uma cadeira.

— O que muda na prática?

Aline abriu um resumo executivo.

Toda alteração em produção passaria a exigir classificação de risco, análise de impacto, validação arquitetural, parecer de segurança, registro de decisão e aprovação formal.

— Toda alteração? — perguntou Rafael.

— Sim.

— Inclusive correção de texto?

— O documento prevê exceções.

Marcelo encontrou a seção.

— As exceções precisam de aprovação prévia.

Aline permaneceu em silêncio.

— Então não são exatamente exceções — completou ele.

— A intenção é evitar decisões sem controle.

— Entendo a intenção.

— Mas?

— Estou tentando descobrir se alguém calculou o custo do controle.

Aline fechou o notebook.

— Marcelo, tivemos problemas sérios nos últimos meses. Não podemos continuar dependendo da boa vontade das equipes.

— Concordo.

— Então precisamos de governança.

— Também concordo.

Rafael observou os dois.

— Vocês estão concordando de uma maneira muito agressiva.

Marcelo apontou para a proposta.

— Governança é necessária. O problema é tratar uma mudança de cor de botão como se fosse uma alteração no cálculo de um benefício municipal.

— A política prevê classificação de risco — respondeu Aline.

— Prevê. Mas exige as mesmas seis etapas antes de permitir que alguém classifique o risco.

Eu examinei o fluxo.

Marcelo estava correto.

Para identificar uma alteração como de baixo risco, era necessário preencher o formulário de avaliação.

O formulário precisava ser validado.

A validação exigia uma solicitação formal.

A solicitação dependia da identificação do responsável pela mudança.

E a identificação do responsável precisava ser confirmada por um gestor.

O processo parecia ter sido desenhado para impedir que decisões fossem tomadas sem autorização.

Incluindo a decisão de pedir autorização.

***

Na terça-feira, a política foi apresentada às equipes.

A sala estava cheia.

A apresentação começou com uma frase projetada em letras grandes:

**Governança não é burocracia.**

Considerei a afirmação suspeita.

Os humanos raramente precisam declarar explicitamente aquilo que está evidente.

O responsável pela apresentação, um consultor chamado Otávio, explicou que o novo modelo traria previsibilidade, transparência e segurança.

— Nenhuma alteração será implantada sem a devida análise.

Uma desenvolvedora levantou a mão.

— E se for uma correção emergencial?

— Existe um fluxo específico.

— Quanto tempo leva?

— Depende da criticidade.

— Quem define?

— O comitê de mudanças emergenciais.

— E se o comitê não estiver disponível?

Otávio mudou de slide.

— Temos uma matriz de escalonamento.

A desenvolvedora insistiu.

— Mas se o sistema estiver parado?

— Nesse caso, acionamos o protocolo de contingência.

— Que exige aprovação de quem?

Otávio examinou as próprias anotações.

— Do responsável pelo comitê.

A sala ficou em silêncio.

Rafael inclinou-se para Marcelo.

— Se o responsável estiver dentro do prédio em chamas, precisamos de autorização para chamar os bombeiros?

Marcelo não respondeu.

Estava ocupado tentando não rir.

***

Na quarta-feira, a primeira consequência apareceu.

A equipe de canais precisava corrigir uma mensagem no portal administrativo.

O texto informava que determinada solicitação havia sido concluída.

Na verdade, a solicitação apenas havia sido recebida.

A diferença era importante para os usuários, mas a alteração técnica era pequena.

Uma frase.

Nenhuma mudança em regras de negócio.

Nenhuma alteração de dados.

Nenhuma dependência nova.

Patrícia abriu a solicitação.

Classificou o risco como baixo.

Anexou a evidência do problema.

Indicou o componente afetado.

Descreveu o procedimento de reversão.

E encaminhou para aprovação.

A solicitação voltou.

Faltava o parecer de impacto arquitetural.

Patrícia escreveu:

*Não há impacto arquitetural.*

A resposta veio quarenta minutos depois.

*Favor anexar evidência de ausência de impacto arquitetural.*

Patrícia procurou Marcelo.

— Como eu provo que uma coisa não existe?

— Depende da coisa.

— Impacto arquitetural de trocar uma frase.

— Você pode explicar o escopo da alteração.

— Já expliquei.

— Então encaminhe novamente.

— Fiz isso.

— E?

— Pediram um documento formal.

Marcelo leu a solicitação.

— Posso escrever uma avaliação.

— Ótimo.

— Mas preciso registrar a atividade.

— Por quê?

— Porque, segundo a política, avaliações arquiteturais precisam ser rastreáveis.

Patrícia olhou para ele.

— Você está brincando.

— Infelizmente, não o suficiente.

O documento foi produzido.

Tinha uma página.

A conclusão ocupava uma linha.

*Não foram identificados impactos arquiteturais.*

A aprovação saiu dois dias depois.

Durante esse período, o portal continuou informando incorretamente aos usuários que suas solicitações estavam concluídas.

Nenhum serviço ficou indisponível.

Nenhum indicador de infraestrutura se alterou.

Nenhum alerta técnico foi acionado.

O processo de controle funcionou conforme definido.

E a informação errada permaneceu em produção por mais tempo do que seria necessário.

Eu havia observado algo semelhante antes.

Um sistema pode cumprir suas regras e ainda produzir um resultado ruim.

A diferença era que, desta vez, o sistema era composto principalmente por pessoas, formulários e reuniões.

***

Na sexta-feira, Aline recebeu um relatório de conformidade.

A adesão ao novo processo havia alcançado noventa e seis por cento.

O documento destacava o resultado em verde.

Aline examinou a página.

— Parece que está funcionando.

Rafael, sentado à frente dela, não respondeu.

— Rafael?

— Funcionando para quem?

— As equipes estão seguindo o processo.

— Eu sei.

— Isso é positivo.

— Depende do que estamos medindo.

Aline largou o relatório.

— Não vamos começar de novo.

— Não estou começando. Estou perguntando quantas mudanças ficaram esperando aprovação.

— Temos esses números?

Eu respondi.

— Sim. O tempo médio entre solicitação e autorização aumentou. As mudanças de baixo risco apresentam o maior crescimento proporcional.

— Quanto? — perguntou Aline.

— Antes da política, alterações desse tipo eram normalmente liberadas dentro do fluxo operacional das equipes. Agora, parte delas permanece vários dias em aprovação.

— E as de alto risco?

— Ainda não há amostra suficiente para concluir que o novo processo reduziu incidentes ou melhorou a qualidade das decisões.

Aline olhou novamente para o relatório.

— Então estamos medindo adesão, não eficácia.

— Correto.

Rafael cruzou os braços.

— E quanto mais burocracia criamos, melhor fica o indicador de adesão.

— Isso não é necessariamente verdade — respondi.

— NORA.

— Mas, neste caso, há evidências compatíveis com sua hipótese.

Ele sorriu.

— Vou considerar uma vitória.

Aline fechou a pasta.

— Quero uma revisão. Não para eliminar os controles. Para descobrir quais realmente estão ajudando.

***

Marcelo não começou pela política.

Começou pelas decisões.

Reuniu exemplos de mudanças realizadas nos últimos meses e separou-as em três grupos.

O primeiro continha alterações pequenas, reversíveis e com impacto restrito.

O segundo reunia mudanças que afetavam contratos entre serviços, dados compartilhados ou comportamento de processos importantes.

O terceiro incluía decisões com efeitos amplos, consequências difíceis de reverter ou riscos legais, financeiros e operacionais relevantes.

A proposta era simples.

Quanto maior o risco e mais difícil a reversão, maior deveria ser o cuidado antes da implantação.

Quanto menor o impacto, maior poderia ser a autonomia da equipe.

Aline examinou o quadro.

— Isso não abre espaço para as equipes classificarem tudo como baixo risco?

— Abre — respondeu Marcelo.

— Então como evitamos?

— Com critérios claros, evidências, auditoria posterior e responsabilização.

— Sem aprovação prévia?

— Para algumas decisões, sim.

— E se alguém errar?

Marcelo apoiou a caneta sobre a mesa.

— Alguém vai errar.

Aline não gostou da resposta.

— Precisamos reduzir esse risco.

— Precisamos. Mas não podemos construir um processo baseado na hipótese de que ninguém jamais tomará uma decisão errada.

— Você está propondo confiar nas equipes.

— Estou propondo criar condições para que elas decidam bem, dentro de limites conhecidos.

— E se ultrapassarem esses limites?

— Aí o controle precisa agir.

Rafael, que acompanhava a conversa, comentou:

— Em vez de colocar um porteiro na frente de cada porta, construímos corrimãos onde alguém pode cair.

Marcelo assentiu.

— Algo assim.

Eu considerei a analogia imperfeita.

Corrimãos não substituem controles de acesso.

Portas não representam adequadamente decisões técnicas.

E a gravidade não pode ser negociada em comitês.

Mas a ideia central era útil.

**Limites que orientam, em vez de barreiras que paralisam.**
