# Por trás do caos — Capítulo 8

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 8 — Ninguém sabe por que isso funciona](../manuscrito/08-ninguem-sabe-por-que-isso-funciona-parte-1.md). A narrativa aprovada permanece inalterada.

A Ordem removeu sete linhas aparentemente redundantes e provocou pagamentos indevidos. O código era simples, mas escondia uma proteção criada durante uma migração antiga. A falha não estava apenas na implementação: estava na perda do conhecimento necessário para compreendê-la.

**Testes de caracterização (Characterization Tests).** Antes de modificar um sistema legado pouco compreendido, esses testes registram seu comportamento atual. Eles não comprovam que o comportamento está correto; ajudam a identificar o que mudou e quais diferenças precisam ser investigadas. Na Ordem, a ausência dessa proteção permitiu que sete linhas aparentemente redundantes fossem removidas sem que sua verdadeira finalidade fosse compreendida.

**DDD (Domain-Driven Design — Projeto Orientado ao Domínio).** A entidade PessoaUnificada tentava representar conceitos diferentes com um único modelo. O DDD propõe compreender o negócio e estabelecer contextos delimitados (*Bounded Contexts*), nos quais os conceitos possuem significados claros. Cadastro, elegibilidade e pagamento podem compartilhar informações sem precisar compartilhar todas as suas regras e representações.

**Modernização incremental (Strangler Fig Pattern).** Em vez de reescrever todo o motor, a equipe escolheu um fluxo, criou uma camada de tradução (*Anti-Corruption Layer — ACL*) e executou os cálculos em paralelo para comparar resultados. Essa abordagem permite substituir capacidades gradualmente, investigar divergências e limitar os riscos de migração.

Modernizar não significa apagar o passado. Significa compreender quais decisões ainda protegem o sistema, quais se tornaram obstáculos e como substituí-las sem perder o conhecimento que carregam.
