# Edição digital e audiolivro — decisões editoriais

## Objetivo
Obra destinada prioritariamente à leitura em celular, sem previsão de impressão.

## Edições
- **EPUB** como formato principal, com texto adaptável à tela, ajuste de fonte e navegação por capítulos.
- **PDF para celular** como edição complementar, com paginação otimizada para tela pequena.
- Não priorizar redução artificial de páginas nem formato físico 18 × 25 cm.
- Manter a identidade visual de um livro técnico, mas preservar a leitura e o ritmo de romance.

## Regras vigentes de montagem do EPUB — atualização aprovada em 2026-11-17

**Estas regras substituem explicitamente as orientações anteriores de incluir documentos editoriais completos, folha de rosto repetida ou páginas preliminares redundantes.** São regras de montagem, não autorização para reescrever o romance ou os arquivos-fonte.

### Referência visual obrigatória
- **Usar como padrão a edição EPUB original cuja apresentação o autor aprovou**, não as versões compactas/reconstruídas posteriormente. O autor mostrou três capturas da edição original e confirmou que são **referências positivas**: sumário, página de rosto original e “Nota ao leitor”.
- Preservar aparência do sumário (hierarquia e recuos, incluindo “Por trás do caos” subordinado ao capítulo), tipografia, justificação, hifenização em pt-BR, margens, entrelinhas, espaçamentos e quebras de página.
- **Não reconstruir o livro inteiro com CSS genérico ou defaults do Pandoc**. Preferir editar o EPUB-base aprovado e substituir somente o conteúdo necessário. Se o EPUB-base original não estiver disponível, solicitar ao autor o arquivo correspondente às capturas; não afirmar que a aparência foi reproduzida apenas por inspeção textual.
- A paginação é refluível e depende do leitor e tamanho da fonte. Testar visualmente no Google Play Livros, especialmente o sumário e a justificação; não alegar fidelidade visual sem esse teste.
- Não interpretar as três capturas da edição original como exemplos de defeitos. As críticas do autor referiam-se às edições posteriores.

### Abertura, notas e créditos — sem redundância
1. **Capa oficial** de `assets/imagens/capa.jpg`, preservada sem modificações; centralizar horizontal e verticalmente no espaço de leitura, sem deformar nem recortar. Verificar o resultado no Play Livros.
2. **Não criar segunda página com título, subtítulo, autor e edição** depois da capa. Manter título e autor nos metadados EPUB. A captura da folha de rosto antiga é referência de estilo, não autorização para reintroduzir a página duplicada.
3. **“Sobre o autor e este projeto”**: uma única seção de até três páginas nas configurações usuais de leitura, reunindo biografia aprovada (início em 1996 com Delphi, aproximadamente 25 anos com Java e função atual de Technical Product Owner), origem na pós-graduação, organização dos estudos no Notion, criação de NORA e Ordem, processo iterativo com IA e GitHub, e motivação de compartilhar gratuitamente. O limite de páginas é meta visual, pois EPUB é refluível. Não incorporar integralmente `editorial/sobre-este-projeto.md`.
4. **Uso de inteligência artificial integrado à apresentação**: não criar seção ou página independente “Nota sobre o uso de inteligência artificial”. Explicar de maneira transparente, dentro de “Sobre o autor e este projeto”, como o autor concebeu, dirigiu e revisou a obra e como a IA apoiou textos, revisões e ilustrações, sem redundância. Preservar o fecho irônico aprovado, adaptado à seção unificada: “E sim, até esta explicação foi redigida com a ajuda de uma inteligência artificial. A ironia não passou despercebida.”
5. **Não criar “Nota ao leitor” independente**: incorporar apenas sua orientação útil sobre a leitura opcional de “Por trás do caos” e o apêndice na apresentação conjunta. A captura da antiga nota é referência tipográfica.
6. **Sumário navegável** e início da narrativa; manter a hierarquia visual aprovada, sem reiniciar indevidamente a numeração das partes/capítulos nem achatar os itens subordinados.
7. **Direitos autorais no final** do livro, em uma seção breve e única. Não repetir direitos, avisos, notas editoriais e processo de criação em várias páginas.
- Cada seção editorial principal deve começar em nova página/seção EPUB; não criar páginas vazias ou múltiplas seções para o mesmo assunto.
- `editorial/creditos-e-direitos-autorais.md` e `editorial/sobre-este-projeto.md` continuam sendo fontes editoriais no repositório, **não blocos a serem copiados integralmente** para o EPUB.
- Preservar o conteúdo literário aprovado, as 12 ilustrações oficiais e o conteúdo técnico; corrigir somente montagem e apresentação.

### “Por trás do caos” — padrão visual e estrutural obrigatório
- Cada um dos **dez complementos técnicos** deve aparecer **ao final do capítulo correspondente**, não como seção autônoma deslocada do capítulo.
- Reproduzir o tratamento visual da edição original aprovada: título curto **“Por trás do caos”**, destaque discreto com **barra vertical à esquerda**, subtítulo **“Leitura complementar · opcional”**, corpo justificado, margens e espaçamento consistentes com a edição original.
- Não substituir o título visual por “Por trás do caos — Capítulo N”; o vínculo ao capítulo deve ser estabelecido pela posição e pela navegação, não por um título diferente.
- No sumário navegável, cada “Por trás do caos” deve ser **subitem do respectivo capítulo**, com nível hierárquico e recuo apropriados. Garantir âncoras internas funcionais.
- Preservar **integralmente** o texto de cada complemento aprovado. Não resumir, fundir, renomear ou reordenar conteúdos. Se necessário, pode haver separação interna por CSS sem criar uma nova seção principal no sumário.
- Teste de aceitação: abrir pelo sumário o capítulo 1 e seu complemento, verificar o destaque lateral e o subtítulo; repetir por amostragem no meio e no final do livro. Comparar com o EPUB original, não apenas com screenshots de uma versão posterior.

