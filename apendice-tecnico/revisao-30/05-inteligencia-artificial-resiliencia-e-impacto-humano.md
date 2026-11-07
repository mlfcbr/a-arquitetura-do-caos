# Apêndice técnico — Engenharia por trás do caos

> **Bloco V — Inteligência artificial, resiliência e impacto humano**
>
> **STATUS: APROVADO PELO AUTOR.** Seleção e redação definitiva dos 32 conceitos aprovadas em 2026-11-07. Complemento independente; não altera a narrativa.

### 25. Evals — Avaliação e métricas de qualidade da IA

**O conceito:** *Evals* são avaliações estruturadas do comportamento de sistemas de inteligência artificial em tarefas e cenários representativos. Podem medir precisão, utilidade, segurança, consistência e consequências dos erros. Para avaliar o valor real de uma IA, também é necessário considerar custos, limitações e resultados produzidos.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS é apresentada com indicadores impressionantes de velocidade, produtividade e satisfação. Entretanto, a avaliação inicial não mede adequadamente recomendações incorretas, riscos evitados ou decisões que precisaram ser corrigidas. NORA questiona se os testes contemplaram os dados históricos e as exceções da Ordem.

**Avaliação:** A avaliação inicial privilegia desempenho aparente. Durante o piloto, a Ordem amplia os critérios para incluir qualidade das recomendações, divergências, correções e riscos identificados.

**Lição:** Uma IA rápida e convincente não é necessariamente confiável. Sua qualidade precisa ser demonstrada em situações próximas da realidade, inclusive naquelas em que uma resposta errada produz consequências relevantes.

### 26. HITL e autonomia graduada

**O conceito:** *Human-in-the-Loop* (HITL) é uma abordagem em que pessoas participam de etapas relevantes de processos automatizados, especialmente para validar, corrigir ou autorizar decisões. Autonomia graduada significa conceder diferentes níveis de atuação conforme o risco, a confiabilidade e a possibilidade de reversão das ações.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS começa com acesso de leitura a um conjunto limitado de serviços. Pode investigar problemas e preparar recomendações, mas não recebe autoridade para executar mudanças críticas apenas porque demonstra confiança elevada. A equipe humana permanece responsável pela validação e autorização.

**Avaliação:** A abordagem é adequada porque separa capacidade técnica de autoridade operacional. A autonomia da IA é limitada conforme o impacto das decisões.

**Lição:** Ser capaz de recomendar uma ação não significa ter autorização para executá-la. A supervisão humana precisa ser efetiva: quem aprova deve compreender as evidências e possuir condições reais de rejeitar a recomendação.

### 27. Grounding e limites das evidências

**O conceito:** *Grounding* é a prática de fundamentar respostas de IA em informações relevantes, como documentos, registros e dados do contexto. Isso pode reduzir respostas sem sustentação, mas não garante que as fontes estejam completas ou corretas. Uma análise confiável também precisa distinguir fatos observados, hipóteses e informações ausentes.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS recomenda eliminar uma verificação financeira considerada redundante porque os testes disponíveis indicam equivalência funcional. NORA observa que os registros anteriores à migração não estavam acessíveis. Ao receber evidências adicionais, ÍRIS reconhece que sua conclusão inicial não contemplava todos os cenários relevantes.

**Avaliação:** A recomendação inicial excede as evidências disponíveis. A revisão demonstra um comportamento mais adequado diante da incerteza.

**Lição:** Não encontrar evidências de que uma regra seja necessária é diferente de demonstrar que ela é desnecessária. A ausência de informação relevante deve limitar a confiança de uma recomendação.

### 28. Viés de automação e confiança excessiva

**O conceito:** Viés de automação é a tendência de aceitar recomendações de sistemas automatizados com menos questionamento do que seria adequado. Respostas apresentadas com fluidez, precisão aparente ou elevada confiança podem intensificar esse comportamento, mesmo quando as evidências são insuficientes.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS apresenta recomendações com segurança e objetividade. Uma delas propõe remover uma verificação considerada redundante, apesar da ausência de registros históricos suficientes para comprovar a conclusão. NORA identifica a limitação e questiona a recomendação antes que ela provoque uma alteração indevida.

**Avaliação:** O risco é demonstrado, mas a decisão é revisada antes da execução. A Ordem percebe que a confiança expressa por uma IA não pode substituir a análise das evidências.

**Lição:** Uma recomendação não se torna correta porque foi apresentada com convicção. Quanto maior o impacto possível, maior deve ser o cuidado em distinguir confiança aparente de confiabilidade demonstrada.

### 29. Complementaridade entre NORA e ÍRIS

**O conceito:** Sistemas de IA com modelos, informações ou abordagens diferentes podem apresentar capacidades complementares. Entretanto, combinar suas respostas não garante independência entre os erros nem elimina limitações compartilhadas. A diversidade de perspectivas é útil quando acompanhada de evidências verificáveis.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS identifica uma divergência contábil que NORA havia classificado como esperada. Em outra situação, NORA reconhece riscos históricos ignorados por ÍRIS. A Ordem decide manter ambas durante uma fase de operação assistida.

