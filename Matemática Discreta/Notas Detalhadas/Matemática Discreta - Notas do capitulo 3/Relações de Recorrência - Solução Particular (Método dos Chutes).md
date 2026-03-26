---
tags:
  - matematica-discreta
  - Recorrência
  - solucao-particular
---
---
# Encontrando a Solução Particular ($x_n^{(P)}$)

A solução particular depende do formato do termo não-homogêneo $g(n)$. O método consiste em "chutar" uma solução $x_n^{(P)}$ com um formato semelhante ao de $g(n)$, mas com coeficientes desconhecidos, e depois encontrar esses coeficientes.

## Tabela de Chutes para $x_n^{(P)}$

| O que aparece em $g(n)$ | Formato do Chute ($x_n^{(P)}$) | Exemplo Prático |
| :--- | :--- | :--- |
| **Constante** | $A$ | $g(n) = 5 \to A$ |
| **Polinômio Grau 1** | $An + B$ | $g(n) = 3n \to An + B$ |
| **Polinômio Grau 2** | $An^2 + Bn + C$ | $g(n) = n^2 + 1 \to An^2 + Bn + C$ |
| **Exponencial** | $A \cdot r^n$ | $g(n) = 3^n \to A \cdot 3^n$ |
| **Misto** (Polinômio $\times$ Exponencial) | $(An+B) \cdot r^n$ | $g(n) = n \cdot 2^n \to (An+B) \cdot 2^n$ |
| **Soma** ($g_1 + g_2$) | $Chute_1 + Chute_2$ | $n + 2^n \to (An + B) + (C \cdot 2^n)$ |

> [!INFO] Nota sobre Somas
> Ao usar o [[Relações de Recorrência - Princípio da Superposição|Princípio da Superposição]] para somar chutes, use letras diferentes para as constantes de cada parte (ex: $A, B$ para a primeira parte e $C$ para a segunda).

---
## A Regra da Ressonância (O "Empate")

> [!WARNING] Cuidado!
> A Regra da Ressonância ocorre quando o **formato do chute para a solução particular já é uma solução para a parte homogênea**. Isso acontece se a **base** da parte exponencial de $g(n)$ for igual a uma das raízes ($r_1, r_2$) da equação característica.
> 
> **Correção:** Se houver ressonância, multiplique o chute padrão por $n$. Se a ressonância ocorrer com uma raiz dupla, multiplique por $n^2$.

1.  **Correção Padrão (Empate Simples):**
    $$X_n^{(P)} = n \cdot (\text{Chute Padrão})$$

> [!EXAMPLE]- Exemplo 1: Empate Simples (Multiplica por $n$)
> **Equação:** $a_n - 5a_{n-1} + 6a_{n-2} = 2^n$
>
> 1. **Raízes da Homogênea:** $r^2 - 5r + 6 = 0 \to$ Raízes **2** e **3**.
> 2. **Termo Particular:** $g(n) = 2^n$. A base é **2**.
> 3. **O Problema:** A base (2) é igual a uma das raízes (2).
>
> **Solução:**
> * Chute Padrão (Falha): $A \cdot 2^n$
> * **Chute Correto:** $A \cdot n \cdot 2^n$

2.  **Correção Dupla (Raízes Iguais):** Multiplique por $n^2$.
    $$X_n^{(P)} = n^2 \cdot (\text{Chute Padrão})$$

> [!EXAMPLE]- Exemplo 2: Empate Duplo (Multiplica por $n^2$)
> **Equação:** $a_n - 6a_{n-1} + 9a_{n-2} = 3^n$
>
> 1. **Raízes da Homogênea:** $r^2 - 6r + 9 = 0 \to (r-3)^2 = 0$. Raízes **3** e **3** (Dupla).
> 2. **Termo Particular:** $g(n) = 3^n$. A base é **3**.
> 3. **O Problema:** A base (3) empata com ambas as raízes.
>
> **Solução:**
> * Chute Padrão (Falha): $A \cdot 3^n$
> * Chute $\times n$ (Falha): $A \cdot n \cdot 3^n$ (pois $n \cdot 3^n$ já faz parte da solução *homogênea* para raízes duplas).
> * **Chute Correto:** $A \cdot n^2 \cdot 3^n$