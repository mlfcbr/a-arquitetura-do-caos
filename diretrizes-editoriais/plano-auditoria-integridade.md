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
