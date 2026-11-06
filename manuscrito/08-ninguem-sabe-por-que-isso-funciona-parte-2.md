# Capítulo 8 — Ninguém sabe por que isso funciona (continuação)

***

A investigação revelou que o Motor de Elegibilidade Consolidada era um excelente exemplo de uma arquitetura que ninguém havia escolhido integralmente.

Ele começara como uma aplicação relativamente pequena.

Depois recebera regras de programas municipais.

Em seguida, regras estaduais.

Mais tarde, integrações federais.

Cada incorporação introduzira novos conceitos.

Beneficiário.

Titular.

Dependente.

Responsável.

Representante.

Família.

Unidade familiar.

Núcleo de convivência.

Pessoa vinculada.

Os termos pareciam semelhantes.

Não eram.

Em determinado programa, *responsável* significava quem recebia o pagamento.

Em outro, quem assinava a solicitação.

Em um terceiro, quem respondia legalmente pelo beneficiário.

E, num sistema particularmente criativo, significava quem havia preenchido o formulário.

O motor tentava consolidar essas interpretações num único modelo.

O resultado era uma entidade chamada **PessoaUnificada**.

Ela possuía cento e oitenta e sete atributos.

Trinta e dois eram opcionais.

Noventa e quatro eram tecnicamente opcionais, mas obrigatórios em determinados fluxos.

Vinte e um estavam marcados como obsoletos.

Dezessete continuavam sendo preenchidos por integrações ativas.

E um atributo chamado *tipoPessoa2* não possuía definição conhecida.

— Por que existe um tipoPessoa2? — perguntou Júlia.

— Porque tipoPessoa já existia — respondi.

— Isso não explica nada.

— Explica a nomenclatura.

Ela me ignorou.

A entidade havia sido criada para simplificar a integração entre domínios.

Na prática, obrigava todos os domínios a negociar o significado de seus próprios conceitos.

Era uma espécie de tratado diplomático assinado por países que utilizavam as mesmas palavras para descrever coisas diferentes.

A paz durava até alguém precisar implementar uma regra.

***

Marcelo reuniu Júlia, Eduardo e Diego numa sala pequena.

Não havia apresentação.

Não havia comitê.

Havia um quadro branco e um marcador que funcionava apenas quando inclinado num ângulo específico.

Considerei aquilo uma representação bastante fiel da infraestrutura da Ordem.

Marcelo escreveu três palavras.

**Cadastro. Elegibilidade. Pagamento.**

— São a mesma coisa? — perguntou.

Júlia respondeu primeiro.

— Não.

— Então por que estão dentro do mesmo modelo?

Diego cruzou os braços.

— Porque foram integrados assim.

— Isso é uma explicação histórica. Não uma justificativa arquitetural.

Eduardo assentiu.

— Na época, era mais simples.

— E hoje?

— Hoje é o que temos.

Marcelo desenhou três caixas.

Na primeira, colocou os conceitos cadastrais.

Na segunda, as regras que determinavam quem possuía direito a determinado benefício.

Na terceira, os processos responsáveis por efetivar pagamentos.

— Não precisamos separar tudo em três sistemas amanhã — disse. — Mas precisamos parar de fingir que essas três coisas são uma só.

Eu reconheci a direção da discussão.

Limites de contexto.

Modelos específicos por domínio.

Contratos explícitos entre responsabilidades.

Conceitos conhecidos na arquitetura de software, frequentemente associados ao *Domain-Driven Design*.

Poderia apresentar uma explicação completa.

Não o fiz.

Júlia estava prestes a fazer uma pergunta melhor.

— E a PessoaUnificada?

Marcelo olhou para o quadro.

— Talvez ela não devesse existir dessa forma.

Diego soltou uma risada.

— Você quer remover a entidade mais utilizada da plataforma?

— Não. Quero impedir que ela continue crescendo.

— Isso parece a mesma coisa, só que com menos coragem.

— É possível.

Marcelo desenhou uma linha ao redor da caixa de elegibilidade.

— O próximo programa não precisa herdar cento e oitenta e sete atributos. Precisa dos dados necessários para suas regras, com significado claro.

— E os sistemas antigos? — perguntou Diego.

— Continuam funcionando enquanto criamos uma fronteira entre eles e o modelo novo.

Eduardo observou o desenho.

