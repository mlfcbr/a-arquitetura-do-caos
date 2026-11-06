# Por trás do caos — Capítulo 3

> **STATUS: APROVADO PELO AUTOR.**
>
> Material complementar ao [Capítulo 3 — Dividir para complicar](../manuscrito/03-dividir-para-complicar-parte-1.md). A narrativa aprovada permanece inalterada.

A Ordem dividiu suas aplicações para facilitar manutenção, crescimento e autonomia. Algumas separações funcionaram. Outras apenas transformaram problemas internos em dependências entre serviços.

**Coesão e acoplamento.** Um componente possui boa coesão quando reúne responsabilidades relacionadas, que tendem a mudar pelos mesmos motivos. O Serviço de Agendamentos exemplifica essa organização. Já o Serviço de Utilidades Compartilhadas concentra funções sem relação de negócio e cria dependências entre aplicações que deveriam evoluir separadamente. A boa modularidade procura alta coesão e baixo acoplamento.

**Monólitos e microsserviços.** Separar componentes pode permitir escalabilidade e implantação independentes, mas também introduz comunicação pela rede, falhas parciais, consistência distribuída e maior complexidade operacional. Um monólito bem modularizado pode ser mais adequado do que dezenas de serviços excessivamente dependentes.

**Reutilização e fronteiras de responsabilidade (DRY — Don't Repeat Yourself, ou Não se Repita).** O princípio DRY busca evitar a duplicação de conhecimento e regras, não necessariamente de código semelhante. Duas funções podem ter implementações parecidas e responsabilidades diferentes. Compartilhá-las indiscriminadamente pode criar acoplamento desnecessário. O caso das notificações demonstra outro risco: permitir que um componente ultrapasse sua responsabilidade e altere dados cuja autoridade pertence a outro.

A qualidade da arquitetura não está na quantidade de componentes, mas na clareza de suas fronteiras e na capacidade de evoluir sem multiplicar dependências.
