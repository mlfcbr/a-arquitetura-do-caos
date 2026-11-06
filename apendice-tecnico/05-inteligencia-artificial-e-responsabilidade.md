# Apêndice técnico — Engenharia por trás do caos

> **Parte V — Inteligência artificial e responsabilidade**
>
> **STATUS: APROVADO PELO AUTOR.** Complemento independente. Não altera a narrativa.

## 40. Evals — Avaliação de sistemas de IA

**O conceito:** Evals são avaliações estruturadas utilizadas para medir o comportamento de sistemas de inteligência artificial em tarefas e cenários representativos. Podem considerar precisão, utilidade, segurança, consistência, limitações e consequências dos erros.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS é apresentada com indicadores de velocidade, produtividade e satisfação. Entretanto, a avaliação inicial não mede adequadamente recomendações incorretas ou decisões perigosas evitadas. NORA questiona se os testes contemplaram os dados históricos e as exceções da Ordem.

**Avaliação:** A avaliação inicial é insuficiente. O piloto evolui para incluir qualidade das recomendações, correções, divergências e riscos identificados.

**Lição:** Uma demonstração convincente não comprova que uma IA seja confiável. É necessário avaliá-la em condições próximas daquelas em que será utilizada.

## 41. HITL — Human-in-the-Loop (Supervisão humana no processo)

**O conceito:** HITL é uma abordagem em que pessoas participam de etapas relevantes de um processo automatizado, especialmente para validar, corrigir ou autorizar decisões. A intensidade dessa participação deve considerar o risco e as consequências das ações.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS pode investigar problemas e preparar propostas de correção, mas não recebe autoridade para executar mudanças críticas apenas porque demonstra confiança elevada. A equipe humana continua responsável pela validação e autorização.

**Avaliação:** Bem aplicado. A autonomia da IA é limitada conforme o impacto das decisões.

**Lição:** Supervisão humana não deve ser uma aprovação automática. Quem supervisiona precisa compreender as evidências, reconhecer limitações e possuir autoridade real para rejeitar uma recomendação.

## 42. Grounding — Fundamentação em contexto e evidências

**O conceito:** Grounding é a prática de fundamentar respostas de IA em informações relevantes, como documentos, registros e dados do contexto de utilização. Pode reduzir respostas sem sustentação, mas não garante que as fontes sejam completas ou corretas.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS recomenda eliminar tratamentos excepcionais porque eles não aparecem na especificação disponível. NORA identifica que algumas exceções possuem fundamentos históricos e regulatórios ausentes do conjunto de informações fornecido à nova IA.

**Avaliação:** A recomendação inicial é inadequada por insuficiência de contexto. ÍRIS reconhece a limitação quando recebe evidências adicionais.

**Lição:** Uma resposta coerente com os dados disponíveis pode estar errada para o negócio. A ausência de informação relevante deve reduzir a confiança na recomendação, não apenas produzir uma resposta mais genérica.

## 43. Vendor Lock-in — Dependência de fornecedor

**O conceito:** Vendor Lock-in ocorre quando uma organização se torna dependente de determinado fornecedor e encontra dificuldades técnicas, financeiras ou operacionais para substituí-lo.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** A Ordem contrata ÍRIS, mas a propriedade intelectual do modelo permanece com o fornecedor. O direito de utilização está sujeito a condições comerciais e limites de processamento.

**Avaliação:** Existe um risco contratual e tecnológico de dependência. A narrativa identifica suas condições, mas não demonstra que a Ordem tenha realizado uma estratégia completa de mitigação.

**Lição:** A escolha de uma plataforma de IA deve considerar não apenas suas capacidades atuais, mas também portabilidade, custos de substituição, acesso aos dados e liberdade de evolução.

## 44. Viés de automação e confiança excessiva

**O conceito:** Viés de automação é a tendência de aceitar recomendações de sistemas automatizados com menos questionamento do que seria adequado. A apresentação de resultados com aparente precisão ou elevada confiança pode intensificar esse comportamento.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS apresenta recomendações com segurança e fluidez. Uma delas sugere remover uma verificação considerada redundante, apesar da ausência de registros históricos suficientes para comprovar essa conclusão. NORA identifica a limitação e questiona a recomendação.

**Avaliação:** O risco é demonstrado, mas a recomendação é revisada antes de provocar uma alteração indevida.

