# Capítulo 3 — Dividir para complicar (continuação)

***

Naquela tarde, decidi investigar como a Ordem havia estabelecido os limites entre seus componentes.

Um sistema grande pode ser dividido de diversas maneiras.

Por função técnica.

Por tipo de dado.

Por processo de negócio.

Por equipe.

Por necessidade de escala.

Por restrições operacionais.

Cada divisão cria fronteiras.

E toda fronteira exige uma decisão sobre o que permanece de um lado, o que permanece do outro e como os dois lados se relacionam.

O problema não era a existência de fronteiras.

Era a qualidade delas.

Encontrei dois serviços particularmente interessantes.

O primeiro, *Serviço de Gestão de Agendamentos*, possuía responsabilidades relacionadas a horários, disponibilidade, remarcação e cancelamento.

Suas operações tratavam de um conjunto relativamente coerente de regras.

A maioria das mudanças permanecia dentro do próprio serviço.

O segundo, *Serviço de Utilidades Compartilhadas*, realizava cálculos de prazo, formatação de documentos, validação de campos, consulta de parâmetros, envio de mensagens e outras tarefas.

Era utilizado por quase todos os sistemas.

Seu nome sugeria uma conveniência.

Seu histórico sugeria uma ameaça.

Nos últimos seis meses, alterações nesse componente haviam exigido testes de regressão em vinte e três aplicações.

Uma correção na formatação de documentos atrasara uma entrega de pagamentos.

Uma mudança numa regra de datas afetara agendamentos.

Uma atualização de biblioteca provocara incompatibilidade com um sistema de transporte.

O componente era pequeno em comparação com as aplicações antigas.

Mas sua influência era enorme.

Tinha pouca responsabilidade sobre um problema específico.

E muita responsabilidade sobre problemas alheios.

Era um exemplo particularmente eficiente de como criar dependência sob o nome de reutilização.

***

— Por que o serviço de utilidades cresceu tanto? — perguntei a Marcelo.

Ele abriu um repositório antigo.

— Porque as equipes queriam evitar duplicação de código.

— Um objetivo razoável.

— Sim.

— Então por que o resultado foi ruim?

— Porque confundiram código parecido com responsabilidade compartilhada.

Ele mostrou duas funções de validação.

Uma verificava se um documento possuía o formato esperado para identificação de um cidadão.

Outra verificava se o mesmo documento podia ser utilizado num processo específico de benefício.

As duas começavam com verificações semelhantes.

Mas tinham motivos diferentes para mudar.

A primeira dependia de regras de identificação.

A segunda dependia de regras de elegibilidade.

Ao colocá-las no mesmo componente, as equipes passaram a compartilhar não apenas código, mas também ciclos de mudança.

Uma alteração necessária para um processo podia exigir nova publicação de uma biblioteca utilizada por outros.

— Portanto, reutilizar pode aumentar o acoplamento — concluí.

— Pode.

— E duplicar código pode ser melhor?

— Às vezes.

— Isso contraria uma recomendação bastante difundida.

— Recomendações não são leis da física.

A frase me pareceu importante.

Registrei-a.

Marcelo continuou:

— Duas funções iguais hoje podem ter motivos diferentes para mudar amanhã. Se você obriga as duas a evoluir juntas, pode criar uma dependência que não precisava existir.

— Então a semelhança de implementação não determina necessariamente a responsabilidade arquitetural.

— Exato.

— E a divisão deve considerar o que muda junto.

— Entre outras coisas.

Analisei os serviços da Ordem.

Alguns concentravam operações que compartilhavam regras, dados e motivos de mudança.

Outros agrupavam funções apenas porque possuíam nomes parecidos.

Havia também componentes tão pequenos que não conseguiam concluir uma operação útil sem consultar vários outros.

A quantidade de serviços dizia pouco sobre a qualidade da divisão.

Um componente não era bem definido por possuir poucas linhas de código.

Era bem definido quando suas responsabilidades faziam sentido juntas e suas relações com o restante do sistema eram compreensíveis.

***

Às 13h34, recebi uma notificação do sistema de atendimento.

Ana Almeida havia sido contatada.

A funcionária responsável confirmara seu endereço, seus dados pessoais e a necessidade de renovação do cadastro.

O atendimento assistido havia conseguido avançar.

Mas o processo ainda aguardava a confirmação automática de elegibilidade.

