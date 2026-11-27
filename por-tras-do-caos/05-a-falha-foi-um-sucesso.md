# Por trás do caos — Capítulo 5

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 5 — A falha foi um sucesso](../manuscrito/05-a-falha-foi-um-sucesso-parte-1.md).

A implantação do novo processo de atendimento foi tecnicamente bem-sucedida. O sistema estava disponível, os testes passaram e as metas operacionais foram alcançadas. Mesmo assim, a quantidade de benefícios concedidos diminuiu significativamente.

**Verificação e validação (V&V).** Verificação pergunta se construímos o sistema conforme os requisitos definidos. Validação pergunta se construímos o sistema adequado à necessidade real. A Ordem verificou corretamente o funcionamento do novo processo, mas não validou suficientemente se o encerramento automático das solicitações incompletas contribuía para melhorar o atendimento aos cidadãos.

**Requisitos e conhecimento tácito.** Os funcionários da central de atendimento conheciam dificuldades enfrentadas pelos cidadãos que não haviam sido consideradas na definição dos requisitos. Compreender um processo exige investigar não apenas suas regras formais, mas também o contexto em que são aplicadas. A participação dos usuários e dos profissionais que executam o trabalho ajuda a identificar necessidades que dificilmente aparecem em especificações elaboradas de forma isolada.

**Indicadores técnicos versus resultados de negócio.** Disponibilidade e taxa de erros medem aspectos importantes da operação. Tempo de conclusão e quantidade de solicitações encerradas medem a eficiência do processo. Nenhum desses indicadores demonstra, isoladamente, que o produto alcançou seu propósito. É necessário avaliar também os resultados efetivamente entregues aos usuários.

**Lei de Goodhart.** Quando uma medida se transforma em uma meta, pode deixar de representar adequadamente aquilo que pretendia medir. Ao transformar a redução de pendências em um objetivo, a Ordem passou a encerrar solicitações sem necessariamente resolver as necessidades que as originaram. O indicador melhorou, mas o resultado que deveria representar piorou.

Um sistema pode executar perfeitamente a solução errada. Por isso, qualidade não se resume à correção do código: inclui a adequação dos requisitos e a responsabilidade pelas consequências.
