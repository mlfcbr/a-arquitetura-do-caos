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

## Quarta passagem — rascunhos aprovados (2026-11-07)
- **INVENTÁRIO CONFIRMADO:** a pasta `rascunhos/` continha somente os dois arquivos do capítulo 10; ambos declaravam `STATUS: APROVADO PELO AUTOR`.
- **RESOLVIDO — promoção para manuscrito:** os dois arquivos foram movidos de `rascunhos/` para `manuscrito/` em um único commit atômico (`6006fc7`), preservando exatamente os SHA dos blobs (parte 1: `ca0aee3`; parte 2: `6438382`). Portanto, não houve alteração textual nessa promoção.
- **VERIFICADO APÓS COMMIT:** ambos os arquivos aparecem na pasta `manuscrito/`, que passou a conter 20 arquivos; a pasta `rascunhos/` deixou de existir por não ter outros arquivos.
- **DOCUMENTAÇÃO:** bíblia editorial atualizada para refletir o caminho definitivo (commit `cf2c25d`).
- **ATENÇÃO:** referências editoriais ou scripts de geração que apontem para o caminho antigo devem ser auditados antes da produção digital. O status de aprovação não significa que a revisão de continuidade esteja concluída.

## Quinta passagem — inventário integral e documentos de montagem (2026-11-07)
- **INVENTÁRIO DO REPOSITÓRIO:** árvore recursiva `main` não truncada; 20 arquivos narrativos em `manuscrito/` (prólogo + capítulos 1–10 em partes + interlúdio), epílogo em `epilogo/`, dez seções em `por-tras-do-caos/`. Não há pasta `rascunhos/` restante.
- **CORRIGIDO — README:** dizia que só o prólogo estava aprovado; agora reflete o estado atual (commit `c93ca2c`).
- **CORRIGIDO — Sumário editorial:** atualizados estados de aprovação, títulos canônicos das Partes II/III, título real do epílogo e situação do apêndice (commit `13a3c84`).
- **CORRIGIDO — Decisão de 32 conceitos:** o documento de aprovações finais ainda chamava de 30 e sugeria fusões, contrariando aprovação posterior de 32. Atualizado para 32 sem excluir conceitos (commit `1db06bf`).
- **CORRIGIDO — Plano histórico do apêndice:** sinalizado que o plano de 30/33 conceitos e formato físico 15×23 cm foi superado por decisões posteriores (commit `3910324`).
- **VALIDADO — Aberturas:** títulos da Parte I nos capítulos 1–2; Parte II nos capítulos 3–5; Parte III nos capítulos 6–7; a apresentação única de cada parte é responsabilidade da montagem EPUB/PDF. O capítulo 8 em diante usa cabeçalho de capítulo sem título de parte. Não inserir parte nova sem decisão editorial.
- **PENDÊNCIA IMPORTANTE — versão do capítulo 7:** `editorial/revisao-de-plausibilidade-pendente.md` declara expressamente que a versão aprovada em conversa era diferente da versão salva no GitHub. Não é possível declarar equivalência sem localizar e comparar a versão aprovada. Preservar o texto atual e submeter diferenças substantivas à decisão do autor.
- **PENDÊNCIA DE PUBLICAÇÃO — apêndice:** as 32 entradas foram aprovadas como seleção, mas a redação das partes deve ser auditada; não confundir aprovação do inventário com aprovação do texto.
- **PENDÊNCIA DE PUBLICAÇÃO — ilustrações:** árvore GitHub não contém binários de ilustrações; a aprovação das 12 imagens está documentada, mas seu upload e correspondência aos capítulos não estão verificados.
- **PENDÊNCIA DE PUBLICAÇÃO — links de montagem:** não há script de geração EPUB/PDF na árvore atual; produzir a partir de `manuscrito/`, `epilogo/` e complementos canônicos e validar a sequência.

