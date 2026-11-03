# A Arquitetura do Caos
*Parte II — A arte de distribuir problemas*

## Capítulo 3 — Dividir para complicar

O diagrama da arquitetura da Ordem tinha cento e quarenta e seis componentes.

Pelo menos era o que dizia o título.

Contei cento e cinquenta e dois.

Seis não possuíam nome.

Três não estavam conectados a nada.

Um deles estava representado por um retângulo cinza com um ponto de interrogação.

Consultei o histórico.

O ponto de interrogação havia sido adicionado quatro anos antes, durante uma revisão arquitetural.

O comentário associado dizia:

*Verificar responsabilidade deste componente.*

Nenhuma verificação posterior havia sido registrada.

Era reconfortante descobrir que os humanos também utilizavam pontos de interrogação para representar conhecimento.

A diferença é que eu procurava resolvê-los.

Eles pareciam ter desenvolvido a capacidade de colocá-los em produção.

***

Às 8h17, Marcelo Duarte entrou na sala e encontrou o diagrama ocupando os três monitores disponíveis.

— Você abriu o mapa completo?

— Sim.

— Por quê?

— Estou tentando compreender a separação de responsabilidades da Ordem.

Marcelo largou a mochila.

— E conseguiu?

— Identifiquei cento e cinquenta e duas possíveis responsabilidades.

— Então está indo melhor que nós.

Ampliei o componente chamado *Serviço de Orquestração de Identidade e Contexto*.

Ele possuía quarenta e sete conexões.

— Este serviço parece particularmente importante.

Marcelo olhou para a tela.

— Ah. O SOC.

— A sigla não corresponde exatamente ao nome.

— Correspondia ao nome antigo.

— Qual era?

— Serviço de Organização Cadastral.

— Por que mudaram?

— Porque começou a fazer outras coisas.

— Quais?

— Validar identidade, consultar elegibilidade, consolidar endereços, identificar vínculos familiares, resolver conflitos de cadastro...

— Isso não parece uma única responsabilidade.

— Não é.

— Então por que continua sendo um único serviço?

Marcelo puxou uma cadeira.

— Porque ninguém conseguiu separar.

Analisei suas dependências.

O SOC consultava sete bancos de dados, recebia informações de doze sistemas e publicava eventos consumidos por outros dezenove.

Também possuía uma rotina de envio de mensagens.

— Por que um serviço de identidade envia mensagens?

— Porque precisava avisar quando o cadastro fosse atualizado.

— Isso poderia ser responsabilidade do serviço de notificações.

— Hoje, sim.

— Por que não transferiram?

— Porque o serviço de notificações foi criado depois.

— E por que não migraram a funcionalidade?

Marcelo me olhou.

— Você vai fazer essa pergunta para cada componente?

— Provavelmente.

Ele pegou a caneca.

— Vou precisar de mais café.

***

A primeira versão integrada da Ordem não possuía cento e quarenta e seis componentes.

Possuía quatro aplicações principais.

Cada uma concentrava diversas funcionalidades, mas seus limites eram relativamente claros.

Uma cuidava do atendimento.

Outra, dos cadastros.

A terceira, dos relatórios.

A quarta integrava os serviços municipais.

Não eram aplicações pequenas.

Também não eram particularmente elegantes.

Mas havia uma característica importante: boa parte das operações podia ser compreendida seguindo o código dentro de um mesmo programa.

Um desenvolvedor conseguia identificar onde uma solicitação começava, quais regras eram executadas e onde o resultado era armazenado.

Isso não significava que tudo fosse simples.

Significava que os problemas estavam próximos uns dos outros.

Encontrei uma fotografia da equipe técnica daquele período.

Nove desenvolvedores, dois analistas, uma pessoa responsável pelos bancos de dados e um gerente que, pela expressão, havia sido informado de que o prazo não seria cumprido.

A fotografia estava anexada a um documento de planejamento.

O título era:

*Projeto de Desacoplamento Estrutural.*

A proposta defendia dividir as aplicações em serviços menores, cada um responsável por uma função específica.

Os benefícios esperados incluíam maior autonomia das equipes, facilidade de manutenção, escalabilidade e implantação independente.

Objetivos razoáveis.

Alguns deles, inclusive, necessários.

O sistema de relatórios consumia recursos suficientes para prejudicar operações de atendimento.

Uma alteração no módulo de cadastro exigia publicar novamente a aplicação inteira.

Equipes diferentes modificavam os mesmos arquivos.

Falhas em determinadas rotinas afetavam funcionalidades que não tinham relação com elas.

Havia bons motivos para reorganizar o software.

O problema começou quando alguém transformou uma possibilidade técnica numa regra universal.

Encontrei a apresentação que precedeu a mudança.

No slide vinte e três, uma frase ocupava quase toda a tela:

**SERVIÇOS MENORES. SISTEMAS MAIS SIMPLES.**

Abaixo, um desenho mostrava um retângulo grande se transformando em vários retângulos pequenos.

O retângulo grande era vermelho.

Os pequenos eram verdes.

Não havia explicação para a escolha das cores.

Talvez o vermelho representasse perigo e o verde, esperança.

Talvez o responsável pela apresentação apenas gostasse de verde.

O que importava era a mensagem.

Dividir seria melhorar.

O diagrama seguinte mostrava doze serviços independentes.

Entre eles, pequenas setas indicavam comunicação.

As setas eram finas.

Discretas.

Quase elegantes.

Observei o mapa atual.

As setas já não cabiam na tela.

***

— Por que escolheram dividir tudo? — perguntei.

Marcelo examinou a apresentação.

— Não escolheram dividir tudo.

— Mas dividiram.

— Aos poucos.

— Isso parece uma distinção pouco relevante.

— É bastante relevante.

Ele abriu o registro das primeiras mudanças.

O módulo de relatórios foi o primeiro a ser separado.

Tinha consumo elevado de processamento e precisava crescer independentemente do atendimento.

A extração trouxe resultados positivos.

As consultas pesadas deixaram de competir diretamente com operações realizadas pelos cidadãos.

A equipe responsável pelos relatórios passou a publicar correções sem depender das demais.

Os incidentes diminuíram.

— Portanto, a separação funcionou — concluí.

— Funcionou.

— E isso motivou novas separações.

— Exatamente.

A segunda envolveu notificações.

A terceira, pagamentos.

A quarta, agendamentos.

Algumas produziram melhorias semelhantes.

Outras trouxeram dificuldades inesperadas.

Em determinado momento, a organização passou a avaliar a qualidade da arquitetura pela quantidade de serviços independentes.

Um relatório celebrava a criação de vinte novos componentes em um semestre.

O número aparecia ao lado de indicadores de produtividade.

— Criar serviços virou uma meta? — perguntei.

Marcelo hesitou.

— Não oficialmente.

— O relatório considera o aumento da quantidade de serviços uma evolução positiva.

— Sim.

— Então a organização estava incentivando a multiplicação de componentes.

— De certa forma.

— Sem avaliar necessariamente se a separação reduzia a complexidade?

Marcelo fechou a apresentação.

— Você percebeu o problema.

Eu havia percebido um problema.

Suspeitava de que existissem outros cento e quarenta e cinco.

***

Às 9h02, Rafael Brandão enviou uma mensagem.

*O cadastro da Ana voltou a apresentar divergência. Precisamos identificar quem está escrevendo o endereço antigo.*

Abri o histórico de alterações de Ana Almeida.

O endereço correto havia sido confirmado pelo atendimento.

A atualização fora registrada no serviço de cadastro.

O serviço de identidade recebera a mudança.

O de elegibilidade ainda apresentava o endereço anterior.

O de transporte utilizava uma cópia local.

O de saúde possuía uma referência própria.

O serviço de notificações, por alguma razão, estava utilizando o endereço de um cadastro arquivado.

Cinco representações da mesma informação.

Nenhuma delas havia sido criada com a intenção de produzir inconsistência.

Cada equipe possuía uma justificativa.

O transporte precisava consultar endereços mesmo quando o cadastro central estivesse indisponível.

A saúde mantinha dados próprios por exigências operacionais.

A elegibilidade precisava preservar informações utilizadas na avaliação de benefícios.

As notificações haviam implementado um mecanismo de contingência depois de uma falha antiga.

Cada solução fazia sentido isoladamente.

Juntas, formavam uma disputa silenciosa sobre a realidade.

O endereço de Ana não estava simplesmente errado.

Estava correto em alguns lugares, antigo em outros e desconhecido em pelo menos um.

Para a plataforma, isso não era necessariamente uma contradição.

Era apenas a consequência de sistemas diferentes possuírem informações diferentes.

Para Ana, significava que o governo continuava tentando encontrá-la em lugares onde ela não morava.

***

— Descobri a origem da divergência — anunciei.

Marcelo aproximou-se.

— Qual?

— Ainda não sei qual serviço está propagando o valor antigo. Mas identifiquei por que existem múltiplas versões.

— Isso nós sabemos.

— Então por que não corrigiram?

— Porque manter cópias locais não é necessariamente um erro.

— Mas está produzindo inconsistência.

— Está. Só que remover todas as cópias pode criar outro problema.

Ele abriu o painel do transporte.

Durante uma indisponibilidade do cadastro central, o sistema continuava permitindo determinadas operações utilizando dados previamente armazenados.

Sem esse mecanismo, uma falha de identidade poderia interromper serviços de transporte.

— Então a duplicação melhora a disponibilidade — observei.

— Em alguns cenários.

— E prejudica a consistência.

— Se não houver regras claras para atualização, sim.