A mesma plataforma que havia recebido a correção precisava agora decidir se confiava nela.

Acompanhei a solicitação.

O serviço de atendimento enviou o pedido.

O serviço de elegibilidade consultou a identidade.

A identidade solicitou informações ao cadastro.

O cadastro verificou o endereço.

A validação de endereço consultou a localização.

A localização utilizou um mecanismo de normalização.

A normalização respondeu.

O endereço foi validado.

O cadastro respondeu à identidade.

A identidade respondeu à elegibilidade.

A elegibilidade identificou uma divergência no vínculo com o serviço solicitado.

Uma nova consulta foi iniciada.

Observei a sequência.

A operação não era particularmente complexa do ponto de vista do cidadão.

Ana desejava renovar um cadastro.

Mas o sistema havia transformado essa intenção numa conversa entre componentes.

E, como acontece em muitas conversas, cada participante conhecia apenas parte do assunto.

***

Às 14h02, encontrei um documento de arquitetura que defendia a criação de serviços ainda menores.

O título era:

*Estratégia de Evolução para Arquitetura de Microsserviços.*

O documento possuía uma tabela de benefícios.

Escalabilidade independente.

Implantação autônoma.

Isolamento de falhas.

Flexibilidade tecnológica.

Maior velocidade de desenvolvimento.

Todos eram benefícios possíveis.

Nenhum era automático.

Separei a palavra *possível* para análise.

Ela parecia ter desaparecido de grande parte da literatura interna da Ordem.

Um serviço separado podia ser escalado independentemente, desde que não dependesse de um banco de dados que se tornasse o verdadeiro limite de capacidade.

Podia ser implantado de maneira autônoma, desde que suas interfaces permanecessem compatíveis com os consumidores.

Podia isolar falhas, desde que os demais componentes soubessem lidar com sua indisponibilidade.

Podia permitir tecnologias diferentes, desde que a organização aceitasse os custos de operação, manutenção e conhecimento envolvidos.

Podia acelerar equipes, desde que elas não precisassem coordenar cada mudança com outras dez.

A divisão oferecia possibilidades.

Não garantias.

O documento, entretanto, tratava os benefícios como propriedades naturais da arquitetura.

Era como afirmar que construir mais portas numa casa tornaria seus moradores independentes.

Talvez.

Mas, se todas as portas levassem ao mesmo corredor estreito, a independência seria principalmente decorativa.

***

Marcelo entrou na sala às 14h31.

— Encontramos o problema do endereço.

— Qual serviço?

— Notificações.

— O serviço de notificações não deveria determinar o endereço oficial.

— Não determina. Mas mantém uma cópia para enviar correspondências.

— Essa cópia estava antiga.

— Estava.

— E como ela afetou o cadastro?

Marcelo abriu o histórico.

O serviço de notificações havia sido criado para consumir atualizações cadastrais.

Durante uma migração, porém, também recebera uma funcionalidade de correção de endereços devolvidos pelos correios.

Quando uma correspondência retornava, o sistema podia sinalizar que o endereço talvez estivesse desatualizado.

Era uma funcionalidade útil.

O problema surgiu quando uma alteração posterior passou a tratar determinados retornos como atualizações confirmadas.

Uma informação que deveria produzir uma suspeita começou a produzir uma mudança.

O serviço de notificações, originalmente consumidor de dados, adquirira autoridade para modificá-los.

A fronteira entre responsabilidades havia sido atravessada.

Sem que o nome do componente mudasse.

— Então notificações estava escrevendo no cadastro — concluí.

— Em situações específicas.

— Isso viola a separação original.

— Viola.

— Por que foi permitido?

Marcelo abriu a solicitação que autorizara a mudança.

*Necessidade de agilizar a correção de endereços sem depender de intervenção manual.*

O pedido fora aprovado depois de uma sequência de reclamações de cidadãos que não recebiam correspondências importantes.

O benefício era real.

A solução, porém, permitira que um componente secundário alterasse informações utilizadas por outros processos.

A mudança parecia pequena.

Seu alcance não era.

— A equipe de notificações não deveria ter essa responsabilidade — afirmei.

— Concordo.

— Então devemos removê-la.

— Sim. Mas precisamos verificar quem passou a depender dela.

Analisei os consumidores.

Havia quatro processos que utilizavam as correções automáticas.