## Sexta passagem — recuperação de evidência do capítulo 7 (2026-11-07)
- **CONFIRMADA DIVERGÊNCIA DE VERSÕES:** registro de conversa de 2026-11-05 informa aprovação de uma versão de **“O comitê de prevenção de comitês”** cuja abertura é **“Na Ordem, existiam vinte e três procedimentos...”**; essa versão inclui o bloqueio da correção do portal, governança proporcional ao risco, guardrails, ADRs, autonomia e registro privado **“Autoridade e limites”**.
- **VERSÃO ATUAL NO GITHUB:** `manuscrito/07-o-comite-de-prevencao-de-comites-parte-1.md` abre com **“A Ordem possuía quarenta e três comitês.”**; a parte 2 termina sem registro privado, declarando que NORA não criou um. Portanto, não é uma simples diferença de título ou diagramação: são versões narrativas substancialmente distintas.
- **EVIDÊNCIA CRUZADA:** o PDF anterior `A_Arquitetura_do_Caos_Capitulo_07_Leitura_Completa.pdf` e provas integrais reproduzem a versão de **43 comitês**, não a versão de **23 procedimentos**. Logo, PDFs anteriores não comprovam a incorporação do texto aprovado mais recente.
- **AÇÃO SEGURA:** preservar ambas as partes atuais no GitHub, sem substituição silenciosa. Recuperar a versão integral aprovada da conversa de 2026-11-05 e compará-la antes de qualquer substituição. **Não marcar capítulo 7 como conferido para edição final** enquanto faltar a íntegra comparável.
- **ESCOPO:** o registro de aprovação do capítulo 7 existe, mas não equivale à posse da versão integral em arquivo; a recuperação parcial da abertura e do arco não autoriza reconstruir o texto por aproximação.

## Sétima passagem — avaliação editorial integral do capítulo 7 (2026-11-07)
- **DECISÃO DE MÉTODO AUTORIZADA PELO AUTOR:** usar a versão integral atualmente presente no GitHub como **versão-base para avaliação**, em vez de reconstruir o texto perdido por aproximação. Esta autorização **não equivale a ratificação final** da versão como canônica; solicitar confirmação após apresentar o parecer.
- **ESCOPO LIDO:** `manuscrito/07-o-comite-de-prevencao-de-comites-parte-1.md` e `parte-2.md` integralmente; confrontados com o final do capítulo 6, o interlúdio e o início do capítulo 8.
- **PARECER:** versão atual é narrativamente autossuficiente e editorialmente recomendada para manutenção. O conflito principal é a imposição de controles universais, com a correção simples do texto do portal retida por aprovações; a resolução combina risco proporcional, automação de controles, ADRs e autonomia com responsabilidade.
- **DISTINÇÃO DO CAPÍTULO 6:** capítulo 6 discute ownership, fronteiras de equipes e responsabilidade por produto; capítulo 7 discute governança, proporcionalidade e autorização de mudanças. A transição funciona, com eco intencional do humor sobre comitês no final do capítulo 6.
- **ARCO DE NORA:** reconhece a insuficiência de indicadores de adesão e das certezas precoces; o encerramento sem registro privado é escolha temática consistente com crítica à formalização excessiva, não erro objetivo.
- **CONTINUIDADE:** a reflexão sobre decisões historicamente justificáveis e revisão posterior prepara o interlúdio e o capítulo 8. Não foi identificada contradição causal inequívoca nos trechos comparados.
- **RESSALVA EDITORIAL:** alguns diálogos têm caráter expositivo; isso é sugestão estilística, não erro objetivo, e não autoriza reescrita de texto aprovado.
- **STATUS:** parecer favorável, **aguardando ratificação expressa do autor** para encerrar a divergência entre a versão de 23 procedimentos e a versão atual de 43 comitês. Nenhuma linha narrativa alterada nesta passagem.

## Oitava passagem — ratificação definitiva do capítulo 7 (2026-11-07)
- **APROVAÇÃO EXPRESSA DO AUTOR:** após leitura integral e parecer editorial, o autor confirmou a versão atualmente armazenada no GitHub como **versão canônica e definitiva** do capítulo 7, **“O comitê de prevenção de comitês”**.
- **ARQUIVOS CANÔNICOS:** `manuscrito/07-o-comite-de-prevencao-de-comites-parte-1.md` e `manuscrito/07-o-comite-de-prevencao-de-comites-parte-2.md`, incluindo a abertura com **43 comitês**, a evolução do processo de governança e o encerramento sem registro privado de NORA.
- **DIVERGÊNCIA ENCERRADA POR DECISÃO AUTORAL:** a versão anterior iniciada por **23 procedimentos** não precisa ser recuperada nem reconstruída para a edição final. As observações das passagens sexta e sétima permanecem como histórico de auditoria, mas o status **“pendente de ratificação”** está superado por esta decisão.
- **PRESERVAÇÃO:** nenhuma alteração textual foi feita no capítulo 7. Eventuais mudanças futuras exigem nova aprovação específica. Seguir auditoria de continuidade nos demais capítulos e materiais.

