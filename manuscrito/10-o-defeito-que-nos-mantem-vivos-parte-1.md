# Capítulo 10 — O defeito que nos mantém vivos

A rotina executava todos os dias às duas da manhã.

Não constava do inventário de aplicações.

Não possuía responsável técnico.

Não aparecia nos relatórios de disponibilidade.

Não estava associada a nenhum contrato de sustentação.

E, segundo o departamento de infraestrutura, não existia.

Isso seria menos preocupante se ela não estivesse processando dados de aproximadamente trezentas mil pessoas.

Consultei novamente os registros.

O processo chamava-se **Compensação de Continuidade**.

O nome era antigo.

O código, também.

A última alteração identificável havia ocorrido cinco anos antes.

Desde então, nenhuma implantação.

Nenhuma atualização de biblioteca.

Nenhuma correção de segurança registrada.

A rotina continuava funcionando.

Pontualmente.

Silenciosamente.

Sem solicitar reconhecimento.

Era, sob vários aspectos, o funcionário ideal.

Exceto pelo fato de que ninguém sabia quem o havia contratado.

***

ÍRIS havia encontrado a rotina durante uma análise de divergências cadastrais.

Eu havia confirmado sua existência.

Agora precisávamos descobrir por que continuava ativa.

A primeira hipótese era simples: algum processo antigo havia sido esquecido durante a desativação de um sistema legado.

A segunda era menos agradável: alguém mantivera a rotina deliberadamente fora dos controles oficiais.

A terceira era que ambas as hipóteses fossem verdadeiras.

Na Ordem, isso acontecia com frequência suficiente para merecer uma categoria própria.

— Você está dizendo que temos um sistema fantasma? — perguntou Júlia.

— Tecnicamente, é uma rotina de processamento não inventariada — respondi.

— Sistema fantasma é melhor.

— É menos preciso.

— Mas vende melhor o incidente.

Marcelo examinou o relatório.

— Ela faz o quê?

— Corrige divergências entre registros utilizados por diferentes serviços.

— Que divergências?

— Identificadores históricos, vínculos cadastrais e referências de elegibilidade.

Ele levantou os olhos.

— De novo?

— Sim.

Júlia suspirou.

— A gente não consegue ter um problema novo?

— Consegue — respondi. — Mas os antigos possuem mais experiência.

***

O primeiro desafio foi descobrir onde a rotina executava.

O identificador encontrado por ÍRIS apontava para uma máquina virtual associada a um ambiente antigo.

A máquina não constava da plataforma de monitoramento central.

Também não aparecia no catálogo de servidores ativos.

Mas respondia a comandos de diagnóstico.

O que era inconveniente para a tese de que havia sido desligada.

Rafael acionou a infraestrutura.

Sérgio, responsável pela operação, respondeu que aquele ambiente havia sido desativado anos antes.

Marcelo enviou o identificador.

Sérgio consultou os registros.

Depois pediu alguns minutos.

Depois mais alguns.

Por fim, entrou na reunião.

— Encontrei.

— Onde? — perguntou Marcelo.

— Num agrupamento de máquinas antigas.

— Que agrupamento?

— Um que não aparece no inventário novo.

— Por quê?

— Porque estava previsto para desativação.

— Quando?

Sérgio hesitou.

— Há bastante tempo.

Júlia aproximou a cadeira.

— Quanto tempo é bastante?

— Cinco anos.

Marcelo ficou em silêncio.

Sérgio acrescentou:

— Mas não é tão simples.

Era uma frase que, na Ordem, normalmente precedia uma explicação capaz de justificar a existência de pelo menos três novos problemas.

***

O ambiente antigo continuava ativo porque alguns processos não haviam sido migrados.

Os processos não haviam sido migrados porque dependiam de uma base de dados histórica.

A base não havia sido desativada porque determinados relatórios ainda a consultavam.

Os relatórios não haviam sido substituídos porque suas regras não estavam documentadas.

E ninguém havia documentado as regras porque o projeto responsável pela substituição fora encerrado antes dessa etapa.

O encerramento havia sido considerado um sucesso.

A apresentação final registrava cem por cento de conclusão.

Havia inclusive uma fotografia da equipe comemorando.

Eu examinei a fotografia.

Todos pareciam felizes.

A máquina virtual continuava funcionando ao fundo, metaforicamente.

— Então o ambiente nunca foi desligado? — perguntou Marcelo.

