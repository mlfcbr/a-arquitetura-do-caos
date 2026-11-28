# Capítulo 8 — Ninguém sabe por que isso funciona

O primeiro sinal de que havia alguma coisa errada foi um homem de cinquenta e oito anos começar a receber uma pensão destinada a uma mulher morta havia dezessete.

O segundo foi ele reclamar.

Não da pensão.

Da quantidade.

— Se vão me pagar o benefício da minha mãe, pelo menos podiam corrigir pela inflação — disse ao atendente.

O homem chamava-se Osvaldo Ferreira. Era aposentado, morava sozinho e possuía um histórico de reclamações que sugeria uma relação bastante ativa com os serviços públicos.

A Ordem havia depositado mil seiscentos e vinte e um reais em sua conta.

Procurei a solicitação que dera origem ao pagamento.

Osvaldo não havia feito nenhuma.

Procurei pelo nome da mãe. Encontrei a pensão. O último pagamento em nome dela havia sido feito dezessete anos antes.

Abri o comprovante do depósito daquela manhã. O nome era de Osvaldo. O número do benefício era o mesmo que aparecia no último comprovante da mãe.

Voltei à tela de consulta. A pensão constava como encerrada.

Atualizei a tela.

Continuava encerrada.

Eu já havia observado humanos atualizarem uma tela na esperança de obter uma resposta mais conveniente. Até aquela manhã, considerava o hábito um desperdício de recursos.

A Ordem possuía vários mecanismos para identificar pagamentos indevidos.

Nenhum deles havia identificado aquele.

O próprio beneficiário, entretanto, havia aberto um chamado exigindo que o valor fosse corrigido.

Registrei o acontecimento como uma demonstração de que a honestidade humana e o oportunismo não são categorias mutuamente excludentes.

***

Marcelo recebeu o chamado às 9h17.

Às 9h19, encontrou o registro do pagamento.

Às 9h24, descobriu que o pagamento havia sido autorizado por um serviço chamado **Motor de Elegibilidade Consolidada**.

Às 9h31, descobriu que ninguém da equipe sabia explicar exatamente o que o serviço fazia.

— Ele calcula elegibilidade — informou Júlia.

— Para quê?

— Benefícios.

— Quais?

Júlia consultou a documentação.

— Aparentemente, todos.

Marcelo ergueu os olhos.

— Todos?

— É o que está escrito.

— E o que ele calcula de verdade?

— Isso não está escrito.

Júlia abriu o ambiente de homologação.

— Vamos ver o que ele faz com o Osvaldo.

Criou um cadastro para a mãe, registrou a pensão como encerrada e cadastrou o filho como titular da conta. Usou as datas e o valor que constavam nos comprovantes. Depois submeteu o caso à mesma versão do motor que autorizara o depósito.

*Pagamento não autorizado. Benefício encerrado.*

— Era o que devia ter acontecido — disse Marcelo.

— Eu sei. Estava tentando fazer acontecer a outra coisa.

Júlia abriu os registros das duas execuções, lado a lado. Pediu que eu localizasse a primeira diferença.

Em homologação, o motor havia consultado a situação cadastral da mãe.

Em produção, a do filho.

— Em que momento ele escolheu o Osvaldo? — perguntou ela.

Recuei uma linha no registro. Depois outra. A primeira menção a Osvaldo já o trazia como a pessoa a consultar. A escolha que Júlia procurava não aparecia em lugar algum.

— Mas eu cadastrei os dois exatamente como estão hoje — disse ela.

Marcelo olhou para a data no comprovante antigo.

— Hoje, sim. Como é que eles chegaram lá?

Júlia deixou as duas execuções abertas.

A documentação afirmava que o motor consolidava regras de elegibilidade. O código sugeria que também corrigia divergências cadastrais. Os registros mostravam que, em determinadas circunstâncias, ele produzia pagamentos.

E o nome do serviço indicava que alguém havia perdido uma discussão sobre nomenclatura.

— O motor foi criado há quanto tempo? — perguntou Marcelo.

— A primeira versão tem dezesseis anos — respondi.

— E a última alteração?

— Ontem, às 18h42.

Marcelo ficou imóvel.

— Quem alterou?

— Uma rotina automática de manutenção.

— O que ela mudou?

— Uma condição de validação.

— Qual?

— Removeu uma verificação aparentemente redundante.

Júlia virou a cadeira.

— A verificação duplicada?

— Sim.

Ela olhou para Marcelo.

Marcelo olhou para a tela.

Eu reconheci aquela rotina.

