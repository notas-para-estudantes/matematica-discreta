---
tags:
  - matematica-discreta
  - Resíduos
  - Função
  - Phi-de-Euler
---
---
## Sumário
- [[#1. Menor Inteiro em Valor Absoluto]]
- [[#2. Sistema Reduzido de Resíduos]]
- [[#3. Função $\phi$ de Euler (Totiente)]]
- [[#4. Classes de Equivalência e Resíduos ($ mathbb{Z}_m$)|4. Classes de Equivalência e Resíduos]]
- [[#5. Algoritmos de Cálculo (A "Bruxaria")]]

---

## 1. Menor Inteiro em Valor Absoluto

Em aritmética modular padrão, o resto costuma ser $0 \le r < m$. Porém, muitas vezes é útil encontrar o número congruente que esteja **mais próximo de zero**, mesmo que seja negativo.

> [!INFO] O Critério
> O objetivo é minimizar $|x|$.
> O conjunto de escolha é centrado no zero: $\{ \dots, -2, -1, 0, 1, 2, \dots \}$.
>
> * **Se o resto $r > \frac{m}{2}$:** O número está "longe" demais no positivo. Subtraímos $m$ para achar o equivalente negativo.
> * **Se o resto $r \le \frac{m}{2}$:** Mantém-se o positivo.

> [!EXAMPLE] Exemplo: Módulo 9
> O conjunto de resíduos absolutos é $\{-4, -3, -2, -1, 0, 1, 2, 3, 4\}$.
>
> **Caso 1:** $511 \equiv 7 \pmod 9$.
> * $7$ é maior que 4.
> * Ajuste: $7 - 9 = -2$.
> * Resposta: **-2** (Pois $|-2| < |7|$).
>
> **Caso 2:** $-2717 \equiv -8 \pmod 9$.
> * $-8$ está longe do zero.
> * Ajuste: $-8 + 9 = 1$.
> * Resposta: **1** (Pois $|1| < |-8|$).

---

## 2. Sistema Reduzido de Resíduos

Diferente do sistema completo (que pega todos os restos de $0$ a $m-1$), o sistema reduzido foca apenas nos números que não têm fatores em comum com $m$.

> [!INFO] Definição
> Um Sistema Reduzido de Resíduos módulo $m$ consiste em todos os inteiros $r$ (onde $1 \le r < m$) tal que:
> $$\text{mdc}(r, m) = 1$$
> Ou seja, são os números **coprimos** com $m$.

> [!TIP] Exemplo Prático ($m=15$)
> * **Sistema Completo:** $\{0, 1, 2, \dots, 14\}$
> * **Elimina múltiplos de 3:** (3, 6, 9, 12)
> * **Elimina múltiplos de 5:** (0, 5, 10)
> * **Sistema Reduzido:** $\{1, 2, 4, 7, 8, 11, 13, 14\}$

---

## 3. Função $\phi$ de Euler (Totiente)

A função $\phi(m)$ conta a **quantidade** de elementos no Sistema Reduzido de Resíduos. Ela diz quantos inteiros positivos menores que $m$ são coprimos com $m$.

> [!teorema] Fórmula Geral
> Se a fatoração de $m$ é $p_1^{a_1} \cdot p_2^{a_2} \cdots$, então:
> $$\phi(m) = m \cdot \left(1 - \frac{1}{p_1}\right) \cdot \left(1 - \frac{1}{p_2}\right) \cdots$$
> *Basicamente: Pega o total e vai descontando a fração correspondente a cada fator primo.*

---

## 4. Classes de Equivalência e Resíduos ($\mathbb{Z}_m$)

Uma vez que congruência é uma relação de equivalência, ela particiona o conjunto dos inteiros ($\mathbb{Z}$) em classes de **equivalência** disjuntas chamadas **classes de resíduos módulo $m$**.

> [!INFO] Definição
> A Classe de Resíduos pode ser definida como o conjunto de todos os números inteiros congruentes a um inteiro $a$ módulo $m$.
> 
> <small>De forma matemática:</small>
> $$\overline{x} = [x] = \{a \in \mathbb{Z} \mid a \equiv x \pmod m\}$$

> [!EXAMPLE] Exemplo: Classes de resíduo do módulo $m = 6$
> 
> |  Classe   | Conjunto de Elementos                 | Descrição (Resto)         |
> | :-------: | :------------------------------------ | :------------------------ |
> | $\bar{0}$ | $\{\dots, -6, 0, 6, 12, 18, \dots\}$  | Resto **0** na div. por 6 |
> | $\bar{1}$ | $\{\dots, -5, 1, 7, 13, 19, \dots\}$  | Resto **1** na div. por 6 |
> | $\bar{2}$ | $\{\dots, -4, 2, 8, 14, 20, \dots\}$  | Resto **2** na div. por 6 |
> | $\bar{3}$ | $\{\dots, -3, 3, 9, 15, 21, \dots\}$  | Resto **3** na div. por 6 |
> | $\bar{4}$ | $\{\dots, -2, 4, 10, 16, 22, \dots\}$ | Resto **4** na div. por 6 |
> | $\bar{5}$ | $\{\dots, -1, 5, 11, 17, 23, \dots\}$ | Resto **5** na div. por 6 |

> [!TIP] Nota
> Note que $[3] = \bar{3}$. Qualquer número dentro do conjunto pode representar a classe!

### Sistema Completo e Aritmética

Um **sistema completo de resíduos** é denotado por:
$$\mathbb{Z}_m = \{[0], [1], [2], [3], \dots, [m-1]\}$$

> [!teorema] Aritmética de classes de resíduos
> $$[a] + [b] = [a + b]$$
> $$[a] \cdot [b] = [a \cdot b]$$

![[Teoria dos Números - Adicao e Multiplicacao.png]]

---

## 5. Algoritmos de Cálculo (A "Bruxaria")

Existem atalhos para calcular $\phi(m)$ sem precisar da fórmula completa, dependendo da natureza do número.

### Caso A: O número é Primo ($p$)
Se $p$ é primo, ele não tem divisores. Todos os anteriores são coprimos.
> [!algoritmos] Atalho Primos
> $$\phi(p) = p - 1$$
> **Ex:** $\phi(17) = 16$.

### Caso B: Potência de Primo ($p^k$)
Se $m$ é uma potência (tipo $25 = 5^2$ ou $8 = 2^3$), só precisamos tirar os múltiplos da base.
> [!algoritmos] Atalho Potências
> $$\phi(p^k) = p^k - p^{k-1}$$
> *Tradução:* Total - (Total dividido pela base).

> [!EXAMPLE] Exemplo Resolvido: $m=8$ ($2^3$)
> * **Total:** $2^3 = 8$.
> * **Múltiplos de 2 a remover:** $2^{3-1} = 2^2 = 4$.
> * **Cálculo:** $8 - 4 = 4$.
> * **Conferindo:** $\{1, 3, 5, 7\}$ são os 4 coprimos.

### Caso C: Número Composto Genérico
Use a propriedade multiplicativa para separar os fatores.
> [!algoritmos] Divisão e Conquista
> Se $m = A \cdot B$ (onde A e B são coprimos):
> $$\phi(A \cdot B) = \phi(A) \cdot \phi(B)$$

> [!EXAMPLE] Exemplo Resolvido: $m=60$
> $60 = 4 \cdot 3 \cdot 5$ (Note que 4, 3 e 5 são coprimos entre si).
> $$\phi(60) = \phi(4) \cdot \phi(3) \cdot \phi(5)$$
> * $\phi(4) = 4 - 2 = 2$ (Regra da potência $2^2$)
> * $\phi(3) = 2$ (Regra do primo)
> * $\phi(5) = 4$ (Regra do primo)
>
> **Resultado:** $2 \cdot 2 \cdot 4 = 16$.