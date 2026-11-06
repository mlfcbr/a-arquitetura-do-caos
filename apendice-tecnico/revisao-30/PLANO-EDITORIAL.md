# Plano editorial — Revisão do apêndice técnico para aproximadamente 30 conceitos

**Status:** Diretrizes aprovadas pelo autor; implementação parcial.

## Escopo imutável
- Não alterar nenhum dos dez capítulos, prólogo, epílogo ou interlúdio.
- Não alterar as dez seções aprovadas “Por trás do caos”.
- Alterar exclusivamente o apêndice técnico, mantendo as versões anteriores preservadas até a revisão integral ser aprovada.
- Usar os capítulos aprovados como fonte para conceitos, exemplos e avaliação; não inventar cenas nem atribuir à narrativa técnicas não demonstradas.

## Objetivo
Reduzir os 59 conceitos inicialmente inventariados para aproximadamente 30 entradas independentes, eliminando redundâncias e itens pouco relevantes sem perder explicações técnicas úteis. O número não é uma meta rígida. Organizar em cerca de cinco blocos temáticos.

## Formato de cada entrada
1. O conceito
2. Onde aparece
3. Na história
4. Avaliação
5. Lição

Escrever em português; usar siglas e termos consagrados quando agregarem precisão, explicando-os. Não acrescentar tradução inglesa desnecessária para termos comuns em português. Conectar cada conceito à história. A conclusão geral deve ser curta e separada dos conceitos.

## Matriz de decisão (numeração do inventário original)
**Manter como entrada independente (30):** 1, 2, 4, 5, 7, 8, 10, 11, 13, 15, 16, 18, 20, 22, 23, 24, 26, 27, 29, 31, 32, 33, 34, 35, 40, 41, 42, 44, 46, 50, 51, 52, 53.

**ATENÇÃO:** a lista acima contém **33** entradas; para chegar ao alvo aproximado de 30, as três fusões adicionais acordadas são:
- #3 DRY incorporado a #2 acoplamento e coesão (já classificado como fusão).
- #43 Vendor Lock-in incorporado à discussão de riscos de adoção de IA (não permanece como entrada independente).
- #55 Dependências operacionais ocultas incorporadas a #50 resiliência operacional (não permanece como entrada independente).

**Correção editorial da contagem:** a lista de 33 acima é a seleção independente definitiva após as três fusões adicionais, e não deve ser chamada de lista de 30. Revisar e consolidar mais três entradas na elaboração dos blocos seguintes para obter aproximadamente 30, sem cortes artificiais. A primeira parte condensada possui 6 entradas.

### Demais decisões de fusão
- #6 Reversibilidade → #5 Trade-offs.
- #9 Dependências circulares → #2 Acoplamento e coesão.
- #12 Timeouts e #14 Circuit Breaker → #13 Retries e mecanismos de resiliência.
- #17 Ordenação, duplicação e versionamento de eventos → #16 Consistência eventual.
- #19 Recuperação e reconciliação de estados → #16 e/ou #50.
- #21 Requisitos e critérios de aceitação → #20 Verificação e validação.
- #25 Contextos delimitados → #24 DDD.
- #28 Execução paralela → #27 Strangler Fig.
- #30 Documentação viva → #8 ADR e #22 conhecimento institucional.
- #36 Governança automatizada → #35 Guardrails.
- #37 Gestão de mudanças e contratos → #33 Autonomia e limites.
- #39 Responsabilidade compartilhada → #32 Product Ownership e #33 Autonomia.
- #45 Autonomia graduada → #41 HITL.
- #47 Auditabilidade de IA e #49 Métricas de IA → #40 Evals.
- #48 Limites das evidências → #42 Grounding e #44 Viés de automação.
- #54 Recuperação e continuidade, #56 Detecção e contenção → #50 Resiliência.
- #57 Correção na origem → #53 Controles compensatórios.

### Remover como entrada independente
- #38 Priorização por valor, risco e capacidade (tangencia Product Ownership).
- #58 Impacto humano (abrangido por sistemas sociotécnicos).
- #59 Adaptação e aprendizagem (melhor como conclusão).
- Não excluir conceitos fundamentais da história; itens fundidos podem permanecer como subtópicos.

## Estado do trabalho
- Versões anteriores das partes I–V estão em `apendice-tecnico/01-...` até `05-...`.
- A parte VI foi apenas rascunhada em conversa e não foi aprovada nem salva.
- A nova parte I está em `apendice-tecnico/revisao-30/01-principios-e-decisoes-arquiteturais.md`.
- As novas partes II–V ainda precisam ser elaboradas e revisadas.
- Não substituir versões antigas antes da aprovação editorial da nova versão integral.

## Prévia editorial do livro
- Formato visual proposto: livro 15 × 23 cm, capa, folha de rosto, sumário, aberturas de capítulos, ilustrações e paginação.
- A prévia visual é apenas estudo de diagramação; nomes, autoria, títulos e números de página devem vir do texto real, nunca de imagens conceituais.
- Não alterar a narrativa para adequá-la ao projeto gráfico.
