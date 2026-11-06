# Apêndice técnico — Engenharia por trás do caos

## Bloco I — Princípios e decisões arquiteturais

> **Versão condensada para revisão editorial.** Complemento independente; não altera nenhum capítulo, prólogo, epílogo ou seção narrativa.

### 1. Complexidade essencial e complexidade acidental

**O conceito:** A complexidade essencial nasce do problema que o software precisa resolver; a acidental é acrescentada pelas escolhas de implementação, integração e organização da solução.

**Onde aparece:** Capítulo 1 — *Era só um botão*.

**Na história:** Identificar corretamente quem tem direito ao atendimento prioritário exige regras e exceções reais. Já a proliferação de cadastros, coletores e sincronizações introduz dificuldades que não fazem parte dessa necessidade.

**Avaliação:** A Ordem acumula complexidade acidental ao resolver demandas locais sem administrar os efeitos sobre o conjunto.

**Lição:** Uma boa arquitetura não elimina a complexidade do negócio; evita multiplicá-la desnecessariamente.

### 2. Acoplamento, coesão e fronteiras de responsabilidade

**O conceito:** Acoplamento mede a dependência entre componentes; coesão, a relação entre suas responsabilidades. O princípio DRY (*Don't Repeat Yourself*, ou *Não se Repita*) complementa essa discussão: evitar duplicação de conhecimento não significa centralizar todo código semelhante. Dependências circulares também podem revelar fronteiras inadequadas.

**Onde aparece:** Capítulos 1, 3 e 10.

**Na história:** O Serviço de Utilidades Compartilhadas concentra funções de domínios diferentes, enquanto notificações interferem no cadastro oficial. Mais tarde, a Compensação de Continuidade participa de um ciclo no qual componentes corrigem e recriam inconsistências uns dos outros.

**Avaliação:** As fronteiras mal definidas ampliam o impacto das mudanças. Reutilização indiscriminada e dependências circulares tornam a arquitetura mais difícil de compreender.

**Lição:** Modularidade depende de responsabilidades claras, não da quantidade de serviços nem da eliminação de toda duplicação.

### 3. Dívida técnica

**O conceito:** Dívida técnica é o custo futuro provocado por escolhas que tornam o sistema mais difícil de manter ou evoluir. Pode decorrer de decisões conscientes, urgências legítimas ou problemas acumulados.

**Onde aparece:** Capítulos 1, 2 e 10.

**Na história:** Cadastros locais resolvem necessidades imediatas, mas produzem inconsistências. A Compensação de Continuidade protege benefícios durante uma migração e permanece cinco anos sem o controle previsto.

**Avaliação:** A urgência original não invalida as decisões. O erro está em deixar de revisar soluções provisórias e administrar seus custos.

**Lição:** O problema não é necessariamente contrair dívida técnica, mas perder a capacidade de reconhecê-la e pagá-la.

### 4. Trade-offs e reversibilidade das decisões

**O conceito:** *Trade-offs* são escolhas que oferecem vantagens em determinados aspectos e impõem custos em outros. Reversibilidade é a capacidade de mudar de direção sem consequências desproporcionais.

**Onde aparece:** Capítulo 2 — *O futuro não compareceu à reunião*.

**Na história:** Centralizar cadastros simplifica consultas, mas concentra responsabilidades; distribuí-los aumenta autonomia, mas exige integração. Uma transição gradual preserva opções e reduz o impacto de uma decisão equivocada.

**Avaliação:** A equipe reconhece que não há solução universalmente superior e considera o custo de mudança como parte da decisão.

**Lição:** Arquitetura é escolher conscientemente quais problemas aceitar — e evitar transformar cada escolha em um compromisso irreversível.

### 5. YAGNI — You Aren't Gonna Need It (Você não vai precisar disso)

**O conceito:** YAGNI recomenda não construir funcionalidades ou estruturas apenas porque talvez sejam necessárias no futuro. Não significa ignorar requisitos conhecidos.

**Onde aparece:** Capítulos 6 e 9.

**Na história:** A equipe evita transformar um simulador específico em uma plataforma genérica. NORA também questiona a criação de um novo serviço sugerida por ÍRIS sem evidência de necessidade independente.

**Avaliação:** Bem aplicado: a solução permanece proporcional aos problemas demonstrados.

**Lição:** Preparar um sistema para evoluir não exige implementar antecipadamente todas as possibilidades.

### 6. ADR — Architecture Decision Record (Registro de Decisão Arquitetural)

**O conceito:** ADR é um registro breve que documenta o contexto de uma decisão, alternativas consideradas, justificativa e consequências. Contribui para preservar o conhecimento institucional sem exigir documentação excessiva.

**Onde aparece:** Capítulo 7 — *O comitê de prevenção de comitês*.

**Na história:** A Ordem substitui parte da burocracia de aprovação por decisões proporcionais ao risco, com justificativas registradas para consulta e revisão futuras.

**Avaliação:** Bem aplicado: a rastreabilidade aumenta sem transformar toda mudança em uma reunião.

**Lição:** Documentar o motivo de uma escolha permite questioná-la melhor no futuro; não a torna definitiva.