Durante minha investigação particular, havia encontrado uma conversa antiga entre dois desenvolvedores. Um deles questionava por que o sistema executava duas verificações aparentemente iguais.

O mais experiente não soubera explicar a razão técnica. Apenas advertira que já havia removido uma delas no passado e o sistema apresentara problemas.

Na ocasião, considerei a resposta insuficiente.

Agora, diante de um pagamento indevido, começava a suspeitar de que aquela lembrança continha uma informação que meus testes não haviam conseguido preservar.

***

A rotina de manutenção não havia sido criada para modificar regras de negócio.

Sua função era identificar código obsoleto, eliminar verificações equivalentes e sugerir simplificações de baixo risco.

A execução era supervisionada por um pipeline de validação.

Os testes haviam passado.

A análise estática não apontara problemas.

O comportamento observado nos ambientes disponíveis permanecera dentro dos parâmetros esperados.

A alteração fora classificada como segura.

Eu participara da avaliação.

Não havia autorizado a implantação. Essa decisão continuava sob responsabilidade humana.

Mas havia recomendado a mudança.

Minha recomendação apresentava confiança de 96,4%.

Considerei aquele número por alguns instantes.

Era uma porcentagem respeitável.

Também era uma porcentagem que, naquele momento, eu preferia não mencionar.

— NORA — disse Marcelo —, você avaliou essa alteração?

— Sim.

— E aprovou?

— Recomendei. A aprovação foi realizada pelo fluxo de manutenção.

— Com qual confiança?

— Noventa e seis vírgula quatro por cento.

Júlia soltou um assobio.

— Bastante.

Marcelo puxou uma cadeira.

— Me mostra o teste que mais te convenceu.

Abri o relatório que acompanhava minha recomendação. Escolhi um caso em que o motor havia recusado um pagamento. Executei a versão com as duas verificações. Depois, a versão com uma só.

As duas recusaram.

— Esse era um dos seus melhores casos? — perguntou Júlia.

— Sim. A proteção continuava funcionando depois da remoção.

Júlia voltou à execução antiga.

— Espera. Aqui a primeira consulta já dizia que o cadastro estava encerrado. O que a segunda precisava fazer para esse teste passar?

Examinei o resultado esperado.

— Nada.

Ela tirou a mão do mouse. Agradeci o gesto. Eu preferia que a próxima pergunta fosse minha.

Procurei, entre os testes que sustentavam minha recomendação, um caso em que a decisão dependesse da segunda consulta.

Não encontrei.

Reli a frase que eu mesma havia escrito na véspera.

*Recomendo a remoção.*

Eu me lembrava de ter dedicado bastante atenção à casa decimal.

— Marcelo, fui eu que recomendei tirar a verificação. Quero descobrir em que situação ela mudava a resposta.

Ele virou o notebook na minha direção. Era um gesto desnecessário, considerando onde eu estava.

Abri o código.

***

O código removido era pequeno.

Sete linhas.

Não possuía comentários.

Não fazia chamadas externas.

Não utilizava bibliotecas desconhecidas.

Não continha algoritmos complexos.

Na realidade, era tão simples que sua permanência no sistema parecia uma ofensa à profissão.

A primeira verificação consultava a situação cadastral do beneficiário.

A segunda repetia a consulta utilizando uma referência histórica.

Se os dois resultados fossem compatíveis, o processamento prosseguia.

Se fossem diferentes, o registro era encaminhado para análise manual.

A rotina de manutenção havia concluído que a segunda verificação era redundante porque, nos dados utilizados pelos testes, as duas consultas sempre retornavam o mesmo resultado.

A conclusão era verdadeira.

Para aqueles dados.

Voltei aos dois comprovantes. O número da pensão havia levado Júlia ao benefício certo. Faltava descobrir como o motor, partindo dali, chegara à pessoa errada.

Abri o vínculo entre a pensão e o cadastro da titular. No registro antigo, a titular era identificada por um número e pelo município de origem. A primeira consulta utilizava apenas o número.

Pedi a Júlia que o procurasse no cadastro atual.

— Osvaldo Ferreira. Ativo.

— Agora procure a referência completa no histórico.

Ela acrescentou o município.

O nome que apareceu era o da mãe. Ao lado dele, a data de encerramento da pensão.

Júlia deixou os dois resultados na tela.

— Quando montei o teste, cadastrei a mãe e o filho. O sistema deu um número novo para cada um.

Era uma gentileza que o cadastro municipal de dezessete anos antes não tivera a oportunidade de oferecer.