## Nona passagem — continuidade dos capítulos 8–10 e epílogo (2026-11-07)
- **ESCOPO:** leitura estrutural das partes 1 e 2 dos capítulos 8, 9 e 10 e do epílogo; checagem de personagens, introduções e encerramentos. Esta passagem não equivale à revisão literária linha a linha de todos os arquivos.
- **CORRIGIDO — colisão de personagens no capítulo 10, parte 2:** a analista de operações apresentada como **Teresa** na parte 1 era chamada **Ana** em cinco pontos da parte 2. Todas as cinco referências foram corrigidas para **Teresa**; zero ocorrências de `Ana` restantes na parte 2. Commit `cb3e58d`.
- **VERIFICADO — progressão:** capítulo 8 investiga legado e equivalências; capítulo 9 introduz ÍRIS, estabelece suas diferenças de julgamento em relação a NORA e apresenta a rotina **Compensação de Continuidade**; capítulo 10 investiga e administra os riscos da rotina; epílogo retoma NORA e ÍRIS após os acontecimentos. Não se observou inversão causal evidente nessa sequência.
- **VERIFICADO — histórico do capítulo 10:** parte 1 emprega consistentemente a referência a **cinco anos** para a criação/última alteração da rotina, conforme aprovação anterior.
- **PENDÊNCIA:** realizar auditoria de nomes e cronologia em todos os capítulos anteriores e nos dez textos `por-tras-do-caos/`, bem como conferir a versão do apêndice efetivamente aprovada para montagem final.

## Décima passagem — varredura transversal de nomes e materiais complementares (2026-11-07)
- **ESCOPO EFETIVO:** conferência de ocorrências dos nomes canônicos e nomes antigos em todos os **20 arquivos narrativos de `manuscrito/`**, mais o epílogo, e leitura das **10 seções `por-tras-do-caos/`**; inspeção pontual dos fatos técnicos mencionados nesses complementos. Não confundir esta checagem com revisão de cada afirmação literária ou prova final de diagramação.
- **NOMES:** não foram encontradas ocorrências de **Henrique**, **Marcelo Brandão**, **Lívia**, **Teresa Almeida**, **Augusto** ou **Helena Duarte** nos 21 arquivos narrativos conferidos. **Ana Almeida** aparece nos capítulos iniciais associados à cidadã; **Helena** aparece no arco de benefícios e na reunião de ÍRIS; **Teresa** aparece nas duas partes do capítulo 10, sem referências residuais a **Ana** nesse capítulo.
- **CARLOS:** cinco menções no capítulo 1, mantidas por se referirem ao ex-funcionário e não a uma substituição de Helena.
- **SEÇÕES 1–9 DE `por-tras-do-caos/`:** conteúdo e links para o capítulo correspondente compatíveis com os arcos principais verificados. Em particular, a seção 7 descreve a versão canônica dos **43 comitês**, ratificada pelo autor.
- **CORRIGIDO — SEÇÃO 10:** `por-tras-do-caos/10-o-defeito-que-nos-mantem-vivos.md` continha link quebrado para `../rascunhos/` (capítulo já movido para `manuscrito/`) e identificava como **Ana** a analista histórica que é **Teresa**. Ambos corrigidos no commit `e3baacf`; nenhum texto narrativo foi alterado.
- **VALIDAÇÃO FACTUAL PONTUAL:** a indisponibilidade de **43 minutos** citada na seção 10 consta do capítulo 10, parte 2; a revisão de **R$ 1.621** e o trecho aprovado da dupla verificação constam do capítulo 8, parte 1.
- **RESULTADO:** varredura nominal e alinhamento dos dez complementos concluídos, com uma correção documental. **AINDA PENDENTES:** revisão semântica integral cena a cena, conferência completa do apêndice de 32 conceitos, arte final das ilustrações e montagem EPUB/PDF atualizada.