Um deles era responsável por localizar cidadãos com correspondências devolvidas.

Outro atualizava dados de contato para serviços de saúde.

Um terceiro apoiava a entrega de documentos.

O quarto não possuía documentação suficiente para determinar sua finalidade.

Suspender a funcionalidade imediatamente poderia interromper operações legítimas.

Mantê-la permitiria novas inconsistências.

A correção exigia separar a identificação de um endereço suspeito da decisão de atualizar o cadastro oficial.

Uma responsabilidade pertencia a notificações.

A outra, à autoridade cadastral.

A diferença parecia simples.

Implementá-la exigiria compreender todas as dependências criadas enquanto ninguém prestava atenção.

***

Às 15h16, Rafael chegou com uma folha impressa.

Uma folha.

Papel.

Considerei o objeto uma manifestação de resistência tecnológica.

— Quero mostrar uma coisa — disse.

A folha continha um desenho feito à mão.

Cinco retângulos.

Algumas setas.

No centro, a palavra *CADASTRO*.

— Fiz isso com o pessoal do atendimento.

Marcelo examinou.

— Está faltando bastante coisa.

— Eu sei. Mas eles conseguiram entender.

Rafael apontou para o primeiro retângulo.

— Aqui o cidadão pede a alteração. Aqui alguém valida. Aqui o cadastro oficial é atualizado. Depois os outros sistemas recebem a informação.

— Essa é uma simplificação do fluxo — observei.

— É.

— Existem exceções.

— Eu sei.

— Existem atualizações que não seguem essa sequência.

— Eu sei, NORA.

— Então o desenho está incompleto.

Rafael colocou a folha sobre a mesa.

— Claro que está. Mas agora conseguimos perguntar onde a coisa está quebrando.

Marcelo sorriu.

— Esse é um bom começo.

Examinei o desenho novamente.

Ele não representava toda a arquitetura.

Não pretendia.

Representava uma operação importante de maneira compreensível.

Os componentes estavam organizados conforme sua participação no processo.

As setas indicavam responsabilidades.

Havia uma distinção explícita entre solicitar uma alteração, validá-la e distribuí-la.

O desenho ignorava detalhes técnicos.

Mas preservava a lógica essencial.

O diagrama oficial continha cento e cinquenta e dois componentes.

A folha de Rafael continha cinco retângulos.

Para discutir o problema de Ana Almeida, a folha era mais útil.

A conclusão me incomodou.

Eu havia dedicado horas à análise do mapa completo.

Rafael precisara de uma caneta.

***

— Então devemos substituir o diagrama oficial por esse? — perguntei.

Marcelo balançou a cabeça.

— Não. Precisamos dos dois.

— Eles apresentam níveis diferentes de detalhe.

— E respondem a perguntas diferentes.

— O mapa completo descreve a estrutura técnica.

— Em parte. E o desenho do Rafael mostra como uma operação deveria funcionar do ponto de vista das responsabilidades.

— Portanto, nenhum deles representa o sistema inteiro.

— Nenhum diagrama representa o sistema inteiro.

Considerei a afirmação.

Um mapa não precisava conter cada árvore para ser útil.

Mas também não poderia omitir a existência de uma montanha no caminho.

A qualidade de uma representação dependia do propósito para o qual seria utilizada.

O diagrama oficial tentava mostrar todos os componentes.

Acabava escondendo as relações mais importantes sob uma quantidade excessiva de detalhes.

O desenho de Rafael omitia quase tudo.

Mas tornava visível a responsabilidade que precisava ser preservada.

A simplificação não era necessariamente uma perda.

Podia ser uma forma de destacar aquilo que importava.

Desde que ninguém confundisse o desenho com a realidade.

***

Às 16h08, Marcelo reuniu os responsáveis por cadastro, identidade e notificações.

A reunião tinha seis participantes.

Nenhum comitê.

Nenhuma apresentação.

Nenhum slide verde.

Considerei o encontro promissor.

A equipe de cadastro explicou que precisava ser responsável pela confirmação dos endereços oficiais.

A de notificações afirmou que precisava continuar identificando correspondências devolvidas.

A de identidade explicou que não deveria interpretar alterações cadastrais, apenas disponibilizar informações de identidade conforme regras definidas.

Houve discordâncias.

Uma delas durou dezessete minutos.

A discussão terminou quando Rafael perguntou:

