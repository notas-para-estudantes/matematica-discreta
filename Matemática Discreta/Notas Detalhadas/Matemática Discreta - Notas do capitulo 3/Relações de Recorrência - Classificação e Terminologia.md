---
tags:
  - matematica-discreta
  - Recorrência
  - terminologia
---
---
# Classificação de Relações de Recorrência

Para entender e resolver relações de recorrência, primeiro as classificamos com base em suas propriedades estruturais.

## Linear
> [!INFO] Definição: Linearidade
> Uma relação de recorrência é **linear** se os termos anteriores da sequência (como S(n-1), S(n-2)) aparecem apenas na primeira potência e não são multiplicados entre si.
> 
> - **Forma Geral:** $$ \begin{aligned} S(n) &= f_1(n)S(n - 1) + f_2(n)S(n - 2) \\ &+ \cdots + f_k(n)S(n - k) + g(n) \end{aligned} $$
> - **Em português claro:** Os termos S(...) não estão elevados a potências ($S(n-1)^2$), dentro de raízes ($\sqrt{S(n-1)}$) ou outras funções.

## Ordem
> [!INFO] Definição: Ordem
> A **ordem** de uma relação de recorrência é o número de termos anteriores necessários para calcular o termo atual.
> 
> - **Primeira Ordem:** Depende apenas de S(n-1). Ex: `S(n) = cS(n-1) + g(n)`.
> - **Segunda Ordem:** Depende de S(n-1) e S(n-2). Ex: `a_n = 8a_{n-1} - 16a_{n-2}`.

## Coeficientes Constantes
> [!INFO] Definição: Coeficientes Constantes
> Uma relação de recorrência tem **coeficientes constantes** se os multiplicadores dos termos S(...) são números fixos (constantes), e não variáveis que dependem de *n*.
> 
> - **Constante:** `S(n) = 5S(n-1) - 6S(n-2)`. (Os coeficientes são 5 e -6).
> - **Não-Constante:** $x_{n+1} = (n + 1)x_n + n$. (O coeficiente de $x_n$ é $n+1$, que é uma variável).

## Homogeneidade
> [!INFO] Definição: Homogeneidade
> Uma relação de recorrência linear é **homogênea** se todos os seus termos envolvem um fator S(...). Não há um termo "extra" que seja apenas uma função de *n*.
> 
> - Na forma geral, isso significa que $g(n) = 0$.
> - **Homogênea:** $a_n = 5a_{n-1} - 6a_{n-2}$.
> - **Não-Homogênea:** $a_n = 5a_{n-1} - 6a_{n-2} + n$. (O $+ n$ é o termo extra).