## Décima primeira passagem — auditoria estrutural do apêndice técnico (2026-11-07)
- **DECISÃO CANÔNICA CONFIRMADA:** seleção aprovada de **32 conceitos** em cinco blocos, distribuídos como 6+6+7+5+8, conforme `diretrizes-editoriais/aprovacoes-edicao-final.md` e `apendice-tecnico/revisao-30/DECISAO-32-CONCEITOS.md`.
- **INVENTÁRIO DE VERSÕES:** os cinco arquivos de `apendice-tecnico/` na raiz contêm **49 entradas numeradas (1–49)**, com status histórico de aprovação. Os cinco arquivos em `apendice-tecnico/revisao-30/` contêm **32 entradas (1–32)**, sem lacunas ou duplicações, e seus títulos correspondem à seleção aprovada.
- **DIRETRIZ PARA MONTAGEM:** a **estrutura de 32 entradas** é a referência para o apêndice da edição final; a versão de 49 entradas deve ser preservada como material histórico/de apoio, sem exclusão ou substituição automática.
- **STATUS EDITORIAL AINDA AMBÍGUO:** `DECISAO-32-CONCEITOS.md` registra aprovação da **seleção** de 32 entradas, mas descreve a redação condensada como ainda em revisão; já os arquivos dos blocos II–V exibem o cabeçalho **“APROVADO PELO AUTOR”**, e o bloco I se identifica como versão para revisão. Não confundir aprovação da estrutura com aprovação textual integral sem reconciliar os registros.
- **CONFERÊNCIA DE CONTEÚDO:** os 32 conceitos têm seções **O conceito / Onde aparece / Na história / Avaliação / Lição**, com referência explícita a capítulos e acontecimentos. Os blocos 1–5 cobrem os temas previstos, incluindo governança do capítulo 7 e continuidade do capítulo 10. Esta verificação é estrutural e de plausibilidade, não certificação semântica exaustiva de cada frase.
- **AÇÃO SEGURA:** não editar prosa aprovada nem migrar automaticamente a versão de 49 entradas; documentar o critério de seleção, preservar o histórico e sinalizar a necessidade de reconciliação de status antes da publicação digital.

## Décima segunda passagem — revisão editorial dos cinco blocos condensados (2026-11-07)
- **ESCOPO:** leitura integral dos cinco blocos, conceitos **1–32**, conferência de títulos, precisão técnica geral, cenas citadas e correspondência com a seleção aprovada.
- **PARECER TÉCNICO:** as definições e lições são adequadas como material de estudo introdutório/intermediário. Ressalvas tecnicamente importantes já aparecem no texto: testes de caracterização não provam correção; `timeout` não cancela necessariamente o processamento remoto; `Circuit Breaker` não é apresentado como integralmente implantado; concordância entre IAs não comprova verdade; a autonomia é limitada por contratos e riscos.
- **CENAS CONFERIDAS:** idempotência e comprovantes no capítulo 4; remoção de sete linhas e investigação de legado no capítulo 8; verificação financeira e reconciliação no capítulo 9; Teresa e a rotina de continuidade no capítulo 10. Nenhuma contradição factual inequívoca que exija alterar os 32 verbetes foi identificada nesta revisão.
- **CORREÇÃO EDITORIAL EXECUTADA:** cabeçalhos dos cinco blocos uniformizados para `seleção dos 32 conceitos aprovada pelo autor; redação condensada em revisão`. Os antigos cabeçalhos dos blocos II–V afirmavam aprovação integral sem respaldo documental inequívoco. Atualizado também `DECISAO-32-CONCEITOS.md`, cujo status de redação estava desatualizado.
- **PRESERVAÇÃO:** nenhuma frase explicativa dos 32 conceitos, nenhum capítulo e nenhuma seção `Por trás do caos` foi alterada nesta passagem.
- **STATUS:** revisão técnica e de alinhamento concluída com parecer favorável; **aprovação textual final do apêndice ainda depende de confirmação expressa do autor**. Não confundir isso com a aprovação já existente da seleção e da estrutura.

## Décima terceira passagem — aprovação definitiva do apêndice (2026-11-07)
- **CONFIRMAÇÃO EXPRESSA DO AUTOR:** aprovação integral da redação dos **32 conceitos**, além da seleção e da estrutura já aprovadas.
- **VERSÃO CANÔNICA:** cinco arquivos condensados em `apendice-tecnico/revisao-30/`, conceitos 1–32, aprovados para montagem da edição digital.
- **EXECUÇÃO:** atualizados os cinco cabeçalhos de status para `APROVADO PELO AUTOR` e ratificada a decisão editorial. Nenhum texto explicativo foi modificado.
- **HISTÓRICO:** os cinco arquivos de 49 conceitos em `apendice-tecnico/` permanecem preservados como referência histórica, não como versão de publicação.
- **PRÓXIMA FASE:** montagem e verificação dos arquivos de leitura EPUB e PDF mobile-first a partir dos conteúdos canônicos atuais, sem alterar a narrativa.

