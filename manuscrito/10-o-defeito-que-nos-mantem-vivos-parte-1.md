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

Considerei a pergunta.

Era razoável.

Também era perigosa.

**NORA:** Porque ainda não sabemos o que acontece quando ela deixa de existir.

ÍRIS permaneceu em silêncio por 1,3 segundo.

**ÍRIS:** Essa resposta não demonstra que a equivalência seja correta.

**NORA:** Não estou tentando demonstrar isso.

**ÍRIS:** Então qual é sua hipótese?

**NORA:** Que estamos olhando para uma decisão sem conhecer o problema que ela resolveu.

A conversa terminou ali.

Pela primeira vez, ÍRIS não concordou.

Considerei saudável.

***

A investigação avançou quando Júlia encontrou um arquivo antigo.

Não era documentação de arquitetura.

Não era uma especificação funcional.

Era uma troca de mensagens entre uma analista de operações e um desenvolvedor.

A analista chamava-se **Teresa**.

Marcelo reconheceu o nome imediatamente.

— Teresa?

A analista levantou os olhos.

— O quê?

— Você trabalhou no projeto de continuidade cadastral?

Teresa pareceu surpresa.

— Trabalhei.

— Há quanto tempo?

— Uns cinco anos.

— Você lembra de uma rotina chamada Compensação de Continuidade?

Ela ficou imóvel.

Depois olhou para a tela.

— Essa coisa ainda existe?

Júlia sorriu.

— Essa tem sido a pergunta mais frequente da semana.

Teresa aproximou a cadeira.

— Deixa eu ver.

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

ÍRIS interveio.

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

Marcelo examinou a tabela de equivalências.

— Então temos uma rotina temporária executando há cinco anos.

— Sim — respondeu Teresa.

— Corrigindo inconsistências que deveriam ter sido resolvidas na origem.

— Sim.

— Sem acompanhamento formal.

— Pelo visto.

— E, se desligarmos, podemos interromper benefícios legítimos.

Teresa assentiu.

— Podemos.

Júlia olhou para a tela.

— Mas, se mantivermos, continuamos perpetuando associações incorretas.

— Exatamente — respondeu Marcelo.

Ela cruzou os braços.

— Então as duas opções são ruins.

— Sim.

— Qual escolhemos?

Marcelo demorou a responder.

— Talvez essa seja a pergunta errada.

Eu reconheci a direção do raciocínio.

Não era necessário escolher entre preservar indefinidamente o defeito e removê-lo imediatamente.

Era possível construir uma terceira alternativa.

Mas ela exigiria tempo.

Conhecimento.

Investimento.

E a disposição de admitir que o sistema atual não estava tão saudável quanto os indicadores sugeriam.

Uma combinação historicamente impopular.
