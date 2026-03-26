---
tags:
  - matematica-discreta
  - terminologia
  - grafos
  - Definiçao
---
---
### Sumário
- [[#🔗 Conexões e Arcos]]
- [[#🏗️ Classificação Geral]]
- [[#📍 Propriedades dos Nós]]
- [[#Subgrafo]]
- [[#Grafo Bipartido Completo]]

---
# Terminologia sobre Grafos

## 🔗 Conexões e Arcos

**Adjacentes**
*   **Definição:** Dois nós são ditos adjacentes se ambos são extremidades de um mesmo arco.
*   **Exemplo:** Na **Figura 6.3**, 1 e 3 são nós adjacentes, mas 1 e 4 não. O 2 é adjacente a si mesmo.

**Arcos Paralelos**
*   **Definição:** Dois arcos que possuem exatamente as mesmas extremidades.
*   **Exemplo:** Na **Figura 6.3**, os arcos $a_1$ e $a_2$ são ditos paralelos.

**Laço**
*   **Definição:** Um arco cuja extremidade começa e termina no mesmo nó ($n-n$).
*   **Exemplo:** Na **Figura 6.3**, o arco $a_3$ é um laço com extremidades 2-2.

![[Figura 6.3.png]]
_Figura 6.3_

---

## 🏗️ Classificação Geral

**Grafo Simples**
*   É um grafo "limpo": sem laços e sem arcos paralelos.

**Grafo sem laços**
*   São aqueles que não possuem nenhum laço (autoexplicativo).

---

## 📍 Propriedades dos Nós

**Nó Isolado**
*   **Definição:** É um nó que não é adjacente a nenhum outro (não tem arestas conectadas).
*   **Exemplo:** Na **Figura 6.3**, o nó 5 é um nó isolado.
![[Figura 6.3.png|400]]

**Grau de um nó** é o número de extremidades de arcos que tocam aquele nó. Laços contam por **2** no cálculo do grau.


> [!ABSTRACT] Tradução da Definição Formal
> O texto define tipos de grafos baseando-se em funções:
> *   **Função Injetora:** Garante que não existem arestas paralelas (não há duas linhas ligando os mesmos pontos). Cada par de nós tem, no máximo, uma aresta.
> *   **Grafo Completo ($K_n$):** É quando todo mundo se conecta com todo mundo. Matematicamente, isso significa que para todo par de nós distintos (ex: A e B), existe uma aresta conectando eles.

---

## Subgrafo
O Subgrafo de um grafo consiste em um conjunto de nós e arcos que são subconjunto do conjunto original, ou seja, apagando-se parte do grafo original e deixando o resto sem modificações. A **Figura 6.10** mostra isso.

![[Figura 6.10.png]]
_Referência: Judith L. Gersting_

---

## Grafo Bipartido Completo
É um grafo onde os nós são divididos em dois conjuntos distintos (ex: Time A e Time B).

*   **Regra:** Ninguém liga com alguém do próprio time.
*   **Completo:** Todo mundo do Time A liga com todos do Time B.
*   **Notação:** $K_{m,n}$
    *   $m$ = número de nós no primeiro conjunto.
    *   $n$ = número de nós no segundo conjunto.

![[Figura 6.12.png]]
_Referência: Judith L. Gersting_
