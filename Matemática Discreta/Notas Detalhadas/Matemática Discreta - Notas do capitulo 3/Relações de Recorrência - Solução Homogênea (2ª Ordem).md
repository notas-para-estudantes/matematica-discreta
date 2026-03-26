---
tags:
  - matematica-discreta
  - Recorrência
  - solucao-homogenea
---
---
# Encontrando a Solução Homogênea ($x_n^{(H)}$)

A solução homogênea é a solução da recorrência linear de segunda ordem quando o termo "extra" $g(n)$ é zero.

> [!INFO] Definição: Equação Característica
> Dada uma recorrência linear homogênea:
> $$ S(n) - c_1S(n – 1) - c_2S(n – 2) = 0 $$
> Sua **equação característica** correspondente é a equação quadrática:
> $$ r^2 - c_1r - c_2 = 0 $$

A forma da solução homogênea $x_n^{(H)}$ depende das raízes ($r_1, r_2$) desta equação.

## Caso 1: Raízes Reais e Distintas ($r_1 \neq r_2$)

> [!TIP] Fórmula para Raízes Distintas
> A solução geral homogênea é:
> $$ x_n^{(H)} = c_1 \cdot (r_1)^n + c_2 \cdot (r_2)^n $$
> Onde $c_1$ e $c_2$ são constantes determinadas pelas condições iniciais.

## Caso 2: Raízes Reais e Iguais ($r_1 = r_2 = r$)

> [!TIP] Fórmula para Raízes Iguais
> Se as raízes são iguais, multiplicamos o segundo termo por $n$ para garantir que as partes da solução sejam linearmente independentes.
> $$ x_n^{(H)} = c_1 \cdot r^n + c_2 \cdot n \cdot r^n $$

