# DDD e contextos delimitados — A arquitetura começa no negócio

*Um sistema pode estar tecnicamente bem organizado e, ainda assim, representar mal o negócio que deveria atender.*

Uma das maiores dificuldades no desenvolvimento de software é transformar regras, processos e conceitos de negócio em modelos compreensíveis e consistentes.

O **DDD (*Domain-Driven Design*, ou Projeto Orientado ao Domínio)** é uma abordagem popularizada por Eric Evans que coloca o conhecimento do domínio no centro das decisões de modelagem e desenvolvimento.

Seu objetivo não é simplesmente organizar classes ou escolher uma arquitetura. É aproximar o software da realidade do negócio, especialmente quando essa realidade envolve regras complexas.

## 1. Domínio — O problema que o software precisa compreender

O **domínio (*domain*)** representa a área de conhecimento e as atividades que o sistema procura atender.

Em um sistema de benefícios, por exemplo, podem existir conceitos como saldo, benefício, elegibilidade, utilização e prestação de contas. Cada um possui regras e significados que precisam ser compreendidos antes de serem transformados em funcionalidades.

O DDD valoriza a colaboração contínua entre especialistas do negócio e profissionais de tecnologia. A intenção é construir um entendimento compartilhado, evitando que decisões técnicas sejam tomadas sobre interpretações incorretas das regras.

**Cuidado:** DDD não significa que toda regra de negócio precise se transformar em uma estrutura sofisticada de objetos. A modelagem deve ser proporcional à complexidade do domínio.

## 2. Linguagem ubíqua — Todos estão falando da mesma coisa?

A **linguagem ubíqua (*ubiquitous language*)** é um vocabulário compartilhado entre especialistas do negócio e equipe técnica, utilizado em conversas, documentação e implementação.

Quando uma expressão possui significados diferentes para áreas distintas, o risco de erros aumenta.

Por exemplo, o termo “saldo disponível” pode representar valores diferentes para um sistema de autorização e para um sistema contábil. Tratar esses significados como idênticos pode gerar inconsistências.

A linguagem ubíqua busca tornar essas diferenças explícitas.

**Cuidado:** não se trata de impor um único dicionário para toda a organização. O mesmo termo pode ter significados legítimos em contextos diferentes.

## 3. Contextos delimitados — Onde um conceito possui significado próprio?

Um **contexto delimitado (*bounded context*)** define uma fronteira dentro da qual determinado modelo e sua linguagem possuem significados consistentes.

Um mesmo conceito pode assumir regras diferentes dependendo do contexto em que é utilizado.

Por exemplo, um “cliente” pode representar uma organização contratante no contexto comercial, uma entidade responsável por pagamentos no contexto financeiro e um usuário atendido no contexto de suporte.

Essas representações não precisam ser idênticas. Cada contexto deve preservar as informações e regras necessárias às suas responsabilidades.

Um contexto delimitado é uma fronteira na qual determinado modelo de domínio e sua linguagem possuem significado consistente. Ele não precisa corresponder a um microsserviço, banco de dados ou equipe.

## 4. DDD estratégico e tático — Duas perspectivas complementares

O DDD costuma ser dividido em duas perspectivas.

**DDD estratégico** ajuda a identificar os diferentes domínios, suas fronteiras e as relações entre contextos. Seu foco está na organização do negócio e nas decisões de arquitetura.

**DDD tático** apresenta padrões de modelagem para implementar regras dentro de um contexto, como entidades, objetos de valor, agregados, repositórios e serviços de domínio.

| Conceito | Finalidade |
|---|---|
| **Entidade (*Entity*)** | Representar algo cuja identidade permanece relevante ao longo do tempo |
| **Objeto de valor (*Value Object*)** | Representar um conceito definido por seus atributos e sem identidade própria relevante |
| **Agregado (*Aggregate*)** | Definir um limite de consistência e proteção de invariantes de negócio |
| **Repositório (*Repository*)** | Oferecer acesso a agregados sem expor detalhes de persistência |
| **Serviço de domínio (*Domain Service*)** | Representar uma operação de domínio que não pertence naturalmente a uma entidade ou objeto de valor |

Esses padrões são ferramentas, não uma lista obrigatória de componentes.

## 5. Subdomínios — Onde está o diferencial do negócio?

DDD também ajuda a distinguir partes do domínio segundo sua relevância estratégica.

O **domínio principal (*core domain*)** concentra capacidades que diferenciam o negócio e merecem atenção especial.

Os **subdomínios de suporte (*supporting subdomains*)** viabilizam atividades necessárias, mas não representam necessariamente o principal diferencial competitivo.

Os **subdomínios genéricos (*generic subdomains*)** abrangem capacidades comuns a muitas organizações, que podem eventualmente ser atendidas por soluções existentes.

Essa classificação auxilia decisões sobre investimento, especialização e adoção de produtos de terceiros.

**Cuidado:** a importância estratégica pode mudar. Um subdomínio considerado genérico hoje pode se tornar relevante para a diferenciação futura.

## 6. Como os contextos se relacionam?

Contextos delimitados raramente operam isoladamente. Eles precisam trocar informações e coordenar processos.

O **mapa de contextos (*context map*)** descreve essas relações, incluindo dependências e formas de integração.

Entre as estratégias possíveis estão contratos compartilhados, tradução entre modelos e a **camada anticorrupção (*Anti-Corruption Layer*)**, que protege um contexto contra conceitos e estruturas externas incompatíveis com seu próprio modelo.

O objetivo não é eliminar integrações, mas impedir que a linguagem e as decisões de um sistema contaminem indevidamente as responsabilidades de outro.

**Cuidado:** criar uma camada de tradução para toda comunicação pode introduzir complexidade desnecessária. A proteção deve responder a diferenças reais entre modelos.

## 7. DDD não é sinônimo de microsserviços

DDD pode orientar a definição de fronteiras de microsserviços, mas não exige arquitetura distribuída.

É perfeitamente possível aplicar DDD em um monólito modular, preservando contextos delimitados dentro de uma única aplicação.

Da mesma forma, utilizar microsserviços não significa que os limites de domínio foram corretamente identificados.

A distribuição técnica deve decorrer de necessidades concretas de autonomia, escala e operação, e não apenas da existência de diferentes contextos.

## 8. Quando DDD faz sentido?

DDD costuma oferecer maior valor em sistemas com regras de negócio complexas, conceitos ambíguos, diferentes áreas envolvidas e evolução frequente das políticas do domínio.

Em aplicações simples, predominantemente cadastrais ou com poucas regras, a aplicação completa de padrões táticos pode representar um custo maior que seus benefícios.

Nesses casos, práticas como linguagem compartilhada e delimitação clara de responsabilidades ainda podem ser úteis, mesmo sem a adoção formal de todos os padrões de DDD.

**A lição central:** DDD não começa pela tecnologia, mas pela compreensão do negócio. Bons modelos tornam regras e significados explícitos; bons limites impedem que conceitos diferentes sejam tratados como se fossem iguais.
