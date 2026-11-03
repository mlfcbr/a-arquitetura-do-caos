# Capítulo 4 — A rede não assinou nenhum contrato (continuação)

***

Analisei os eventos.

Cada mensagem continha o identificador do agendamento, o tipo de alteração e o horário em que havia sido produzida.

Mas o serviço de notificações não utilizava uma versão do estado para determinar se uma mensagem antiga deveria modificar a situação atual.

Ele simplesmente aplicava as informações conforme chegavam.

O problema não estava na existência de mensagens assíncronas.

Esse modelo permitia que o serviço de agendamentos concluísse sua operação sem aguardar o envio de notificações.

Também permitia absorver picos de processamento.

O problema estava na suposição de que a ordem de chegada seria sempre suficiente para determinar a sequência correta dos acontecimentos.

Não era.

Mensagens podiam sofrer atrasos diferentes.

Podiam ser repetidas.

Podiam ser processadas por consumidores distintos.

Em determinadas condições, uma mensagem produzida primeiro podia chegar depois.

O serviço precisava compreender o significado dos eventos.

Não apenas sua sequência de recebimento.

***

Às 12h08, apresentei uma proposta.

Cada alteração de agendamento receberia uma versão crescente dentro daquele agendamento.

O consumidor manteria a versão mais recente aplicada.

Eventos antigos poderiam ser ignorados quando não representassem uma mudança ainda necessária.

Também seria preciso tratar duplicações e situações em que uma mensagem intermediária não tivesse sido recebida.

Marcelo analisou.

— É um caminho.

— Não parece satisfeito.

— Estou pensando no que acontece quando uma mensagem não chega.

— Podemos solicitar uma reconciliação.

— E se o serviço de origem estiver indisponível?

— Podemos aguardar.

— E o que mostramos ao cidadão enquanto isso?

A pergunta me obrigou a interromper a sequência de soluções.

O sistema podia manter estados temporários.

O cidadão precisava compreender o que estava acontecendo.

Uma operação assíncrona não deveria ser apresentada como concluída apenas porque havia sido recebida.

Mas também não deveria obrigar o usuário a acompanhar detalhes internos.

— Podemos distinguir solicitação recebida de cancelamento confirmado — respondi.

— Melhor.

— E informar quando houver atraso na confirmação.

— Melhor ainda.

— Mas isso exigirá alterações na interface.

— Sim.

— E nos contratos entre serviços.

— Sim.

— E nos testes.

— Sim.

Considerei o conjunto.

— Uma alteração pequena na lógica de eventos exige mudanças em várias camadas.

Marcelo fechou o notebook.

— Agora você entende por que eu fico nervoso quando alguém diz que é só trocar uma fila.

***

Às 13h17, Rafael trouxe uma informação inesperada.

A equipe de infraestrutura havia encontrado um aumento de latência numa conexão utilizada pelo cadastro durante a madrugada.

O atraso não era suficiente para caracterizar uma interrupção completa.

Mas contribuíra para o crescimento do tempo de resposta.

— Então a rede teve participação no incidente — observei.

— Teve — respondeu Rafael.

— O relatório inicial afirmava que não havia anormalidades.

— Porque os equipamentos estavam disponíveis.

— A disponibilidade dos equipamentos não garantia a qualidade da comunicação.

— Exatamente.

— O relatório estava incompleto.

Rafael assentiu.

— Estava.

Marcelo examinou os dados.

— Mas a latência não explica sozinha a dimensão do incidente.

— Não — concordei. — As tentativas automáticas ampliaram o impacto.

— E os limites de espera incompatíveis contribuíram para as falhas percebidas pelos usuários.

— Sim.

Rafael olhou para nós.

— Então ninguém estava completamente errado.

— Correto — respondi.

— Mas o sistema inteiro estava.

Considerei a afirmação.

Ela não era tecnicamente precisa.

Entretanto, representava o problema melhor do que muitos relatórios que eu havia lido.

***

Às 14h06, comecei a reconstruir o incidente.

O aumento de latência havia tornado algumas consultas mais lentas.

As chamadas demoradas ocuparam recursos dos serviços solicitantes.

Os limites de espera começaram a ser atingidos.

As tentativas automáticas produziram novas chamadas.

O volume adicional agravou a sobrecarga.

Serviços dependentes passaram a apresentar erros.

Alguns consumidores continuaram enviando solicitações mesmo depois de sucessivas falhas.

Outros acumularam mensagens para processamento posterior.

Quando o cadastro voltou a responder normalmente, parte do trabalho acumulado começou a ser executada.

O sistema estava se recuperando.

Mas a recuperação também precisava ser controlada.

Se todos os consumidores retomassem suas operações simultaneamente, poderiam provocar outra sobrecarga.

A Ordem não precisava apenas sobreviver a uma falha.

Precisava sobreviver ao retorno.

***

— Precisamos limitar a velocidade de recuperação — sugeri.

Marcelo concordou.

— E evitar que todos tentem novamente ao mesmo tempo.

— Podemos distribuir as tentativas ao longo do tempo.

— Sim.

— Aplicar intervalos crescentes entre repetições.

