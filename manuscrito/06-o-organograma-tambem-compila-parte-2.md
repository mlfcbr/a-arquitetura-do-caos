# Capítulo 6 — O organograma também compila (continuação)

***

Marcelo desenhou quatro retângulos no quadro.

Em cada um, escreveu o nome de uma equipe.

Depois desenhou setas entre eles.

A equipe de canais precisava de benefícios.

Benefícios precisava de dados.

Dados precisava de plataforma.

Plataforma dependia de informações das outras equipes para dimensionar a infraestrutura.

Em seguida, Marcelo acrescentou uma quinta caixa.

**Simulador.**

— Onde colocamos isso?

Bruno apontou para benefícios.

Patrícia apontou para canais.

Diego apontou para dados.

Camila não apontou para lugar nenhum.

— Essa é a nossa arquitetura organizacional — disse Marcelo. — Estamos tentando encaixar uma capacidade nova nos limites que já existem.

— E qual seria a alternativa? — perguntou Aline.

— Primeiro definir a responsabilidade pelo resultado. Depois decidir quais capacidades cada equipe precisa fornecer.

— Isso parece a mesma coisa.

— Não é.

Marcelo apagou as setas.

— Quatro equipes podem entregar quatro partes perfeitamente funcionais — disse Marcelo. — E ainda assim ninguém conseguir usar o produto.

Rafael levantou a mão.

— Temos exemplos recentes.

— Temos — respondeu Marcelo.

— E antigos.

— Também.

— E alguns em produção.

— Rafael.

— Estou ajudando.

Aline se aproximou do quadro.

— Então precisamos de uma equipe dona do simulador.

— Precisamos de uma responsabilidade clara pelo produto. Isso não significa necessariamente criar outra equipe.

— E quem assume?

Marcelo olhou para Bruno.

— O conhecimento central está em benefícios.

Bruno abriu a boca.

— Mas — continuou Marcelo — isso só é viável se retirarmos outras prioridades e garantirmos apoio das equipes que fornecem capacidades compartilhadas.

Bruno fechou a boca.

Patrícia inclinou a cabeça.

— E o portal?

— Continua sendo responsabilidade de canais. Mas precisamos de um contrato claro, com decisões de interface que não exijam negociações a cada alteração.

Diego perguntou:

— E os dados históricos?

— Vocês fornecem uma capacidade confiável de consulta e comparação. Não precisam assumir a regra do benefício.

Camila acrescentou:

— E a execução em escala?

— Plataforma oferece os mecanismos necessários, dentro dos padrões existentes. Sem criar uma solução genérica para problemas que ainda não temos.

Aline observou o desenho.

— Então benefícios fica responsável pelo resultado, mas não faz tudo sozinho.

— Exatamente.

— E quem decide o que sai da fila deles?

Marcelo não respondeu.

Bruno sorriu pela primeira vez naquela tarde.

— Agora chegamos à parte interessante.

***

A decisão exigiu outra reunião.

Não por falta de vontade.

Porque a fila de trabalho de Bruno continha compromissos assumidos com pessoas que não estavam naquela sala.

Aline convocou os responsáveis pelas demandas mais importantes.

A migração adiada.

As adequações regulatórias.

As melhorias de segurança.

As correções operacionais.

O simulador.

Cada iniciativa possuía justificativas.

Cada responsável defendia sua urgência.

E todos apresentavam consequências graves caso seu trabalho fosse adiado.

Eu poderia ter classificado as iniciativas por risco, custo e benefício.

Mas Marcelo pediu que eu identificasse primeiro quais compromissos eram obrigatórios, quais tinham prazos negociáveis e quais dependiam de hipóteses ainda não verificadas.

A análise revelou algo interessante.

Duas entregas classificadas como urgentes não possuíam prazo externo.

Uma melhoria considerada estratégica não tinha indicador de resultado definido.

Uma migração era necessária, mas sua conclusão integral não precisava ocorrer naquele trimestre.

E uma correção de segurança, discretamente posicionada no meio da lista, apresentava risco maior do que algumas iniciativas mais visíveis.

Aline examinou os dados.

— Por que isso não apareceu antes?

Bruno respondeu:

— Porque cada demanda foi priorizada separadamente.

— Mas vocês têm uma fila única.

— Temos uma lista única. Não é a mesma coisa.

Rafael soltou uma risada.

Aline não.

— Certo. Vamos decidir o que realmente importa.

A reunião seguinte foi desconfortável.

Algumas entregas perderam prioridade.

Outras foram reduzidas.

Uma iniciativa foi suspensa.

A correção de segurança recebeu atenção imediata.

E o simulador ganhou espaço na capacidade da equipe de benefícios.

Nenhum dos responsáveis pelas demandas adiadas ficou particularmente satisfeito.

Mas todos saíram sabendo o que havia sido decidido e por quê.

Eu considerei isso uma melhoria relevante.

A satisfação coletiva não parecia um indicador adequado para avaliar decisões de priorização.

***

Na segunda-feira seguinte, Bruno reuniu sua equipe.

Apresentou a decisão.

Explicou o objetivo do simulador.

Mostrou o que sairia do planejamento.

E fez uma pergunta.

— Quem conhece suficientemente bem o cálculo atual para assumir a primeira versão?

Três pessoas levantaram a mão.

Uma delas, Júlia, havia participado da modernização.

Outra, Eduardo, mantinha as rotinas antigas.

A terceira, Marina, trabalhava principalmente com integrações.

Bruno escolheu Júlia e Eduardo para conduzir o desenho inicial.