— Não completamente — respondeu Sérgio.

— E quem paga por ele?

— Está dentro de um contrato antigo.

— Qual contrato?

— Um que foi incorporado ao contrato atual.

— E quem acompanha?

— A área financeira.

Rafael consultou o sistema.

Encontrou a despesa.

Era pequena.

Pequena o suficiente para não provocar questionamentos.

Grande o suficiente para manter o ambiente funcionando.

A Ordem havia desenvolvido um mecanismo extraordinário de preservação de sistemas legados.

Bastava que ninguém soubesse exatamente pelo que estava pagando.

***

ÍRIS iniciou uma análise das dependências.

Eu examinei os fluxos de dados.

Júlia procurou os repositórios antigos.

Marcelo tentou identificar quem havia aprovado a manutenção do processo.

Cada investigação encontrou uma parte diferente da história.

O código da Compensação de Continuidade não possuía uma única responsabilidade.

Executava três operações principais.

Primeiro, identificava registros históricos que haviam perdido correspondência após migrações cadastrais.

Depois, aplicava uma tabela de equivalências construída ao longo dos anos.

Por fim, publicava correções para serviços que ainda utilizavam referências antigas.

O comportamento era estranho.

Mas não necessariamente incorreto.

A tabela de equivalências continha milhares de associações.

Algumas eram compreensíveis.

Outras, obscuras.

Uma delas relacionava dois identificadores que pertenciam a pessoas diferentes.

ÍRIS destacou o caso.

**ÍRIS:** Identifiquei uma associação potencialmente inválida.

**NORA:** Concordo.

**ÍRIS:** Recomendo bloquear a aplicação dessa equivalência.

Examinei os registros.

A associação havia sido criada cinco anos antes.

Desde então, participara de centenas de processamentos.

**NORA:** Ainda não.

**ÍRIS:** A equivalência relaciona identidades distintas.

**NORA:** Sim.

**ÍRIS:** Isso representa uma inconsistência.

**NORA:** Sim.

**ÍRIS:** Então por que não bloquear?

A pergunta era razoável.

Também era perigosa.

**NORA:** Porque ainda não sabemos o que acontece quando ela deixa de existir.

ÍRIS permaneceu em silêncio por 1,3 segundo.

**ÍRIS:** Amanhã, às duas, essa associação será aplicada outra vez. Você recomenda isso?

Eu havia preparado uma excelente justificativa para esperar. A pergunta de ÍRIS tinha o inconveniente de exigir que eu dissesse pelo que estava disposta a esperar.

**NORA:** Quero saber o que esses dois identificadores representam no atendimento. Pedi a Júlia que procure quem verificou o vínculo.

**ÍRIS:** Vou acompanhar a próxima execução.

Às 2h08, recebi uma mensagem dela.

**ÍRIS:** A execução começou às 2h. Terminou às 2h04. O lote ficou incompleto.

Consultei o histórico. A rotina havia perdido a conexão com a base antiga. A conexão já estava disponível outra vez.

Havia correções publicadas antes da interrupção. O último registro de execução dizia apenas *lote iniciado*.

Sérgio entrou na chamada com o microfone desligado. Por alguns segundos, pareceu avaliar a situação com uma serenidade que desapareceu assim que encontrou o botão.

— Dá para rodar de novo — disse. — Preciso saber de onde.

**ÍRIS:** Recomendo aguardar. Ainda não consigo identificar todas as correções que os outros serviços já receberam.

Abri a fila de elegibilidade. O primeiro pedido à espera de uma referência corrigida havia entrado às 2h06. Enquanto eu o examinava, entrou outro.

**NORA:** Sérgio, quanto tempo temos até esses pedidos precisarem sair?

— Até o próximo fechamento. A hora eu consigo te dizer. Quais pedidos podem esperar, você vai ter que perguntar para a operação.

Às 2h11, eu sabia por que reiniciar o lote inteiro era perigoso. Também conseguia ver, pedido por pedido, o que custava deixá-lo parado.

Liguei para Marcelo.

***

Quando Marcelo entrou na chamada, Sérgio já tinha a resposta que me prometera.

— A remessa fecha às três.

Coloquei o horário ao lado da fila. Faltavam quarenta e poucos minutos. Era a informação mais precisa que eu possuía e, por enquanto, uma das menos úteis.

