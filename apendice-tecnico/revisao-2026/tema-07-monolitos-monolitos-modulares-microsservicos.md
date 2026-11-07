# Monólitos, monólitos modulares e microsserviços

*Dividir um sistema em vários serviços não significa, necessariamente, dividir sua complexidade.*

A organização de uma aplicação influencia como ela é desenvolvida, implantada, operada e modificada. Entre as abordagens mais conhecidas estão o monólito, o monólito modular e a arquitetura de microsserviços.

Nenhuma delas é universalmente superior. A escolha depende do domínio, das necessidades de escala, da autonomia das equipes e da capacidade operacional da organização.

## 1. Monólito — Uma aplicação, uma unidade de implantação

Um **monólito (*monolith*)** é uma aplicação cujas funcionalidades são normalmente desenvolvidas e implantadas como uma única unidade.

Isso não significa que todo o código esteja misturado. Um monólito pode apresentar boa separação de responsabilidades, organização interna e testes automatizados.

Entre suas vantagens estão a simplicidade de implantação, a comunicação interna direta e a facilidade de manter determinadas operações e transações dentro de um mesmo processo.

Por outro lado, à medida que cresce, pode se tornar difícil modificar, testar ou implantar partes isoladamente, especialmente quando suas responsabilidades estão mal organizadas.

**Cuidado:** o problema não é necessariamente ser monolítico, mas possuir dependências internas tão intensas que qualquer alteração afete o sistema inteiro.

## 2. Monólito modular — Uma aplicação com fronteiras internas claras

Um **monólito modular (*modular monolith*)** mantém uma unidade de implantação, mas organiza suas funcionalidades em módulos com responsabilidades e interfaces bem definidas.

Cada módulo procura preservar suas regras e detalhes internos, reduzindo dependências indevidas entre diferentes partes do sistema.

Essa abordagem combina algumas vantagens operacionais do monólito com benefícios da modularidade, como maior facilidade de compreensão, testes e evolução.

Também pode facilitar uma futura separação de componentes em serviços independentes, caso essa necessidade se torne real.

**Cuidado:** a modularidade não aparece apenas porque o projeto possui pastas ou pacotes separados. É necessário respeitar as fronteiras definidas e controlar o acesso aos dados e comportamentos internos dos módulos.

## 3. Microsserviços — Autonomia acompanhada de responsabilidades

Uma arquitetura de **microsserviços (*microservices*)** organiza o sistema em serviços menores, com responsabilidades delimitadas e possibilidade de implantação independente.

Cada serviço pode evoluir e ser escalado conforme suas necessidades, permitindo maior autonomia para equipes que possuem domínios bem definidos.

Entretanto, a distribuição introduz dificuldades que não existem da mesma forma em uma aplicação executada em um único processo: comunicação pela rede, falhas parciais, latência, observabilidade distribuída e coordenação de dados.

Operações que antes utilizavam transações locais podem exigir mecanismos específicos para preservar a consistência entre serviços.

**Cuidado:** dividir uma aplicação em muitos serviços sem estabelecer fronteiras adequadas pode produzir um *monólito distribuído*: um sistema que mantém o acoplamento de um monólito, mas incorpora a complexidade operacional de uma arquitetura distribuída.

## 4. Comparação entre as abordagens

| Característica | Monólito | Monólito modular | Microsserviços |
|---|---|---|---|
| Implantação | Conjunta | Conjunta | Independente por serviço |
| Separação interna | Variável | Explícita | Por fronteiras de serviço |
| Comunicação | Principalmente local | Principalmente local | Frequentemente pela rede |
| Complexidade operacional | Geralmente menor | Geralmente menor | Geralmente maior |
| Escalabilidade independente | Limitada | Limitada | Possível por serviço |
| Autonomia de equipes | Depende da organização | Favorecida por módulos | Favorecida por serviços bem delimitados |

Essas características são tendências, não garantias. Uma arquitetura de microsserviços mal organizada pode oferecer menos autonomia prática do que um monólito modular bem estruturado.

## 5. Quando cada abordagem faz sentido?

O **monólito** pode ser apropriado para sistemas pequenos ou médios, produtos em validação e equipes que precisam privilegiar simplicidade de desenvolvimento e operação.

O **monólito modular** é uma alternativa relevante quando o domínio possui responsabilidades distintas, mas ainda não existe justificativa suficiente para assumir os custos de uma arquitetura distribuída.

Os **microsserviços** podem ser vantajosos quando diferentes partes do sistema apresentam necessidades próprias de implantação, escala, disponibilidade ou evolução, e a organização dispõe de capacidade para operar serviços distribuídos.

A quantidade de usuários ou o tamanho do código, isoladamente, não determinam a arquitetura ideal.

## 6. O custo oculto da distribuição

Uma chamada entre componentes de uma mesma aplicação costuma ser diferente de uma chamada entre serviços remotos.

A comunicação pela rede introduz falhas parciais, latência e dependências operacionais que precisam ser tratadas explicitamente.

Além disso, a autonomia de implantação pode ser comprometida quando os serviços compartilham diretamente bancos de dados, exigem liberações coordenadas ou dependem de alterações simultâneas.

Por isso, **microsserviços exigem tanto maturidade organizacional quanto técnica**. Ferramentas de infraestrutura ajudam, mas não substituem boas fronteiras de responsabilidade.

## 7. Evoluir a arquitetura sem seguir modismos

Uma arquitetura não precisa começar distribuída para se tornar escalável ou sustentável.

Frequentemente, é possível iniciar com uma aplicação bem modularizada e separar serviços apenas quando surgirem necessidades concretas que justifiquem essa mudança.

Também não existe obrigação de migrar um monólito funcional para microsserviços. A migração deve demonstrar benefícios proporcionais aos custos, riscos e dificuldades operacionais introduzidos.

**A lição central:** monólitos, monólitos modulares e microsserviços são maneiras diferentes de organizar responsabilidades e dependências. A melhor escolha não é a mais moderna ou distribuída, mas aquela que atende às necessidades reais com complexidade proporcional.