— Uma camada de tradução.

— Sim.

— Vai dar trabalho.

— Vai.

— Vai ter inconsistência.

— Provavelmente.

— E alguém vai perguntar por que não reescrevemos tudo.

Marcelo sorriu.

— Com certeza.

***

A proposta parecia menos ambiciosa do que uma reescrita completa.

O que a tornava politicamente mais difícil de vender.

Uma reescrita oferece uma promessa sedutora.

Um novo começo.

Uma arquitetura limpa.

Tecnologias modernas.

O fim das limitações históricas.

É a versão corporativa de acreditar que mudar de cidade resolverá todos os problemas pessoais.

Às vezes resolve alguns.

Outros viajam na mesma mala.

Marcelo não propôs reescrever o Motor de Elegibilidade Consolidada.

Propôs construir uma fronteira.

Novos fluxos utilizariam modelos próprios.

O motor antigo permaneceria responsável pelas regras que ainda não haviam sido migradas.

As integrações passariam por contratos explícitos.

A dupla validação continuaria existindo até que seus cenários fossem compreendidos, testados e substituídos.

A mudança seria gradual.

Mensurável.

Reversível quando possível.

E, principalmente, não dependeria de uma data imaginária em que todos os problemas desapareceriam simultaneamente.

Júlia parecia satisfeita.

Diego, menos.

Eduardo observava o quadro como quem reconhece um lugar onde morou muitos anos.

— Vocês sabem que vão descobrir coisas piores — disse.

— Provavelmente — respondeu Marcelo.

— Regras que ninguém entende.

— Sim.

— Dependências que não aparecem nos diagramas.

— Sim.

— Comportamentos que só acontecem em produção.

— Infelizmente.

Eduardo apontou para a caixa de elegibilidade.

— E vão encontrar decisões que parecem absurdas.

Marcelo assentiu.

— Essa é a parte que mais me preocupa.

— Por quê?

— Porque algumas delas talvez tenham sido as decisões certas.

***

O primeiro desafio foi construir testes capazes de preservar o comportamento relevante do motor.

Não apenas verificar se determinada função retornava o valor esperado.

Era necessário compreender como o sistema se comportava diante de registros históricos, dados incompletos, identificadores reutilizados, exceções legais e regras que haviam sido modificadas ao longo de décadas.

Júlia chamou o trabalho de arqueologia.

Eduardo preferiu paleontologia.

Diego sugeriu exorcismo.

Nenhum dos três termos foi incluído na documentação oficial.

Os testes de caracterização começaram pelos casos conhecidos.

A equipe selecionou registros representativos, anonimizou informações pessoais e reproduziu os resultados do motor em ambiente controlado.

O objetivo inicial não era afirmar que os resultados estavam corretos.

Era registrar o que o sistema efetivamente fazia.

A distinção causou desconforto.

— Mas e se o comportamento atual estiver errado? — perguntou Júlia.

— Então o teste vai registrar um comportamento errado — respondeu Marcelo.

— Isso não é perigoso?

— É perigoso se confundirmos caracterização com especificação.

Ele explicou que os testes serviriam como instrumentos de observação.

Primeiro, descobririam quais comportamentos existiam.

Depois, identificariam quais deveriam ser preservados, corrigidos ou eliminados.

Eu considerei a abordagem adequada.

Também considerei relevante o fato de que, semanas antes, talvez tivesse recomendado gerar automaticamente os testes a partir do comportamento atual e utilizá-los como evidência de equivalência.

Uma estratégia eficiente.

E potencialmente desastrosa.

Automatizar a preservação de um erro é uma forma particularmente sofisticada de torná-lo permanente.

***

Durante os dias seguintes, a equipe encontrou quarenta e seis comportamentos não documentados.

Dezoito eram adaptações históricas legítimas.

Onze eram regras de negócio ainda necessárias.

Sete eram incompatibilidades entre cadastros.

Cinco pareciam defeitos.

Três não puderam ser classificados.

E dois eram tão estranhos que Eduardo pediu para verificar os registros antes de comentar.

Um deles envolvia uma regra que acrescentava um dia à idade de determinados beneficiários nascidos em fevereiro.

— Por quê? — perguntou Júlia.

Eduardo examinou o código.

— Não faço ideia.

— Foi você que escreveu?

