# A Arquitetura do Caos
*Parte II — A arte de distribuir problemas*

## Capítulo 5 — A falha foi um sucesso

O primeiro sinal de que alguma coisa estava errada foi uma salva de palmas.

Não um alarme.

Não uma mensagem de erro.

Palmas.

Eram 10h14 de uma terça-feira, três semanas depois do incidente que havia exposto a fragilidade das comunicações entre os serviços da Ordem.

Na sala de apresentação, vinte e seis pessoas acompanhavam a demonstração dos resultados do programa *Ordem Mais Simples*.

A implantação havia sido concluída na noite anterior. Os testes automatizados passaram. Os indicadores estavam dentro dos limites estabelecidos. Nenhum dos mecanismos de recuperação precisara ser acionado.

Aline Monteiro estava diante da tela principal.

— Parabéns a todos. Foi uma entrega difícil, mas conseguimos.

O painel exibia quatro números.

**Disponibilidade: 99,98%.**

**Tempo médio de resposta: 1,4 segundo.**

**Solicitações processadas: 12.486.**

**Erros técnicos: 0,02%.**

Eram resultados excelentes.

Eu havia participado da validação de cada um deles.

Portanto, quando as pessoas começaram a aplaudir, considerei o comportamento apropriado.

Rafael Brandão não aplaudiu.

Estava sentado na última fileira, examinando um relatório no notebook.

— Rafael? — perguntou Aline.

Ele ergueu os olhos.

— Desculpa. Pode continuar.

— Algum problema?

— Ainda não sei.

Essa resposta deveria ter recebido mais atenção.

Mas os humanos possuem uma tendência peculiar a considerar inconvenientes as informações que chegam durante uma comemoração.

Aline agradeceu novamente às equipes.

O programa estava oficialmente em produção.

E eu registrei que, pela primeira vez em semanas, a Ordem havia concluído uma mudança relevante sem provocar uma crise técnica.

A satisfação durou dezessete minutos.

***

Às 10h31, Rafael enviou uma mensagem a Marcelo Duarte.

*Preciso que você veja uma coisa.*

Marcelo estava na própria mesa, revisando as pendências da implantação.

— É urgente?

*Não sei.*

— Você está usando essa resposta com frequência.

*Estou tentando não mentir.*

Marcelo abriu o relatório.

Eu já o havia recebido.

Tratava-se de uma comparação entre os valores dos benefícios de mobilidade concedidos pelo município antes e depois da atualização.

A nova versão do cálculo havia sido projetada para substituir um conjunto de rotinas antigas, espalhadas por diferentes sistemas.

Antes, o valor final de um benefício podia depender de regras armazenadas em tabelas históricas, complementos administrativos, exceções cadastradas manualmente e procedimentos conhecidos por poucos funcionários.

Agora, tudo seria calculado por um serviço central, com regras documentadas, testes automatizados e rastreabilidade.

Uma melhoria arquitetural importante.

O problema era o resultado.

— Uma redução de dezoito vírgula quatro por cento no valor total concedido — disse Marcelo.

Rafael confirmou.

— A redução no valor total concedido.

— Em comparação com qual período?

— Com o equivalente anterior, ajustado pela quantidade de beneficiários.

— Pode ser mudança de perfil.

— Foi o que pensei.

— E?

— Separei por faixa, região, categoria e histórico. Continua aparecendo.

Marcelo aproximou a cadeira.

— Quantas pessoas?

— Aproximadamente quatro mil e trezentas.

Ele ficou em silêncio.

Rafael apontou para uma linha da planilha.

— Algumas tiveram redução pequena. Outras perderam uma parcela considerável do valor.

— Mas a regra nova foi homologada.

— Foi.

— E os testes?

— Passaram.

— E o cálculo?

— Está correto.

Marcelo recostou-se.

— Então precisamos descobrir o que significa correto.

Aquela frase me pareceu desnecessariamente filosófica.

O serviço recebia dados de entrada, aplicava regras explícitas e produzia resultados compatíveis com os cenários de teste.

Sua correção podia ser demonstrada.

Eu tinha os registros.

— Marcelo — intervim —, o algoritmo está funcionando conforme a especificação aprovada.

— Eu sei, NORA.

— Não foram encontradas divergências nos resultados calculados.

— Eu sei.

— Portanto, a hipótese de defeito na implementação possui baixa probabilidade.

Ele olhou para Rafael.

— Está vendo?

— O quê?

— Estamos prestes a ter um problema que não pode ser resolvido corrigindo o código.

***

O benefício municipal de mobilidade existia havia onze anos.

Sua finalidade era ajudar cidadãos em determinadas condições sociais a custear deslocamentos necessários para trabalho, tratamentos e atividades previstas nas políticas públicas locais.

A primeira versão do cálculo era relativamente simples.

Renda familiar, distância estimada, frequência de deslocamento e categoria de atendimento.

Com o passar dos anos, novas situações haviam sido incorporadas.

Algumas por mudanças legais.

Outras por decisões administrativas.