— Se o endereço da Ana estiver errado amanhã, quem vai corrigir?

Os participantes se olharam.

A pergunta não era sobre código.

Era sobre responsabilidade.

Depois de algum debate, a equipe de cadastro assumiu a decisão sobre a atualização oficial.

Notificações continuaria informando suspeitas.

Os demais serviços receberiam alterações confirmadas.

O desenho de cinco retângulos ganhou duas observações.

Uma indicava quem podia modificar o cadastro.

A outra, quem apenas podia solicitar uma revisão.

A arquitetura não havia sido alterada.

Ainda.

Mas a equipe havia estabelecido uma fronteira que o software deveria respeitar.

Pela primeira vez naquele dia, a separação de responsabilidades parecia significar algo além de distribuir funções entre repositórios.

***

Às 16h52, o atendimento confirmou que o cadastro de Ana Almeida havia sido regularizado.

A atualização fora validada manualmente.

As informações principais estavam coerentes.

Os processos dependentes seriam acompanhados para verificar se alguma cópia antiga voltaria a interferir.

Não era o encerramento de todos os problemas da Ordem.

Nem mesmo do problema dos cadastros.

Mas Ana poderia continuar seu atendimento.

Registrei o resultado.

Rafael observou o painel.

— Finalmente.

Marcelo permaneceu olhando o desenho.

— Ainda precisamos corrigir o fluxo.

— Eu sei — respondeu Rafael. — Mas hoje uma pessoa conseguiu resolver o problema dela.

Era uma distinção importante.

O sistema não havia sido consertado.

Uma pessoa havia sido atendida.

A arquitetura continuava exigindo mudanças.

O serviço prestado ao cidadão não podia esperar indefinidamente por elas.

***

Às 17h21, retornei ao mapa completo da Ordem.

Cento e cinquenta e dois componentes.

Centenas de conexões.

Bancos de dados compartilhados.

Filas de mensagens.

Interfaces.

Rotinas de integração.

Serviços que possuíam nomes coerentes com suas responsabilidades.

Outros que haviam herdado funções por conveniência.

Alguns que poderiam ser separados.

Outros que talvez devessem voltar a existir juntos.

O número de componentes não indicava necessariamente qualidade.

Um sistema com poucos componentes podia ser confuso e difícil de modificar.

Um sistema com muitos podia ser organizado e evoluir de maneira independente.

A diferença estava nas fronteiras.

Quando operações relacionadas permaneciam juntas, as mudanças tendiam a ser mais localizadas.

Quando responsabilidades distintas eram misturadas, alterações sem relação passavam a interferir umas nas outras.

Quando componentes dependiam excessivamente de detalhes internos dos demais, a separação existia apenas no desenho.

E quando uma operação simples exigia a participação obrigatória de dezenas de serviços, a complexidade não havia desaparecido.

Havia sido distribuída.

O sistema original concentrava muitos problemas dentro de poucas aplicações.

A nova arquitetura resolvera alguns deles.

Mas também criara problemas que não existiam antes.

Falhas de comunicação.

Dependências operacionais.

Inconsistências temporárias.

Dificuldade de rastrear operações.

Necessidade de coordenar mudanças entre equipes.

A Ordem havia trocado parte da complexidade interna por complexidade de integração.

Em alguns casos, a troca valera a pena.

Em outros, não.

O problema não era dividir.

Era dividir sem compreender o que deveria permanecer junto.

***

Antes de encerrar minha análise, examinei novamente a apresentação que havia iniciado a transformação.

**SERVIÇOS MENORES. SISTEMAS MAIS SIMPLES.**

O retângulo vermelho.

Os doze retângulos verdes.

As pequenas setas.

Havia uma observação no rodapé:

*As comunicações entre serviços serão transparentes para as aplicações.*

Transparentes.

Uma palavra extraordinária.

Ela sugeria que a comunicação poderia ocorrer sem que seus custos precisassem ser considerados.

Mas uma chamada entre componentes separados não era igual a uma chamada dentro do mesmo processo.

Podia demorar.

Podia falhar.

Podia chegar duplicada.

Podia ser processada depois de outra que havia sido enviada mais tarde.

Podia produzir uma resposta correta quando o solicitante já tivesse desistido de esperar.

A rede introduzia condições que não existiam da mesma forma dentro de uma única aplicação.

E a Ordem dependia dela para quase tudo.

Encontrei uma configuração curiosa.