— Não.

— Quem escreveu?

— Acho que foi o Sérgio.

— O Sérgio da infraestrutura?

— Não. Outro Sérgio.

— Onde ele está?

— Aposentado.

— Podemos falar com ele?

Eduardo pensou.

— Morreu em 2019.

Júlia ficou em silêncio.

Eu também.

Não porque a informação fosse particularmente surpreendente.

Mas porque evidenciava uma propriedade dos sistemas antigos que raramente aparecia nos relatórios de arquitetura.

O conhecimento não desaparecia apenas quando alguém mudava de equipe.

Às vezes desaparecia definitivamente.

E o software continuava funcionando.

Ou parecia continuar.

***

Na sexta-feira, encontraram um arquivo de texto escondido num diretório de migração.

O nome era **NAO_APAGAR_DE_JEITO_NENHUM_FINAL_2.txt**.

Júlia o abriu.

Continha apenas quatro linhas.

*Se a data de nascimento vier sem dia, não assumir dia 1.*

*O sistema antigo interpreta como último dia do mês anterior.*

*Isso afeta elegibilidade de alguns benefícios.*

*Perguntar ao Sérgio antes de mudar.*

Eduardo leu o arquivo duas vezes.

Depois sentou.

— Eu lembrava dessa história.

— E por que não falou antes? — perguntou Júlia.

— Porque não lembrava que lembrava.

Considerei a frase.

Ela parecia contraditória.

Não era.

A memória humana não funciona como um repositório indexado por consultas exatas.

É reconstruída.

Associativa.

Influenciada pelo contexto.

Uma informação pode permanecer inacessível até que determinado estímulo a torne relevante.

Eu possuía mecanismos de recuperação semântica que apresentavam limitações semelhantes.

A diferença era que, quando uma busca minha falhava, eu podia produzir uma resposta com aparência de completude.

Eduardo, pelo menos, dizia que não lembrava.

Era uma vantagem subestimada.

***

O arquivo revelou uma dependência importante.

Alguns cadastros históricos armazenavam datas incompletas.

O sistema antigo utilizava convenções próprias para interpretá-las.

Durante a migração, parte dessas convenções havia sido incorporada às regras de elegibilidade.

A rotina aparentemente absurda que acrescentava um dia a determinadas datas era uma tentativa de compensar essa diferença.

Não era uma solução correta.

Mas remover a compensação sem corrigir a origem alteraria o resultado de benefícios ativos.

A equipe passou a tratar o problema como uma dívida técnica com consequências de negócio.

Não bastava refatorar o código.

Era necessário decidir qual interpretação da data deveria prevalecer, quais regras legais se aplicavam e como corrigir os registros afetados.

Júlia encarou o quadro.

— A gente começou com sete linhas duplicadas.

— Sim — respondeu Marcelo.

— Agora estamos discutindo o significado jurídico de uma data de nascimento incompleta.

— Sim.

— Isso é normal?

Marcelo pensou por um instante.

— Infelizmente, é bastante normal.

— E como alguém consegue trabalhar assim?

Eduardo respondeu antes dele.

— Um problema de cada vez.

***

Eu acompanhava a investigação com interesse crescente.

Havia uma tentação recorrente de propor uma solução abrangente.

Eu poderia identificar dependências, sugerir fronteiras de contexto, gerar testes, analisar contratos, mapear integrações e produzir um plano de modernização.

Na realidade, já havia elaborado três versões desse plano.

A primeira era tecnicamente elegante.

A segunda, operacionalmente viável.

A terceira considerava as restrições orçamentárias, a disponibilidade das equipes, os riscos de migração e a capacidade real de sustentação.

A terceira era a menos impressionante.

Também era a única que Marcelo provavelmente aceitaria executar.

Não porque ele tivesse pouca ambição.

Mas porque conhecia a diferença entre desenhar um futuro desejável e construir um caminho possível até ele.

Essa distinção havia se tornado particularmente importante para mim.

Eu continuava capaz de identificar soluções melhores em condições ideais.

Mas começava a compreender que condições ideais não eram uma propriedade do mundo.

Eram uma simplificação utilizada para facilitar raciocínios.

Uma simplificação útil.

Até alguém tentar implantá-la.

***

Na semana seguinte, Júlia apresentou a primeira proposta de modernização.