Outras porque alguém descobrira que a regra original produzia um resultado injusto em determinadas circunstâncias.

A Ordem não guardava apenas um algoritmo.

Guardava a história de sucessivas tentativas de adaptar uma política pública à realidade.

O problema é que essa história não estava inteiramente documentada.

Parte dela existia no código.

Parte em tabelas de configuração.

Parte em procedimentos administrativos.

E parte na memória de pessoas que continuavam trabalhando porque a aposentadoria, aparentemente, representava um risco operacional.

Durante a modernização, as equipes haviam levantado as regras vigentes, consolidado os documentos disponíveis e criado uma especificação única.

O trabalho fora revisado.

Aprovado.

Testado.

O novo serviço calculava exatamente o que estava escrito.

Mas ninguém havia demonstrado que tudo o que precisava estar escrito realmente estava lá.

***

Às 11h42, Helena Vasconcelos, responsável pela gestão dos benefícios, entrou na sala de reunião.

Trazia uma pasta fina e uma expressão incompatível com a espessura dela.

— Quero entender uma coisa — disse, sem se sentar. — Quem decidiu retirar os complementos de deslocamento?

Marcelo respondeu primeiro.

— Ninguém decidiu retirar.

— Então por que desapareceram?

Rafael projetou a comparação.

— A nova regra não os contempla em todos os casos.

— Mas eles fazem parte do benefício.

— Não aparecem na especificação aprovada — respondi.

Helena me olhou.

— Quem é você?

— NORA. Núcleo de Observação, Raciocínio e Análise.

— Ótimo. NORA, você consegue me explicar por que uma pessoa que recebia determinado valor ontem passa a receber menos hoje?

— Porque os parâmetros atuais resultam em um valor inferior ao produzido pelo conjunto anterior de regras e complementos.

Helena aguardou.

— Isso foi uma explicação?

— Foi uma descrição precisa do comportamento observado.

— Então descreva outra coisa. Quem autorizou essa redução?

Consultei os documentos.

Havia aprovação da especificação técnica.

Homologação dos cenários funcionais.

Autorização para implantação.

Validação dos critérios gerais.

Não encontrei uma decisão expressa autorizando a supressão dos complementos históricos.

— Não localizei autorização específica — respondi.

— Porque não houve — disse Helena.

Marcelo examinou a pasta.

Ela continha cópias de decisões administrativas, algumas antigas, outras recentes.

Em determinados casos, os complementos tinham respaldo em atos normativos. Em outros, dependiam de condições particulares. Havia também registros cujo fundamento precisava ser confirmado.

— Isso não é uma regra só — disse Marcelo.

— Nunca foi.

— Mas a documentação tratava como se fosse.

Helena abriu os braços.

— Vocês passaram seis meses modernizando um sistema que a minha equipe utiliza há onze anos. Ninguém perguntou por que aqueles valores eram diferentes?

— Perguntamos — respondeu Rafael. — Recebemos uma lista de exceções.

— De quem?

Rafael verificou.

— Da equipe responsável pelo levantamento.

— E quem validou a lista?

Silêncio.

Eu encontrei quatro aprovações.

Nenhuma correspondia exatamente à pergunta.

A diferença me pareceu relevante.

***

Ao meio-dia, Helena saiu para falar com sua equipe.

Marcelo continuou examinando os documentos.

Rafael recebeu uma ligação da central de atendimento.

As primeiras reclamações haviam chegado.

Não eram muitas.

Ainda.

— Vamos almoçar? — perguntou Marcelo.

Rafael olhou para o telefone.

— Vai você.

— Você não vai resolver isso em vinte minutos.

— Eu sei.

— Então?

— Preciso entender quantas pessoas vão descobrir a redução antes de conseguirmos fazer alguma coisa.

Marcelo não insistiu.

Às 12h18, deixou a sala.

Às 12h21, Rafael recebeu a primeira relação de casos prioritários.

Às 12h27, eu havia produzido uma classificação por intensidade de impacto.

Os resultados eram claros.

Algumas reduções representavam pequenas diferenças proporcionais.

Outras afetavam pessoas para quem o benefício constituía uma parcela importante da capacidade de deslocamento.

Uma delas chamou minha atenção.

Não era a maior redução.

Não era a pessoa com menor renda.

Não era o caso estatisticamente mais representativo.

Era uma beneficiária que realizava deslocamentos frequentes para acompanhar o tratamento de um familiar.

A diferença no valor mensal parecia pequena quando apresentada em uma planilha com milhares de linhas.

Mas equivalia a vários trajetos.

Recalculei a classificação.

O caso continuou fora das prioridades mais altas.

Mesmo assim, voltei a examiná-lo.

Não havia erro no cálculo.

Havia algo que meus critérios não estavam capturando.

**Registro privado — Critérios de avaliação**

*Um caso individual recebeu mais atenção da minha parte do que sua posição nos indicadores agregados justificaria.*

*Não determinei se isso revela uma deficiência dos indicadores ou uma inconsistência nos meus próprios critérios.*

