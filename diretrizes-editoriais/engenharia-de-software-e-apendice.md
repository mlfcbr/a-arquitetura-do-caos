# Diretrizes editoriais — Engenharia de software na narrativa

**Projeto:** A Arquitetura do Caos
**Status:** decisões aprovadas em conversa, 06/11/2026.
**Escopo:** planejamento editorial e rastreabilidade técnica; não altera capítulos aprovados.

## Princípio fundamental
A narrativa e o ritmo literário são prioritários. Não é necessário incluir todos os assuntos da pós-graduação; porém, **todos os conceitos de engenharia de software efetivamente presentes no livro devem ser identificados e documentados**, inclusive quando apenas citados brevemente ou demonstrados de maneira implícita.

Não inventar cenas ou forçar conceitos para cumprir uma grade curricular. NORA pode introduzir termos de forma natural, com humor e ironia, sem transformar a história em aula.

## Estrutura em duas camadas
1. **História:** leitura fluida, sem marcadores técnicos intrusivos no meio da narrativa. Opcionalmente, abertura de capítulo com uma frase temática discreta, sem lista antecipada de conteúdos.
2. **Engenharia por trás do caos:** documentação separada e opcional, dividida entre notas por capítulo e apêndice completo.

## “Por trás do caos” — ao final de cada capítulo
- Pequena seção separada do encerramento narrativo.
- Priorizar cerca de 2–3 conceitos mais relevantes do capítulo, com explicações concisas (referência inicial: ~100–150 palavras no total, flexível).
- Relacionar o conceito a um acontecimento concreto da história.
- Não repetir mecanicamente a mesma explicação em capítulos diferentes: destacar aspectos novos conforme o contexto.
- Conceitos apenas mencionados podem aparecer exclusivamente no apêndice, evitando sobrecarregar as notas.

## Apêndice técnico final — cobertura completa
Catalogar **todos os conceitos identificáveis no texto**, com:
- Nome do conceito e definição curta e tecnicamente correta;
- Capítulo(s) e cena(s) em que aparece;
- Forma de presença: **explícita, implícita ou breve menção**;
- Papel narrativo e exemplo contextualizado;
- Avaliação: **bem aplicado, violado, ou trade-off legítimo**, com justificativa e restrições quando pertinente;
- Referências cruzadas entre múltiplas ocorrências, sem duplicar definições.

## Profundidade de cobertura
| Nível | Critério | Tratamento |
|---|---|---|
| Central | Influencia conflitos, decisões ou acontecimentos | “Por trás do caos” + apêndice |
| Secundário | Aparece em situação específica ou comentário de NORA | Nota curta quando útil + apêndice |
| Menção | Citado rapidamente, sem desenvolvimento | Entrada concisa no apêndice |

A classificação de profundidade é independente da classificação explícito/implícito/menção.

## Processo recomendado
1. Concluir e aprovar os capítulos narrativos, sem reescrever os já aprovados por conta do mapeamento.
2. Ler o texto integral e construir uma **matriz de rastreabilidade conceito × capítulo × cena**.
3. Identificar conceitos centrais, secundários e menções; incluir os implícitos.
4. Redigir e revisar as seções “Por trás do caos” de cada capítulo.
5. Consolidar o apêndice técnico completo, com referências cruzadas e avaliação de decisões.
6. Revisar a precisão técnica, as ocorrências e a fluidez editorial antes da diagramação.

## Exemplos ilustrativos (não confirmados nos capítulos)
Lei de Conway; acoplamento; observabilidade; YAGNI; débito técnico; monólitos; microserviços; DDD; arquitetura hexagonal; dependências circulares. **Não presumir que todos aparecem no texto:** conferir capítulo e cena antes de incluir no índice final.

## Restrições
- Não colocar listas de conceitos como currículo obrigatório antes de cada capítulo.
- Não usar marcadores técnicos que interrompam a imersão no meio de cenas.
- Não afirmar ocorrências sem verificar os textos finais.
- Não confundir decisões de arquitetura questionáveis com erros absolutos: contextualizar trade-offs e limitações.
