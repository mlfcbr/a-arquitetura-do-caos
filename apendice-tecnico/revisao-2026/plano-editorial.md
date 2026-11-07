# Plano editorial — novo apêndice técnico

Status: **diretrizes aprovadas; índice em avaliação; temas 01 e 02 aprovados; demais temas pendentes**.
Data: 2026-11-07.

## Limites
- Narrativa, prólogo, interlúdio, epílogo e dez textos «Por trás do caos» permanecem congelados. Nenhuma reescrita literária.
- O novo apêndice será uma referência técnica independente da história da Ordem, sem obrigação de retomar personagens ou cenas.
- Não substituir o EPUB vigente antes da aprovação do novo apêndice completo.

## Critérios de seleção
Avaliar relevância prática, reconhecimento no mercado, importância, valor didático, vínculo com a proposta do livro, grau de superestimação, redundância e origem nos materiais da pós. As notas de adoção são avaliações qualitativas, não percentuais comprovados. O número final de temas não está fixado.

## Linguagem
Português brasileiro como idioma principal. Traduzir termos quando o equivalente é claro e consagrado; preservar jargões relevantes entre parênteses para permitir pesquisa e reconhecimento, por exemplo retentativa (*retry*) e tempo limite (*timeout*). Manter siglas consolidadas como DRY, KISS, YAGNI, SOLID, DDD e ADR; explicar a expressão original, tradução e sentido prático na primeira ocorrência. Evitar traduções artificiais.

## Formato dos temas
**Padrão condensado aprovado em 2026-11-07:** textos objetivos, sem código, diagramas ou exemplos detalhados por padrão; definição e tradução, importância, aplicação, limites e trade-offs, comparação breve quando útil. Um exemplo curto apenas quando indispensável. A extensão pode variar conforme a complexidade; não repetir conclusões ou criar checklists extensos sem necessidade. O apêndice deve complementar o romance, não competir com ele. Esta diretriz prevalece sobre a orientação inicial de aprofundamento extenso.

Perguntas e respostas adaptadas ao assunto: o que é; por que importa; quando utilizar; como aplicar ou avaliar; trade-offs; erros comuns; critérios práticos. Usar tabelas e exemplos técnicos quando acrescentarem clareza. Profundidade proporcional ao tema; evitar repetição e conteúdo artificialmente extenso.

## Índice candidato — sujeito a aprovação
1. DRY, KISS e YAGNI
2. SOLID; separação de responsabilidades e composição em vez de herança
3. Acoplamento, coesão e modularidade
4. Complexidade essencial e acidental
5. Dívida técnica
6. Decisões arquiteturais, trade-offs, reversibilidade e ADR
7. Monólitos, monólitos modulares e microsserviços
8. DDD e contextos delimitados
9. Comunicação síncrona e assíncrona
10. Arquitetura orientada a eventos
11. Consistência de dados e teorema CAP
12. Transações distribuídas e SAGA
13. Idempotência
14. Padrões de integração (Outbox, camada anticorrupção, API Gateway)
15. Modernização de sistemas legados e Strangler Fig
16. Requisitos, verificação e validação
17. Estratégias de testes
18. Resiliência e tolerância a falhas (retry, timeout, Circuit Breaker, Bulkhead)
19. Observabilidade
20. Confiabilidade e SRE (SLI, SLO, SLA)
21. Escalabilidade e desempenho
22. Segurança por design
23. Lei de Conway e sistemas sociotécnicos
24. Governança técnica e autonomia
25. Métricas técnicas e de negócio
26. Conhecimento técnico e continuidade operacional
27. Dependência de fornecedor (vendor lock-in)
28. Avaliação de sistemas de IA (evals)
29. Fundamentação em evidências (grounding)
30. Supervisão humana e riscos da automação

### Pontos a revisar antes do índice definitivo
- Explicitar arquitetura em camadas e cache, confirmados no material de Software Design & System Design.
- Definir se separação de responsabilidades e composição merecem tópicos próprios ou permanecem no tema 2.
- Verificar redundâncias e profundidade apropriada de SRE e IA.
- Rastrear conceitos aos materiais originais da pós por curiosidade, sem exigir correspondência integral.
- Avaliar a relação entre os 30 temas candidatos e os 32 conceitos da versão anterior; não perder assuntos relevantes por acidente.

## Fluxo de aprovação
1. Apresentar um tema completo para revisão do autor.
2. Registrar a aprovação ou os ajustes explicitamente solicitados.
3. Somente depois da aprovação, marcar o texto técnico como definitivo.
4. Repetir por tema, revisar coerência do conjunto e então gerar novo EPUB.

## Controle de aprovação dos temas
- **Tema 01 — DRY, KISS e YAGNI: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-01-dry-kiss-yagni.md`.
- **Tema 02 — SOLID: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-02-solid.md`.
- **Tema 03 em diante: NÃO APROVADOS**, aguardando apresentação e avaliação.
