# Lei de Conway, governança e autonomia — Quando o organograma vira arquitetura

*As equipes foram divididas para reduzir a complexidade. Agora precisam de cinco reuniões para alterar uma única funcionalidade.*

A arquitetura de um sistema não é determinada apenas por tecnologias, padrões e decisões de engenharia.

Ela também é influenciada pela maneira como as pessoas trabalham, compartilham informações, distribuem responsabilidades e tomam decisões.

Essa relação aparece na **Lei de Conway**, um princípio que ajuda a compreender por que problemas organizacionais frequentemente se manifestam como problemas técnicos.

A governança e a autonomia das equipes fazem parte desse contexto: podem facilitar a colaboração e a evolução dos sistemas ou criar dependências e obstáculos adicionais.

## 1. Lei de Conway — A organização aparece no software

A **Lei de Conway (*Conway's Law*)**, formulada por Melvin Conway em 1968, descreve a tendência de sistemas refletirem as estruturas de comunicação das organizações que os desenvolvem.

Uma organização dividida em departamentos com pouca comunicação pode produzir sistemas com fronteiras semelhantes, mesmo quando essa separação não corresponde às necessidades do negócio.

Por outro lado, equipes que colaboram intensamente podem desenvolver componentes mais integrados.

A Lei de Conway não é uma regra determinística. É uma observação sobre a influência das estruturas sociais nas decisões técnicas.

**Cuidado:** reorganizar equipes não garante automaticamente uma arquitetura melhor. É necessário considerar também as responsabilidades, os processos e os objetivos compartilhados.

## 2. Sistemas sociotécnicos — Pessoas e tecnologia não são independentes

Um **sistema sociotécnico (*sociotechnical system*)** envolve a interação entre pessoas, processos, organizações e tecnologias.

Na engenharia de software, isso significa reconhecer que decisões técnicas dependem de fatores humanos e organizacionais.

Um serviço pode apresentar uma interface bem definida, mas sua evolução continuar dependendo de aprovações, reuniões e negociações entre diferentes áreas.

Da mesma forma, duas equipes podem utilizar tecnologias distintas e trabalhar de maneira eficiente quando suas responsabilidades são claras e seus mecanismos de colaboração são adequados.

**Cuidado:** problemas recorrentes de integração nem sempre são resolvidos com novas ferramentas ou padrões arquiteturais. Às vezes, a dificuldade está na distribuição de responsabilidades e na comunicação.

## 3. Governança — Orientar decisões sem controlar cada detalhe

A **governança técnica (*technical governance*)** estabelece princípios, responsabilidades e mecanismos para orientar decisões relacionadas à tecnologia.

Seu objetivo é manter coerência, reduzir riscos e permitir que diferentes equipes trabalhem de maneira compatível.

Ela pode incluir padrões de segurança, contratos de integração, critérios de qualidade, diretrizes arquiteturais e processos para registrar decisões relevantes.

Entretanto, governança não precisa significar centralização de todas as escolhas.

Uma abordagem eficaz diferencia decisões que exigem alinhamento organizacional daquelas que podem ser tomadas pelas próprias equipes.

Quando toda decisão depende de autorização externa, a governança deixa de orientar as equipes e passa a limitar sua capacidade de agir. O controle precisa ser proporcional ao risco da decisão.

## 4. Autonomia com limites claros

A **autonomia (*autonomy*)** permite que equipes tomem decisões dentro de suas responsabilidades, sem depender continuamente de outras áreas.

Ela favorece velocidade, aprendizado e capacidade de resposta.

Mas autonomia não significa ausência de padrões ou liberdade irrestrita.

Uma organização pode definir requisitos obrigatórios de segurança, interoperabilidade e qualidade, permitindo que cada equipe escolha como atendê-los.

Essa abordagem é frequentemente resumida pela expressão **“guardrails, not gates”** — estabelecer limites de proteção, em vez de transformar cada decisão em uma autorização obrigatória.

O equilíbrio está em definir claramente o que precisa ser comum e o que pode variar conforme o contexto.

**Cuidado:** padronizar todas as soluções pode ignorar diferenças legítimas entre sistemas. Por outro lado, permitir decisões completamente independentes pode criar incompatibilidades e custos desnecessários.

## 5. Responsabilidade sem autoridade é uma contradição

Um problema organizacional frequente ocorre quando uma equipe é responsabilizada pelos resultados de um sistema, mas não possui autoridade suficiente para tomar as decisões necessárias.

Ela pode responder por disponibilidade, prazo e qualidade, enquanto mudanças relevantes dependem de aprovações externas ou de equipes que possuem prioridades diferentes.

Essa separação dificulta a identificação de responsáveis e reduz a capacidade de reação diante de problemas.

Por isso, a distribuição de responsabilidades precisa considerar também a autoridade para decidir, os recursos disponíveis e os mecanismos de colaboração.

**Cuidado:** delegar responsabilidade sem oferecer condições para exercê-la não produz autonomia. Produz dependência acompanhada de cobrança.

## 6. Alinhamento não é sinônimo de consenso permanente

Organizações precisam de mecanismos para compartilhar decisões, resolver conflitos e manter objetivos comuns.

Entretanto, exigir consenso de todos os envolvidos para cada mudança pode tornar a evolução excessivamente lenta.

Uma alternativa é estabelecer critérios claros para identificar decisões que exigem participação mais ampla, como alterações de contratos compartilhados, riscos relevantes ou mudanças difíceis de reverter.

Decisões locais, reversíveis e de baixo impacto podem permanecer sob responsabilidade das equipes.

Os registros de decisões arquiteturais (ADRs), apresentados no Tema 06, permitem preservar decisões relevantes sem transformar cada escolha em uma autorização obrigatória.

**Cuidado:** a quantidade de pessoas envolvidas em uma decisão não determina sua qualidade. Participação deve acrescentar conhecimento e responsabilidade, não apenas etapas ao processo.

## 7. A arquitetura também é consequência da organização

Quando uma empresa enfrenta dificuldades recorrentes de integração, mudanças lentas ou responsabilidades fragmentadas, pode ser necessário examinar sua estrutura de colaboração antes de propor uma transformação tecnológica.

Dividir um sistema em microsserviços, por exemplo, não resolve automaticamente dependências entre equipes.

Da mesma forma, centralizar decisões arquiteturais pode produzir uniformidade, mas também reduzir a capacidade de adaptação.

A organização precisa equilibrar alinhamento e autonomia de acordo com seus objetivos, riscos e contexto operacional.

**A lição central:** a arquitetura de software reflete não apenas como os componentes foram construídos, mas também como as pessoas conseguem trabalhar juntas. Governança eficaz define princípios e limites compartilhados, enquanto preserva a autonomia necessária para que as equipes encontrem boas soluções.