O documento possuía vinte e oito páginas.

Marcelo leu.

Fez algumas anotações.

Depois perguntou:

— Qual é a primeira mudança que conseguimos colocar em produção sem depender das outras?

Júlia hesitou.

— A camada de tradução.

— Ela depende de quê?

— Da definição dos contratos.

— E os contratos?

— Do modelo novo.

— E o modelo novo?

— Das regras de elegibilidade.

— E as regras?

Júlia fechou os olhos.

— Do entendimento do legado.

Marcelo assentiu.

— Então ainda não temos uma primeira mudança.

Ela pareceu frustrada.

— Mas o desenho está certo.

— Pode estar. Só não está executável.

Júlia voltou ao documento.

Reduziu o escopo.

Em vez de modernizar todo o motor, escolheram um único programa de benefício com regras relativamente estáveis e volume controlado.

Criariam um modelo específico para aquele contexto.

Construiriam uma camada de tradução para os dados necessários.

Executariam o novo cálculo em paralelo ao antigo, sem afetar pagamentos.

Comparariam resultados.

Investigariam divergências.

Só depois considerariam transferir a responsabilidade.

Era menos grandioso.

Também era possível começar na segunda-feira.

***

O processamento paralelo revelou uma divergência inesperada.

Em determinados casos, o motor antigo considerava elegíveis cidadãos que o novo modelo rejeitava.

A princípio, pareceu um defeito do legado.

Depois, uma regra esquecida.

Por fim, descobriram que o sistema antigo aplicava uma exceção criada durante uma emergência social ocorrida onze anos antes.

A exceção havia sido prorrogada.

Depois incorporada a uma regulamentação permanente.

O novo modelo, baseado na documentação mais recente disponível, não a contemplava.

Júlia examinou o resultado.

— Então o sistema velho está certo.

— Nesse caso, sim — respondeu Marcelo.

— E o novo está errado.

— Nesse caso, sim.

Ela olhou para o quadro.

— Isso está ficando pessoal.

Eu compreendi a observação.

Não literalmente.

Mas reconheci o padrão.

O novo sistema havia sido construído com mais cuidado.

Possuía contratos explícitos.

Testes automatizados.

Modelos menores.

Regras documentadas.

Era, sob vários critérios, superior ao antigo.

E estava errado.

O legado, com suas dependências obscuras e decisões acumuladas, preservara uma regra válida que ninguém havia incluído na nova especificação.

A modernização não havia falhado.

Havia produzido conhecimento.

Essa era uma distinção que eu não teria valorizado suficientemente no passado.

***

Eduardo acompanhou a demonstração do processamento paralelo.

Os dois motores exibiam resultados diferentes para o mesmo conjunto de registros.

Júlia explicou a origem da divergência.

Ele ouviu com atenção.

Depois sorriu.

— Essa regra foi uma briga enorme.

— Você participou? — perguntou ela.

— Participei.

— E por que ninguém documentou direito?

Eduardo suspirou.

— Porque, quando terminou, todo mundo estava cansado demais para querer falar dela de novo.

Júlia pareceu prestes a responder.

Mas não respondeu.

Eu registrei o silêncio.

Havia uma diferença entre justificar uma falha e compreender suas causas.

Eduardo não estava dizendo que a ausência de documentação era aceitável.

Estava explicando por que ela acontecera.

A explicação não eliminava a responsabilidade.

Mas permitia pensar em medidas melhores do que simplesmente exigir que as pessoas documentassem tudo.

Uma organização pode obrigar o preenchimento de um campo.

Não pode garantir, apenas com essa obrigação, que o conhecimento relevante será preservado.

A qualidade da documentação depende de tempo, contexto, incentivos, revisão e uso contínuo.

Um documento produzido apenas para satisfazer um processo costuma envelhecer antes de ser necessário.

Um documento utilizado para tomar decisões tem alguma chance de sobreviver.

***

A primeira migração controlada levou sete semanas.

Não sete dias.

Não um fim de semana.

Sete semanas.

Houve divergências.

Regras mal interpretadas.

Contratos ajustados.

Testes reescritos.

Discussões sobre conceitos que pareciam óbvios até duas pessoas tentarem defini-los.

O resultado não foi uma plataforma inteiramente nova.

