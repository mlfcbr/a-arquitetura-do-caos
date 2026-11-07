# DRY, KISS e YAGNI — A disciplina de não complicar

Três princípios fundamentais da engenharia de software ajudam a controlar a complexidade, mas atuam sobre problemas diferentes: duplicação de conhecimento, soluções excessivamente elaboradas e antecipação de necessidades.

## DRY — Don't Repeat Yourself

*Tradução: Não se repita.*

DRY recomenda evitar que o mesmo conhecimento seja representado independentemente em diferentes partes de um sistema. Quando uma regra de negócio é duplicada, alterações podem produzir comportamentos inconsistentes.

Entretanto, **códigos semelhantes não representam necessariamente o mesmo conhecimento**. Duas regras podem parecer idênticas hoje e evoluir por motivos diferentes amanhã.

Aplicar DRY indiscriminadamente pode gerar abstrações artificiais e acoplamento desnecessário. Às vezes, uma pequena duplicação é preferível a uma dependência equivocada.

## KISS — Keep It Simple, Stupid

*Tradução literal: Mantenha simples, idiota. Interpretação: Prefira a simplicidade.*

KISS recomenda escolher a solução mais simples capaz de atender adequadamente aos requisitos.

Simplicidade não significa menos linhas de código ou menos componentes. Uma arquitetura organizada em módulos pode ser mais simples de compreender e manter do que uma aplicação pequena com responsabilidades misturadas.

O princípio também não justifica ignorar segurança, confiabilidade ou outras necessidades reais. **A complexidade necessária deve ser preservada; a desnecessária, questionada.**

## YAGNI — You Aren't Gonna Need It

*Tradução: Você não vai precisar disso.*

YAGNI recomenda evitar a implementação antecipada de funcionalidades cuja necessidade ainda não foi demonstrada.

Preparar um sistema para evoluir é diferente de construir recursos para cenários hipotéticos. O primeiro favorece a manutenção; o segundo pode gerar custos permanentes sem benefícios concretos.

YAGNI também não significa ignorar o futuro. Decisões difíceis de reverter, exigências regulatórias e riscos conhecidos precisam ser considerados desde o início.

## Como os três se complementam

| Princípio | Pergunta essencial |
|---|---|
| **DRY** | Estamos duplicando conhecimento? |
| **KISS** | Estamos complicando desnecessariamente? |
| **YAGNI** | Estamos construindo algo de que ainda não precisamos? |

O equilíbrio é importante: eliminar duplicações pode criar abstrações excessivas; simplificar demais pode comprometer requisitos; evitar antecipações pode ser prejudicial quando uma decisão futura terá alto custo de reversão.

**A lição central:** bons princípios não eliminam a necessidade de julgamento técnico. Eles ajudam a questionar decisões, não a substituí-las.
