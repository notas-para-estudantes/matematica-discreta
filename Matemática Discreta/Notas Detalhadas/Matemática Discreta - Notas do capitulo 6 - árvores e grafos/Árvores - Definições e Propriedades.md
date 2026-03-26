---
tags:
  - matematica-discreta
  - grafos
  - arvores
  - Definiçao
---
---
# Árvores: Definições e Propriedades

> [!INFO] Definição Básica
> Um grafo conexo acíclico sem nenhum nó designado de raiz é chamado de **árvore sem raiz** ou **árvore livre** (essa terminologia pode variar).

![[Figura 6.31.png]]
_A figura 6.31 ilustra duas árvores._

## Construção por Recorrência

Podemos definir árvores de forma recursiva. $r_1$ e $r_2$ são filhos de $r$, e $r$ é pai de $r_1$ e $r_2$.
$T_1$ e $T_2$ são árvores disjuntas que, conectadas a uma raiz, formam uma nova árvore.

![[Figura 6.32.png]]
_A figura 6.32 mostra a última etapa na construção por recorrência da árvore na Figura 6.31._

## Terminologia Essencial

* **Folha:** Um nó sem filhos.
* **Nó Interno:** Todos os nós que não são folhas.
* **Floresta:** É a junção de árvores desconexas (como visto na figura 6.32 com $T_1$ e $T_2$ antes de serem unidas).

### Profundidade e Altura (Ênfase)

A profundidade (altura) de uma árvore é a maior distância entre o nó da raiz até um outro nó que irá gerar a distância máxima.

> [!WARNING] Diferença entre Nível e Altura
> *   **Nível (level):** Geralmente contamos os **nós**. (A raiz é nível 1, e vai aumentando).
> *   **Altura (height):** Geralmente contamos os **arcos/linhas** que ligam os nós.

> [!TIP] Fórmula de Padaria
> $$ \text{Altura} = (\text{Número de nós}) - 1 $$
> *(Considerando o caminho da raiz até a folha mais distante).*