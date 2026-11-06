# Apêndice técnico — Engenharia por trás do caos

> **Parte I — Princípios e decisões arquiteturais**
>
> **STATUS: APROVADO PELO AUTOR.** Complemento independente. Não altera a narrativa.

## 1. Complexidade essencial e complexidade acidental

**O conceito:** Complexidade essencial é aquela inerente ao problema que o software precisa resolver. Complexidade acidental é introduzida pelas escolhas de implementação, ferramentas, integrações e estruturas utilizadas para resolvê-lo.

**Onde aparece:** Capítulo 1 — *Era só um botão*.

**Na história:** Identificar cidadãos com direito a atendimento prioritário exige compreender regras e exceções reais. Essa complexidade não desaparece com uma arquitetura melhor. Entretanto, manter múltiplos cadastros, coletores e mecanismos de sincronização acrescenta problemas que não pertencem necessariamente ao domínio.

**Avaliação:** A Ordem acumulou complexidade acidental ao adotar soluções locais sem administrar suas consequências para o conjunto.

**Lição:** Uma boa arquitetura não elimina a complexidade do negócio. Procura evitar que a solução acrescente complexidade desnecessária.

## 2. Acoplamento e coesão

**O conceito:** Acoplamento representa o grau de dependência entre componentes. Coesão representa o quanto as responsabilidades de um componente estão relacionadas entre si.

Em geral, busca-se alta coesão e baixo acoplamento, sem transformar esses objetivos em regras absolutas.

**Onde aparece:** Capítulos 1 e 3 — *Era só um botão* e *Dividir para complicar*.

**Na história:** O Serviço de Utilidades Compartilhadas concentra responsabilidades de diferentes domínios. Alterações necessárias a um consumidor podem afetar aplicações que não possuem relação com aquela mudança. Em outro momento, o serviço de notificações ultrapassa sua responsabilidade ao modificar informações do cadastro oficial.

**Avaliação:** Há violações das fronteiras de responsabilidade. A reorganização proposta pela equipe melhora a definição de autoridade sobre os dados.

**Lição:** Dividir um sistema em muitos componentes não garante modularidade. O que importa é a qualidade das fronteiras e das dependências.

## 3. DRY — Don't Repeat Yourself (Não se Repita)

**O conceito:** DRY procura evitar a duplicação de conhecimento e regras de negócio. Não significa que todo trecho de código parecido deva ser transformado em uma função compartilhada.

**Onde aparece:** Capítulo 3 — *Dividir para complicar*.

**Na história:** A Ordem tenta reutilizar funcionalidades semelhantes, mas algumas delas representam decisões de negócio diferentes. Centralizá-las pode reduzir duplicação de código e, ao mesmo tempo, aumentar o acoplamento.

**Avaliação:** A reutilização é tratada inicialmente como um benefício universal, sem considerar as responsabilidades envolvidas.

**Lição:** Duas implementações semelhantes não representam necessariamente o mesmo conhecimento. Às vezes, manter código separado preserva a independência entre domínios.

## 4. Dívida técnica

**O conceito:** Dívida técnica é o custo futuro associado a escolhas de implementação ou projeto que dificultam a evolução do sistema. Pode surgir de decisões deliberadas, pressões de prazo ou deterioração progressiva da solução.

**Onde aparece:** Capítulos 1, 2 e 10.

**Na história:** O cadastro local resolve uma necessidade urgente, mas sua replicação cria inconsistências. A Compensação de Continuidade preserva benefícios legítimos durante uma emergência, porém continua operando por cinco anos sem o acompanhamento originalmente necessário.

**Avaliação:** As decisões iniciais possuíam justificativas legítimas. O problema foi permitir que soluções provisórias se tornassem dependências permanentes sem revisão adequada.

**Lição:** Nem toda solução improvisada é uma decisão ruim. O risco aumenta quando seu caráter provisório é esquecido e seus custos deixam de ser administrados.

## 5. Trade-offs arquiteturais

**O conceito:** Um trade-off é uma escolha que melhora determinadas características de uma solução enquanto impõe custos, limitações ou riscos em outras.

