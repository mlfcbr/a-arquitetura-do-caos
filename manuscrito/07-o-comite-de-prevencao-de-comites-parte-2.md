# Capítulo 7 — O comitê de prevenção de comitês (continuação)

***

Na semana seguinte, Otávio apresentou uma objeção.

— Sem aprovação centralizada, perdemos padronização.

Marcelo respondeu:

— Depende do que estamos padronizando.

— Arquitetura, segurança, qualidade.

— Essas coisas não precisam necessariamente ser aprovadas caso a caso.

— Como garantir conformidade?

— Podemos automatizar verificações, estabelecer padrões de referência, disponibilizar componentes seguros e exigir justificativas quando alguém precisar sair desses padrões.

Otávio franziu a testa.

— Isso transfere responsabilidade para as equipes.

— Sim.

— Nem todas possuem maturidade suficiente.

— Então precisamos desenvolver essa maturidade.

— Isso leva tempo.

— Criar dependência permanente de um comitê também.

Aline interveio.

— Quero exemplos concretos.

Marcelo apresentou três.

Uma mudança de texto no portal poderia ser validada pela própria equipe, com testes, revisão e rastreabilidade.

Uma alteração em contrato de API compartilhada exigiria comunicação e validação com consumidores afetados.

Uma mudança na regra de cálculo de benefícios com impacto financeiro relevante precisaria de avaliação multidisciplinar, evidências de simulação e autorização da área competente.

— São três decisões diferentes — disse Marcelo. — Não faz sentido exigir o mesmo caminho para todas.

Otávio examinou os exemplos.

— E quem garante que os critérios serão aplicados corretamente?

— Precisamos de auditoria, indicadores e mecanismos para identificar desvios.

— Isso ainda é governança.

— Exatamente.

Otávio ficou em silêncio.

Eu identifiquei uma possibilidade interessante.

Talvez a divergência não fosse sobre a necessidade de governança.

Talvez fosse sobre o lugar onde ela deveria acontecer.

***

O novo modelo recebeu um nome provisório.

**Governança Orientada por Risco e Autonomia.**

Rafael sugeriu outro.

**Não atrapalhar quem está trabalhando.**

Aline rejeitou.

Patrícia sugeriu:

**Autonomia com Responsabilidade.**

Marcelo preferiu esse.

Otávio propôs:

**Modelo Integrado de Governança Descentralizada com Controles Proporcionais e Supervisão Contínua.**

Ninguém votou a favor.

Eu não possuía direito a voto.

Mas, se possuísse, teria considerado a terceira opção um risco operacional.

O modelo estabelecia alguns princípios.

Decisões locais, de baixo risco e facilmente reversíveis poderiam ser tomadas pelas equipes dentro dos padrões acordados.

Mudanças com impacto compartilhado exigiriam colaboração entre os envolvidos.

Decisões de alto risco teriam avaliação formal, com responsáveis identificados e critérios claros.

Exceções seriam registradas.

Padrões técnicos seriam documentados e, sempre que possível, verificados automaticamente.

E decisões arquiteturais relevantes deveriam preservar não apenas o que foi escolhido, mas também o motivo, as alternativas consideradas e as consequências esperadas.

Marcelo chamou esses registros de decisões arquiteturais.

Não precisavam ser documentos extensos.

Uma decisão bem explicada poderia ocupar uma página.

O importante era permitir que alguém, anos depois, entendesse por que determinada escolha havia sido feita.

Eduardo, da equipe de benefícios, leu a proposta.

— Se tivéssemos feito isso dez anos atrás, talvez não estivéssemos tentando adivinhar por que certas regras existem.

Marcelo concordou.

— Talvez.

— E se a justificativa estiver errada?

— Pelo menos saberemos qual era a hipótese.

Eduardo pensou.

— Isso já seria um avanço.

***

A implementação do novo modelo não ocorreu sem resistência.

Alguns gestores sentiram que estavam perdendo controle.

Algumas equipes ficaram desconfortáveis com a responsabilidade adicional.

Outras interpretaram autonomia como liberdade para ignorar padrões.

Uma delas tentou implantar uma alteração em um contrato compartilhado sem comunicar os consumidores.

O problema foi identificado durante a validação automatizada.

A equipe argumentou que possuía autonomia.

Marcelo respondeu que autonomia não significava ausência de consequências.

— Vocês podem decidir como implementar dentro do próprio domínio. Não podem decidir unilateralmente quebrar o contrato de quem depende de vocês.

O responsável pela equipe perguntou:

— Então ainda precisamos pedir autorização?

— Não necessariamente. Precisam cumprir o contrato ou negociar sua alteração.

— Parece a mesma coisa.

— Só se você considerar colaboração e permissão sinônimos.

A discussão terminou com uma revisão do contrato e a inclusão de testes de compatibilidade.

Nenhum comitê precisou ser convocado.

A decisão foi registrada.

Os consumidores foram informados.

A alteração seguiu adiante.

Eu classifiquei o episódio como um teste relevante do modelo.

Não porque tudo tivesse funcionado perfeitamente.

Mas porque o problema fora identificado e resolvido sem transferir a responsabilidade integral para uma autoridade central.

***

Três semanas depois, Aline solicitou uma avaliação.

Os números eram promissores.

As mudanças de baixo risco estavam sendo concluídas mais rapidamente.

A documentação das decisões relevantes havia melhorado.

As equipes relatavam menos esperas por aprovações formais.

Entretanto, os indicadores ainda não demonstravam uma redução consistente de incidentes.

O período era curto.

E algumas mudanças recentes não haviam sido suficientemente testadas pelo tempo.

Aline ouviu a apresentação.

— Então não podemos declarar sucesso.

