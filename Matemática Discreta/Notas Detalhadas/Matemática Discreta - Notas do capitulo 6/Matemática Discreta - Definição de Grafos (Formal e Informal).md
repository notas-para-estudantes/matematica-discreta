---
tags:
  - matematica-discreta
  - grafos
  - Definiçao
---
# Definição de Grafos

## Definição Informal
Grafo é um conjunto não vazio de nós (vértices) e um conjunto de arcos (arestas) tais que cada arco conecta dois nós.

> [!EXAMPLE] Exemplo
> O grafo da **Figura 6.3** tem cinco nós e seis arcos. O arco $a_1$ conecta os nós 1 e 2, $a_3$ conecta os nós 2 e 2 e assim por diante.
> ![[Figura 6.3.png]]
>  Referência: Judith L. Gersting
> 

## Definição Formal
Um grafo é uma tripla ordenada $(N, A, g)$ em que:
*   $N$ = um conjunto não vazio de nós (vértices).
*   $A$ = um conjunto de arcos (arestas).
*   $g$ = uma função que associa cada arco $a$ a um par não ordenado $x-y$ de nós, chamamos de extremidades de $a$.

**Aplicação na Figura 6.3:**
Para o grafo da Figura 6.3 (ver acima), a função $g$ que associa arcos a suas extremidades é a seguinte:
$$\begin{aligned}
g(a_1) = 1-2,\\g(a_2) = 1-2,\\ g(a_3) = 2-2,\\ g(a_4) = 2-3,\\ g(a_5) = 1-3 ,\\g(a_6) = 3-4 \text{.}\\
\end{aligned}$$

---

## Grafo Direcionado (Dígrafo)
Podemos querer que arcos de um grafo comecem em um nó e terminem em outro.

**Definição:**
Um grafo direcionado (dígrafo) é uma tripla ordenada $(N, A, g)$ em que:
*   $N$ = Um conjunto não vazio de nós (vértice).
*   $A$ = Um conjunto de arcos (arestas).
*   $g$ = Uma função que associa a cada arco um **par ordenado** $(x, y)$ de nós, em que $x$ é o ponto inicial (extremidade inicial) e $y$ é o ponto final (extremidade final) de $a$.

> [!EXAMPLE] Exemplo
> A **Figura 6.4** mostra um grafo direcionado, com 4 nós e 5 arcos.
> A função $g$ que associa a cada arco suas extremidades satisfaz $g(a_1) = (1, 2)$, o que significa que o arco $a_1$ começa no nó 1 e termina no nó 2.
> Temos, também, $g(a_3) = (1, 3)$ e $g(a_4) = (3, 1)$.
> 
>  ![[Figura 6.4.png]]
>  Referência: Judith L. Gersting

