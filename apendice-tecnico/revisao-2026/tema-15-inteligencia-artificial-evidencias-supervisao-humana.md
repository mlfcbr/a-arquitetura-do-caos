# Inteligência artificial, evidências e supervisão humana — Quando a máquina tem certeza demais

*Uma inteligência artificial pode produzir uma resposta impecavelmente estruturada, acompanhada de uma explicação convincente. Nada disso garante que esteja certa.*

Sistemas de inteligência artificial podem analisar informações, identificar padrões, gerar conteúdo e apoiar decisões complexas.

Entretanto, sua capacidade de produzir respostas plausíveis não equivale à capacidade de demonstrar que essas respostas são verdadeiras, adequadas ou seguras.

Quando sistemas de IA influenciam decisões relevantes, três preocupações tornam-se fundamentais: **qualidade das evidências, avaliação sistemática e supervisão humana**.

O desafio não é apenas desenvolver modelos capazes de responder. É construir sistemas que permitam compreender, avaliar e controlar as consequências de suas respostas.

## 1. Respostas plausíveis não são necessariamente verdadeiras

Modelos de linguagem podem produzir afirmações incorretas com aparência de precisão.

Esse fenômeno é frequentemente chamado de **alucinação (*hallucination*)**: a geração de conteúdo que não corresponde adequadamente aos fatos, às fontes ou ao contexto solicitado.

Uma resposta pode apresentar datas, números, referências e explicações coerentes sem que essas informações tenham sido verificadas.

A confiança demonstrada pela linguagem não deve ser confundida com evidência de correção.

**Cuidado:** uma resposta detalhada não é necessariamente mais confiável que uma resposta curta. A qualidade depende de sua correspondência com os fatos e com o problema real.

## 2. Fundamentação em evidências — De onde veio essa conclusão?

A **fundamentação em evidências (*grounding*)** consiste em vincular respostas e decisões a informações relevantes e verificáveis.

Em aplicações de IA, isso pode envolver documentos, bases de dados, registros operacionais ou outras fontes autorizadas.

Uma abordagem comum é a **geração aumentada por recuperação (*Retrieval-Augmented Generation*, ou RAG)**, na qual informações externas são recuperadas e fornecidas ao modelo para apoiar a elaboração da resposta.

Essa técnica pode fornecer contexto relevante e referências às fontes consultadas, mas a qualidade da resposta continua dependendo da recuperação, da interpretação e da verificação das informações.

Entretanto, recuperar informações não garante que elas estejam corretas, atualizadas ou tenham sido interpretadas adequadamente.

**Cuidado:** citar uma fonte não significa que ela sustente a conclusão apresentada. A relação entre evidência e afirmação também precisa ser avaliada.

## 3. Avaliação de IA — Medir mais do que respostas convincentes

A **avaliação de sistemas de IA (*AI evaluation*, frequentemente abreviada como *evals*)** consiste em examinar seu desempenho diante de critérios e situações relevantes.

Essas avaliações podem considerar precisão factual, aderência às instruções, segurança, consistência, utilidade e capacidade de lidar com situações inesperadas.

Um conjunto de avaliações pode incluir casos conhecidos, situações de exceção, informações incompletas e tentativas de induzir comportamentos inadequados.

Também é importante avaliar o sistema completo, não apenas o modelo isolado. Ferramentas, dados recuperados, regras de negócio e integrações podem introduzir erros próprios.

**Cuidado:** obter bons resultados em testes previamente definidos não garante desempenho equivalente em produção. Mudanças nos dados, no comportamento dos usuários e no contexto podem alterar os resultados.

## 4. Automação não elimina responsabilidade

Quando uma IA recomenda uma ação, é necessário definir quem pode autorizá-la, executá-la, contestá-la e revertê-la.

Essa preocupação se torna especialmente importante em decisões que afetam direitos, recursos financeiros, acesso a serviços ou segurança das pessoas.

A **supervisão humana (*human oversight*)** envolve mecanismos para que pessoas possam acompanhar, avaliar e intervir no funcionamento de sistemas automatizados.

Ela pode incluir aprovação prévia de ações críticas, revisão de decisões, limites de atuação e procedimentos de contestação.

Entretanto, inserir uma pessoa no processo não garante automaticamente uma supervisão eficaz.

Se o responsável não possui informações suficientes, tempo adequado ou autoridade para discordar da máquina, sua participação pode se tornar apenas uma formalidade.

**Cuidado:** supervisão humana precisa representar capacidade real de intervenção, não apenas um botão de aprovação.

## 5. O risco da confiança excessiva

Pessoas podem atribuir credibilidade elevada a recomendações produzidas por sistemas automatizados, especialmente quando elas parecem consistentes ou são apresentadas com segurança.

Esse comportamento é conhecido como **viés de automação (*automation bias*)**: a tendência de aceitar ou privilegiar recomendações automatizadas mesmo quando existem motivos para questioná-las.

O problema pode ser agravado quando a IA apresenta conclusões sem evidências suficientes ou quando os usuários não compreendem suas limitações.

Por isso, sistemas que apoiam decisões importantes devem comunicar incertezas relevantes, permitir a consulta às evidências e facilitar a identificação de situações que exigem análise adicional.

**Cuidado:** apresentar uma pontuação de confiança não garante que ela corresponda à probabilidade real de acerto. Medidas desse tipo precisam ser interpretadas e, quando apropriado, calibradas e validadas.

## 6. Autonomia proporcional ao risco

Nem todas as aplicações de IA precisam do mesmo nível de controle.

Gerar um resumo preliminar possui consequências diferentes de bloquear uma conta, autorizar uma transferência financeira ou determinar a elegibilidade de uma pessoa para um serviço.

Quanto maiores os efeitos potenciais de uma decisão, maior tende a ser a necessidade de mecanismos de avaliação, rastreabilidade, autorização e reversão.

Uma arquitetura responsável deve considerar:

- **Impacto:** o que pode acontecer se a decisão estiver errada?
- **Reversibilidade:** é possível corrigir seus efeitos?
- **Evidências:** quais informações sustentam a conclusão?
- **Autoridade:** quem pode permitir ou impedir a ação?
- **Rastreabilidade:** será possível compreender posteriormente o que ocorreu?

Essas questões ajudam a definir limites adequados para diferentes níveis de automação.

**Cuidado:** aumentar a autonomia de um sistema sem aumentar proporcionalmente os mecanismos de controle pode ampliar a velocidade e a escala de seus erros.

## 7. Inteligência não é sinônimo de julgamento adequado

Um sistema pode identificar padrões complexos e produzir recomendações tecnicamente sofisticadas sem compreender integralmente o contexto social, institucional ou humano em que elas serão aplicadas.

Mesmo uma conclusão baseada em dados corretos pode ser inadequada quando ignora consequências relevantes, restrições legítimas ou objetivos conflitantes.

Por isso, a qualidade de uma decisão não depende apenas da capacidade de processamento ou da precisão de uma previsão.

Depende também dos critérios utilizados, das informações disponíveis, dos limites estabelecidos e da responsabilidade por seus efeitos.

**A lição central:** inteligência artificial confiável não é aquela que parece ter resposta para tudo. É aquela cujas conclusões podem ser avaliadas, cujas limitações são reconhecidas e cujas ações permanecem sujeitas a controles proporcionais às suas consequências.