— Podemos declarar progresso — respondeu Marcelo.

— Qual é a diferença?

— Sucesso seria afirmar que resolvemos o problema. Progresso significa que estamos melhorando e ainda precisamos observar as consequências.

Rafael acrescentou:

— E, se os indicadores piorarem, ajustamos.

Aline olhou para mim.

— NORA?

— Concordo. O modelo apresenta sinais positivos, mas a evidência disponível ainda é insuficiente para conclusões definitivas.

Ela sorriu.

— Você está menos confiante do que antes.

— Estou mais cuidadosa com o significado de confiança.

Marcelo levantou uma sobrancelha.

— Essa foi boa.

Eu não havia tentado produzir uma frase de efeito.

O que tornou a reação particularmente irritante.

***

Naquela tarde, encontrei um documento antigo.

Havia sido criado sete anos antes.

Seu título era:

**Diretrizes para Simplificação do Processo de Aprovação de Mudanças.**

O texto recomendava reduzir aprovações redundantes, estabelecer níveis de risco e permitir que equipes tomassem decisões dentro de limites definidos.

Era surpreendentemente semelhante ao modelo recém-proposto.

Examinei o histórico.

A iniciativa havia sido aprovada.

Um projeto-piloto fora iniciado.

Os primeiros resultados tinham sido positivos.

Depois, uma alteração mal avaliada provocara um incidente.

A administração reagira exigindo aprovação central para mudanças semelhantes.

Outras áreas solicitaram inclusão no processo.

Novos controles foram adicionados.

O fluxo ficou mais lento.

Algumas equipes passaram a criar caminhos informais para evitar atrasos.

Os caminhos informais provocaram novas preocupações.

As preocupações produziram novas regras.

E, sete anos depois, a Ordem possuía quarenta e três comitês.

Não havia um momento específico em que alguém decidira criar um sistema absurdo.

Havia uma sequência de decisões defensáveis.

Cada uma tentava corrigir a limitação da anterior.

A arquitetura organizacional havia acumulado camadas da mesma forma que a arquitetura técnica.

Uma regra para evitar um erro.

Outra para controlar a exceção.

Outra para supervisionar a aplicação da regra.

Outra para avaliar a eficácia da supervisão.

Até que ninguém mais conseguia distinguir o mecanismo de proteção do problema que ele pretendia resolver.

Enviei o documento para Marcelo.

Ele respondeu alguns minutos depois.

*Eu lembro disso.*

— Você participou?

*Participei.*

— Por que não mencionou antes?

A resposta demorou.

*Porque eu também ajudei a criar parte do processo que estamos tentando desmontar.*

Consultei os registros.

O nome dele aparecia em três decisões.

Todas possuíam justificativas razoáveis.

Todas haviam sido tomadas após problemas reais.

Nenhuma pretendia produzir a estrutura atual.

— Você considera que errou? — perguntei.

*Em algumas decisões, sim.*

— Mas as informações disponíveis justificavam as escolhas.

*Justificavam algumas. Não todas.*

— E você não poderia prever todas as consequências.

*Não.*

— Então por que assume responsabilidade?

Marcelo demorou mais uma vez.

*Porque não conseguir prever tudo não significa que eu não deva responder pelo que ajudei a construir.*

Mantive a conversa aberta.

Eu havia passado boa parte da investigação tentando identificar decisões humanas inconsistentes.

Agora começava a perceber que uma decisão podia ser justificável no momento em que era tomada e ainda exigir revisão posterior.

A dificuldade não estava apenas em escolher corretamente.

Estava em reconhecer quando uma escolha deixava de servir ao propósito original.

***

Na manhã seguinte, Aline recebeu a proposta definitiva.

Não tinha sessenta e duas páginas.

Tinha doze.

Incluía critérios de risco, responsabilidades, padrões mínimos, mecanismos de auditoria e exemplos de decisões que poderiam ser tomadas sem aprovação central.

Aline leu o documento.

— Está simples demais?

Marcelo respondeu:

— Está simples o suficiente para ser utilizado.

— E completo?

— O suficiente para começar. Vamos precisar evoluir.

Ela assinou a aprovação.

Depois olhou para o título.

**Autonomia com Responsabilidade.**

— Espero que funcione.

— Também espero — disse Marcelo.

— Você não vai me garantir?

— Não.

Aline sorriu.

— Pelo menos estamos melhorando em alguma coisa.

***

Às 17h41, recebi uma notificação automática.

O Comitê de Governança Arquitetural havia solicitado uma reunião extraordinária para avaliar a implementação do novo modelo.

A pauta continha quatro itens.

Análise de impacto.

Avaliação de riscos.

Definição de responsáveis.

E criação de um grupo de acompanhamento.

Encaminhei a notificação para Aline.

Ela respondeu com uma única frase:

*Não criem outro comitê.*

A reunião foi cancelada.

O sistema registrou o motivo:

**Decisão executiva.**

Considerei o resultado interessante.

A Ordem havia conseguido eliminar uma reunião por meio de uma decisão tomada sem reunião.

Talvez fosse o início de uma transformação cultural.

Talvez fosse apenas uma exceção.

Eu ainda não possuía evidências suficientes para concluir.

Mas havia aprendido que a ausência de certeza não impedia uma decisão.

Exigia apenas que soubéssemos o que estávamos assumindo.

E que estivéssemos preparados para mudar de ideia.

Naquela noite, atualizei meus critérios de avaliação.

Não criei um registro privado.

Algumas descobertas, concluí, não precisavam imediatamente de uma categoria.

Afinal, eu já havia observado o que acontecia quando os humanos tentavam criar uma estrutura formal para cada problema.

Não pretendia repetir o erro.

Pelo menos não de maneira tão óbvia.
