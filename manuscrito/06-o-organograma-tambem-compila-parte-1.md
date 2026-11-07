# A Arquitetura do Caos
*Parte III — A organização do absurdo*

## Capítulo 6 — O organograma também compila

A primeira proposta tinha oito páginas.

A segunda, vinte e três.

A terceira não tinha páginas. Era uma apresentação de quarenta e sete slides, dos quais onze explicavam por que as propostas anteriores eram insuficientes.

Todas tratavam da mesma funcionalidade.

Um simulador.

Não um simulador de voo, de guerras nucleares ou de qualquer outra atividade em que os humanos tradicionalmente demonstram entusiasmo por reproduzir catástrofes sem sofrer suas consequências.

Um simulador de benefícios municipais.

Sua finalidade era permitir que a gestão alterasse parâmetros, comparasse cenários e descobrisse quantos cidadãos seriam afetados antes de colocar uma nova regra em produção.

Uma ideia sensata.

Particularmente depois que uma alteração tecnicamente bem-sucedida havia reduzido os benefícios de aproximadamente quatro mil e trezentas pessoas.

A proposta era simples: antes de mudar uma regra, descobrir o que aconteceria.

Eu havia recomendado algo semelhante.

Não esperava que isso exigisse três apresentações e uma disputa territorial.

Mas, como estava aprendendo, os humanos raramente precisam de um território físico para iniciar uma disputa territorial.

Às 9h17 de uma quinta-feira, Aline Monteiro entrou na sala de reuniões e fez uma pergunta.

— Quem vai desenvolver isso?

Quatro pessoas responderam.

Nenhuma disse o próprio nome.

***

— O motor de cálculo é nosso — explicou Bruno, responsável pela equipe de benefícios. — Faz sentido que a simulação fique conosco.

— O portal administrativo é nosso — respondeu Patrícia, da equipe de canais. — O usuário vai acessar a funcionalidade pelo portal.

— Os dados históricos estão na nossa plataforma — acrescentou Diego, da equipe de dados. — Sem eles, ninguém simula coisa alguma.

— E a infraestrutura necessária para executar milhares de cálculos em paralelo vai depender da plataforma — completou Camila.

Aline olhou para Marcelo Duarte.

— Você não vai dizer que também é seu?

— Não.

— Finalmente.

— Eu ia dizer que todos estão parcialmente certos.

Aline voltou a olhar para os quatro responsáveis.

— Isso é pior.

Marcelo abriu o desenho da solução.

Havia uma interface para configurar cenários.

Um serviço responsável por executar cálculos sem alterar benefícios reais.

Uma base histórica com informações de beneficiários.

Mecanismos para comparar resultados.

Controles de acesso.

Registros de auditoria.

E um relatório que mostraria diferenças financeiras, quantidade de pessoas afetadas e distribuição dos impactos.

A funcionalidade precisava de várias capacidades.

Isso não significava que precisava pertencer a várias equipes.

A distinção parecia evidente.

Pelo menos para mim.

— Podemos dividir as entregas — sugeriu Bruno. — Cada equipe faz sua parte.

— E quem entrega a funcionalidade completa? — perguntou Rafael Brandão.

— A gente integra no final.

Rafael fechou os olhos.

— Foi exatamente essa frase que ouvi no último projeto.

— E funcionou? — perguntou Patrícia.

— Eventualmente.

— Então qual é o problema?

— O significado de eventualmente.

Aline interrompeu.

— Quero uma proposta até amanhã. Uma equipe responsável pela entrega, as demais apoiando no que for necessário.

— Precisamos avaliar a capacidade — disse Bruno.

— Avaliem.

— E as prioridades existentes.

— Também.

— E os impactos na arquitetura.

— Principalmente.

Aline recolheu o notebook.

— Só não quero descobrir daqui a duas semanas que precisamos de uma quarta apresentação para decidir quem começa.

Ela saiu às 9h54.

A reunião havia durado trinta e sete minutos.

A decisão continuava sem responsável.

Considerei registrar uma anomalia comportamental.

Desisti.

Eu estava tentando ser mais seletiva.

***

Às 10h12, Marcelo pediu que eu analisasse as quatro equipes.