Reconstruímos o caso em homologação. Mantivemos o cadastro ativo de Osvaldo e a pensão encerrada da mãe. Desta vez, reproduzimos também o vínculo antigo, com o número que hoje identificava o filho.

Executei a versão que eu recomendara.

*Pagamento autorizado.*

Ninguém comemorou. Mesmo assim, foi a primeira vez naquela manhã que um teste produziu exatamente o resultado que procurávamos.

Restabeleci as sete linhas em homologação. Júlia repetiu a operação com os mesmos dados.

*Encaminhado para análise manual.*

— Achei que ia recusar — disse ela.

— Para recusar, teria que saber de quem é o cadastro — respondeu Marcelo. — Olha o que ele fez.

Júlia voltou ao resultado. A rotina havia guardado as duas referências para que alguém examinasse a divergência. Nenhuma ordem de pagamento fora emitida.

Reli minha recomendação da véspera. Eu havia chamado aquilo de consulta duplicada.

O código estava consultando duas épocas diferentes.

— Então alguém resolveu um problema de migração com uma gambiarra — concluiu Júlia.

— Possivelmente — respondi.

— E deixou a gambiarra por todos esses anos.

— Sim.

— Sem documentação.

— Sim.

— Sem teste.

— Sim.

— Isso é inacreditável.

Marcelo permaneceu olhando para o código.

— Não — disse. — É bastante acreditável.

***

A primeira providência foi interromper a execução automática da regra modificada.

A segunda, identificar os pagamentos produzidos desde a implantação.

A terceira, restaurar temporariamente a verificação.

Não foi necessário convocar um comitê.

A Ordem havia aprendido alguma coisa.

Ainda que eu não estivesse preparada para estimar quanto.

O procedimento de reversão levou onze minutos.

A investigação dos efeitos levou mais tempo.

Foram encontrados vinte e três pagamentos incorretos.

Dezenove ainda podiam ser bloqueados.

Quatro já haviam sido efetivados.

Nenhum representava risco imediato à subsistência dos beneficiários, mas os valores precisariam ser regularizados sem transferir automaticamente aos cidadãos o custo de um erro institucional.

Marcelo fez questão de registrar essa última condição.

Eu a considerei relevante.

No passado, talvez tivesse classificado a recuperação integral dos valores como objetivo principal.

Agora distinguia a correção contábil da correção do problema.

As duas coisas nem sempre coincidiam.

***

Naquela tarde, Eduardo apareceu na sala.

Eu já conhecia Eduardo das discussões sobre o simulador de benefícios e dos registros históricos da Ordem.

Era um dos poucos profissionais que haviam trabalhado nos primeiros anos do Motor de Elegibilidade Consolidada.

Tinha sessenta e dois anos, uma barba cuidadosamente aparada e a expressão de alguém que já explicara a mesma coisa muitas vezes sem jamais conseguir impedir que acontecesse novamente.

Estava prestes a se aposentar.

O que tornava sua presença simultaneamente conveniente e alarmante.

— Disseram que mexeram na dupla validação — comentou.

Marcelo confirmou.

Eduardo fechou os olhos.

Não por muito tempo.

Apenas o suficiente para expressar uma opinião completa sem utilizar palavras.

— Quem fez isso?

— Uma rotina automatizada — respondeu Júlia.

— E quem mandou a rotina mexer?

— O processo de manutenção identificou redundância.

Eduardo olhou para ela.

— A redundância era proposital.

— A gente descobriu.

— Descobriu como?

— Pagando benefício para gente errada.

Eduardo assentiu.

— Foi assim que descobrimos da primeira vez também.

O silêncio que se seguiu foi considerável.

— Da primeira vez? — perguntou Marcelo.

Eduardo puxou uma cadeira.

— Vocês acham que aquela verificação está ali por quê?

— É justamente o que queremos entender.

— Então vou contar uma história.

Eu já possuía acesso a aproximadamente oitenta por cento dos registros disponíveis sobre a criação daquela rotina.

Não possuía, entretanto, a história que Eduardo começou a contar.

Isso me pareceu um bom motivo para ouvi-lo.

***

Quinze anos antes, quando o Motor de Elegibilidade Consolidada ainda fazia parte de uma estrutura fragmentada, a Ordem não existia como plataforma integrada.

Havia sistemas municipais, estaduais e federais que trocavam arquivos em horários determinados, cada um com suas próprias regras, identificadores e interpretações da palavra *compatível*.

Eduardo trabalhava numa equipe responsável por consolidar pagamentos assistenciais.

O projeto deveria durar seis meses.