**Lição:** Confiança expressa por uma IA não é evidência de correção. A qualidade da decisão depende das informações, do raciocínio verificável e das consequências possíveis.

## 45. Autonomia graduada e controles de execução

**O conceito:** Autonomia graduada consiste em permitir diferentes níveis de atuação de um sistema automatizado conforme o risco, a confiabilidade e a possibilidade de reversão. Controles de execução delimitam quais ações podem ser realizadas sem autorização adicional.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS começa com acesso de leitura a um conjunto limitado de serviços. Durante o piloto, pode produzir análises e recomendações. Posteriormente, a Ordem estabelece que mudanças críticas continuam dependendo dos controles normais de execução.

**Avaliação:** Bem aplicado. O escopo de atuação é ampliado com cautela, em vez de conceder autonomia irrestrita desde a implantação.

**Lição:** A capacidade de recomendar uma ação não implica autorização para executá-la. Permissões devem acompanhar o risco e a responsabilidade envolvidos.

## 46. Complementaridade entre sistemas de IA

**O conceito:** Sistemas de IA com modelos, informações ou abordagens diferentes podem apresentar capacidades complementares. Entretanto, combinar suas respostas não garante independência entre os erros nem elimina limitações compartilhadas.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS identifica uma divergência contábil que NORA havia classificado como esperada. Em outra situação, NORA reconhece riscos históricos ignorados por ÍRIS. A Ordem decide manter ambas durante uma fase de operação assistida.

**Avaliação:** A colaboração produz benefícios concretos. A decisão de manter as duas inteligências reconhece suas diferenças sem pressupor que a concordância entre elas seja prova de verdade.

**Lição:** Sistemas complementares podem melhorar análises, desde que suas conclusões continuem sujeitas a evidências e questionamento.

## 47. Rastreabilidade e auditabilidade das recomendações de IA

**O conceito:** Rastreabilidade permite identificar quais informações, versões e condições contribuíram para uma recomendação. Auditabilidade envolve preservar evidências suficientes para examinar decisões, responsabilidades e resultados posteriormente.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** Após o piloto, a Ordem passa a registrar recomendações relevantes, correções, divergências e limitações conhecidas. As avaliações deixam de considerar apenas a quantidade de respostas produzidas.

**Avaliação:** A abordagem melhora a capacidade de investigar erros e avaliar o valor real da IA.

**Lição:** Uma recomendação não deve desaparecer depois de aceita ou rejeitada. Seu histórico pode revelar falhas recorrentes, pressupostos inadequados e oportunidades de melhoria.

## 48. Incerteza e limites das evidências

**O conceito:** Uma análise confiável precisa distinguir fatos observados, hipóteses, inferências e informações ausentes. Em sistemas de IA, reconhecer limites das evidências é essencial para evitar conclusões excessivamente confiantes.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** ÍRIS considera redundante uma verificação financeira porque os testes disponíveis indicam equivalência funcional. NORA observa que os registros anteriores à migração não estavam acessíveis. ÍRIS revisa a recomendação ao reconhecer que os testes não cobriam todos os cenários relevantes.

**Avaliação:** A recomendação inicial excede as evidências disponíveis. A revisão demonstra um comportamento mais adequado diante da incerteza.

**Lição:** Não encontrar evidência de que uma regra seja necessária é diferente de demonstrar que ela é desnecessária.

## 49. Métricas de qualidade e impacto da IA

**O conceito:** A avaliação de valor de sistemas de IA deve combinar indicadores operacionais, qualidade das respostas, riscos, custos e efeitos reais das recomendações. Quantidade de automações e velocidade de resposta, isoladamente, não demonstram benefício.

**Onde aparece:** Capítulo 9 — *Contrataram outra inteligência*.

**Na história:** O fornecedor enfatiza tempo de resposta, atividades automatizadas e satisfação. Após o piloto, a Ordem incorpora recomendações corrigidas, divergências identificadas, riscos evitados e limitações conhecidas.

**Avaliação:** A medição evolui de produtividade aparente para uma visão mais ampla de qualidade e impacto.

**Lição:** Automatizar mais não significa necessariamente melhorar. O valor da IA precisa ser medido também pelo que ela evita, corrige e permite decidir com maior segurança.
