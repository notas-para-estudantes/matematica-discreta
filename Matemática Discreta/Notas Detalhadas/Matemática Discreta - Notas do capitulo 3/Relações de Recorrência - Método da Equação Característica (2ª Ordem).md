---
tags:
  - matematica-discreta
  - Recorrência
  - metodo-resolucao
  - equacao-caracteristica
---
---
# Método da Equação Característica (Recorrências Lineares de 2ª Ordem)

Este é um método algorítmico para encontrar a solução em forma fechada de **relações de recorrência lineares, de segunda ordem e com coeficientes constantes**.

> [!TIP] Teorema: A Solução Geral
> A solução geral de uma recorrência linear não-homogênea é a soma da sua solução homogênea com uma solução particular:
> $$ x_n = x_n^{(H)} + x_n^{(P)} $$

O processo de resolução se divide em três passos principais:

1.  **Resolver a Parte Homogênea:** Encontrar a solução $x_n^{(H)}$ tratando a equação como se $g(n) = 0$.
    - > [[Relações de Recorrência - Solução Homogênea (2ª Ordem)|Veja como encontrar a Solução Homogênea]]
2.  **Resolver a Parte Particular:** Encontrar uma solução particular $x_n^{(P)}$ com base no formato do termo $g(n)$ da equação original.
    - > [[Relações de Recorrência - Solução Particular (Método dos Chutes)|Veja como encontrar a Solução Particular]]
3.  **Somar as Soluções:** Combinar as duas para obter a solução geral e, se houver condições iniciais, usá-las para encontrar os valores das constantes $c_1$ e $c_2$.

---

> [!EXAMPLE]- Exemplo Completo: Superposição e Ressonância
> **Equação:** $x_{n+2} - 5x_{n+1} + 6x_n = n + 3^n$
> 
> #### 1. Solução Homogênea ($x_n^{(H)}$)
> A equação característica é $r^2 - 5r + 6 = 0$, que tem as raízes $r_1=2$ e $r_2=3$.
> A solução homogênea é:
> $$x_n^{(H)} = c_1 \cdot 2^n + c_2 \cdot 3^n$$
> 
> #### 2. Solução Particular ($x_n^{(P)}$)
> O termo não-homogêneo é $g(n) = \underbrace{n}_{\text{Parte 1}} + \underbrace{3^n}_{\text{Parte 2}}$. Usaremos o [[Relações de Recorrência - Princípio da Superposição|Princípio da Superposição]].
> 
> -   **Para a Parte 1 ($g_1(n) = n$):** É um polinômio de grau 1. O chute padrão é $An + B$. Não há ressonância (as raízes são 2 e 3).
> -   **Para a Parte 2 ($g_2(n) = 3^n$):** É uma exponencial. O chute padrão seria $C \cdot 3^n$.
>     -   > [!WARNING] **Ressonância!** A base da exponencial (3) é igual a uma das raízes da equação homogênea (3).
>     -   **Chute Corrigido:** Precisamos multiplicar o chute por $n$. O chute correto é $C \cdot n \cdot 3^n$.
> 
> Combinando os chutes, a forma da solução particular é:
> $$x_n^{(P)} = (An + B) + (C \cdot n \cdot 3^n)$$
> 
> Após substituir na equação original e resolver os coeficientes, encontramos (conforme o rascunho): $A = 1/2$, $B = 3/4$ e $C = 1/3$.
> $$x_n^{(P)} = \frac{1}{2}n + \frac{3}{4} + \frac{1}{3}n \cdot 3^n$$
> 
> #### 3. Solução Geral Final
> Somando a homogênea e a particular:
> $$x_n = c_1 \cdot 2^n + c_2 \cdot 3^n + \frac{n}{2} + \frac{3}{4} + \frac{n \cdot 3^n}{3}$$


