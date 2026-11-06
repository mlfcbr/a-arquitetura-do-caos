# Apêndice técnico — Engenharia por trás do caos

> **Parte III — Qualidade e evolução de sistemas**
>
> **STATUS: APROVADO PELO AUTOR.** Complemento independente. Não altera a narrativa.

## 20. Verificação e validação (V&V)

**O conceito:** Verificação avalia se o sistema foi construído conforme os requisitos e especificações definidos. Validação avalia se o sistema atende às necessidades reais e ao uso pretendido. Ambas são necessárias para avaliar a qualidade de uma solução.

**Onde aparece:** Capítulo 5 — *A falha foi um sucesso*.

**Na história:** A Ordem implanta um novo motor de cálculo de benefícios. Os testes automatizados passam, os indicadores permanecem normais e o algoritmo executa corretamente a especificação. Entretanto, aproximadamente 4.300 cidadãos recebem valores menores porque a especificação não contemplava todas as regras legítimas.

**Avaliação:** A verificação técnica foi bem-sucedida, mas a validação das necessidades e regras de negócio foi insuficiente.

**Lição:** Um sistema pode estar tecnicamente correto e, ainda assim, produzir o resultado errado. Testar o código não substitui validar o problema que ele deveria resolver.

## 21. Engenharia de requisitos e critérios de aceitação

**O conceito:** Engenharia de requisitos envolve descobrir, analisar, especificar, validar e administrar as necessidades e restrições de um sistema. Critérios de aceitação tornam verificáveis as condições que uma funcionalidade precisa satisfazer.

**Onde aparece:** Capítulos 5 e 6 — *A falha foi um sucesso* e *O organograma também compila*.

**Na história:** O novo cálculo de benefícios foi implementado conforme requisitos formalmente aprovados, mas regras históricas importantes não foram incorporadas. Posteriormente, a proposta de um simulador permite comparar os efeitos de alterações antes de publicá-las, envolvendo usuários e responsáveis pelas regras.

**Avaliação:** O levantamento inicial foi insuficiente. A criação de mecanismos de simulação e validação representa uma melhoria no processo de definição e aceitação das mudanças.

**Lição:** Requisitos aprovados não são necessariamente requisitos completos. É preciso validar também as hipóteses, exceções e consequências das decisões.

## 22. Conhecimento tácito e conhecimento institucional

**O conceito:** Conhecimento tácito é aquele adquirido pela experiência e difícil de transmitir integralmente por documentos ou procedimentos. Conhecimento institucional inclui práticas, decisões e interpretações acumuladas por uma organização.

**Onde aparece:** Capítulos 5 e 8.

**Na história:** Parte das regras de benefícios existe na experiência de funcionários e em decisões administrativas antigas. No capítulo 8, Eduardo explica por que uma dupla validação aparentemente redundante foi criada para proteger registros históricos após uma migração.

**Avaliação:** A Ordem depende de conhecimentos que não foram suficientemente documentados ou compartilhados. A investigação do legado recupera parte desse contexto.

**Lição:** Documentar código não equivale a documentar suas razões. Sistemas críticos precisam preservar o conhecimento sobre por que determinados comportamentos existem.

## 23. Testes de caracterização

**O conceito:** Testes de caracterização registram o comportamento observado de um sistema, especialmente quando suas regras não são completamente conhecidas. Eles ajudam a identificar mudanças de comportamento, mas não demonstram, por si só, que o resultado original está correto.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** Uma rotina automatizada remove uma verificação aparentemente duplicada. Os testes existentes passam, mas a alteração permite um pagamento indevido. A equipe passa a construir testes que consideram cadastros históricos, identificadores reutilizados e exceções antes de substituir comportamentos antigos.

**Avaliação:** A ausência inicial desses testes contribuiu para a falha. Sua adoção posterior melhora a segurança da modernização.

**Lição:** Antes de modificar um comportamento desconhecido, é necessário compreendê-lo. Caracterizar não significa aceitar como correto tudo o que o legado faz.

## 24. DDD — Domain-Driven Design (Projeto Orientado ao Domínio)

**O conceito:** DDD é uma abordagem de desenvolvimento e modelagem que coloca o domínio de negócio no centro das decisões de software. Valoriza a colaboração com especialistas e a construção de modelos que representem adequadamente os conceitos e regras de cada contexto.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** A entidade PessoaUnificada tenta representar informações de diferentes domínios em um único modelo. Com o crescimento da Ordem, atributos e regras passam a ter significados conflitantes para cadastro, elegibilidade e outros serviços.

**Avaliação:** O modelo compartilhado tornou-se excessivamente abrangente. A equipe reconhece a necessidade de separar conceitos e responsabilidades de negócio.

**Lição:** Compartilhar dados não exige compartilhar integralmente o mesmo modelo. Um conceito pode assumir significados diferentes conforme o contexto.

## 25. Contextos delimitados (Bounded Contexts)