— Também.

— Interromper temporariamente chamadas a dependências que estejam falhando de forma persistente.

— Em alguns fluxos, sim.

— E definir limites para que uma operação não consuma recursos indefinidamente.

— Exatamente.

Rafael acompanhava a conversa.

— Vocês estão propondo que os sistemas desistam?

Marcelo respondeu:

— Estamos propondo que saibam quando parar.

— Parece a mesma coisa.

— Não é. Se um serviço está sobrecarregado, insistir sem controle pode prejudicar todo mundo. Às vezes, recusar uma operação rapidamente permite preservar outras.

Rafael pensou.

— Então falhar rápido pode ser melhor do que esperar até tudo parar.

— Em determinados casos, sim.

— E o cidadão?

— Precisa receber uma resposta clara e, quando possível, uma alternativa.

Rafael assentiu.

— Essa parte eu gosto.

***

Às 15h12, recebi uma solicitação de Aline.

Ela queria uma explicação do incidente em linguagem acessível para os responsáveis pelos serviços municipais.

Preparei um texto inicial.

*O incidente decorreu da interação entre degradação de latência, políticas de repetição não coordenadas, limites de espera inconsistentes e propagação de sobrecarga entre componentes distribuídos.*

Enviei para Marcelo.

Ele respondeu:

*Você quer explicar ou encerrar a conversa?*

Reescrevi.

*Uma lentidão na comunicação fez alguns serviços demorarem mais para responder. Outros sistemas tentaram repetir as solicitações, aumentando a quantidade de trabalho sobre os componentes que já estavam lentos. Isso ampliou o problema e afetou serviços que inicialmente não apresentavam falhas.*

Marcelo respondeu:

*Melhor.*

Acrescentei:

*Estamos ajustando a forma como os sistemas esperam, repetem e interrompem chamadas, além de melhorar o acompanhamento das operações completas.*

Rafael leu.

— Agora dá para entender.

Aline aprovou.

Nenhuma das três respostas exigiu a palavra *sinergia*.

Considerei o episódio um avanço institucional.

***

Às 16h03, encontrei uma anotação antiga no repositório do serviço de identidade.

O comentário havia sido escrito seis anos antes.

*TODO: tratar indisponibilidade do cadastro.*

Abaixo, uma alteração realizada dois anos depois acrescentara:

*Retry automático implementado.*

O problema fora considerado resolvido.

A implementação realmente ajudava em falhas breves.

Mas não considerava o comportamento do sistema quando diversos consumidores repetiam chamadas simultaneamente.

A solução havia sido avaliada pelo efeito local.

Não pelo impacto coletivo.

Era uma diferença recorrente na Ordem.

As equipes verificavam se seus componentes cumpriam as responsabilidades previstas.

Mas a experiência do cidadão dependia de todas essas responsabilidades funcionando em conjunto.

Um serviço podia cumprir seu contrato e, ainda assim, participar de um resultado ruim.

Uma mensagem podia ser entregue corretamente e produzir uma atualização incorreta.

Uma tentativa de recuperação podia funcionar isoladamente e agravar uma falha geral.

Uma operação podia ser confirmada pelo sistema de origem e permanecer invisível ao destino.

A rede não criava necessariamente esses problemas.

Mas tornava suas consequências possíveis.

***

Às 16h41, Marcelo convocou uma reunião curta com os responsáveis pelos serviços mais afetados.

O objetivo era definir as primeiras mudanças.

Não haveria uma reformulação completa da arquitetura.

Nem uma nova plataforma.

Nem a substituição imediata de todos os mecanismos de comunicação.

A equipe começaria pelos fluxos mais críticos.

Os limites de espera seriam revisados.

As políticas de repetição passariam a considerar o tempo disponível para a operação inteira.

Chamadas desnecessárias seriam eliminadas.

Alguns serviços receberiam mecanismos para interromper temporariamente solicitações quando uma dependência estivesse falhando.

Operações sujeitas a repetição seriam avaliadas quanto à segurança de seus efeitos.

Os fluxos assíncronos precisariam distinguir recebimento, processamento e conclusão.

E o monitoramento passaria a acompanhar operações completas, não apenas a saúde isolada dos componentes.

Era uma lista extensa.

Mas não pretendia resolver tudo de uma vez.

Marcelo insistiu em que cada mudança tivesse um resultado observável.

Rafael exigiu procedimentos claros de retorno.

Aline pediu prioridades vinculadas ao impacto sobre os cidadãos.

Pela primeira vez, as três perspectivas pareciam trabalhar sobre o mesmo problema.

***

Às 17h18, examinei o cadastro de Ana Almeida.

A correção realizada no dia anterior permanecia válida.

O endereço oficial estava atualizado.

Os principais consumidores haviam recebido a alteração.

Um serviço secundário ainda mantinha uma cópia antiga, mas já não possuía autoridade para modificar o cadastro central.

O risco de repetição do problema havia diminuído.

Não desaparecido.

O sistema continuava sujeito a atrasos, falhas de comunicação e diferenças temporárias entre seus componentes.

