# Acoplamento, coesão e modularidade

*Como organizar um sistema para que suas partes possam evoluir sem transformar cada mudança em uma reação em cadeia.*

Um sistema pode funcionar corretamente e, ainda assim, ser difícil de manter. Muitas vezes, o problema não está na qualidade de cada componente isoladamente, mas na maneira como suas responsabilidades e dependências foram organizadas.

Três conceitos ajudam a compreender essa situação: **acoplamento, coesão e modularidade**.

## 1. Acoplamento — O quanto as partes dependem umas das outras?

Acoplamento (*coupling*) representa o grau de dependência entre componentes de um sistema.

Quanto mais um componente precisa conhecer os detalhes internos de outro, maior tende a ser o impacto de alterações.

O **baixo acoplamento** é desejável porque facilita mudanças, testes e substituições. Uma alteração em determinado módulo não deveria exigir modificações desnecessárias em vários outros.

Por exemplo, quando uma regra de negócio depende diretamente de detalhes de um banco de dados específico, uma mudança na persistência pode afetar o comportamento da aplicação. Separar essas responsabilidades pode reduzir essa dependência.

Entretanto, baixo acoplamento não significa ausência de comunicação. Componentes precisam colaborar para produzir resultados.

**Cuidado:** tentar eliminar todas as dependências pode introduzir interfaces, eventos e camadas artificiais, tornando o sistema mais complexo. Além disso, serviços distribuídos podem continuar fortemente acoplados por contratos, dados e exigências de disponibilidade, mesmo executando em processos separados.

## 2. Coesão — As responsabilidades fazem sentido juntas?

Coesão (*cohesion*) representa o quanto as responsabilidades de um componente estão relacionadas entre si.

Um componente com **alta coesão** concentra comportamentos que pertencem a uma mesma responsabilidade ou finalidade.

Um módulo de faturamento, por exemplo, pode reunir operações relacionadas ao cálculo e à consolidação de cobranças. Incluir nele a administração de usuários ou a configuração visual do portal provavelmente reduziria sua coesão.

Alta coesão favorece a compreensão do sistema, pois torna mais previsível onde determinada regra deve estar.

**Cuidado:** coesão não significa criar componentes minúsculos. Dividir uma responsabilidade coerente em várias partes pode aumentar a quantidade de dependências sem melhorar o projeto.

## 3. Modularidade — Como dividir o sistema em partes compreensíveis?

Modularidade (*modularity*) é a organização do sistema em unidades com responsabilidades e fronteiras definidas.

Um módulo deve oferecer funcionalidades claras e, sempre que possível, proteger seus detalhes internos de implementação.

Essa organização permite que equipes compreendam, testem e modifiquem partes do sistema sem precisar conhecer todos os seus detalhes.

A modularidade independe da forma de implantação: pode existir tanto em uma aplicação monolítica quanto em sistemas distribuídos.

**Cuidado:** criar módulos apenas para distribuir arquivos ou classes não garante modularidade. As fronteiras precisam refletir responsabilidades reais, e não apenas uma organização visual do código.

## 4. Como os três conceitos se complementam

| Conceito | Pergunta essencial | Objetivo |
|---|---|---|
| **Acoplamento** | Quanto uma parte depende das outras? | Reduzir dependências desnecessárias |
| **Coesão** | As responsabilidades deste componente pertencem umas às outras? | Manter responsabilidades relacionadas |
| **Modularidade** | As fronteiras entre as partes estão bem definidas? | Facilitar compreensão e evolução |

Em geral, buscamos **alta coesão, baixo acoplamento e fronteiras modulares coerentes**.

Mas esses objetivos não devem ser perseguidos isoladamente. Uma tentativa de reduzir acoplamento pode aumentar a complexidade de comunicação; uma divisão excessiva pode prejudicar a coesão; e uma modularização mal planejada pode criar dependências circulares.

## 5. Quando esses conceitos são especialmente importantes?

Eles ganham relevância quando o sistema cresce, novas equipes passam a trabalhar sobre o mesmo código, diferentes funcionalidades evoluem em ritmos distintos ou alterações pequenas começam a provocar impactos inesperados.

Alguns sinais de problemas estruturais são:

- Uma mudança simples exige alterações em muitos módulos.
- Regras de negócio estão espalhadas por diferentes componentes.
- Existem dependências circulares difíceis de eliminar.
- É necessário compreender grande parte do sistema para modificar uma funcionalidade isolada.
- Os limites entre responsabilidades não são claros.

Esses sinais não determinam automaticamente qual arquitetura deve ser adotada. Eles indicam que a distribuição de responsabilidades e dependências merece revisão.

## 6. O equilíbrio entre independência e colaboração

A organização ideal não é aquela em que todos os componentes são completamente independentes. Isso seria incompatível com a própria natureza de um sistema, cujas partes precisam colaborar.

O objetivo é criar dependências **intencionais, explícitas e proporcionais às necessidades**.

Uma boa fronteira permite que detalhes internos mudem sem obrigar todos os consumidores a mudar junto. Ao mesmo tempo, evita transformar operações simples em fluxos excessivamente distribuídos.

**A lição central:** um sistema bem organizado não é aquele que possui mais módulos ou menos dependências, mas aquele em que as responsabilidades estão claras e as mudanças permanecem tão localizadas quanto possível.
