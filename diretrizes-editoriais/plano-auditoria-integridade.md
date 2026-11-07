# Auditoria de integridade e continuidade — plano de execução

## Princípio
O manuscrito aprovado é a fonte da verdade. Corrigir somente erros objetivos e decisões já aprovadas; alterações de enredo, caracterização ou causalidade exigem aprovação do autor. Cada correção deve ter commit próprio ou agrupamento lógico, com descrição rastreável.

## Etapas
- [ ] Inventariar todos os arquivos narrativos e materiais complementares da branch principal.
- [ ] Auditar nomes, sobrenomes, funções, relações e referências isoladas em todos os capítulos.
- [ ] Construir matriz de continuidade (eventos, cronologia, conhecimento dos personagens e consequências).
- [ ] Conferir transições entre partes de capítulos, interlúdio e epílogo.
- [ ] Conferir continuidade técnica da Ordem, NORA, ÍRIS e apêndice.
- [ ] Confrontar decisões editoriais registradas com o texto vigente.
- [ ] Verificar correspondência das 12 ilustrações com os capítulos.
- [ ] Regenerar EPUB/PDF apenas após aprovação das pendências narrativas e auditar os arquivos finais.

## Correções já registradas
- Prólogo: Henrique → Marcelo; Teresa → Ana, nos contextos do técnico e da cidadã.
- Capítulo 5, parte 1: apresentação da gestora como Helena Vasconcelos.
- Capítulo 9, parte 1: participante da reunião de ÍRIS corrigida de Ana Almeida para Helena Vasconcelos.
- Helena Vasconcelos permanece mulher e não é parente de Marcelo Duarte.
- A regra Augusto → Marcelo está revogada, sem identificação confirmada de Augusto.

## Política de commits
1. Correções objetivas: alterar somente os trechos necessários, documentar o motivo no commit e conferir o diff.
2. Hipóteses: registrar como pendência, sem editar a narrativa antes da aprovação.
3. Manter o relatório atualizado a cada conjunto de verificações.
4. Não declarar a edição final validada até concluir todos os itens.

## Execução da auditoria — achados de continuidade
- **CRÍTICO — Capítulo 10, parte 1:** uma analista de operações é explicitamente apresentada como **Ana Almeida**, e Marcelo a reconhece como colega que acompanha reuniões e trabalhou em continuidade cadastral. A **Ana Almeida do prólogo** é uma cidadã de 73 anos. São identidades incompatíveis, provavelmente resultado de substituição editorial que fundiu duas personagens. **Não alterar sem aprovação do nome da analista.** A correção isolada no capítulo 9 para Helena Vasconcelos não resolve essa segunda ocorrência.
- **VERIFICADO — Capítulo 1:** Carlos é ex-funcionário que saiu sete anos antes e deixou procedimentos; não é a gestora Helena Vasconcelos.
- **VERIFICADO — Capítulo 5:** primeira apresentação da gestora já contém Helena Vasconcelos.
- **VERIFICADO — Capítulo 9:** a participante da apresentação da ÍRIS já está como Helena Vasconcelos.
- **VERIFICADO — Prólogo (GitHub):** referências a Henrique e Teresa corrigidas para Marcelo e Ana.
- **ARTEFATOS:** a cópia local usada para a geração dos arquivos digitais contém referências antigas a Henrique e Teresa. Não distribuir as edições digitais existentes como definitivas; regenerar do repositório atualizado após resolução das pendências.
- **PUBLICAÇÃO:** capítulo 10 permanece na pasta `rascunhos/` embora integre a narrativa; confirmar status editorial antes da geração final.

**Escopo desta passagem:** conferência automatizada de nomes antigos e nomes completos nos arquivos narrativos, seguida de leitura contextual das ocorrências suspeitas. A auditoria profunda de cronologia, transições e conceitos técnicos permanece em andamento, não validada.

## Segunda passagem — estrutura e transições (2026-11-07)
- **PENDÊNCIA DE DECISÃO — Título da Parte III:** capítulo 6 usa **“Parte III — A organização do absurdo”**, mas capítulo 7 usa **“Parte III — O componente humano”**. São títulos diferentes para a mesma parte. Como o autor aprovou aberturas únicas de partes, confirmar o título canônico antes de alterar qualquer capítulo ou índice.
- **INCONSISTÊNCIA DOCUMENTAL — Bíblia do livro:** `editorial/biblia-do-livro.md` (datada 2026-11-05) afirma que capítulos 7–10 e epílogo ainda não foram escritos/aprovados, mas os arquivos existem e há registro de aprovação final. Atualizar o status editorial após confirmar a localização definitiva do capítulo 10.
- **INCONSISTÊNCIA DE PUBLICAÇÃO — Capítulo 10:** as duas partes estão em `rascunhos/`, apesar de seus cabeçalhos declararem aprovação pelo autor. Não mover automaticamente antes de conferir referências e o pipeline de geração.
- **VALIDADO PARCIALMENTE — Aberturas:** capítulo 3 inicia a Parte II; capítulo 6 inicia a Parte III. O capítulo 7 repete um título divergente da Parte III, embora a decisão editorial seja exibir a parte somente na abertura. A remoção visual da repetição é de diagramação, não exige mudar o texto narrativo.
- **REGRA DE INTEGRIDADE:** não confundir uma correção de continuidade comprovada com reescrita estilística; quaisquer mudanças de causalidade ou papéis dependem de autorização.

**Limite:** esta passagem cobriu cabeçalhos e transições estruturais e confronto com documentos editoriais; não equivale a validação integral de toda a narrativa.

## Terceira passagem — decisões aplicadas (2026-11-07)
- **RESOLVIDO — Título da Parte III:** o autor confirmou **“A organização do absurdo”**; capítulo 7, parte 1, padronizado conforme capítulo 6 (commit `91a4cf6`). A edição digital exibirá o título da parte apenas na sua abertura, conforme decisão anterior.
- **RESOLVIDO — Bíblia editorial desatualizada:** atualizado o status dos capítulos 7–10, interlúdio, epílogo, apêndice aprovado e nomes canônicos (commit `334fda8`).
- **RESOLVIDO — Colisão Ana/Teresa:** capítulo 10, parte 1, já corrigido conforme autorização do autor (commits `29a47df` e `d47f00a`).
- **CONFIRMADO — Capítulo 10:** ambas as partes registram expressamente `STATUS: APROVADO PELO AUTOR`; a localização em `rascunhos/` é um problema de organização, não evidência de falta de aprovação. Ainda não movido para evitar quebrar referências existentes.
- **VERIFICAÇÃO DE ARCO — ÍRIS:** introduzida no capítulo 9, atua no capítulo 10 e aparece no epílogo; sequência macro consistente nas amostras verificadas. Ainda não é validação linha a linha de causalidade e tempo.

**Próximos controles:** inventário de links e referências de arquivos, consistência temporal detalhada, transições e apêndice técnico, ilustrações e artefatos digitais.