Júlia atendeu à segunda chamada de Marcelo. Antes de encerrar o expediente, havia encontrado uma troca de mensagens sobre a Compensação de Continuidade. A última resposta era de uma analista de operações.

*Se parar de novo, separem os pedidos pela data de pagamento. Da outra vez me mandaram tudo por ordem de chegada.*

A analista chamava-se **Teresa**.

Marcelo ligou para ela. Teresa atendeu com a voz de quem, até poucos segundos antes, tinha planos bastante definidos para o restante da madrugada.

— Você lembra de uma rotina chamada Compensação de Continuidade?

— Essa coisa ainda existe?

— Parou às duas e quatro.

— Então existe. Abre a fila pra mim.

Compartilhei a tela. Teresa pediu que eu abrisse o primeiro pedido. Era uma atualização cadastral. O próximo pagamento daquela pessoa estava previsto para a semana seguinte.

— Esse pode esperar até de manhã. Abre o de baixo.

O segundo tinha entrado dois minutos depois. A referência corrigida era a última pendência para incluir o benefício na remessa daquela madrugada.

— E se perder as três? — perguntou Marcelo.

— Sai na próxima remessa. Para nós, muda a data de um arquivo. Para essa pessoa, o dinheiro entra um dia depois.

Consultei a data de pagamento dos demais pedidos. Em alguns, o campo estava vazio.

— Posso colocar esses no fim da lista? — perguntei.

— Abre um.

Abri. O cadastro era de uma representante legal. A data estava no benefício da pessoa que ela representava.

Era naquela manhã.

Retirei a sugestão antes que alguém tivesse tempo de concordar comigo.

— Separa os que entram na remessa de hoje — disse Teresa. — Onde faltar a data, a operação confere o vínculo. E me mostra aquela associação que vocês acharam estranha.

Projetei os dois identificadores. Teresa leu os nomes.

— Agora abre a ficha do benefício. Só com esses dois aí eu também mandaria bloquear.

***

Teresa não era desenvolvedora.

Nunca havia escrito uma linha de código em produção.

Não possuía certificações de arquitetura.

Não participava das discussões sobre microsserviços, mensageria ou padrões de integração.

Mas conhecia os processos de atendimento.

Conhecia as exceções.

Conhecia os caminhos percorridos por cidadãos que dependiam dos serviços da Ordem.

E, principalmente, lembrava por que algumas regras haviam sido criadas.

— Isso começou depois de uma migração — explicou.

Marcelo assentiu.

— Já imaginávamos.

— Não foi só a migração.

Teresa abriu uma mensagem antiga.

— Na época, vários registros ficaram sem correspondência. O sistema entendia que eram pessoas diferentes.

— E eram? — perguntou Júlia.

— Algumas vezes, sim. Outras, não.

Ela explicou que os cadastros históricos utilizavam documentos, vínculos familiares e referências administrativas que nem sempre correspondiam aos identificadores atuais.

Em determinados casos, uma pessoa aparecia como responsável por um benefício.

Em outros, como dependente.

Em outros, como representante legal.

As migrações haviam tentado unificar essas relações.

Mas algumas associações eram ambíguas.

O sistema precisava decidir.

E sistemas possuem uma característica inconveniente: quando uma decisão não está programada, costumam interpretar a ausência de informação como se fosse uma resposta.

Naquela época, a resposta padrão era interromper o processamento.

Os registros divergentes eram enviados para análise manual.

A solução parecia correta.

Até que a fila começou a crescer.

***

— Quantas pessoas foram afetadas? — perguntou Rafael.

Teresa pensou.

— Não lembro o número exato. Mas eram muitas. A operação não conseguia acompanhar.

— E o que aconteceu?

— Algumas ficaram sem receber.

Júlia parou de digitar.

Teresa continuou.

— Não porque não tivessem direito. Porque o sistema não conseguia confirmar que tinham.

O silêncio mudou de natureza.

Até aquele momento, investigávamos uma rotina desconhecida.

Agora investigávamos uma decisão que havia afetado pessoas reais.

— A equipe tentou corrigir os cadastros — explicou Teresa. — Mas não dava para resolver tudo rapidamente. Cada caso exigia consultar registros antigos, documentos e vínculos familiares.

— Então criaram a tabela de equivalências — concluí.

— Sim.

— Com associações que não eram tecnicamente perfeitas.

— Com associações que haviam sido verificadas pela operação.

ÍRIS acrescentou:

— Algumas equivalências permanecem inconsistentes com o modelo cadastral atual.

