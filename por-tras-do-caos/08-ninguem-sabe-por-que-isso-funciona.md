# Por trás do caos — Capítulo 8

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 8 — Ninguém sabe por que isso funciona](../manuscrito/08-ninguem-sabe-por-que-isso-funciona-parte-1.md).

A mesma versão do motor autorizou o pagamento de Osvaldo em produção e o recusou no primeiro teste de Júlia. Ao cadastrar mãe e filho em homologação, ela criou duas pessoas com identificadores novos. Em produção, a pensão da mãe ainda guardava uma referência municipal antiga cujo número coincidia com o cadastro atual do filho. Para reproduzir o incidente, foi preciso reconstruir esse vínculo.

**Engenharia reversa.** A equipe partiu do depósito, comparou os comprovantes e seguiu as referências até descobrir quem o motor consultava em cada etapa. Depois repetiu a operação com os mesmos dados, alterando apenas as sete linhas investigadas. Sem a segunda consulta, o motor autorizou o pagamento. Com ela, encaminhou a divergência para análise manual. O experimento revelou o que o código fazia. Eduardo acrescentou uma informação que nenhuma execução poderia fornecer: por que a equipe havia escolhido essa proteção quando ainda precisava manter os pagamentos em dia.

**Limites dos testes e da confiança.** No exemplo que NORA escolheu para defender sua recomendação, a primeira consulta já bastava para recusar o pagamento. A versão antiga e a modificada produziriam o mesmo resultado mesmo que a segunda consulta fosse indispensável em outros casos. A pergunta que faltou fazer antes da implantação era simples: em qual dos nossos testes retirar essa verificação mudaria a decisão? NORA não encontrou nenhum. Os 96,4% de confiança atribuídos à recomendação escondiam essa lacuna.

**Testes de caracterização.** Esses testes registram o comportamento observado para que uma alteração posterior possa revelar diferenças. No caso de Osvaldo, Júlia preservou nos dados anonimizados a coincidência entre os identificadores e verificou dois efeitos: o pedido chegava à análise manual e nenhuma ordem de pagamento era emitida. Ao repetir a remoção das sete linhas, o teste falhou. Já nas três divergências do processamento paralelo, reproduzir a diferença era só o primeiro passo. Para definir o resultado esperado, a equipe ainda precisava entender qual regra do benefício se aplicava.

**DDD (Domain-Driven Design — Projeto Orientado ao Domínio).** A entidade PessoaUnificada tentava representar conceitos diferentes com um único modelo. O DDD propõe compreender o negócio e estabelecer contextos delimitados (*Bounded Contexts*), nos quais os conceitos possuem significados claros. Cadastro, elegibilidade e pagamento podem compartilhar informações sem precisar compartilhar todas as suas regras e representações.

**Modernização incremental (Strangler Fig Pattern).** Em vez de reescrever todo o motor, a equipe escolheu um fluxo, criou uma camada de tradução (*Anti-Corruption Layer — ACL*) e executou os cálculos em paralelo para comparar resultados. Essa abordagem permite substituir capacidades gradualmente, investigar divergências e limitar os riscos de migração.

Modernizar não significa apagar o passado. Significa compreender quais decisões ainda protegem o sistema, quais se tornaram obstáculos e como substituí-las sem perder o conhecimento que carregam.
