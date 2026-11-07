# SOLID — cinco princípios, não cinco mandamentos

SOLID reúne cinco princípios de projeto de software, especialmente associados à programação orientada a objetos. Seu objetivo é ajudar a construir componentes compreensíveis, testáveis e capazes de evoluir sem que pequenas mudanças provoquem efeitos inesperados em todo o sistema.

A sigla foi popularizada por Michael Feathers a partir de princípios difundidos por Robert C. Martin. Embora bastante conhecidos, esses princípios não devem ser interpretados como regras universais nem como uma obrigação de criar interfaces e classes para tudo.

## S — Single Responsibility Principle (SRP)

*Tradução: Princípio da Responsabilidade Única.*

Um componente deve possuir uma responsabilidade bem definida, associada a um motivo coerente para mudar.

Isso não significa que uma classe deva executar apenas uma operação. Significa evitar reunir responsabilidades que evoluem por razões independentes.

Por exemplo, uma classe responsável por calcular uma tarifa não deveria necessariamente controlar também o envio de e-mails e a geração de relatórios.

**Cuidado:** dividir excessivamente responsabilidades pode produzir dezenas de componentes pequenos, difíceis de localizar e compreender.

## O — Open/Closed Principle (OCP)

*Tradução: Princípio Aberto/Fechado.*

Componentes devem permitir extensão de comportamento sem exigir alterações constantes em seu funcionamento existente.

Uma estratégia é definir pontos de extensão para comportamentos que realmente variam, preservando o código que já está estável.

**Cuidado:** não significa que código existente nunca possa ser modificado. Criar mecanismos de extensão para necessidades hipotéticas contraria o YAGNI.

## L — Liskov Substitution Principle (LSP)

*Tradução: Princípio da Substituição de Liskov.*

Uma implementação deve poder substituir outra que cumpra o mesmo contrato sem comprometer o comportamento esperado pelos consumidores.

Não basta compartilhar uma interface ou uma relação de herança. É necessário respeitar as garantias comportamentais do contrato, incluindo pré-condições, pós-condições e invariantes relevantes.

**Cuidado:** uma hierarquia pode compilar corretamente e ainda assim violar expectativas de comportamento. Herança não garante substituibilidade.

## I — Interface Segregation Principle (ISP)

*Tradução: Princípio da Segregação de Interfaces.*

Consumidores não devem ser obrigados a depender de operações que não utilizam.

Interfaces menores e orientadas às necessidades reais de seus consumidores podem reduzir dependências e facilitar mudanças.

**Cuidado:** fragmentar interfaces indiscriminadamente também aumenta a complexidade. A separação deve refletir necessidades distintas, não uma regra sobre quantidade de métodos.

## D — Dependency Inversion Principle (DIP)

*Tradução: Princípio da Inversão de Dependências.*

Componentes responsáveis por políticas importantes do sistema não deveriam depender diretamente de detalhes técnicos voláteis. Ambos podem depender de abstrações adequadas ao domínio.

Isso permite, por exemplo, que uma regra de negócio não fique diretamente vinculada à tecnologia utilizada para persistir informações.

**Cuidado:** inversão de dependências não é sinônimo de usar um contêiner de injeção de dependências. Tampouco exige criar uma interface para cada classe.

## Como os cinco princípios se complementam

| Princípio | Pergunta essencial |
|---|---|
| **SRP** | Este componente reúne responsabilidades que mudam por motivos diferentes? |
| **OCP** | Conseguimos acrescentar variações relevantes sem alterar repetidamente o comportamento estável? |
| **LSP** | Uma implementação pode substituir outra sem violar o contrato esperado? |
| **ISP** | Estamos obrigando consumidores a depender de operações desnecessárias? |
| **DIP** | As regras importantes estão excessivamente dependentes de detalhes técnicos? |

## Separação de responsabilidades e composição em vez de herança

Dois conceitos complementam SOLID.

**Separação de responsabilidades (*Separation of Concerns*)** recomenda organizar diferentes interesses do sistema de forma que possam ser compreendidos e modificados com interferência mínima entre si. É uma orientação mais ampla do que o SRP, pois também se aplica a módulos, camadas e subsistemas.

**Composição em vez de herança (*Composition over Inheritance*)** recomenda considerar a combinação de componentes como alternativa à criação de hierarquias rígidas. A composição frequentemente oferece maior flexibilidade, mas a herança continua adequada quando existe uma relação legítima de especialização e substituição.

Nenhuma dessas técnicas deve ser aplicada mecanicamente.

## Quando SOLID ajuda — e quando atrapalha

SOLID é particularmente útil quando um sistema possui regras de negócio complexas, mudanças frequentes, múltiplas implementações ou dependências técnicas que dificultam testes e evolução.

Entretanto, sua aplicação excessiva pode gerar abstrações prematuras, interfaces sem finalidade clara, hierarquias artificiais e navegação difícil pelo código.

Os princípios precisam ser equilibrados com DRY, KISS e YAGNI. Uma arquitetura não se torna melhor simplesmente por apresentar mais interfaces, camadas ou padrões de projeto.

**A lição central:** SOLID ajuda a organizar responsabilidades e dependências para facilitar mudanças. Seu valor está na qualidade das decisões de projeto, não na quantidade de abstrações criadas.