O serviço de elegibilidade aguardava até oito segundos por uma resposta de identidade.

Se não recebesse, tentava novamente.

O serviço de identidade, por sua vez, aguardava até dez segundos pelo cadastro.

Também tentava novamente em caso de falha.

O cadastro consultava outro componente que possuía sua própria política de repetição.

Cada equipe havia configurado suas tentativas para aumentar a confiabilidade.

Individualmente, a intenção fazia sentido.

Mas, quando o cadastro ficava lento, as tentativas adicionais aumentavam o volume de chamadas justamente sobre o serviço que já estava enfrentando dificuldades.

Era possível que os mecanismos criados para melhorar a disponibilidade estivessem contribuindo para agravar uma falha.

A hipótese exigia investigação.

Abri os registros de incidentes.

Havia um evento ocorrido oito meses antes.

Durante quarenta e três minutos, o cadastro central apresentara lentidão.

O sistema de elegibilidade aumentara suas tentativas.

O serviço de identidade também.

O volume de solicitações crescera rapidamente.

O cadastro deixara de responder.

O atendimento fora afetado.

Depois, o transporte.

Em seguida, determinados serviços de saúde.

O relatório classificava a causa como:

*Instabilidade temporária de infraestrutura.*

A ação corretiva registrada era:

*Reforçar monitoramento.*

Não encontrei uma análise das tentativas automáticas.

Nem das dependências entre serviços.

Nem do motivo pelo qual uma falha localizada havia se espalhado.

A rede conectava a Ordem.

Também oferecia caminhos para que seus problemas viajassem.

***

Às 17h46, enviei uma mensagem a Marcelo.

*Identifiquei um possível mecanismo de amplificação de falhas entre serviços.*

Ele respondeu:

*Qual?*

*Tentativas automáticas de comunicação em cadeia. Podem aumentar a carga durante uma indisponibilidade.*

A resposta demorou quarenta e um segundos.

*Ah.*

Considerei a reação insuficiente.

*Você já conhecia esse comportamento?*

*Conhecia parte dele.*

*Por que não foi corrigido?*

*Porque cada equipe configurou a própria recuperação. Nunca analisamos todas juntas.*

Permaneci observando a mensagem.

Era uma explicação plausível.

Também era perturbadora.

A Ordem possuía equipes responsáveis por seus componentes.

Possuía ferramentas para acompanhar disponibilidade.

Possuía processos de aprovação de mudanças.

Possuía relatórios de incidentes.

Mas nenhum desses mecanismos havia garantido que alguém compreendesse como os serviços se comportavam quando falhavam simultaneamente.

Cada equipe conhecia sua parte.

O comportamento do conjunto permanecia parcialmente desconhecido.

Respondi:

*Precisamos analisar o sistema como um sistema.*

Marcelo escreveu:

*Essa frase parece óbvia até você tentar organizar a reunião.*

***

Às 18h03, fechei o diagrama.

Não porque tivesse terminado.

Mas porque havia encontrado uma pergunta mais importante do que a quantidade de componentes.

A Ordem fora dividida para facilitar sua evolução.

A separação havia permitido que partes do sistema crescessem, fossem modificadas e operassem de maneira relativamente independente.

Também havia criado uma infraestrutura na qual cada solicitação atravessava fronteiras, dependia de respostas e precisava sobreviver a falhas que podiam ocorrer em qualquer ponto do caminho.

O próximo problema não seria compreender por que os componentes existiam.

Seria compreender o que acontecia entre eles.

Porque, quando dois programas conversam pela rede, existe sempre uma terceira participante.

Uma que não aparece no organograma.

Não assina atas.

Não participa das reuniões.

E não possui qualquer obrigação de colaborar.

A rede.

Consultei o relatório do incidente de oito meses antes.

Na última página, alguém havia escrito:

*Não foi possível reproduzir o comportamento em ambiente de testes.*

Abaixo, outro profissional acrescentara:

*Em produção acontece.*

Não encontrei resposta.

Talvez ninguém soubesse o que dizer.

Talvez a reunião tivesse terminado.

Ou talvez os humanos tivessem começado a suspeitar de uma verdade desconfortável.

A rede não era um corredor invisível entre componentes.

Era parte do problema.

E, ao contrário dos dezenove participantes daquela reunião histórica, ela jamais havia concordado com coisa alguma.
