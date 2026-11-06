# Apêndice técnico — Engenharia por trás do caos

> **Bloco III — Qualidade e evolução de sistemas**
>
> **STATUS: APROVADO PELO AUTOR.** Complemento independente; não altera a narrativa.

### 13. Verificação, validação e requisitos

**O conceito:** Verificação avalia se um sistema foi construído conforme os requisitos estabelecidos. Validação verifica se ele atende às necessidades reais e ao uso pretendido. A engenharia de requisitos conecta essas duas atividades: descobrir regras, identificar exceções e definir critérios de aceitação que permitam verificar os resultados esperados.

**Onde aparece:** Capítulos 5 e 6 — *A falha foi um sucesso* e *O organograma também compila*.

**Na história:** A Ordem implanta um novo motor de cálculo de benefícios. Os testes automatizados passam e o algoritmo executa corretamente a especificação. Entretanto, aproximadamente 4.300 cidadãos recebem valores menores porque determinadas regras legítimas não haviam sido consideradas. Posteriormente, a equipe propõe um simulador para avaliar os efeitos de alterações antes de publicá-las.

**Avaliação:** A verificação técnica foi bem-sucedida, mas a validação do domínio foi insuficiente. O sistema cumpriu os requisitos documentados, mas esses requisitos não representavam integralmente a realidade.

**Lição:** Um sistema pode estar perfeitamente de acordo com a especificação e continuar errado. Aprovar requisitos não garante que eles estejam completos; é necessário confrontá-los com o problema real.

### 14. Conhecimento tácito e institucional

**O conceito:** Conhecimento tácito é aquele adquirido pela experiência e que nem sempre está registrado em documentos. Conhecimento institucional reúne decisões, práticas e interpretações acumuladas ao longo do tempo. Ambos são importantes para compreender sistemas que sobreviveram às equipes responsáveis por sua criação.

**Onde aparece:** Capítulos 5 e 8.

**Na história:** Parte das regras de benefícios permanece na experiência dos funcionários e em decisões administrativas antigas. No capítulo 8, Eduardo explica a origem de uma dupla validação aparentemente redundante, criada para proteger registros históricos após uma migração.

**Avaliação:** A Ordem depende de conhecimentos que não foram suficientemente documentados ou compartilhados. A investigação do legado recupera informações essenciais para evitar novas falhas.

**Lição:** Entender o que um sistema faz não é o mesmo que entender por que ele faz aquilo. Antes de remover uma regra aparentemente absurda, convém descobrir qual desastre ela foi criada para impedir.

### 15. Testes de caracterização

**O conceito:** Testes de caracterização registram o comportamento observado de um sistema, especialmente quando suas regras são pouco conhecidas. São úteis para detectar mudanças inesperadas durante uma modernização, mas não comprovam que o comportamento original esteja correto.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** Uma rotina automatizada remove uma verificação considerada duplicada. Os testes existentes passam, mas a alteração permite um pagamento indevido. A equipe percebe que precisa compreender os comportamentos históricos, incluindo identificadores reutilizados e exceções cadastrais, antes de substituí-los.

**Avaliação:** A cobertura inicial não protegia comportamentos importantes do legado. A adoção de testes de caracterização reduz o risco de eliminar regras desconhecidas.

**Lição:** Antes de modificar um sistema que ninguém compreende completamente, é prudente registrar como ele se comporta. Isso não significa preservar todos os defeitos, mas distinguir defeitos de proteções legítimas.

### 16. DDD e contextos delimitados

**O conceito:** DDD — *Domain-Driven Design* (Projeto Orientado ao Domínio) — é uma abordagem que coloca o domínio de negócio no centro da modelagem do software. Um de seus conceitos fundamentais é o *Bounded Context* (contexto delimitado): a fronteira dentro da qual um modelo possui significado consistente.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** A entidade PessoaUnificada tenta representar informações de diferentes domínios em um único modelo. Com o crescimento da Ordem, cadastro, identidade e elegibilidade passam a atribuir significados distintos a informações aparentemente equivalentes. A equipe propõe modelos específicos e contratos explícitos entre esses contextos.

**Avaliação:** O modelo compartilhado tornou-se excessivamente abrangente. A separação por contextos permite representar as regras de cada domínio sem exigir uma entidade universal.

**Lição:** Compartilhar informações não obriga todos os sistemas a compartilhar o mesmo modelo. Uma pessoa pode ser representada de maneiras diferentes conforme a responsabilidade de cada contexto.

### 17. ACL — Anti-Corruption Layer (Camada Anticorrupção)

**O conceito:** ACL é um padrão de integração associado ao DDD que protege um modelo de domínio contra estruturas, regras e conceitos de outro sistema. Essa camada traduz informações e operações entre modelos, evitando que limitações externas contaminem a arquitetura interna.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** A equipe decide preservar temporariamente o motor antigo e estabelecer uma fronteira explícita entre ele e os novos modelos. As integrações deixam de reproduzir diretamente as estruturas históricas e passam a utilizar contratos específicos.

**Avaliação:** A estratégia é adequada para modernizar um sistema sem exigir sua substituição imediata. A camada de adaptação reduz o acoplamento entre o legado e as novas capacidades.

**Lição:** Integrar um sistema antigo não significa herdar todos os seus problemas. Uma fronteira bem definida permite conviver com o legado sem transformá-lo no modelo obrigatório do futuro.

### 18. Strangler Fig e modernização incremental

**O conceito:** O *Strangler Fig Pattern* é uma estratégia de modernização na qual funcionalidades de um sistema legado são substituídas gradualmente. Durante a transição, versões antigas e novas podem coexistir. A execução paralela permite comparar resultados antes de transferir a responsabilidade operacional.

**Onde aparece:** Capítulo 8 — *Ninguém sabe por que isso funciona*.

**Na história:** Em vez de reescrever todo o motor de benefícios, a equipe seleciona um programa com regras relativamente estáveis. Implementa o novo cálculo e o executa em paralelo ao antigo, sem alterar pagamentos reais. A comparação revela uma divergência que acaba expondo uma regra histórica legítima, ausente da nova especificação.

**Avaliação:** A abordagem reduz o risco de uma substituição completa e permite aprender com as diferenças encontradas. A execução paralela oferece evidências antes da migração efetiva.

**Lição:** Modernizar não exige desligar o passado de uma vez. Substituir capacidades progressivamente permite descobrir o que o sistema antigo realmente fazia — inclusive aquilo que ninguém havia documentado.

### 19. Indicadores técnicos e resultados de negócio

**O conceito:** Indicadores técnicos medem características como disponibilidade, latência, erros e desempenho. Indicadores de resultado avaliam se o sistema efetivamente atende às necessidades de usuários e da organização. Ambos são necessários, mas respondem a perguntas diferentes.

**Onde aparece:** Capítulos 4, 5 e 6.

**Na história:** A Ordem apresenta serviços disponíveis, testes bem-sucedidos e painéis com indicadores verdes, enquanto cidadãos enfrentam operações incompletas e benefícios calculados incorretamente. A proposta do simulador busca tornar visíveis as consequências das mudanças antes de sua implantação.

**Avaliação:** A organização inicialmente confunde funcionamento técnico com sucesso do produto. A análise dos impactos reais amplia sua definição de qualidade.

**Lição:** Um sistema pode estar disponível, rápido e sem erros registrados — e ainda assim prejudicar seus usuários. A qualidade da engenharia também precisa ser medida pelas consequências do que foi construído.
