# Fechamento editorial — versão 1.0.0

**Data:** 2026-11-07
**Status:** MANUSCRITO CONGELADO PELO AUTOR PARA A EDIÇÃO 1.0.0.
**Fonte canônica:** branch `main` de `mlfcbr/a-arquitetura-do-caos`, no commit que contém este registro.

## Autorização do autor
O autor aprovou expressamente o encerramento da revisão literária, as correções editoriais objetivas abaixo, a estrutura em quatro partes conforme o sumário atual e a identificação da edição como `v1.0.0`. Nenhuma nova revisão estilística está autorizada.

## Conteúdo aprovado
- Prólogo, capítulos 1 a 10, interlúdio e epílogo, integralmente preservados.
- Dez seções `por-tras-do-caos/`, sem reescrita.
- Apêndice canônico: cinco arquivos em `apendice-tecnico/revisao-30/`, 32 conceitos aprovados; não publicar os 49 conceitos históricos da raiz.
- Manter todas as ilustrações somente após conferir sua correspondência com os capítulos.

## Estrutura da edição
- Prólogo.
- Parte I — O nascimento da complicação: capítulos 1 e 2.
- Parte II — A arte de distribuir problemas: capítulos 3, 4 e 5.
- Parte III — A organização do absurdo: capítulos 6, 7 e 8, incluindo o interlúdio na posição aprovada pelo sumário editorial.
- Parte IV — O problema aprende a pensar: capítulos 9 e 10.
- Epílogo.
- Dez textos “Por trás do caos” e apêndice de 32 conceitos, segundo a ordem editorial final.

**Regra de diagramação:** apresentar cada título de parte uma única vez, em página/seção própria; não repetir os cabeçalhos de parte existentes nos arquivos de capítulos. As divisões físicas de capítulos em `parte-1`/`parte-2` não representam capítulos separados.

## Limpeza editorial exclusivamente na publicação
- Omitir, na edição renderizada, as linhas de controle iniciadas por `> **STATUS: APROVADO PELO AUTOR.**` em `manuscrito/10-o-defeito-que-nos-mantem-vivos-parte-1.md`, `parte-2.md` e `epilogo/a-proxima-excecao.md`.
- Omitir outros cabeçalhos de aprovação e controle editorial em complementos, se existirem, sem remover conteúdo literário.
- Preservar esses marcadores nos arquivos-fonte como registro histórico.
- Não incorporar documentos de `editorial/` e `diretrizes-editoriais/` ao texto de leitura.
- Documentos históricos com status antigo não revogam as aprovações mais recentes.

## Critério de encerramento
Somente erro factual/técnico demonstrável, contradição objetiva, nome/cronologia inconsistente ou falha de montagem poderá justificar correção posterior; mudanças de prosa exigem autorização expressa do autor. Não abrir novas rodadas de revisão de ritmo, humor ou estilo.

## Integridade
Este registro é documental e de preparação editorial. **Nenhuma linha da narrativa foi modificada no fechamento.**

## Identificador de lançamento
A intenção aprovada é usar a tag Git `v1.0.0` apontando para o commit de fechamento. A criação e verificação da tag são uma operação separada; não considerar a tag existente até confirmada no GitHub.

## Avaliação literária final e decisão de não reabrir a prosa (2026-11-07)
O autor solicitou uma avaliação final específica de qualidade, analisou os resultados e autorizou avançar para a edição digital. As notas são **juízos editoriais subjetivos da IA**, não notas de leitores independentes, nem resultados científicos.

**Nota global estimada:** 8,3/10. **Média simples das notas por unidade narrativa:** aproximadamente 8,6/10 (métrica diferente da nota global).

**Notas por unidade:** prólogo 9,0; capítulo 1 8,8; capítulo 2 8,1; capítulo 3 8,0; capítulo 4 8,5; capítulo 5 9,2; capítulo 6 8,0; capítulo 7 8,7; interlúdio 7,7; capítulo 8 8,8; capítulo 9 9,0; capítulo 10 8,9; epílogo 9,1.

**Notas por dimensão:** voz narrativa 9,2; humor 8,7; conteúdo técnico 9,0; coerência interna 8,8; evolução de NORA 9,0; personagens secundários 7,8; diálogos 8,2; tensão dramática 7,6; ritmo 7,5; originalidade 9,0; finalização 8,9.

**Diagnóstico:** maior força na voz de NORA, sátira, integração de conceitos técnicos e evolução do conflito; capítulo 5 é especialmente forte. Interlúdio é mais introspectivo e capítulos 3 e 6 são relativamente didáticos, mas cumprem função narrativa. Limitações transversais de tensão emocional, densidade desigual de personagens secundários e exposição técnica nos diálogos não justificam nova reescrita. A diferença de notas entre capítulos não demonstrou defeito grave. Nenhuma alteração narrativa foi autorizada ou feita por essa avaliação.

