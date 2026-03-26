---
tags:
  - matematica-discreta
  - contagem
  - PFC
  - arvores
  - conjuntos
---
---
## Sumário
- [[#1. Princípio da Multiplicação (PFC)]]
- [[#2. Princípio da Adição]]
- [[#3. Aplicação Unificada (Mista)]]
- [[#4. Árvores de Decisão (Pág. 204)]]

---

## 1. Princípio da Multiplicação (PFC)

> [!ABSTRACT] Definição (Pág. 200)
> Se existirem $n_1$ resultados possíveis para um primeiro evento **e** $n_2$ para um segundo, então existirão $n_1 \cdot n_2$ resultados possíveis para a sequência dos dois eventos.

### Definição Rigorosa (Teoria dos Conjuntos)
Para qualquer conjunto finito $S$, denote por $|S|$ o número de elementos em $S$. Se $A$ e $B$ são conjuntos finitos, então:

$$ |A \times B| = |A| \cdot |B| $$

## 2. Princípio da Adição

> [!INFO] Definição (Pág. 202)
> Ocorre quando temos 2 **conjuntos disjuntos** com $n_1$ e $n_2$ resultados possíveis, respectivamente. O número total de possibilidades para o evento "$A$ **ou** $B$" será $n_1 + n_2$.
> 
> *Nota:* Conjuntos disjuntos significam que **não há intersecção** entre os conjuntos.

### 3. Aplicação Unificada (Mista)

Podemos unir o princípio da adição com o da multiplicação.

> [!EXAMPLE] O Problema do Vestuário
> "Se uma mulher tem sete blusas, cinco saias e nove vestidos, de quantas maneiras diferentes ela pode se vestir?"
> 
> **Passo 1: Aplicando PFC (Conjunto Blusa + Saia)**
> $$ 7 \times 5 = 35 $$
> 
> **Passo 2: Aplicando Princípio da Adição (Conjunto OU Vestido)**
> $$ 35 + 9 = 44 $$
> 
> **Resposta:** 44 maneiras diferentes de se vestir!

## 4. Árvores de Decisão (Pág. 204)

São usadas para problemas onde o PFC não se aplica diretamente, permitindo visualizar ramificações condicionais.

![[Figura 4.5.png]]