# Plano editorial — novo apêndice técnico

Status: **diretrizes e índice definitivo de 15 temas aprovados; temas 01 a 11 aprovados e salvos; temas 12 a 15 pendentes de avaliação**.
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

## Índice definitivo — 15 temas (aprovado pelo autor em 2026-11-07)

O índice anterior de 30 temas foi reduzido após revisão editorial e confronto com a narrativa e os textos «Por trás do caos». Preservar os dez primeiros temas, já aprovados, e concluir com cinco temas integradores. Não acrescentar capítulos sem nova aprovação explícita.

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
11. Resiliência, idempotência e observabilidade
12. Verificação, validação e resultados de negócio
13. Modernização de sistemas legados e conhecimento perdido
14. Lei de Conway, governança e autonomia
15. Inteligência artificial, evidências e supervisão humana

### Justificativa narrativa para os temas finais
- **11:** capítulo 4 — falhas distribuídas, retentativas, duplicações e visibilidade operacional.
- **12:** capítulo 5 — implantação tecnicamente bem-sucedida com resultados prejudiciais aos cidadãos; diferenciar conformidade técnica de validação de necessidades reais.
- **13:** capítulos 8 e 10 — regras históricas desconhecidas, código legado e conhecimento tácito.
- **14:** capítulos 6 e 7 — organograma, comitês, responsabilidades fragmentadas e autonomia.
- **15:** capítulo 9 — ÍRIS, decisões automatizadas, qualidade das evidências e supervisão humana.

### Escopo deliberadamente excluído ou incorporado
- CAP, SAGA, segurança por design, escalabilidade, padrões de integração, SRE/SLI/SLO/SLA, estratégias extensas de testes e dependência de fornecedores não terão capítulos próprios.
- Mencionar esses conceitos pontualmente quando indispensáveis, sem criar novos temas.
- Idempotência e observabilidade entram no tema 11; verificação e validação, no tema 12; métricas e resultados de negócio entram no tema 12; conhecimento técnico e continuidade, no tema 13.
- Evitar repetir definições já desenvolvidas nos temas 01–10. Os temas finais devem ser concisos e relacionados aos acontecimentos do romance, mas continuar úteis como referência técnica independente.

## Fluxo de aprovação
1. Apresentar um tema completo para revisão do autor.
2. Registrar a aprovação ou os ajustes explicitamente solicitados.
3. Somente depois da aprovação, marcar o texto técnico como definitivo.
4. Repetir por tema, revisar coerência do conjunto e então gerar novo EPUB.

## Controle de aprovação dos temas
- **Tema 01 — DRY, KISS e YAGNI: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-01-dry-kiss-yagni.md`.
- **Tema 02 — SOLID: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-02-solid.md`.
- **Tema 03 — Acoplamento, coesão e modularidade: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-03-acoplamento-coesao-modularidade.md`.
- **Tema 04 — Complexidade essencial e acidental: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-04-complexidade-essencial-e-acidental.md`.
- **Tema 05 — Dívida técnica: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-05-divida-tecnica.md`.
- **Tema 06 — Decisões arquiteturais, trade-offs, reversibilidade e ADR: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-06-decisoes-arquiteturais-trade-offs-reversibilidade-adr.md`.
- **Tema 07 — Monólitos, monólitos modulares e microsserviços: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-07-monolitos-monolitos-modulares-microsservicos.md`.
- **Tema 08 — DDD e contextos delimitados: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-08-ddd-contextos-delimitados.md`.
- **Tema 09 — Comunicação síncrona e assíncrona: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-09-comunicacao-sincrona-assincrona.md`.
- **Tema 10 — Arquitetura orientada a eventos: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-10-arquitetura-orientada-a-eventos.md`.
- **Tema 11 — Resiliência, idempotência e observabilidade: APROVADO** pelo autor em 2026-11-07, na versão condensada, arquivo `apendice-tecnico/revisao-2026/tema-11-resiliencia-idempotencia-observabilidade.md`.
- **Temas 12 a 15: NÃO APROVADOS**, aguardando apresentação e avaliação.