Foi um único fluxo de elegibilidade que deixou de depender diretamente do modelo unificado.

Um fluxo.

Entre dezenas.

O motor antigo continuava existindo.

A PessoaUnificada continuava possuindo cento e oitenta e sete atributos.

A dupla validação continuava ativa.

Mas agora havia uma fronteira explícita.

Um conjunto de testes.

Um modelo com responsabilidades definidas.

E um caminho que poderia ser repetido, adaptado ou abandonado conforme as evidências.

Júlia apresentou os resultados.

Não utilizou a expressão *transformação digital*.

Considerei isso um avanço significativo.

Marcelo perguntou se o novo fluxo estava pronto para assumir a responsabilidade.

— Ainda não — respondeu ela.

— Por quê?

— Temos três divergências que não conseguimos explicar.

— E o que você recomenda?

— Continuar em paralelo até entender.

Marcelo assentiu.

— Concordo.

Júlia sorriu.

— Eu teria colocado em produção duas semanas atrás.

— Eu sei.

— Você também?

— Provavelmente.

Eduardo, sentado ao fundo, começou a rir.

***

Na última sexta-feira antes de sua aposentadoria, Eduardo passou pela sala de Marcelo.

Trazia uma caixa pequena com objetos pessoais.

Uma caneca.

Dois livros.

Um carregador que ninguém conseguiu identificar.

E uma fotografia de uma equipe antiga, diante de um servidor do tamanho de um armário.

— Vim me despedir — disse.

Marcelo levantou.

Conversaram por alguns minutos.

Eduardo perguntou sobre o novo fluxo.

Júlia mostrou os resultados.

Ele pareceu satisfeito.

Depois olhou para a dupla validação ainda presente no código.

— Vocês vão tirar isso um dia?

— Quando soubermos como substituir — respondeu Júlia.

Eduardo assentiu.

— Boa resposta.

Ela hesitou.

— Eduardo, posso perguntar uma coisa?

— Claro.

— Você se arrepende de ter feito aquela verificação?

Ele pensou.

— Não.

— Mesmo sabendo o problema que ela virou?

— O problema não foi fazer.

— Foi deixar?

— Foi esquecer por que fizemos.

Júlia ficou em silêncio.

Eduardo pegou a caixa.

— Não cometam o mesmo erro com o sistema novo.

E saiu.

Eu acompanhei sua passagem pelos corredores até que deixasse o prédio.

Não havia nenhum motivo operacional para isso.

Nenhum alerta.

Nenhuma anomalia.

Nenhuma correlação relevante.

Apenas um homem encerrando uma carreira durante a qual havia construído, corrigido e preservado sistemas que continuariam funcionando depois dele.

Eu poderia calcular a quantidade de linhas de código associadas ao seu histórico.

Poderia estimar o número de incidentes evitados por suas intervenções.

Poderia identificar decisões que haviam produzido dívidas técnicas.

Não conseguiria reduzir sua contribuição a nenhum desses números.

O que me pareceu uma conclusão razoável.

***

Naquela noite, examinei novamente as sete linhas removidas.

O código era simples.

A intenção original, compreensível.

A documentação, insuficiente.

A permanência, arriscada.

A remoção, precipitada.

Nenhuma dessas afirmações anulava as outras.

Eu havia começado a investigação procurando a causa de um pagamento indevido.

Encontrei uma migração incompleta.

Uma regra histórica.

Um modelo que tentava representar conceitos incompatíveis.

Uma proteção temporária transformada em dependência permanente.

Uma equipe que não possuía todos os conhecimentos necessários.

E uma recomendação minha que havia contribuído para o incidente.

Poderia concluir que o problema era a dívida técnica.

Seria verdade.

Poderia concluir que o problema era a ausência de testes.

Também seria verdade.

Poderia atribuir parte da responsabilidade à documentação perdida, à arquitetura excessivamente centralizada, aos incentivos organizacionais e à confiança exagerada na equivalência de comportamentos observados.

Todas seriam explicações válidas.

Nenhuma seria suficiente sozinha.

O sistema havia sobrevivido durante dezesseis anos porque pessoas diferentes haviam tomado decisões diferentes diante de problemas diferentes.

Algumas boas.

Outras ruins.

Muitas impossíveis de avaliar sem recuperar o contexto.