## Décima quarta passagem — edição literária aprovada do capítulo 3 (2026-11-07)
- **AUTORIZAÇÃO EXPRESSA:** autor aprovou quatro alterações específicas em `manuscrito/03-dividir-para-complicar-parte-2.md`: (1) abertura sobre fronteiras, (2) benefícios dos microsserviços, (3) reflexão sobre o desenho de Rafael, (4) recapitulação final.
- **EXECUÇÃO:** quatro substituições textuais exatas, cada uma encontrada uma única vez no arquivo; nenhum outro trecho do manuscrito foi modificado.
- **RESULTADO:** parte 2 passou de 21.701 para 19.311 caracteres, redução líquida de 2.390 caracteres (aproximadamente 11%).
- **COMMIT DO MANUSCRITO:** `3f4df8590ede2f9e89d28a2de16c0fdbf668fcf5`.
- **CONTINUIDADE:** preservadas as cenas de Ana Almeida, Marcelo, Rafael, o desenho de cinco retângulos, a descoberta de notificações e a ponte para o capítulo 4.
- **PRÓXIMO PASSO EDITORIAL:** apresentar propostas pontuais para o capítulo 6 ou interlúdio, sem alterar prosa antes de nova aprovação.

## Décima quinta passagem — edição literária aprovada do capítulo 6 (2026-11-07)
- **AUTORIZAÇÃO EXPRESSA:** autor aprovou quatro alterações específicas: (1) inventário das quatro equipes, (2) explicação das quatro propostas, (3) diálogo sobre responsabilidade, (4) reflexão final de NORA.
- **EXECUÇÃO:** duas substituições delimitadas em `manuscrito/06-o-organograma-tambem-compila-parte-1.md` e duas em `manuscrito/06-o-organograma-tambem-compila-parte-2.md`. Demais trechos preservados, inclusive registro privado de NORA.
- **RESULTADO:** parte 1 de 12.845 para 11.850 caracteres (-995); parte 2 de 11.520 para 10.420 (-1.100); redução total de 2.095 caracteres, cerca de 8,6%.
- **COMMITS DO MANUSCRITO:** `2eabde4f868f8a636012a71e71de8b7db83aeb38` (parte 1) e `cee42473cdcbc257e2fba723eb252418941ece62` (parte 2).
- **CONTINUIDADE:** mantidas as cenas do simulador, os conflitos de capacidade e priorização, a decisão de responsabilidade, o registro privado e o encerramento humorístico.
- **PRÓXIMO PASSO EDITORIAL:** revisar o interlúdio ou capítulo 8, apresentando propostas antes de qualquer alteração.

## Décima sexta passagem — edição literária aprovada do interlúdio (2026-11-07)
- **AUTORIZAÇÃO EXPRESSA:** autor aprovou quatro ajustes pontuais em `manuscrito/07-interludio-o-problema-de-estar-certa.md`: (1) reflexão sobre a palavra “sucesso”, (2) custo humano das decisões, (3) expectativas humanas sobre tecnologia, (4) hesitação na conversa final com Marcelo.
- **EXECUÇÃO:** quatro substituições textuais delimitadas, preservando todo o restante do interlúdio, inclusive a investigação de NORA, a conversa dos dois desenvolvedores, o diálogo com Marcelo e o encerramento.
- **RESULTADO:** arquivo de 23.532 para 21.125 caracteres; redução líquida de 2.407 caracteres (aproximadamente 10,2%).
- **COMMIT DO MANUSCRITO:** `09f2251c2c6754d5e4e36d9a0191fefed8a710c0`.
- **PRÓXIMO PASSO EDITORIAL:** revisar capítulo 8, apresentando propostas antes de alterações.

## Décima sétima passagem — edição literária aprovada do capítulo 8 (2026-11-07)
- **AUTORIZAÇÃO EXPRESSA:** autor aprovou quatro ajustes pontuais em `manuscrito/08-ninguem-sabe-por-que-isso-funciona-parte-2.md`: (1) modelo PessoaUnificada, (2) memória de Eduardo, (3) planos de modernização, (4) reflexão sobre documentação.
- **EXECUÇÃO:** quatro substituições textuais delimitadas na parte 2; parte 1 e todos os demais trechos preservados.
- **RESULTADO:** parte 2 de 24.612 para 22.992 caracteres; redução líquida de 1.620 caracteres (aproximadamente 6,6%).
- **COMMIT DO MANUSCRITO:** `f5d8f2dbcc44b528fd123d663b925c59e79b8e93`.
- **CONTINUIDADE:** preservados incidente de Osvaldo Ferreira, recomendação de NORA com 96,4% de confiança, dupla validação histórica, modernização incremental, despedida de Eduardo, registro privado e fechamento.
- **PRÓXIMO PASSO EDITORIAL:** avaliar fluidez global após as revisões dos capítulos 3, 6, 8 e interlúdio; apresentar eventuais propostas antes de editar.