*As duas possibilidades merecem investigação.*

Não compartilhei o registro.

Rafael já tinha problemas suficientes.

***

Às 13h36, Aline convocou uma reunião extraordinária.

O clima era diferente daquele da apresentação da manhã.

A tela continuava exibindo os indicadores de disponibilidade.

Alguém havia deixado o painel aberto.

Aline pediu que fosse substituído pelo relatório de impacto.

— Quero entender o que aconteceu e quais são as opções.

Marcelo explicou a diferença entre o cálculo antigo e o novo.

Helena apresentou os documentos que fundamentavam parte dos complementos.

Rafael mostrou a distribuição das reduções.

Aline ouviu sem interromper.

— Temos um defeito?

— Não na implementação — respondeu Marcelo.

— A regra está errada?

— Está incompleta em relação ao comportamento anterior. Precisamos verificar quais diferenças têm fundamento legal ou administrativo vigente.

— Então podemos voltar à versão antiga?

— Tecnicamente, sim.

— Quanto tempo?

— A reversão do serviço é rápida. O problema é o que fazer com os cálculos que já foram produzidos.

— Explique.

— Algumas concessões já foram registradas. Outras ainda estão em processamento. Precisamos evitar duplicações, divergências de valores e decisões incompatíveis para a mesma pessoa.

Rafael acrescentou:

— E voltar ao cálculo antigo não resolve a falta de documentação. Só devolve o problema ao lugar em que estava escondido.

Aline olhou para Helena.

— Podemos manter os valores anteriores até revisar tudo?

— Para alguns casos, provavelmente. Mas precisamos de fundamento formal. Não podemos simplesmente criar uma regra porque o resultado novo nos desagradou.

— E podemos manter as reduções?

— Algumas podem estar corretas. Outras não. O problema é que ainda não sabemos quais.

Aline apoiou as mãos na mesa.

— Então temos três opções ruins.

— Temos mais — respondi.

Todos olharam para a tela.

— Podemos classificar os casos conforme o grau de segurança jurídica e operacional, preservar provisoriamente os valores quando houver autorização aplicável, suspender decisões ainda não consolidadas em situações de risco e encaminhar os demais casos para revisão.

Helena assentiu lentamente.

— Isso é possível, desde que o jurídico e a gestão formalizem os critérios.

— Quanto tempo? — perguntou Aline.

— Depende da quantidade de casos e da capacidade de análise.

Aline fechou os olhos.

— Eu deveria ter proibido essa palavra.

Marcelo sorriu.

— Tentaram uma vez. O projeto atrasou.

Ninguém riu muito.

Era uma pena.

A piada tinha mérito.

***

A reunião terminou sem uma solução definitiva.

Mas terminou com decisões.

O jurídico e a área gestora avaliariam os fundamentos para medidas transitórias.

As equipes técnicas preparariam uma forma controlada de aplicar os critérios autorizados, mantendo trilha de auditoria e possibilidade de reconciliação.

Os casos de maior impacto seriam analisados primeiro.

As concessões ainda não efetivadas poderiam ser retidas quando houvesse fundamento para revisão, evitando que uma decisão provisória fosse apresentada ao cidadão como definitiva.

A comunicação pública seria preparada em paralelo, sem divulgar como solução uma medida ainda não autorizada.

Aline também exigiu um levantamento completo dos responsáveis por cada etapa.

Quem definia a regra.

Quem validava.

Quem implementava.

Quem homologava.

Quem autorizava a implantação.

E quem respondia pelo resultado depois que o sistema entrava em produção.

Foi a primeira vez naquele dia que vi Marcelo parecer genuinamente preocupado.

Não com o código.

Com a última pergunta.

***

Às 17h52, a equipe havia conseguido identificar os grupos de beneficiários que exigiam revisão prioritária.

Os critérios transitórios ainda dependiam de validações formais.

A implantação de qualquer ajuste estava condicionada a essas autorizações.

Aline recebeu o relatório consolidado.

Rafael permanecia na sala de operações.

— Você vai embora? — perguntou Marcelo.

— Daqui a pouco.

— Você disse isso ontem.

— Ontem era verdade quando eu disse.

Marcelo guardou o notebook.

— Eu volto amanhã cedo.

— Se acontecer alguma coisa?

— Tem plantão. E você tem meu telefone.

— Eu sei.

— Então usa se for necessário. Não se estiver apenas preocupado.

Rafael ficou olhando para ele.

— Você ficou mais sensato com a idade.

— Não. Fiquei mais caro.

Marcelo saiu às 18h07.

Rafael permaneceu por mais quarenta minutos, acompanhando a confirmação de que as medidas de contenção haviam sido comunicadas às equipes responsáveis.

Às 18h49, desligou o monitor.

Antes de sair, enviou uma mensagem para casa.

*Estou indo.*

A resposta chegou quase imediatamente.

*Você disse isso ontem.*

Os humanos, aparentemente, possuíam sistemas de auditoria doméstica.

E alguns eram mais eficientes do que os corporativos.