### Apêndice técnico — preservação literal
- O apêndice da edição final é composto por **15 temas individuais** aprovados, nesta ordem, conforme `apendice-tecnico/revisao-2026/plano-editorial.md` e os arquivos `apendice-tecnico/revisao-2026/tema-01-*.md` a `tema-15-*.md`.
- **Não** condensar os 15 temas em cinco seções, agrupar capítulos, reescrever exemplos, reduzir explicações ou substituir títulos. Manter a estrutura de títulos e subtítulos, exemplos, tabelas e demais elementos de cada fonte.
- Incluir entradas de navegação para os 15 temas, na mesma ordem, com links funcionais.
- A edição EPUB original aprovada é a **referência visual**; os arquivos aprovados do GitHub são a **referência textual**. Em caso de divergência entre texto do EPUB-base antigo e GitHub atualizado, preservar o estilo do EPUB-base, mas utilizar o texto vigente do GitHub.
- Conferir por comparação programática a presença e a ordem dos 15 arquivos-fonte no EPUB, além de inspeção visual. Não declarar a edição final se o conteúdo tiver sido transformado ou omitido.

### Controle de qualidade da geração
- Antes de montar o EPUB, construir uma lista explícita de arquivos-fonte e seções; verificar que cada arquivo literário e técnico aprovado foi incorporado **uma única vez**.
- Comparar a edição resultante com a original quanto a capa, sumário, recuos, corpo justificado, hifenização, barras de destaque, títulos, subtítulos e quebras de página.
- Fazer inspeção visual real de páginas representativas: abertura, capítulo 1, “Por trás do caos” do capítulo 1, complemento de capítulo intermediário, apêndice e final do livro.
- Não confundir validação de ZIP/XML/EPUB com aprovação da diagramação: são verificações distintas.
- Se a versão original necessária para comparação não estiver acessível, declarar essa limitação e solicitar o arquivo; **não afirmar equivalência visual não verificada**.

### Checklist obrigatório antes de entregar
- Confirmar a versão atualizada do GitHub e identificar o commit-fonte; não partir de EPUB com texto desatualizado.
- Confirmar capa oficial e metadados “A Arquitetura do Caos” / “Marcelo Corrêa”.
- Conferir que não existe folha de rosto duplicada, “Nota ao leitor” separada ou repetição de créditos, biografia e explicações sobre IA; confirmar que a IA está explicada na apresentação unificada, sem nota independente.
- Confirmar quebra de página para seções editoriais e aberturas principais, sumário com recuos e níveis corretos e corpo justificado sem espaçamento excessivo entre palavras.
- Conferir 4 partes, prólogo, capítulos 1–10, interlúdio, epílogo, dez seções “Por trás do caos”, apêndice técnico e 12 ilustrações.
- Validar integridade EPUB, referências internas e, se possível, EpubCheck; comparar visualmente com a edição original no Google Play Livros antes de declarar a edição definitiva.
- Não alterar a fonte do romance, não publicar binário nem modificar o repositório fora das diretrizes sem autorização específica.

## Regras editoriais aprovadas
- Preservar integralmente o texto narrativo aprovado; mudanças apenas de apresentação e formatação.
- Recuos consistentes de primeira linha, definidos por estilo, sem tabulações manuais.
- Primeiro parágrafo após título ou quebra de cena sem recuo; demais parágrafos com recuo consistente.
- Partes I, II e III com abertura exclusiva e centralizada; não repetir título da parte antes de cada capítulo.
- Preservar prólogo, dez capítulos, interlúdio, epílogo, conteúdos 'Por trás do caos' e apêndice técnico.
- Manter as 12 ilustrações aprovadas, com correspondência verificada a cada capítulo; não há ilustração própria para o interlúdio.
- Manter arquivos-fonte, versões finais, decisões, guia de arte e imagens no repositório, com histórico de versões.

## Audiolivro — proposta (ainda não produzido)
- Gerar versão em áudio por capítulo, com prólogo, interlúdio e epílogo; separar material técnico complementar quando conveniente.
- Narrativa em português do Brasil, preservando literalmente o texto aprovado.
- Definir voz e interpretação da NORA, vozes dos diálogos e ritmo antes da produção integral.
- Gerar amostra piloto e revisar pronúncia de nomes, siglas, termos técnicos, pausas e cortes.
- Exportar em arquivos por capítulo (MP3 ou M4B) e preservar roteiro, metadados e parâmetros de produção.
- A síntese de voz exige um mecanismo/serviço de TTS; a existência deste plano não significa que o áudio já foi gerado.

## Estado
Decisões registradas. Os binários EPUB, PDF e imagens devem ser publicados e conferidos separadamente, com nomes, tamanhos e integridade verificáveis. Não marcar como concluído antes da confirmação de upload.

## Auditoria de procedência das ilustrações
- **Status: encerrado por declaração expressa do autor (2026-11-17).** O autor confirma a procedência das ilustrações e assume a responsabilidade por essa confirmação; não há pendência de coleta de evidências de origem para esta edição.
- Esta anotação registra a declaração do autor, não constitui certificação jurídica de inexistência de direitos de terceiros.
- Manter as ilustrações aprovadas sem alterações. A auditoria de originalidade textual permanece independente.