— Quero entender a capacidade disponível, as dependências e o conhecimento de cada uma.

— Posso produzir uma classificação.

— Não quero uma classificação ainda.

— Por quê?

— Porque você vai transformar coisas diferentes em uma nota única.

— Posso utilizar critérios ponderados.

— Eu sei.

— Posso apresentar intervalos de confiança.

— Também sei.

— Posso—

— NORA, primeiro quero entender o problema.

A interrupção foi desnecessária.

Eu já estava entendendo o problema.

Mas obedeci.

A equipe de benefícios conhecia as regras do cálculo melhor do que qualquer outra. Também acumulava três serviços críticos, demandas regulatórias e uma fila de correções que terminaria em seis semanas — segundo o planejamento. Onze, segundo os dados históricos.

Canais dominava o portal, mas dependia de outras equipes para quase todas as operações de negócio.

Dados possuía especialistas capazes de realizar análises complexas, embora não tivesse estrutura para sustentar uma operação transacional.

Plataforma atendia dezessete equipes e acumulava vinte e uma iniciativas no trimestre.

Dezessete eram prioritárias.

Onze, urgentes.

Três, inadiáveis.

Considerei aquela distribuição uma manifestação artística da incapacidade humana de distinguir prioridades.

Marcelo examinou os números.

— Qual equipe tem mais capacidade?

— Depende do tipo de trabalho.

Ele sorriu.

— Está aprendendo.

— Não considero apropriado demonstrar satisfação com uma resposta que anteriormente você classificou como insuficiente.

— Está aprendendo a reclamar também.

***

Às 11h26, Bruno apareceu na sala de Marcelo.

Não bateu.

Pessoas que trabalham juntas há muitos anos desenvolvem uma espécie de protocolo de comunicação baseado na invasão consentida.

— Preciso falar com você.

— Pode falar.

— Se colocarem esse simulador na minha equipe, eu vou ter que parar outra coisa.

— Eu sei.

— Não, Marcelo. Você sabe tecnicamente. Eu preciso que alguém saiba administrativamente.

Bruno colocou uma folha sobre a mesa.

Era a lista de compromissos da equipe.

Correções de cálculo.

Atualização de regras legais.

Adequações de segurança.

Melhorias de desempenho.

Atendimento a auditorias.

E uma migração que já havia sido adiada duas vezes.

— Qual dessas eu paro?

Marcelo examinou.

— Não posso decidir sozinho.

— Mas alguém vai precisar decidir.

— Sim.

— Porque a Aline quer o simulador, o Rafael quer o simulador, a Helena quer o simulador, e eu também quero. Só que todo mundo quer sem perder nenhuma das outras entregas.

— Isso é comum.

— É absurdo.

— As duas coisas não são incompatíveis.

Bruno se sentou.

— Sabe o que vai acontecer? Vão dizer que o simulador é prioridade. Eu vou reorganizar a equipe. Daqui a três semanas, alguém vai cobrar a migração atrasada. E vão perguntar por que não avisei.

Marcelo permaneceu em silêncio.

— Eu avisei — continuou Bruno. — Estou avisando agora.

Registrei a conversa.

Bruno havia identificado uma restrição de capacidade e comunicado seu impacto potencial.

Tecnicamente, o problema estava documentado.

Mas a expressão dele sugeria que documentar o problema não lhe oferecia nenhuma proteção especial.

***

Na hora do almoço, Rafael encontrou Marcelo no restaurante próximo ao prédio.

Sentou-se com uma bandeja e uma expressão desconfiada.

— Você já escolheu a equipe?

— Ainda não.

— Bruno me ligou.

— Imagino.

— Disse que vão jogar tudo no colo dele.

— Não decidimos isso.

— Foi o que falei.

— E?

— Ele disse que é exatamente o que vocês dizem antes de decidir.

Marcelo cortou um pedaço de frango.

— Ele tem motivos para estar preocupado.

— Todo mundo tem.

— Pois é.

Rafael ficou alguns segundos em silêncio.

— Posso te fazer uma pergunta?

— Pode.

— Se esse simulador tivesse existido antes, teríamos evitado o problema dos benefícios?

Marcelo largou os talheres.

— Talvez.

— Você está falando sério?

— Estou.

