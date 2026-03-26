---
tags:
  - matematica-discreta
  - grafos
  - planaridade
  - euler
---
---
# Grafos Planares
Em resumo, um grafo planar é aquele que pode ser representado (em uma folha de papel, ou seja, em um plano) de modo que seus arcos se intersectam apenas em nós. Ou seja, um arco não "cruza" com outro.

*   **Aplicação:** Um grafo planar pode ser buscado por pessoas que projetam circuitos integrados e precisam que uma camada do chip formem um grafo planar.
*   **Não Planares:** $K_5$ é o primeiro grafo "não planar", ou seja, é impossível desenhar ele sem que ao menos duas linhas se cruzem (fiquem uma por cima da outra).

## Fórmula de Euler
$$n - a + r = 2$$
*   $n$ = números de nós
*   $a$ = números de arcos
*   $r$ = número de regiões

> [!NOTE] Por que a aresta removida deve definir uma região?
> **Razão 1 (Balanço):** Ao remover a aresta, duas regiões se fundem em uma ($R$ diminui 1). Isso compensa a perda da aresta ($A$ diminui 1) na equação $V - A + R = 2$.
>
> **Razão 2 (Conectividade):** Se a aresta não definisse uma região, ela seria uma **ponte**. Remover uma ponte desconectaria o grafo, violando a premissa de que o grafo deve ser conexo para a prova continuar.

> [!WARNING] Limites de Planaridade (Detectores de Não-Planaridade)
> Se um grafo ultrapassar esses limites de arestas, ele **com certeza NÃO é planar**.
> Mas passar não é condição suficiente para ser considerado planar (pag. 355, Q.15)
>
> **1. Regra Geral (Baseada em Triângulos):**
> $$a \le 3n - 6$$
> * *Uso:* Testa a maioria dos grafos (ex: prova que $K_5$ não é planar).
>
> **2. Regra Sem Triângulos (Baseada em Quadrados):**
> $$a \le 2n - 4$$
> * *Uso:* Testa grafos que não possuem ciclos de 3 nós (ex: prova que $K_{3,3}$ não é planar).