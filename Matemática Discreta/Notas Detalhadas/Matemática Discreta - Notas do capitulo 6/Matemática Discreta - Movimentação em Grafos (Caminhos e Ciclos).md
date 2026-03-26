---
tags:
  - matematica-discreta
  - grafos
  - solucao-caminhos
  - caminhos
---
# Movimentação em Grafos

> [!NOTE] Definições de Rotas
> * **Caminho:** Uma sequência de passos de um nó a outro (ex: $1 \to 2 \to 3$). Se existe um caminho de $n_0$ para $n_k$, então $n_k$ será acessível de $n_0$.
> * **Comprimento:** O número de arestas (traços) percorridas no caminho.
> * **Conexo:** Um grafo onde tudo está interligado. Não existem "ilhas" isoladas. Se você pegar um carro, chega em qualquer lugar.
> * **Ciclo:** Uma rota que começa e termina no mesmo nó (uma volta) tal que nenhum arco aparece mais de uma vez.
> * **Acíclico:** Um grafo que não possui nenhum ciclo (não dá para dar voltas).

---

## Caminhos Eulerianos (Cruzar arestas sem repetir)

1. **Ciclo Euleriano (Começa e termina no mesmo lugar)**
   Todos os vértices devem ter **GRAU PAR**.
2. **Caminho Euleriano (Começa em A e termina em B)**
   Exatamente **2 vértices** têm **GRAU ÍMPAR** (o resto é par).
3. **Impossível**
   Se houver qualquer outra quantidade de vértices ímpares (1, 3, 4, etc).