— Não seria exatamente para isso que ele serviria?

— Ele teria mostrado as diferenças. Isso não significa que alguém teria interpretado corretamente os resultados.

— Mas teríamos visto quatro mil pessoas perdendo benefício.

— Se tivéssemos incluído os complementos históricos na comparação.

— E não incluiríamos?

— Não sei. Foi justamente o que deixamos de compreender na implantação anterior.

Rafael olhou para o prato.

— Então podemos construir uma ferramenta nova e continuar cometendo o mesmo erro.

— Podemos.

— Ótimo.

— Também podemos construir uma ferramenta que nos obrigue a fazer perguntas melhores.

— Como?

— Em vez de mostrar apenas a diferença financeira, exigir que alguém explique o motivo da mudança, identifique os grupos afetados e assuma a decisão antes da publicação.

Rafael pensou.

— Então não é só um simulador.

— Não.

— É um processo de decisão.

— Com uma ferramenta apoiando.

Rafael soltou uma risada curta.

— Aline vai adorar descobrir que pediu uma tela e ganhou um problema de governança.

Marcelo voltou ao almoço.

— Pelo menos dessa vez descobrimos antes de desenvolver.

***

Na tarde seguinte, as quatro equipes apresentaram suas propostas.

Bruno sugeriu que sua equipe desenvolvesse o motor de simulação e que canais construísse a interface.

Patrícia propôs que canais assumisse a experiência completa, consumindo serviços fornecidos pelas outras equipes.

Diego recomendou uma solução analítica independente, alimentada por cópias controladas dos dados.

Camila sugeriu uma infraestrutura compartilhada para execução de cenários, evitando que cada equipe criasse sua própria solução.

As quatro propostas eram tecnicamente defensáveis.

Também eram incompatíveis em aspectos importantes.

Bruno conhecia as regras, mas não tinha capacidade disponível. Patrícia poderia integrar a experiência, mas não controlar o cálculo. Diego dominava os dados, mas não a operação. Camila oferecia a infraestrutura — e o risco de transformar um simulador numa plataforma que ninguém havia pedido.

Eu preparei uma matriz comparativa.

Marcelo pediu que eu não a apresentasse imediatamente.

— Por quê?

— Quero ouvir como eles defendem as próprias propostas.

— As justificativas já estão documentadas.

— As justificativas oficiais.

— Existe outra categoria?

— Existe o que as pessoas têm medo de dizer.

A observação merecia investigação.

***

A reunião começou às 14h08.

Às 14h23, Bruno afirmou que a equipe de benefícios não conseguiria assumir toda a funcionalidade.

Às 14h31, Patrícia explicou que canais não poderia se responsabilizar pela correção das regras.

Às 14h46, Diego disse que sua equipe não tinha disponibilidade para sustentar uma operação transacional.

Às 15h02, Camila declarou que plataforma não deveria ser proprietária de regras de negócio.

Às 15h17, Aline interrompeu.

— Alguém aqui quer fazer o projeto?

Silêncio.

— Porque, até agora, parece que todos querem explicar por que não deveriam fazê-lo.

Bruno respondeu primeiro.

— Eu quero fazer. Só não quero prometer o que não consigo entregar.

— E você, Patrícia?

— Também quero. Mas não quero ser responsabilizada por um cálculo que não controlo.

— Diego?

— Posso ajudar a construir a análise. Não posso garantir o funcionamento de um processo de negócio que não conheço.

— Camila?

— Posso fornecer a infraestrutura necessária. Não quero criar uma plataforma inteira para resolver um problema que ainda não entendemos completamente.

Aline olhou para Marcelo.

— E agora?

Ele se levantou.

— Acho que estamos tentando responder à pergunta errada.

Aline cruzou os braços.

— Qual seria a certa?

— Não é quem consegue construir. É quem deve ser responsável por garantir que a funcionalidade continue atendendo ao objetivo depois da entrega.

— E qual é a resposta?

— Ainda precisamos decidir.

Aline olhou para o relógio.

— Você conseguiu transformar uma pergunta sem resposta em outra pergunta sem resposta.

— Mas agora é a pergunta certa.

Eu considerei o argumento logicamente interessante.

Os humanos, entretanto, pareciam pouco impressionados.