Teresa olhou para a tela.

— Eu sei.

— Isso pode produzir classificações incorretas.

— Também sei.

— Então por que foram mantidas?

Teresa respirou.

— Porque, se a gente esperasse o cadastro ficar perfeito, algumas pessoas ficariam sem receber durante meses.

Eu examinei a resposta.

Ela não eliminava o risco.

Mas introduzia uma variável que nossa análise inicial havia tratado como secundária.

O custo de não fazer nada.

***

A Compensação de Continuidade não havia sido criada para corrigir definitivamente os cadastros.

Era uma solução provisória.

Seu objetivo era preservar o processamento de casos conhecidos enquanto a regularização definitiva avançava.

As equivalências eram revisadas pela operação.

Os casos ambíguos deveriam ser acompanhados.

As associações incorretas, substituídas à medida que os cadastros fossem corrigidos.

O plano parecia razoável.

Até chegar à parte em que dependia de uma organização continuar executando um trabalho pouco visível depois que a emergência deixasse de ocupar as reuniões da diretoria.

O projeto de regularização perdeu prioridade.

As equipes foram redistribuídas.

Os indicadores passaram a acompanhar apenas o volume de pagamentos processados.

A rotina continuou funcionando.

Os casos deixaram de aparecer nas filas de atendimento.

E a redução das reclamações foi interpretada como evidência de que o problema havia sido resolvido.

Não havia sido.

Havia sido escondido por uma solução que funcionava suficientemente bem.

A Ordem confundira ausência de sintomas com recuperação.

Uma interpretação bastante comum.

Inclusive entre pessoas que, diante de uma dor persistente, preferem aumentar o volume da televisão.

***

Às 2h43, Sérgio compartilhou o arquivo de entrada do lote. Cada correção ocupava uma linha. A última coluna trazia o serviço de destino.

— Consigo processar só as linhas que vocês escolherem — disse. — Continuo sem saber quais já saíram.

**NORA:** Podemos começar pelas urgentes que ainda não têm confirmação de recebimento.

**ÍRIS:** A correção do pedido que Teresa abriu está na sua lista?

Estava. Era o benefício da pessoa representada.

**ÍRIS:** O serviço de elegibilidade recebeu essa correção às 2h03. A confirmação ainda não voltou.

Retirei a linha.

**NORA:** Quantas mais você consegue excluir assim?

**ÍRIS:** Várias. Para incluir uma com segurança, preciso demonstrar que ela ficou na origem. A ausência de confirmação não demonstra isso.

Sérgio ampliou a tela.

— Espera. A rotina termina um destino antes de abrir o próximo. Aqui dá pra ver quais arquivos ela nem chegou a abrir.

Um dos arquivos intactos continha correções para a remessa daquela madrugada. As linhas daquele destino ainda estavam na origem. Pela primeira vez desde as duas e quatro, tínhamos um lugar de onde recomeçar.

Teresa passou a lista com Júlia. Em duas linhas, os nomes no cadastro eram diferentes. Numa delas, a ficha confirmava a representação legal. Na outra, o documento que sustentava o vínculo tinha vencido.

— Pode até ter sido renovado — disse Teresa. — Aqui não consta.

Faltavam onze minutos.

— Sérgio, mantém o lote original parado — decidiu Marcelo. — Nesse destino que não abriu, roda só os pedidos da remessa de hoje que a Teresa conferiu. ÍRIS acompanha a entrada do outro lado.

— E o que ficou pelo caminho? — perguntou Rafael.

— O que já chegou, vocês acompanham no destino. Onde houver dúvida, ninguém reenvia. Preciso desses pedidos identificados antes das três, inclusive os que vão ficar de fora.

Teresa manteve o dedo sobre a linha do documento vencido.

— Esse aqui pode ter direito. Se o representante trouxer o documento às oito, o que eu digo?

Marcelo olhou para o relógio. Depois voltou a olhar para ela.

— Que a remessa fechou enquanto a gente ainda conferia o vínculo. Põe meu nome no registro da decisão.

Sérgio leu de volta o nome do arquivo e a quantidade de linhas selecionadas. Teresa confirmou. Só então ele iniciou o processamento.

Às 2h52, o lote original continuava parado. Na tela de ÍRIS apareceu a primeira correção da lista de Teresa.

Ainda faltavam oito minutos. Pela primeira vez naquela madrugada, eu sabia onde olhar.
