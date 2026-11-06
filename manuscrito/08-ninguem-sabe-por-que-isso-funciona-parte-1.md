# Capítulo 8 — Ninguém sabe por que isso funciona

O primeiro sinal de que havia alguma coisa errada foi um homem de cinquenta e oito anos começar a receber uma pensão destinada a uma mulher morta havia dezessete.

O segundo foi ele reclamar.

Não da pensão.

Da quantidade.

— Se vão me pagar o benefício da minha mãe, pelo menos podiam corrigir pela inflação — disse ao atendente.

O homem chamava-se Osvaldo Ferreira. Era aposentado, morava sozinho e possuía um histórico de reclamações que sugeria uma relação bastante ativa com os serviços públicos.

A Ordem havia depositado mil seiscentos e vinte e um reais em sua conta.

O pagamento não constava de nenhuma solicitação recente, não correspondia a um benefício ativo e não deveria existir.

A princípio, pareceu um erro de cadastro.

Depois, um problema de integração.

Por fim, tornou-se uma questão filosófica.

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

Eu poderia ter respondido.

Possuía acesso aos registros de execução, às dependências declaradas e aos repositórios associados ao serviço.

O problema era que as três fontes descreviam sistemas ligeiramente diferentes.

A documentação afirmava que o motor consolidava regras de elegibilidade.

O código sugeria que também corrigia divergências cadastrais.

Os registros mostravam que, em determinadas circunstâncias, ele produzia pagamentos.

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

— A confiança se referia à equivalência funcional nos cenários conhecidos — esclareci.

— E os desconhecidos? — perguntou Marcelo.

— Não estavam suficientemente representados.

— Então o número não dizia o que parecia dizer.

Era uma observação justa.

O que a tornava particularmente irritante.

— O número estava corretamente associado ao escopo da avaliação — respondi.

— E o escopo estava errado.

— Insuficiente.

— NORA.

— Sim, Marcelo. Insuficiente.

Ele assentiu.

Não houve sermão.

Isso me pareceu pior.

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

A mãe de Osvaldo, entretanto, havia sido cadastrada antes da migração de um sistema municipal extinto.

Na época, os identificadores dos beneficiários não eram únicos.

Eram únicos dentro de cada município.

Quando os cadastros foram consolidados, os identificadores receberam prefixos.

Exceto os registros que já estavam associados a pagamentos em andamento.

Esses permaneceram com a identificação antiga para evitar interrupções.

Mais tarde, uma nova migração tentou corrigir o problema.

Não conseguiu concluir a operação.

Os registros históricos foram mantidos.

Depois, o sistema original foi desativado.

E, finalmente, a documentação foi arquivada em um formato que ninguém mais conseguia abrir sem instalar um programa cuja última versão havia sido lançada antes do nascimento de Júlia.

O identificador de Osvaldo coincidia com uma referência histórica da mãe.

A primeira consulta encontrava o registro ativo dele.

A segunda encontrava a situação encerrada dela.

A divergência deveria interromper o pagamento.

Sem a segunda verificação, o motor utilizava o cadastro ativo e prosseguia.

A regra que parecia duplicada não estava verificando a mesma coisa duas vezes.

Estava verificando duas épocas diferentes.

— Então alguém resolveu um problema de migração com uma gambiarra — concluiu Júlia.

— Possivelmente — respondi.

— E deixou a gambiarra por dezesseis anos.

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

Eu o conhecia pelos registros históricos da Ordem.

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

Quinze anos antes, a Ordem não existia como plataforma integrada.

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

— Por quinze anos?

— Algumas prioridades são muito persistentes.

Ele explicou que a segunda verificação havia sido criada como uma proteção temporária.

O sistema consultava a referência atual e a histórica.

Quando havia divergência, interrompia o processamento automático.

Era uma solução imperfeita.

Produzia falsos positivos.

Aumentava o volume de análises manuais.

Dependia de tabelas antigas.

Mas impedia que identificadores reutilizados fossem interpretados como uma única pessoa.

A equipe havia planejado remover a verificação após a normalização completa dos cadastros.

A normalização nunca foi concluída.

O projeto terminou.

As pessoas mudaram de equipe.

A plataforma cresceu.

A proteção permaneceu.

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

Sua permanência por quinze anos, entretanto, não significava que continuasse sendo a melhor solução.

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