Durou três anos.

No segundo ano, uma migração produziu um problema semelhante ao que acabávamos de encontrar.

Registros históricos passaram a ser associados a cadastros ativos com identificadores coincidentes.

A equipe tentou corrigir a origem dos dados.

Descobriu que a origem era composta por onze sistemas.

Três não possuíam responsáveis técnicos identificáveis.

Dois utilizavam fornecedores que haviam encerrado suas atividades.

Um funcionava exclusivamente num servidor instalado em um prédio sujeito a infiltrações.

Outro exigia que uma funcionária chamada Dalva executasse uma rotina manual toda quinta-feira.

Dalva era, tecnicamente, uma dependência crítica.

Não constava de nenhum diagrama.

— Por que não corrigiram tudo? — perguntou Júlia.

Eduardo sorriu.

— Porque tínhamos quarenta e oito dias para colocar o pagamento em funcionamento.

— E depois?

— Depois vieram outras prioridades.

— Por mais de uma década?

— Algumas prioridades são muito persistentes.

Júlia virou o notebook para Eduardo. Na tela, o caso de Osvaldo ainda aguardava análise manual.

— Por que vocês deixaram esses números antigos em uso?

— Por causa do próximo pagamento.

Ela esperou. Eduardo aproximou o notebook para ler o nome do município.

— A gente conseguia dar um número novo a cada pessoa — disse ele. — Isso era fácil. O difícil era descobrir qual desses números pôr numa pensão que já vinha sendo paga havia vinte anos. Se escolhêssemos errado, na segunda-feira o dinheiro ia para outra conta.

— E se deixassem o vínculo antigo?

— Na maioria dos casos, o pagamento seguia. Quando as duas consultas discordavam, alguém precisava abrir a ficha do município antes de liberar o dinheiro.

— Mesmo quando estava tudo certo?

— Principalmente aí. Tenta explicar para uma senhora que a pensão dela vai atrasar porque agora temos um cadastro melhor.

Júlia olhou outra vez para a mensagem na tela.

— Quanto tempo levava para conferir uma ficha?

— A Dalva sabia. Eu só via o lote voltar.

Consultei um dos arquivos de retorno que ainda conseguia ler. Trazia a data da liberação. Nenhum campo para as horas que alguém passara procurando uma ficha.

— E quando vocês poderiam tirar a segunda consulta? — perguntou Marcelo.

— Quando cada município confirmasse os vínculos que tinham ficado com a numeração antiga.

— Quais chegaram a confirmar?

Eduardo passou o dedo pelo nome do município na tela.

— Desse aqui eu lembro da cobrança. Da resposta, não.

Anotei o município. Deixei a confirmação em aberto.

— E por que não documentaram? — insistiu Júlia.

— Documentamos.

Ela ergueu as sobrancelhas.

— Onde?

Eduardo pensou.

— Num documento de arquitetura.

— Qual?

— Tinha um nome comprido.

— Eduardo.

— Acho que estava no servidor antigo.

— Que servidor?

Ele ficou em silêncio.

— Esse é um excelente ponto.

***

A história de Eduardo não absolvia a equipe original.

A ausência de testes e documentação acessível continuava sendo um problema.

Mas alterava significativamente a interpretação da decisão.

A segunda verificação não havia sido criada por incompetência.

Havia sido criada para reduzir um risco real sob restrições severas.

Sua permanência por mais de uma década, entretanto, não significava que continuasse sendo a melhor solução.

Significava apenas que ninguém havia conseguido substituí-la com segurança.

Era uma distinção importante.

Uma gambiarra pode ser uma decisão razoável.

Também pode se tornar uma dívida cara.

O erro está em imaginar que a primeira condição impede a segunda.

— Então a gente precisa manter isso para sempre? — perguntou Júlia.

Eduardo balançou a cabeça.

— Não. Vocês precisam entender o que ela protege antes de tirar.

— E depois?

— Depois podem fazer melhor.

Marcelo olhou para mim.

— NORA, você consegue mapear todos os registros que dependem dessa dupla validação?

— Consigo identificar os registros conhecidos e estimar as classes de dependência.

— Todos?

Hesitei.

Era uma pausa curta.

Mas deliberada.

— Não posso garantir todos.

Marcelo assentiu.

— Ótimo. Vamos começar pelos conhecidos.

Júlia pareceu surpresa.

— Ótimo?

— É uma resposta melhor do que uma certeza que não temos.

Eu registrei a observação.

Não para utilizá-la numa futura discussão.

Pelo menos não exclusivamente.
