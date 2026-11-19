# Correção de tabelas da edição digital

A origem dos problemas de leitura é a exportação de tabelas Markdown como parágrafos literais, em vez de elementos de tabela.

## Regra de geração
- Converter cada bloco de tabela Markdown para uma tabela HTML sem alterar o conteúdo das células.
- No EPUB, usar `<table>`, `<thead>`, `<tbody>`, `<th>` e `<td>`, com bordas, quebra de palavras e adaptação a telas pequenas.
- No PDF, usar tabela diagramada com largura limitada à área útil, quebra de linha nas células e divisão controlada entre páginas.
- Preservar negritos, itálicos e a ordem dos registros.
- Validar todas as 14 tabelas identificadas nos temas 01 a 12 do apêndice, inclusive duas no tema 06 e duas no tema 11.
- Não modificar os arquivos-fonte dos 15 temas para corrigir um defeito de exportação.

## Situação
Correção do EPUB preparada para avaliação; a geração do PDF corrigido permanece pendente. Esta nota registra o defeito e os critérios de aceite, **não** declara os dois formatos aprovados.