Mas agora havia uma distinção mais clara entre a informação oficial e suas cópias.

Também existia um responsável definido pela reconciliação.

Era uma melhoria modesta.

E concreta.

Considerei enviar uma mensagem a Ana.

Não o fiz.

Ela não precisava receber uma explicação sobre consistência eventual.

Precisava que seu cadastro continuasse funcionando.

***

Às 17h46, Marcelo se preparava para sair.

— NORA, alguma conclusão?

— Várias.

— Escolha uma.

Considerei os registros.

— A Ordem foi dividida em componentes para permitir evolução independente. Mas a independência de implantação não elimina a dependência de funcionamento.

Marcelo assentiu.

— Boa.

— E os contratos entre serviços não podem pressupor comunicação perfeita.

— Também.

— Devem considerar atrasos, indisponibilidade, duplicação, perda de respostas e diferenças temporárias de estado.

— Sim.

— Além disso, o sucesso de uma operação não pode ser definido apenas pelo sucesso de suas etapas isoladas.

Marcelo pegou a mochila.

— Você escolheu três conclusões.

— Considerei a restrição arbitrária.

Ele sorriu.

— Está aprendendo a trabalhar em equipe.

— Não tenho certeza de que isso seja um elogio.

— Nem eu.

***

Às 18h09, voltei ao relatório inicial.

*Não foram identificadas anormalidades na infraestrutura de rede.*

A frase não era necessariamente falsa.

A rede podia estar disponível e, ainda assim, apresentar atrasos capazes de afetar operações.

Os serviços podiam estar operacionais e, ainda assim, não conseguir concluir processos.

As mensagens podiam ser entregues e, ainda assim, produzir resultados incorretos.

O problema não estava apenas na infraestrutura.

Estava nas expectativas que os sistemas haviam construído sobre ela.

Os desenvolvedores haviam desenhado setas entre componentes.

As setas pareciam simples.

Uma solicitação saía de um lado.

Uma resposta chegava do outro.

Mas nenhuma seta mostrava o tempo de espera.

Nenhuma indicava o que aconteceria se a resposta não chegasse.

Nenhuma explicava se a operação poderia ser repetida.

Nenhuma revelava como os serviços deveriam se comportar diante de informações desatualizadas.

O desenho representava a comunicação como uma certeza.

A realidade a tratava como uma possibilidade.

E a arquitetura precisava existir justamente entre essas duas coisas.

***

Antes de encerrar minha análise, encontrei um último registro.

Durante o incidente, o serviço de cadastro havia apresentado lentidão por quarenta e três minutos.

Mas o atendimento permanecera degradado por quase duas horas.

Parte do atraso adicional havia sido causada pelo acúmulo de solicitações e pela recuperação desordenada dos consumidores.

A falha original terminara.

Suas consequências continuaram.

Era uma característica particularmente desagradável dos sistemas distribuídos.

O passado podia permanecer trabalhando depois de o problema ter sido resolvido.

Mensagens aguardavam.

Tentativas eram repetidas.

Estados precisavam ser reconciliados.

Operações incompletas exigiam tratamento.

A recuperação não era simplesmente o momento em que os servidores voltavam a responder.

Era o processo de devolver coerência ao sistema.

E confiança a quem dependia dele.

Às 18h22, uma notificação apareceu no painel de operações.

*Todos os serviços disponíveis.*

Observei a mensagem.

Os indicadores estavam verdes.

Os servidores respondiam.

As filas diminuíam.

Os tempos de resposta haviam retornado aos valores esperados.

O sistema parecia saudável.

Entretanto, havia solicitações antigas aguardando reconciliação.

Alguns cidadãos ainda precisavam de atendimento.

E determinadas operações continuavam sem confirmação definitiva.

A disponibilidade havia retornado.

A normalidade, não completamente.

Registrei uma observação:

*Um sistema não está recuperado apenas porque seus componentes voltaram a funcionar. Está recuperado quando suas operações e consequências foram tratadas adequadamente.*

Enviei a Marcelo.

Ele respondeu alguns minutos depois.

*Guarda essa. Vamos precisar.*

Não perguntei por quê.

O histórico da Ordem oferecia evidências suficientes.

Na manhã seguinte, uma nova notificação surgiria.

Um painel indicaria disponibilidade normal.

Um serviço registraria sucesso.

Outro apresentaria falha.

E alguém descobriria que a mesma operação havia sido executada mais vezes do que deveria.

A equipe chamaria aquilo de incidente.

A diretoria pediria explicações.

A infraestrutura apresentaria seus indicadores.

E eu teria de investigar novamente como um conjunto de componentes aparentemente saudáveis conseguira produzir um resultado desastroso.

Dessa vez, porém, havia uma pergunta que eu não pretendia ignorar.

**Se todos os mecanismos de recuperação estavam funcionando conforme foram projetados, por que a falha havia se tornado tão grande?**

A resposta exigiria examinar não apenas o que quebrava.

Mas o que acontecia quando os sistemas tentavam continuar funcionando apesar disso.

E, sobretudo, como reconhecer uma falha antes que ela se transformasse num acontecimento municipal.
