# Por trás do caos — Capítulo 2

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 2 — O futuro não compareceu à reunião](../manuscrito/02-o-futuro-nao-compareceu-a-reuniao.md). A narrativa aprovada permanece inalterada.

Arquitetar um sistema não significa prever corretamente o futuro. Significa tomar decisões com informações incompletas, compreender suas consequências e preservar a capacidade de adaptação.

**Trade-offs e restrições.** Centralizar cadastros facilita determinadas consultas, mas concentra responsabilidades e dependências. Mantê-los distribuídos preserva autonomia, porém aumenta os desafios de integração. Uma solução intermediária pode reduzir riscos de migração, ao custo de conviver temporariamente com modelos diferentes. Não existe escolha universalmente superior: a adequação depende do contexto.

**Reversibilidade e gestão de riscos.** A correção gradual dos cadastros permite observar resultados, limitar impactos e interromper o processo quando necessário. Isso não garante que toda mudança possa ser desfeita, mas reduz a exposição a falhas de grande alcance.

**Custo de mudança e dívida técnica.** A decisão de simplificar uma implementação e melhorá-la depois pode ser legítima. O problema surge quando o adiamento não possui responsável, prazo ou critério de revisão. À medida que novas dependências se acumulam, uma alteração inicialmente simples pode se tornar cara e arriscada.

Uma boa arquitetura não é aquela que nunca precisa mudar. É aquela que permite reconhecer quando uma decisão envelheceu e oferece condições para substituí-la.