**Onde aparece:** Capítulo 2 — *O futuro não compareceu à reunião*.

**Na história:** Centralizar os cadastros facilita a consulta a informações compartilhadas, mas concentra responsabilidades. Distribuí-los preserva autonomia, porém aumenta o esforço de integração. A alternativa híbrida reduz parte do risco de migração, mas exige conviver temporariamente com modelos diferentes.

**Avaliação:** A análise das alternativas reconhece que não existe uma solução universalmente superior.

**Lição:** Uma decisão arquitetural deve ser julgada pelos objetivos, restrições e consequências do contexto, não pela popularidade do padrão escolhido.

## 6. Reversibilidade das decisões

**O conceito:** Reversibilidade é a capacidade de modificar, interromper ou desfazer uma decisão sem provocar consequências desproporcionais.

**Onde aparece:** Capítulo 2 — *O futuro não compareceu à reunião*.

**Na história:** A equipe considera corrigir gradualmente os cadastros, acompanhando os resultados e limitando o alcance de eventuais falhas.

**Avaliação:** A abordagem reduz a exposição a mudanças de grande impacto, embora nem todos os efeitos de uma operação possam ser revertidos automaticamente.

**Lição:** Quando o futuro é incerto, preservar opções pode ser mais valioso do que buscar uma solução definitiva.

## 7. YAGNI — You Aren't Gonna Need It (Você não vai precisar disso)

**O conceito:** YAGNI recomenda não implementar funcionalidades ou estruturas apenas porque poderão ser úteis algum dia. Não significa ignorar requisitos conhecidos ou negligenciar necessidades previsíveis.

**Onde aparece:** Capítulos 6 e 9 — *O organograma também compila* e *Contrataram outra inteligência*.

**Na história:** No capítulo 6, a equipe evita transformar um simulador específico em uma plataforma genérica para todas as simulações futuras. No capítulo 9, NORA questiona a proposta de ÍRIS de criar um novo serviço sem evidências de que suas responsabilidades precisariam evoluir independentemente.

**Avaliação:** Bem aplicado nas duas situações.

**Lição:** Arquitetura preparada para evoluir não é sinônimo de arquitetura que implementa antecipadamente todas as possibilidades imagináveis.

## 8. ADR — Architecture Decision Record (Registro de Decisão Arquitetural)

**O conceito:** ADR é um registro conciso de uma decisão arquitetural relevante. Normalmente documenta o contexto, a decisão, as alternativas consideradas e suas consequências.

**Onde aparece:** Capítulo 7 — *O comitê de prevenção de comitês*.

**Na história:** A Ordem substitui parte da burocracia de aprovação por mecanismos proporcionais ao risco. Decisões relevantes passam a preservar suas justificativas, permitindo que equipes futuras compreendam por que determinado caminho foi escolhido.

**Avaliação:** Bem aplicado. O registro aumenta a rastreabilidade sem exigir que toda decisão passe por um comitê.

**Lição:** Documentar uma decisão não significa impedir sua revisão. Significa preservar o conhecimento necessário para revisá-la com responsabilidade.

## 9. Dependências circulares

**O conceito:** Uma dependência circular ocorre quando componentes dependem direta ou indiretamente uns dos outros, formando um ciclo. Nem todo ciclo representa automaticamente uma falha, mas ciclos mal controlados podem dificultar evolução, testes e recuperação.

**Onde aparece:** Capítulo 10 — *O defeito que nos mantém vivos*.

**Na história:** Um serviço produz dados inconsistentes, a Compensação de Continuidade os corrige e outro processo reintroduz parte do problema. Os componentes acabam dependendo das compensações mútuas para produzir um resultado aparentemente correto.

**Avaliação:** Violação arquitetural. A equipe identifica o ciclo e começa a eliminar suas causas gradualmente.

**Lição:** Um sistema pode parecer estável porque seus componentes compensam continuamente os erros uns dos outros. Essa estabilidade aparente não elimina a fragilidade estrutural.
