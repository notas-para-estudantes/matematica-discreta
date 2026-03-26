---
tags:
  - matematica-discreta
  - grafos
  - arvores
  - binaria
---
---
# Árvores Binárias

Em uma árvore binária, cada filho de um nó é designado especificamente como **filho esquerdo** ou **filho direito**.

## Tipos de Árvores Binárias

### 1. Árvore Binária Cheia (ou Estritamente Binária)
É aquela onde todo nó tem **0 ou 2 filhos**. Nenhum nó pode ter apenas 1 filho. Ela não precisa estar alinhada embaixo, pode ser "torta".

### 2. Árvore Binária Perfeita
É a árvore "triângulo perfeito". Todos os nós internos têm 2 filhos e **todas as folhas estão no mesmo nível**.
> [!NOTE] Obs
> É essa o livro chamou erroneamente apenas de "Cheia".

![[Figura 6.33.png]]
_Legenda: A figura 6.33 mostra uma árvore binária de altura 4._

![[Figura 6.34.png]]
_Legenda: A figura 6.34 mostra uma árvore binária cheia de altura 3._

### 3. Árvore Binária Completa
É aquela onde todos os níveis estão preenchidos, exceto possivelmente o último. O último nível deve ser preenchido obrigatoriamente **da esquerda para a direita**.

![[Figura 6.35.png]]
_Legenda: A figura 6.35 mostra uma árvore binária completa de altura 3 (embora uma árvore seja um grafo, uma árvore completa não é um grafo completo!)._

---

## Representação Computacional

Assim como as Listas e Matrizes de adjacência para grafos gerais, árvores binárias também podem ser representadas computacionalmente.

![[Figura 6.41.png]]
![[Figura 6.42.png]]
_Representação de árvore binária como lista de adjacência._
