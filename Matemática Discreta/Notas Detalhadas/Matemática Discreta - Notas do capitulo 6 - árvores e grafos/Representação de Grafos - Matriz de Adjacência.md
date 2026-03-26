---
tags:
  - matematica-discreta
  - grafos
  - representacao
  - matriz
---
---
# Representação de Grafos: Matriz de Adjacência

A Matriz de Adjacência é uma forma de representar grafos computacionalmente utilizando uma tabela quadrada.

> [!INFO] Definição
> É uma tabela quadrada ($n \times n$) onde:
> *   As **Linhas ($i$)** representam o nó de Origem (de onde sai).
> *   As **Colunas ($j$)** representam o nó de Destino (para onde vai).
> 
> O valor escrito na posição $i,j$ (chamado de $a_{ij}$) é a **quantidade de arcos** que conectam o nó da linha ao nó da coluna.
> *   $a_{ij} = 0$: Sem conexão.
> *   $a_{ij} = 1$: Uma conexão.
> *   $a_{ij} = p$: Existem $p$ arcos ligando esses dois nós (arcos paralelos).

> [!NOTE] Nota Importante
> A ordem da numeração ($n_1, n_2...$) serve apenas para organizar as etiquetas das linhas e colunas, não altera o significado do grafo.

## Simetria e Direção

*   **Grafo Não Direcionado:** A matriz será **simétrica**. A existência de um arco entre $i$ e $j$ implica a mesma conexão de $j$ para $i$. Tendo valores da diagonal principal e abaixo dela (ou acima), conseguimos formar a matriz completa.
*   **Grafo Direcionado (Dígrafo):** A matriz **não será simétrica**, pois a existência de um arco $n_i$ para $n_j$ não implica a existência de um arco $n_j$ para $n_i$.

![[Figura 6.25.png]]

## Grafos com Peso (Ponderados)

Em um grafo simples com peso, os elementos na matriz de adjacência podem indicar o **peso** de um arco pelo número apropriado, em vez de indicar apenas a presença de um arco pelo número 1.

![[Figura 6.26.png]]

---
## Comparativo de Eficiência

Para ver a alternativa a este método, veja: [[Representação de Grafos - Lista de Adjacência]].

| Característica | Matriz de Adjacência | Lista de Adjacência |
| :--- | :--- | :--- |
| **Verificação de Aresta** | **Vantagem:** Saber se A liga com B é instantâneo (`matriz[A][B]`). | **Desvantagem:** Exige procurar na lista (loop) para saber se A liga com B. |
| **Memória** | **Desvantagem:** Ocupa muita memória (guarda muitos zeros inúteis). | **Vantagem:** Economiza memória (só armazena o que existe). |
| **Listar Vizinhos** | **Desvantagem:** Lenta (tem que checar a linha inteira, inclusive zeros). | **Vantagem:** Rápido (só lê os elementos da lista encadeada). |