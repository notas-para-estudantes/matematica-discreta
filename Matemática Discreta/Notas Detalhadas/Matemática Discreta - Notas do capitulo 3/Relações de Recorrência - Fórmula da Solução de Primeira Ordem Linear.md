---
tags:
  - matematica-discreta
  - Recorrência
  - formula-solucao
---
---
# A Fórmula da Solução para Recorrências Lineares de Primeira Ordem

Para uma relação de recorrência linear de primeira ordem com coeficientes constantes, da forma $S(n) = cS(n - 1) + g(n)$, existe uma solução geral em forma fechada. Esta fórmula é um atalho que generaliza o método "Expandir, Conjecturar e Verificar".

> [!TIP] Teorema: Fórmula da Solução (Equação 8)
> Dada uma recorrência $S(n) = cS(n - 1) + g(n)$, a sua solução em forma fechada é:
> $$S(n) = c^{n-1}S(1) + \sum_{i=2}^{n} c^{n-i}g(i)$$
> 
> > [!WARNING] Cuidado com o Caso Base!
> > A fórmula acima assume que a sequência começa em $S(1)$. Se a sequência começar em $S(0)$, a fórmula se ajusta para:
> > $$S(n) = c^{n}S(0) + \sum_{i=1}^{n} c^{n-i}g(i)$$

## Quebrando a Fórmula em Partes

##### Parte 1: `c^{n-1}S(1)` (O Efeito do Caso Base)
- **O que é:** Representa o impacto do valor inicial $S(1)$ no termo $S(n)$.
- **Por quê:** Em cada passo da expansão da recorrência, o termo anterior é multiplicado por `c`. Após `n-1` passos para ir de $S(1)$ até $S(n)$, o valor inicial $S(1)$ foi multiplicado por `c` um total de `n-1` vezes.

##### Parte 2: $\sum_{i=2}^{n} c^{n-i}g(i)$ (O Acúmulo dos Termos Extras)
- **O que é:** É a soma de todos os termos "extras" $g(i)$ que são adicionados a cada passo, ajustados pelas multiplicações subsequentes por `c`.
- **Por quê:** O termo $g(i)$ é adicionado no passo `i`. Do passo `i` até o passo `n`, ele será multiplicado por `c` um total de `n-i` vezes. O somatório ($\sum$) apenas soma todos esses pedaços acumulados.
- **Lembrete:** O número de termos em um somatório de $i=a$ até $b$ é $(b - a + 1)$.

---

> [!EXAMPLE]- Exemplo Prático: Usando o Atalho no Problema Prático 11
> **Problema:** Resolver $T(n) = T(n-1) + 3$ com $T(1) = 1$.
> 
> 1.  **Identificar as Peças:**
>     - Comparando com $S(n) = cS(n-1) + g(n)$, temos:
>     - $S(1) = 1$
>     - $c = 1$
>     - $g(n) = 3$ (uma função constante)
> 
> 2.  **Aplicar a Fórmula:**
>     $$T(n) = (1)^{n-1} \cdot (1) + \sum_{i=2}^{n} (1)^{n-i} \cdot (3)$$
> 
> 3.  **Simplificar:**
>     $$T(n) = 1 + \sum_{i=2}^{n} 3$$
> 
> 4.  **Resolver o Somatório:**
>     - O somatório $\sum_{i=2}^{n} 3$ significa somar o número `3` um total de $(n - 2 + 1) = (n-1)$ vezes.
>     - Portanto, $\sum_{i=2}^{n} 3 = 3 \cdot (n-1)$.
> 
> 5.  **Resultado Final:**
>     - $T(n) = 1 + 3(n-1) = 1 + 3n - 3$
>     - $$T(n) = 3n - 2$$
>     - Este é o mesmo resultado obtido pelo método de expansão, confirmando que a fórmula funciona.

## Tabela de Referência (Tabela 3.2)

| Método | Passos |
| :--- | :--- |
| Expandir, conjecturar, verificar | 1. Use repetidamente a relação de recorrência até poder compreender o padrão.<br>2. Decida qual será o padrão quando n – k = 1.<br>3. Verifique a fórmula resultante por indução. |
| **Fórmula da solução** | 1. Coloque sua relação de recorrência na forma<br> &nbsp;&nbsp;&nbsp;&nbsp;S(_n_) = cS(_n_ − 1) + g(_n_) para encontrar c e g(_n_).<br>2. Use c, g(_n_) e S(1) na fórmula<br> &nbsp;&nbsp;&nbsp;&nbsp;$$S(n) = c^{n-1}S(1) + \sum_{i=2}^{n}c^{n-i}g(i)$$<br>3. Calcule o somatório resultante para obter a expressão final. |