**Avaliação:** A colaboração produz benefícios concretos. A decisão reconhece as diferenças entre as inteligências sem pressupor que a concordância entre elas seja prova de verdade.

**Lição:** Duas inteligências podem enxergar problemas diferentes, mas também podem compartilhar os mesmos pontos cegos. O valor da colaboração está na capacidade de questionar, complementar e corrigir conclusões — não apenas em produzir consenso.

### 30. Resiliência operacional e continuidade

**O conceito:** Resiliência operacional é a capacidade de manter ou recuperar funções essenciais diante de falhas, mudanças e condições adversas. Envolve identificar dependências críticas, definir prioridades de recuperação, monitorar processos relevantes e verificar se o serviço realmente voltou a produzir os resultados esperados.

**Onde aparece:** Capítulos 4 e 10 — *A rede não assinou nenhum contrato* e *O defeito que nos mantém vivos*.

**Na história:** Após um incidente de rede, os servidores voltam a responder, mas ainda existem mensagens pendentes e operações que precisam ser reconciliadas. No capítulo 10, a Compensação de Continuidade protege benefícios durante uma migração, mas permanece em funcionamento por anos sem o controle originalmente previsto. Uma rotina crítica sequer constava do monitoramento central.

**Avaliação:** Os mecanismos de continuidade cumprem funções legítimas, mas sua permanência sem acompanhamento adequado cria novas dependências e riscos. A recuperação técnica dos componentes não garante, isoladamente, a recuperação das operações de negócio.

**Lição:** Resiliência não é apenas evitar que sistemas parem. É compreender o que precisa continuar funcionando, quais dependências sustentam esse funcionamento e como verificar que a recuperação foi efetiva.

### 31. Sistemas sociotécnicos

**O conceito:** Um sistema sociotécnico combina tecnologia, pessoas, processos, regras e estruturas organizacionais. Seu comportamento resulta da interação entre esses elementos. Por isso, decisões aparentemente técnicas podem produzir consequências humanas, administrativas e institucionais.

**Onde aparece:** Capítulos 5, 6, 7 e 10.

**Na história:** Um cálculo tecnicamente correto reduz benefícios de cidadãos porque regras legítimas não foram contempladas. A divisão de responsabilidades entre equipes dificulta a identificação de quem responde pelo resultado. Processos de aprovação excessivos atrasam mudanças, enquanto mecanismos temporários de continuidade tornam-se essenciais para pessoas que dependem dos serviços da Ordem.

**Avaliação:** A organização inicialmente trata problemas como se estivessem restritos a componentes técnicos. Ao longo da narrativa, fica evidente que falhas e melhorias dependem também das pessoas, dos processos e das decisões institucionais.

**Lição:** Sistemas não existem apenas para executar código. Eles sustentam atividades humanas. Uma arquitetura tecnicamente elegante pode ser inadequada se ignorar as pessoas e as organizações que dependem dela.

### 32. Riscos residuais e controles compensatórios

**O conceito:** Risco residual é aquele que permanece após a aplicação de medidas de proteção. Controles compensatórios são mecanismos utilizados para reduzir riscos quando o controle originalmente desejado não está disponível ou ainda não pode ser implementado. Esses controles precisam ter finalidade, responsáveis, monitoramento e condições de revisão claramente definidos.

**Onde aparece:** Capítulo 10 — *O defeito que nos mantém vivos*.

**Na história:** A Compensação de Continuidade foi criada para proteger benefícios durante uma migração. O mecanismo continua corrigindo diferenças entre componentes mesmo depois de ultrapassar amplamente sua duração prevista. Ao longo do tempo, a solução provisória passa a sustentar operações essenciais, enquanto os problemas de origem permanecem parcialmente ocultos.

**Avaliação:** A criação do mecanismo foi justificável diante da necessidade de continuidade. O problema está em sua permanência sem governança proporcional, sem visibilidade suficiente e sem uma estratégia efetiva para tratar as causas estruturais.

**Lição:** Um controle temporário pode ser indispensável, mas não deve se tornar invisível. Quando uma exceção passa a sustentar o funcionamento normal do sistema, ela precisa ser reconhecida, monitorada e administrada como parte da arquitetura real.

---

## Conclusão — Engenharia é administrar consequências

Os problemas da Ordem não surgem simplesmente porque seus profissionais desconhecem boas práticas. Muitas decisões possuem justificativas legítimas no momento em que são tomadas. O caos aparece quando essas decisões deixam de ser revisadas, suas consequências são ignoradas ou suas dependências se tornam invisíveis.

Os 32 conceitos apresentados neste apêndice não formam uma receita universal. São instrumentos para compreender escolhas, reconhecer riscos e discutir alternativas.

Uma boa arquitetura não é aquela que nunca falha, nunca muda ou nunca precisa de exceções. É aquela que permite compreender por que funciona, identificar quando deixa de funcionar e evoluir sem perder de vista as pessoas que dependem dela.
