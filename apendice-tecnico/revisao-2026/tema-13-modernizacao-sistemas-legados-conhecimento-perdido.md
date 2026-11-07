# Modernização de sistemas legados e conhecimento perdido — Quando o passado ainda está em produção

*O código é antigo, a documentação desapareceu e ninguém sabe por que aquela condição existe. Naturalmente, a primeira sugestão é removê-la.*

Um **sistema legado (*legacy system*)** é um sistema existente que continua sustentando processos relevantes, mas cuja evolução pode ser dificultada por decisões históricas, tecnologias, dependências ou limitações de conhecimento.

Um legado não é necessariamente um sistema ruim. Pode ser estável, confiável e essencial ao negócio.

O desafio surge quando a organização precisa modificá-lo sem compreender completamente as consequências.

Modernizar esses sistemas exige mais do que substituir tecnologias: exige recuperar conhecimento, preservar comportamentos importantes e reduzir riscos durante a transformação.

## 1. O que torna um sistema legado?

A idade, isoladamente, não determina se um sistema é problemático.

Um software desenvolvido há vinte anos pode continuar atendendo adequadamente às necessidades da organização. Por outro lado, uma aplicação recente pode apresentar dificuldades graves de manutenção.

Algumas características frequentemente associadas a legados são:

- Dependências difíceis de modificar.
- Tecnologias ou componentes com suporte limitado.
- Conhecimento concentrado em poucas pessoas.
- Documentação insuficiente ou desatualizada.
- Regras de negócio incorporadas ao código, sem explicação de sua origem.
- Risco elevado de regressões durante alterações.

O problema central não é simplesmente o tempo de existência, mas a dificuldade de compreender, operar e evoluir o sistema com segurança.

**Cuidado:** classificar um sistema como legado não significa que ele precise ser substituído. A decisão depende dos riscos, custos e necessidades reais de evolução.

## 2. O conhecimento que existe apenas no código

Ao longo dos anos, sistemas acumulam regras que nem sempre permanecem documentadas.

Algumas surgiram para atender exigências legais. Outras foram criadas para corrigir situações excepcionais, compensar limitações de integrações ou preservar comportamentos esperados pelos usuários.

Com a saída de profissionais e a perda de registros históricos, essas decisões podem deixar de ser compreendidas.

Parte desse conhecimento é **tácita (*tacit knowledge*)**: depende da experiência das pessoas e não foi suficientemente explicitada. Outra parte permanece incorporada ao comportamento do sistema, mesmo depois que os profissionais que conheciam suas razões deixam a organização.

Quando esse conhecimento desaparece, o próprio código pode se tornar a principal evidência das decisões anteriores.

**Cuidado:** uma condição aparentemente redundante pode representar uma regra de negócio ainda necessária. Removê-la sem investigação pode reintroduzir problemas que haviam sido resolvidos anos antes.

## 3. Modernizar não é necessariamente reescrever

A modernização (*modernization*) busca melhorar a capacidade de um sistema continuar atendendo às necessidades atuais e futuras.

Isso pode envolver atualização tecnológica, reorganização de componentes, melhoria de testes, redução de dependências ou substituição gradual de funcionalidades.

Uma **reescrita completa (*rewrite*)** é apenas uma das alternativas possíveis — e frequentemente uma das mais arriscadas.

Reescrever exige recuperar não apenas os requisitos conhecidos, mas também comportamentos que surgiram ao longo da operação e que podem não estar documentados.

O novo sistema pode apresentar uma arquitetura tecnicamente superior e, ainda assim, deixar de atender situações que o anterior tratava corretamente.

**Cuidado:** substituir código antigo por código novo não garante redução de complexidade. Sem compreender o domínio e as dependências existentes, a organização pode apenas reconstruir os mesmos problemas com tecnologias diferentes.

## 4. Modernização incremental e o padrão Strangler Fig

Uma alternativa à substituição integral é modernizar o sistema progressivamente.

O padrão **Strangler Fig**, frequentemente traduzido como *padrão de substituição gradual*, propõe introduzir novas funcionalidades ou implementações ao redor do sistema existente e transferir responsabilidades para elas de forma controlada.

Com o tempo, partes do legado deixam de ser utilizadas e podem ser desativadas.

Essa abordagem permite reduzir o tamanho das mudanças, validar comportamentos e aprender durante a transição.

Entretanto, pode exigir mecanismos temporários de integração, roteamento e sincronização entre o sistema antigo e o novo.

**Cuidado:** uma migração incremental sem critérios claros de conclusão pode criar dois sistemas permanentes, aumentando os custos e a complexidade em vez de reduzi-los.

## 5. Caracterização antes da mudança

Quando o comportamento de um sistema é pouco conhecido, é importante compreender o que ele realmente faz antes de modificá-lo.

Uma técnica útil são os **testes de caracterização (*characterization tests*)**, que registram comportamentos observados no sistema existente.

Eles ajudam a identificar alterações inesperadas durante a modernização.

Entretanto, esses testes não demonstram necessariamente que o comportamento antigo está correto. Podem registrar inclusive defeitos históricos.

Por isso, é necessário distinguir entre:

- Comportamentos que precisam ser preservados.
- Comportamentos que precisam ser corrigidos.
- Comportamentos que perderam sua finalidade e podem ser eliminados.

Essa classificação exige investigação técnica e participação de pessoas que conhecem o negócio e a operação.

**Cuidado:** preservar tudo indiscriminadamente perpetua problemas. Alterar tudo indiscriminadamente pode destruir regras essenciais. Modernizar exige compreender essa diferença.

## 6. Continuidade operacional e transferência de conhecimento

A dependência de poucas pessoas representa um risco importante para a continuidade de um sistema.

Quando apenas um profissional compreende determinada rotina, a organização pode enfrentar dificuldades para corrigir incidentes, realizar alterações ou recuperar o serviço após uma falha.

A redução desse risco envolve documentação útil, registros de decisões, testes, compartilhamento de conhecimento e participação de diferentes profissionais na manutenção.

O objetivo não é documentar cada linha de código, mas tornar compreensíveis as decisões, regras e procedimentos necessários para operar e evoluir o sistema.

Também é importante registrar por que determinadas soluções foram adotadas, especialmente quando parecem contrariar práticas atuais.

**Cuidado:** documentação não substitui experiência prática. Conhecimento precisa ser compartilhado e exercitado, não apenas armazenado em um repositório que ninguém consulta.

## 7. Quando modernizar — e quando preservar

A decisão de modernizar deve considerar o valor do sistema, os riscos de sua manutenção, os custos da mudança e as necessidades futuras.

Algumas intervenções podem trazer benefícios significativos sem alterar a arquitetura inteira: automatizar testes, atualizar dependências críticas, melhorar a observabilidade ou isolar componentes problemáticos.

Em outros casos, limitações estruturais podem justificar mudanças mais profundas.

O importante é que a decisão seja orientada por problemas concretos, e não apenas pelo desejo de utilizar tecnologias mais recentes.

**A lição central:** sistemas legados carregam não apenas código antigo, mas decisões, exceções e conhecimento acumulado. Modernizá-los exige distinguir aquilo que precisa evoluir daquilo que continua existindo por boas razões — mesmo quando essas razões já foram esquecidas.