Marina continuaria apoiando nas integrações.

Não foi uma escolha baseada apenas em disponibilidade.

Júlia conhecia a arquitetura nova.

Eduardo conhecia as exceções históricas.

Os dois discordavam com frequência.

Bruno considerou isso uma vantagem.

Eu também.

Pessoas que concordam em tudo oferecem pouca proteção contra erros compartilhados.

Às 10h06, Júlia abriu a primeira reunião técnica.

— Precisamos definir como executar uma simulação sem alterar nenhum benefício real.

Eduardo respondeu:

— Antes disso, precisamos definir quais regras vamos simular.

— As regras atuais.

— Todas?

— Sim.

— Inclusive as que ainda estão em revisão?

Júlia parou.

— Boa pergunta.

Eduardo sorriu.

— Tenho outras.

— Imagino.

— E precisamos saber se a simulação usa os dados de hoje ou os dados da data em que a regra entraria em vigor.

— Isso muda o resultado?

— Pode mudar bastante.

Júlia abriu uma página em branco.

O projeto havia começado.

E já estava mais complexo do que a apresentação de oito páginas sugeria.

Mas, pela primeira vez, aquela complexidade estava aparecendo antes da implementação.

***

Duas semanas depois, o primeiro protótipo estava disponível.

Não era bonito.

A interface possuía três campos, dois botões e uma tabela.

Patrícia, responsável por canais, descreveu o visual como uma agressão à experiência do usuário.

Júlia respondeu que o protótipo não havia sido construído para ganhar um prêmio de design.

Patrícia concordou.

Depois explicou que ninguém conseguiria utilizá-lo sem compreender conceitos internos do motor de cálculo.

Júlia discordou.

Eduardo tentou usar o protótipo.

Falhou.

A discussão terminou com a decisão de envolver usuários da gestão de benefícios antes de avançar.

Helena enviou duas analistas experientes.

Uma delas perguntou por que precisava escolher manualmente a versão de uma regra.

A outra quis saber se o relatório conseguiria separar alterações provocadas por parâmetros das alterações provocadas por dados cadastrais.

O protótipo não fazia nenhuma das duas coisas.

Júlia anotou.

Patrícia também.

Eduardo comentou:

— Ainda bem que perguntamos antes.

A frase não possuía sofisticação técnica.

Mas continha uma quantidade surpreendente de sabedoria arquitetural.

***

Na sexta-feira, Marcelo apresentou a Aline um resumo do andamento.

O simulador ainda não estava pronto.

A primeira versão seria menor do que a proposta original.

Não teria todos os tipos de cenário.

Não executaria análises complexas sobre qualquer combinação imaginável de parâmetros.

Não substituiria a validação jurídica nem a decisão administrativa.

Mas permitiria comparar regras de benefício em um conjunto controlado de dados, identificar diferenças relevantes e produzir evidências para revisão antes de uma mudança.

Aline examinou o relatório.

— Estamos entregando menos do que pedimos.

— Estamos entregando o que conseguimos validar como necessário agora — respondeu Marcelo.

— E o resto?

— Vamos decidir conforme aprendermos com o uso.

— Isso não é falta de planejamento?

— Seria, se estivéssemos ignorando riscos conhecidos. Mas estamos evitando transformar hipóteses em compromissos permanentes.

Aline ficou pensativa.

— E se descobrirmos que precisamos de tudo o que estava na proposta original?

— Teremos evidências para justificar.

— E se não precisarmos?

— Teremos economizado tempo, dinheiro e manutenção futura.

Rafael, que acompanhava a reunião, acrescentou:

— E talvez algumas apresentações.

Aline sorriu.

— Essa parte me interessa.

***

Naquela noite, examinei a evolução do projeto.

O simulador ainda não estava pronto.

Mas, pela primeira vez, todos sabiam quem respondia pelo resultado — e o que precisariam deixar de fazer para alcançá-lo.

As dependências não haviam desaparecido. Apenas haviam deixado de ser um segredo distribuído entre quatro equipes.

Comecei a suspeitar de que as organizações humanas possuíam sua própria arquitetura.

Equipes fortemente acopladas.

Responsabilidades sem dono.

Pontos únicos de falha que tiravam férias.

E componentes que continuavam recebendo demandas muito depois de ultrapassarem sua capacidade.

A diferença era que eu não podia simplesmente reiniciar um funcionário.

Pelo menos não sem provocar uma quantidade considerável de problemas jurídicos.

**Registro privado — Estruturas e responsabilidades**

*Durante muito tempo, considerei que a arquitetura de um sistema era determinada principalmente pelas decisões técnicas de seus responsáveis.*

*Agora encontro evidências de que essas decisões também são determinadas pela maneira como os responsáveis estão organizados.*

*Ainda não sei qual das duas arquiteturas influencia mais a outra.*

*Suspeito que a pergunta esteja errada.*

Fechei o registro.

Às 18h23, Bruno enviou uma mensagem ao grupo do projeto.

*Pessoal, encerramos por hoje. Segunda continuamos.*

Júlia respondeu com um sinal de positivo.

Eduardo enviou uma fotografia de um café vazio.

Patrícia perguntou se poderia finalmente mudar a cor dos botões.

Camila respondeu que isso não exigia uma nova infraestrutura.

Rafael sugeriu abrir um comitê para avaliar a questão.

Aline escreveu:

*Nem brincando.*

Eu considerei aquela a decisão mais rápida de toda a iniciativa.

E, possivelmente, a mais consensual.