**Decisão expressa do autor:** “Ótimo podemos ir para a versão final do arquivo para eu subir no play livros e grave tudo que precisa e que avaliamos e décimos no GitHub para lembrar no futuro”. A fase seguinte é produzir e validar o **EPUB refluível com capa para Google Play Livros**, a partir da versão **mais recente** dos textos aprovados no GitHub, nunca de cópia local desatualizada. PDF é secundário e só será gerado se solicitado.

**Checklist de publicação:** confirmar integridade do conteúdo contra a versão canônica; capa identificada no pacote; sumário navegável; quatro páginas de abertura de parte; não duplicar partes de capítulos; prólogo, dez capítulos, interlúdio e epílogo; dez textos “Por trás do caos”; apêndice de 32 conceitos; ilustrações previstas e com legendas/acessibilidade quando aplicável; não incluir notas de STATUS nem documentos editoriais; validar estrutura EPUB e testar leitura no Play Livros. Registrar o commit-fonte e identificador do EPUB produzido.

**Tag Git `v1.0.0`:** a criação da tag foi autorizada, mas não havia ferramenta conectada com permissão para criá-la. Não afirmar que existe sem verificá-la. O commit de fechamento anterior foi `aef09c6ac59c8caa038dcd16aeda1f2910b25712`; este registro posterior de avaliação deve integrar o congelamento antes de eventual tag.

## EPUB final gerado a partir do ZIP atualizado (2026-11-07)
- **Arquivo:** `A_Arquitetura_do_Caos_FINAL_Play_Livros.epub`.
- **Fonte:** ZIP da branch `main` enviado pelo autor após a confirmação do commit `d9116963e882f1b9e3d753ac2a865c991cef60c8`.
- **SHA-256 do EPUB:** `94495b6e2c990085702ce371c0612ff5c97b9ecd39376478b1a1f625983e313a`.
- **Tamanho:** 5.194.102 bytes.
- **Geração:** Pandoc EPUB3, conteúdo refluível em português do Brasil, sumário navegável, CSS de leitura, capa incorporada, 12 ilustrações extraídas da edição ilustrada anterior e 32 verbetes do apêndice canônico.
- **Inspeção automática:** 4 aberturas de partes em seções próprias; prólogo; capítulos 1–10; interlúdio após o capítulo 7; epílogo; 10 leituras complementares; 5 blocos do apêndice; 13 imagens JPEG no pacote (capa + 12 ilustrações); nenhuma ocorrência do marcador `STATUS: APROVADO` nas páginas XHTML.
- **Observação de integridade:** nenhuma alteração foi realizada nos arquivos-fonte narrativos; a limpeza de marcadores e junção das partes de capítulos foram feitas apenas na montagem. As imagens foram reaproveitadas da edição anterior, com distribuição sequencial prólogo, capítulos 1–10 e epílogo. Não declarar teste de importação no Google Play Livros antes de o autor realizá-lo.
- **Disponibilização:** arquivo produzido no ambiente da conversa para download; não foi enviado ao GitHub como binário. Este registro preserva as decisões e a identificação criptográfica da versão.

## Correção de diagramação EPUB — títulos e legendas duplicados (2026-11-07)
- **Relato do autor:** no Google Play Livros, as páginas iniciais dos capítulos exibiam título repetido, linha de parte repetida e legenda desnecessária sob a ilustração; exemplo visual fornecido do capítulo 3.
- **Causa:** o Markdown intermediário de montagem continha um título `# Capítulo` seguido por imagem cujo texto alternativo era tratado pelo conversor como legenda visível; nos capítulos 1–7 também havia linhas editoriais `*Parte ...*` e `## Capítulo ...` repetindo cabeçalhos já existentes. O prólogo tinha linha de título duplicada.
- **Correção exclusivamente de montagem:** retiradas sete linhas de parte duplicadas, sete subtítulos de capítulo duplicados, um título duplicado do prólogo; as 12 ilustrações passaram a ser imagens sem legenda visível. Não houve modificação dos arquivos-fonte narrativos do GitHub.
- **Arquivo substituto:** `A_Arquitetura_do_Caos_FINAL_Play_Livros_CORRIGIDO.epub`.
- **SHA-256:** `b339a310daaa39f1d0b87a9a442bd66f870e75403f9ce69bf02c0be387eb348a`.
- **Validação:** cada capítulo 1–10 tem exatamente um título H1; existem quatro títulos H1 de partes; zero legendas de ilustrações visíveis e zero `figcaption`; 12 imagens narrativas, capa e sumário preservados; arquivo ZIP/EPUB íntegro.
- **Versão anterior:** o EPUB sem sufixo `CORRIGIDO`, com hash `94495b6e2c990085702ce371c0612ff5c97b9ecd39376478b1a1f625983e313a`, está **substituído** e não deve ser distribuído.
- **Próxima validação:** o autor deverá confirmar visualmente a renderização no Google Play Livros. Não alegar que esse teste foi realizado pela IA.
