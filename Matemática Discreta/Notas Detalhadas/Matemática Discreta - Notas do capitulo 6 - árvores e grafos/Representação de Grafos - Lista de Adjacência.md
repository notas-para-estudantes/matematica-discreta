---
tags:
  - matematica-discreta
  - grafos
  - representacao
  - lista
---
---
# Representação de Grafos: Lista de Adjacência

> [!INFO] Definição
> Uma Lista de Adjacência consiste em um array onde cada posição aponta para uma **lista encadeada** de seus vizinhos.
> 
> Quando uma matriz de adjacência é **esparsa** (ou seja, contém muitos zeros), é mais otimizado usar uma lista de adjacência. Ainda que necessite de armazenagem extra para os ponteiros, pode ser mais eficiente do que uma matriz cheia de zeros.

![[Figura 6.27.png]]

## Representando Pesos

Podemos adicionar informações extras nos "quadradinhos" (nós) da lista de adjacência para representar pesos.
Exemplo: `[ Vizinho: 2 | Peso: 50km | -> ] ...`

![[Figura 6.29.png]]
_O peso de ir do nó "2" para o nó "1" é 4, mas para ir do nó "2" para o nó "4" o peso é 2._

---
## Comparativo de Eficiência

Para ver a alternativa a este método, veja: [[Representação de Grafos - Matriz de Adjacência]].

| Característica | Matriz de Adjacência | Lista de Adjacência |
| :--- | :--- | :--- |
| **Verificação de Aresta** | **Vantagem:** Saber se A liga com B é instantâneo (`matriz[A][B]`). | **Desvantagem:** Exige procurar na lista (loop) para saber se A liga com B. |
| **Memória** | **Desvantagem:** Ocupa muita memória (guarda muitos zeros inúteis). | **Vantagem:** Economiza memória (só armazena o que existe). |
| **Listar Vizinhos** | **Desvantagem:** Lenta (tem que checar a linha inteira, inclusive zeros). | **Vantagem:** Rápido (só lê os elementos da lista encadeada). |