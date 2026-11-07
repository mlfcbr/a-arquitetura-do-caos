# Verificação, validação e resultados de negócio — Quando tudo funciona, menos a solução

*O sistema passou em todos os testes. O problema é que ninguém testou se ele deveria fazer aquilo.*

Um projeto pode cumprir seus requisitos documentados, executar corretamente suas funcionalidades e ser implantado sem incidentes técnicos, mas ainda assim fracassar naquilo que deveria resolver.

Isso acontece porque **construir corretamente uma solução** e **construir a solução correta** são desafios diferentes.

Na engenharia de software, essa distinção aparece nos conceitos de verificação e validação. Ela também revela por que indicadores técnicos, isoladamente, não são suficientes para avaliar o sucesso de um produto.

## 1. Verificação — Estamos construindo corretamente?

A **verificação (*verification*)** busca determinar se o produto atende aos requisitos, especificações e critérios definidos.

Ela procura responder:

**“Estamos construindo o produto corretamente?”**

Pode envolver revisões, análise estática, testes automatizados, testes de integração e outras atividades de avaliação.

Por exemplo, se uma regra determina que determinada solicitação deve ser bloqueada após um prazo específico, a verificação avalia se o sistema implementa esse comportamento conforme a especificação.

O problema é que uma especificação pode estar errada, incompleta ou baseada em premissas inadequadas.

**Cuidado:** passar em todos os testes previstos não demonstra que todos os comportamentos importantes foram considerados. Demonstra apenas o que foi efetivamente avaliado, dentro das condições utilizadas.

## 2. Validação — Estamos construindo a coisa certa?

A **validação (*validation*)** busca determinar se o produto atende às necessidades reais de seus usuários e ao uso pretendido.

Ela procura responder:

**“Estamos construindo o produto certo?”**

Enquanto a verificação compara o sistema com aquilo que foi especificado, a validação considera se a solução é adequada ao problema que motivou sua criação.

Isso pode envolver testes com usuários, experimentos, protótipos, acompanhamento operacional e análise dos resultados obtidos.

Uma funcionalidade pode executar exatamente a regra solicitada e, ainda assim, prejudicar pessoas porque a regra não considerou exceções legítimas.

**Cuidado:** validação não deve acontecer apenas no encerramento do projeto. Hipóteses importantes precisam ser examinadas ao longo do desenvolvimento, antes que decisões equivocadas se tornem difíceis de corrigir.

## 3. Requisitos corretos não são necessariamente requisitos adequados

Um requisito descreve uma condição ou capacidade que o sistema deve atender. Mas sua existência em um documento não garante que represente corretamente a necessidade do negócio.

Requisitos podem surgir de interpretações equivocadas, processos antigos, pressões de prazo ou decisões tomadas sem compreender seus efeitos.

Também podem entrar em conflito entre si: reduzir fraudes pode exigir controles adicionais, enquanto facilitar o atendimento pode demandar menos obstáculos para usuários legítimos.

Por isso, requisitos relevantes precisam explicitar suas premissas, restrições, exceções e consequências.

**Cuidado:** transformar uma regra de negócio em código não transfere automaticamente sua responsabilidade para a equipe técnica. As consequências precisam ser avaliadas por quem define, implementa e opera a solução.

## 4. Entregas, resultados e impactos

Um erro frequente é confundir a conclusão de uma entrega com a obtenção de um benefício.

Esses conceitos representam dimensões diferentes:

| Dimensão | O que demonstra |
|---|---|
| **Entrega (*output*)** | O que foi produzido ou disponibilizado |
| **Resultado (*outcome*)** | Que mudança ocorreu no comportamento ou na experiência dos usuários |
| **Impacto (*impact*)** | Que consequência mais ampla foi produzida para o negócio ou para a sociedade |

Uma equipe pode entregar uma funcionalidade dentro do prazo e sem defeitos conhecidos. Isso é relevante, mas não comprova que a funcionalidade melhorou a situação que pretendia resolver.

O resultado precisa ser observado no uso real.

**Cuidado:** métricas escolhidas apenas porque são fáceis de medir podem ocultar efeitos negativos. A quantidade de solicitações processadas, por exemplo, não demonstra sozinha se as decisões foram corretas.

## 5. Quando os indicadores contam apenas metade da história

Indicadores de disponibilidade, desempenho e quantidade de entregas ajudam a acompanhar a qualidade técnica.

Entretanto, precisam ser complementados por medidas relacionadas à experiência e aos resultados do negócio.

Um processo automatizado pode reduzir custos operacionais e, simultaneamente, aumentar o número de usuários prejudicados por decisões incorretas.

Da mesma forma, uma mudança pode melhorar o tempo médio de atendimento, mas piorar drasticamente os casos mais complexos.

É importante observar distribuições, exceções e grupos afetados, não apenas médias e totais agregados.

Uma métrica deve ser interpretada à luz do objetivo que pretende representar. Melhorar o indicador não é suficiente quando o resultado real piora.

## 6. Qualidade é uma responsabilidade compartilhada

A verificação exige disciplina técnica. A validação exige conhecimento do domínio, compreensão das necessidades dos usuários e disposição para questionar premissas.

Nenhuma dessas atividades pertence exclusivamente a uma única função ou departamento.

Equipes de produto, engenharia, operação e especialistas do negócio precisam compartilhar critérios de sucesso e compreender os efeitos das decisões.

Isso também significa aceitar que uma implementação tecnicamente correta pode precisar ser alterada quando seus resultados demonstram que a solução não atende às necessidades reais.

**A lição central:** qualidade não é apenas conformidade com uma especificação. É a combinação entre construir corretamente, resolver o problema adequado e observar as consequências produzidas no mundo real.