**O conceito:** Um contexto delimitado define a fronteira dentro da qual determinado modelo de domínio possui significado consistente. Sistemas podem se integrar entre contextos sem exigir que utilizem as mesmas representações internas.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** A equipe distingue informações de cadastro, identidade e elegibilidade. Em vez de manter uma entidade universal com centenas de atributos, propõe modelos específicos e contratos explícitos entre responsabilidades.

**Avaliação:** Bem aplicado na proposta de modernização. A definição das fronteiras reduz ambiguidades e dependências desnecessárias.

**Lição:** Um modelo não precisa representar todas as interpretações possíveis de uma pessoa, benefício ou transação. Precisa ser coerente dentro do contexto para o qual foi criado.

## 26. ACL — Anti-Corruption Layer (Camada Anticorrupção)

**O conceito:** ACL é um padrão de integração associado ao DDD que protege um modelo de domínio contra conceitos, estruturas e regras de outro sistema. Normalmente utiliza adaptações e traduções explícitas entre modelos.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** A equipe decide preservar temporariamente o motor antigo e criar uma fronteira entre ele e os novos modelos. As integrações passam a utilizar contratos explícitos, evitando que as estruturas históricas sejam reproduzidas diretamente nas novas capacidades.

**Avaliação:** Bem aplicada como estratégia de isolamento do legado.

**Lição:** Integrar um sistema antigo não significa permitir que suas limitações determinem a arquitetura de todos os sistemas novos.

## 27. Strangler Fig Pattern — Modernização incremental

**O conceito:** Strangler Fig Pattern é um padrão de modernização no qual capacidades de um sistema legado são gradualmente substituídas por novas implementações. Durante a transição, soluções antigas e novas podem coexistir até que a substituição seja segura.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** Em vez de reescrever todo o motor de benefícios, a equipe escolhe um programa com regras relativamente estáveis. Cria um modelo específico, executa o cálculo novo em paralelo ao antigo e investiga divergências antes de migrar o processamento real.

**Avaliação:** Bem aplicado. A estratégia reduz a exposição a falhas e permite aprender com as diferenças encontradas.

**Lição:** Modernizar gradualmente pode ser mais seguro do que substituir todo um sistema de uma vez, especialmente quando o comportamento do legado não é completamente conhecido.

## 28. Execução paralela e comparação de resultados

**O conceito:** Execução paralela, frequentemente chamada de *shadow testing* quando uma implementação nova recebe entradas reais sem produzir efeitos de negócio, permite comparar resultados entre versões antes de transferir a responsabilidade operacional.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** O cálculo novo é executado em paralelo ao motor antigo, sem alterar pagamentos. A comparação revela uma divergência que inicialmente parece um defeito, mas acaba expondo uma regra histórica legítima ausente da nova especificação.

**Avaliação:** Bem aplicada. A divergência é investigada antes da substituição definitiva.

**Lição:** Diferenças entre sistemas não devem ser corrigidas automaticamente em favor da versão nova. Elas podem revelar requisitos desconhecidos ou comportamentos incorretos em qualquer uma das implementações.

## 29. Indicadores técnicos e resultados de negócio

**O conceito:** Indicadores técnicos medem características como disponibilidade, latência, erros e desempenho. Indicadores de resultado avaliam se o sistema produz os efeitos esperados para usuários, organização e demais partes interessadas.

**Onde aparece:** Capítulos 4, 5 e 6.

**Na história:** A Ordem apresenta serviços disponíveis e testes bem-sucedidos, mas cidadãos enfrentam operações incompletas e benefícios calculados incorretamente. A proposta do simulador busca tornar visíveis as consequências de mudanças nas regras antes de sua implantação.

**Avaliação:** A organização inicialmente confunde sucesso técnico com sucesso do produto. Posteriormente, passa a considerar impactos reais nas decisões.

**Lição:** Medir a saúde da infraestrutura é necessário, mas insuficiente. O resultado final precisa fazer parte da definição de qualidade.

## 30. Documentação viva e rastreabilidade de decisões

**O conceito:** Documentação viva é mantida próxima das práticas e decisões reais de desenvolvimento, evoluindo junto com o sistema. Rastreabilidade permite relacionar requisitos, regras, decisões, implementações e evidências de validação.

**Onde aparece:** Capítulos 5, 7 e 8.

**Na história:** A Ordem encontra decisões históricas dispersas, regras sem justificativas acessíveis e documentação que não acompanhou a evolução do sistema. Ao investigar o legado, a equipe passa a registrar hipóteses, riscos, testes e decisões pendentes em documentos utilizados durante o próprio trabalho.

**Avaliação:** A documentação anterior era insuficiente. A abordagem posterior melhora a preservação do conhecimento e a capacidade de revisar decisões.

**Lição:** Documentação não deve existir apenas para satisfazer auditorias. Seu maior valor está em ajudar pessoas a compreender, operar e modificar o sistema com segurança.
