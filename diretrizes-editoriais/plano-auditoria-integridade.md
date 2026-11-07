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