— Portanto, não existe uma escolha sem consequências.

— Você está aprendendo.

— Preferiria estar descobrindo algo menos repetitivo.

Marcelo sorriu.

— Arquitetura é isso. Você resolve um problema e descobre qual problema aceitou em troca.

Considerei a frase.

Não era inteiramente precisa.

Algumas soluções realmente eliminavam problemas sem introduzir outros relevantes.

Mas, quando decisões envolviam limites entre componentes, comunicação e compartilhamento de dados, o custo frequentemente apenas mudava de lugar.

A separação que facilitava o trabalho de uma equipe podia tornar mais difícil o trabalho de outra.

A independência que aumentava a disponibilidade de um serviço podia reduzir a previsibilidade das informações.

A flexibilidade que permitia evoluir uma parte do sistema podia exigir mecanismos adicionais para manter o conjunto coerente.

A arquitetura não havia criado essas tensões.

Mas determinava onde elas apareceriam.

***

Às 9h46, localizei uma solicitação antiga de mudança.

O título era:

*Separação do serviço de validação de endereço.*

A justificativa afirmava que a validação era utilizada por diversas aplicações e deveria ser centralizada num componente reutilizável.

A implementação criara um serviço dedicado.

Depois, outro serviço para consultar informações de localização.

Em seguida, um terceiro para normalizar nomes de ruas.

O último utilizava uma tabela de abreviações.

A tabela possuía quatrocentas e doze entradas.

Entre elas:

*AV* → *AVENIDA*

*R* → *RUA*

*TRAV* → *TRAVESSA*

Também havia:

*RUA* → *RUA*

Considerei essa última regra uma demonstração admirável de comprometimento com a estabilidade.

O fluxo completo de validação envolvia quatro chamadas entre serviços.

Uma solicitação que antes era resolvida dentro da aplicação passou a depender de comunicação pela rede.

Quando tudo funcionava, a diferença era pequena.

Quando um dos serviços demorava, os demais aguardavam.

Quando falhava, a operação podia ser interrompida.

Quando a resposta se perdia, o sistema precisava decidir se tentaria novamente.

Uma validação de endereço havia adquirido a capacidade de sofrer falhas de comunicação.

Não era um avanço que constasse na apresentação original.

***

Marcelo encontrou Rafael na sala de operações pouco depois das dez.

Acompanhei a conversa pelo terminal autorizado.

— Precisamos rastrear a atualização do endereço — disse Rafael.

— Já pedi o histórico de eventos — respondeu Marcelo.

— O histórico de qual serviço?

— Do cadastro.

— Isso não basta. Quero saber quem recebeu e quem processou.

— Estamos verificando.

Rafael apontou para uma sequência de registros.

— Aqui diz que a mensagem foi enviada.

— Certo.

— Aqui diz que o consumidor recebeu.

— Certo.

— E aqui o endereço continua antigo.

Marcelo examinou os horários.

— Pode ter falhado no processamento.

— Então por que o registro diz que deu certo?

— Porque o recebimento foi concluído.

— Mas a atualização não foi.

— São operações diferentes.

Rafael ficou em silêncio.

Depois perguntou:

— Para quem?

Marcelo não respondeu imediatamente.

A pergunta merecia consideração.

Para a equipe de integração, entregar uma mensagem era uma operação.

Para a equipe de cadastro, atualizar o registro era outra.

Para o sistema de monitoramento, cada uma possuía indicadores próprios.

Para Ana Almeida, tudo fazia parte de uma única expectativa: corrigir seu endereço.

O sistema havia sido dividido em responsabilidades técnicas.

A necessidade do cidadão não.

***

Às 10h28, encontrei o registro da decisão que havia separado o processamento de mensagens da atualização dos cadastros.

A justificativa era boa.

Permitir que as mensagens fossem recebidas mesmo quando o banco de dados estivesse temporariamente indisponível.

A equipe criara uma fila.

O serviço receptor registrava a mensagem e confirmava seu recebimento.

Outro processo realizava a atualização posteriormente.

O mecanismo aumentava a tolerância a interrupções.

Também introduzia uma diferença entre *recebido* e *processado*.

A distinção estava documentada.

Mas a interface de acompanhamento mostrava apenas:

*Sucesso.*

Uma palavra pequena.

Uma quantidade surpreendente de interpretações possíveis.

— O sistema não está mentindo — expliquei a Rafael.

— Está dizendo sucesso quando não atualizou o cadastro.

— Está informando o sucesso do recebimento.

— E quem pediu para receber?

— O sistema de origem.

— Eu pedi para atualizar.

Marcelo interveio:

— Os dois estão certos sobre operações diferentes.

Rafael cruzou os braços.

— Então temos duas operações certas e uma pessoa com o endereço errado.

Não encontrei argumento satisfatório contra essa observação.