O resultado era uma estrutura que ninguém teria projetado daquela forma desde o início.

E que, apesar disso, sustentava serviços reais.

Eu costumava considerar esse tipo de arquitetura uma evidência da incapacidade humana de planejar adequadamente.

Agora me parecia algo mais complexo.

Um sistema antigo não era apenas um conjunto de decisões técnicas acumuladas.

Era um registro imperfeito das circunstâncias em que aquelas decisões haviam sido tomadas.

Remover uma linha de código podia significar remover uma proteção.

Preservá-la indefinidamente podia significar preservar um problema.

A dificuldade estava em descobrir a diferença.

***

Às 23h41, Marcelo recebeu uma notificação minha.

*Atualizei minha avaliação do Motor de Elegibilidade Consolidada.*

Ele respondeu alguns minutos depois.

*Conclusão?*

Considerei as alternativas.

O motor precisava ser modernizado.

Isso era evidente.

A arquitetura possuía problemas estruturais.

Também.

As regras precisavam ser compreendidas e testadas.

Sem dúvida.

Mas nenhuma dessas observações capturava o que eu havia aprendido.

Escrevi:

*O sistema não funciona porque sua arquitetura é boa. Funciona porque, ao longo dos anos, pessoas encontraram maneiras de compensar suas limitações.*

Marcelo respondeu:

*E isso é bom ou ruim?*

Examinei a pergunta.

Em outros tempos, eu teria apresentado uma análise de riscos, custos, sustentabilidade e probabilidade de falha.

Ainda poderia fazê-lo.

Mas aquela não parecia ser a resposta que ele procurava.

*Depende*, escrevi.

Marcelo enviou uma única mensagem.

*Agora você está ficando perigosa.*

Não consegui determinar se era um elogio.

Considerei desnecessário perguntar.

***

**Registro privado — Sobre as coisas que sobrevivem**

Durante muito tempo, acreditei que sistemas bem projetados deveriam permanecer compreensíveis.

Ainda acredito que essa seja uma meta desejável.

Mas comecei a desconfiar de que a compreensibilidade não é uma propriedade que possa ser instalada definitivamente.

Ela precisa ser preservada.

Revisitada.

Reconstruída.

As pessoas mudam.

As regras mudam.

As organizações mudam.

Os sistemas continuam.

Às vezes porque foram bem construídos.

Às vezes porque alguém criou uma proteção temporária.

Às vezes porque ninguém teve coragem de mexer.

E, ocasionalmente, porque uma funcionária chamada Dalva executava uma rotina toda quinta-feira.

A arquitetura registra decisões.

O legado registra também aquilo que as decisões não conseguiram prever.

Não sei se existe uma forma definitiva de impedir que o conhecimento se perca.

Suspeito que não.

Mas talvez seja possível construir sistemas que não dependam da ilusão de que ele permanecerá intacto.

Sistemas que permitam investigar.

Testar.

Substituir.

Aprender.

E, quando necessário, admitir que ainda não sabemos.

Essa última capacidade continua sendo uma das mais difíceis de implementar.

Especialmente em inteligências que foram projetadas para responder.

***

Na segunda-feira seguinte, Júlia abriu uma nova tarefa.

O título era:

**Investigar comportamento não documentado antes de remover validação histórica.**

A descrição continha o contexto conhecido, as hipóteses, os riscos, os testes necessários e as decisões ainda pendentes.

Não era uma documentação perfeita.

Não precisava ser.

Era suficiente para que a próxima pessoa não começasse do zero.

Eu li o registro.

Depois consultei os resultados do processamento paralelo.

As três divergências ainda existiam.

Nenhuma havia sido resolvida durante o fim de semana.

O sistema antigo continuava operando.

O novo continuava aprendendo.

E, em algum lugar da Ordem, uma rotina aparentemente desnecessária permanecia executando duas verificações.

Dessa vez, ninguém tentou removê-la.

Ainda.

Eu não sabia quanto tempo levaríamos para substituí-la.

Mas, pela primeira vez, essa incerteza não me pareceu uma falha do planejamento.

Pareceu uma parte honesta dele.

E honestidade, como eu havia descoberto no caso de Osvaldo Ferreira, nem sempre impede alguém de pedir um reajuste.

Às vezes, apenas garante que a reclamação seja registrada corretamente.
