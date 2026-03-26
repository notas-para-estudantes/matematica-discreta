---
tags:
  - matematica-discreta
  - capitulo-02
  - MDC
  - MMC
  - Relação-de-Bézout
---
---
## Sumário
- [[#1. Máximo Divisor Comum (MDC)]]
- [[#2. Mínimo Múltiplo Comum (MMC)]]
- [[#3. Propriedades e Lema de Euclides]]
- [[#4. Algoritmo de Euclides]]
- [[#5. Relação de Bézout e Teorema Fundamental]]

---

## 1. Máximo Divisor Comum (MDC)

> [!INFO] Definição
> Considere $a$ e $b$ como números inteiros diferentes de zero. O maior número inteiro $d$, tal que $d|a$ e $d|b$ é chamado Máximo Divisor Comum de $a$ e $b$. 
> Notação: $\text{mdc}(a,b)$.

Para encontrá-lo, basta fatorar ambos números ($a$, $b$) e agrupar os valores que os dividam simultaneamente.

> [!EXAMPLE] Exemplo Básico: $\text{mdc}(24, 36)$
> 24, 36 | **2**
> 12, 18 | **2**
>  6,  9 | **3**
>  2,  3 | FIM
> $\text{mdc}(24, 36) = 2^2 \cdot 3 = 4 \cdot 3 = 12$.

### Relativamente Primos
Os números $a$ e $b$ são relativamente primos (ou primos entre si) se o $\text{mdc}(a, b) = 1$.

### Fatoração em Primos (MDC)
Se fatorarmos dois inteiros $a$ e $b$ tal que:
$a = p_1^{a1}p_2^{a2}...p_n^{an}$ e $b=p_1^{b1}p_2^{b2}...p_n^{bn}$

Logo, o MDC pega os **menores** expoentes:
$$\text{mdc}(a,b) = p_1^{\min(a1,b1)}p_2^{\min(a2,b2)}...p_n^{\min(an,bn)}$$

**Exemplo:** 
* $120 = 2^3 \cdot 3 \cdot 5$ e $500 = 2^2 \cdot 5^3$.
* $\text{mdc}(120, 500) = 2^2 \cdot 3^0 \cdot 5^1 = 4 \cdot 5 = 20$.

---

## 2. Mínimo Múltiplo Comum (MMC)

> [!INFO] Definição
> O mmc dos inteiros positivos $a$ e $b$ é o menor inteiro positivo divisível por $a$ e $b$. Notação: $\text{mmc}(a, b)$.

> [!EXAMPLE] Exemplo Básico: $\text{mmc}(24, 36)$
> * $M(24) = \{0, 24, 48, \mathbf{72}, 96, \dots\}$
> * $M(36) = \{0, 36, \mathbf{72}, 108, 144, \dots\}$
> * $\text{mmc}(24, 36) = 72$.

### Fatoração em Primos (MMC)
Diferente do MDC, o MMC pega os **maiores** expoentes:
$$\text{mmc}(a,b) = p_1^{\max(a1,b1)}p_2^{\max(a2,b2)}...p_n^{\max(an,bn)}$$

* **Exemplo:** Sendo $a = 2^3 \cdot 3^5 \cdot 7^2$ e $b = 2^4 \cdot 3^3$. (O 7 no $b$ seria $7^0$).
* $\text{mmc}(a,b) = 2^4 \cdot 3^5 \cdot 7^2$.

---

## 3. Propriedades e Lema de Euclides

### Divisibilidade
1. Se $d|a$ e $d|b$, então $d|(b+a)$ e $d|(b-a)$.
2. Se $d|(b+a)$ **ou** $d|(b-a)$ e $d|a$, então $d|b$.

### Lema de Euclides
Uma ferramenta para simplificar o cálculo do MDC usando subtrações.
> [!teorema] Fórmula Base
> Dados dois inteiros $a$ e $b$, $\text{mdc}(a,b) = \text{mdc}(a,b-a)$.

Para evitar fazer centenas de subtrações, multiplicamos o $a$ por uma constante $c$:
> [!TIP] Atalho de Euclides
> $\text{mdc}(a,b) = \text{mdc}(a, b - ac)$

---

## 4. Algoritmo de Euclides

Método eficiente para achar o MDC através de divisões sucessivas. Baseia-se na regra da divisão: $b = a \cdot q + r$ (Onde $r$ é o resto).

> [!algoritmos] Passo a Passo
> 1. Divida o maior número pelo menor.
> 2. Pegue o divisor da operação anterior e divida pelo resto atual.
> 3. Repita o processo até o resto dar **zero**.
> 4. O **último resto não-nulo** é o seu MDC.

---

## 5. Relação de Bézout e Teorema Fundamental

### Teorema de Bézout (Combinação Linear)
> [!teorema] Relação de Bézout
> Dados inteiros $a$ e $b$, quaisquer, mas não ambos nulos, existem dois inteiros $n$ e $m$ tais que:
> $$\text{mdc}(a,b) = a \cdot n + b \cdot m$$

*(Pode ser encontrado usando o Algoritmo de Euclides de trás para frente, substituindo os restos) [[Teoria dos Números - Resolução de Congruências e Pequeno Teorema de Fermat#4. Algoritmo Estendido (Para Números Grandes)|Exemplo]].*

### Teorema Fundamental MDC/MMC
Relaciona as duas propriedades em uma única conta.
> [!INFO] Teorema
> Considere $a$ e $b$ como números inteiros positivos.
> Então
> $$ab = \text{mdc}(a,b) \cdot \text{mmc}(a,b)$$


