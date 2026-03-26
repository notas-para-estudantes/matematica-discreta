---
tags:
  - matematica-discreta
  - contagem
  - permutação
  - PFC
  - permutação-com-repetição
  - permutação-com-elementos-indistinguiveis
---
---
## Sumário
- [[#Permutações]]
- [[#1. Permutações Simples (Pág. 214)]]
- [[#Casos Especiais]]
- [[#2. Permutações com Repetições (Pág. 219)]]
- [[#3. Permutações com Elementos Indistinguíveis]]
---

# Permutações

> [!WARNING] O Primeiro Passo
> Em um problema de contagem, pergunte-se primeiro: **A ordem é relevante?**
> *   **Sim:** É um problema de **Permutações**.
> *   **Não:** É um problema de [[05 - Combinações (Simples e com Repetição)|Combinações]].

---

## 1. Permutações Simples (Pág. 214)

Um arranjo ordenado de objetos distintos é chamado de permutação.
*Exemplo:* O número $1259$ é diferente de $2951$, logo, a ordem importa.

> [!ABSTRACT] Definição e Fórmula
> O número de permutações de $r$ objetos distintos escolhidos entre $n$ objetos distintos é denotado por $P(n, r)$.
> 
> $$ P(n, r) = \frac{n!}{(n - r)!} \quad \text{para } 0 \le r \le n $$

### Casos Especiais

> [!SUMMARY] Tabela de Casos
> 
> | Caso | Fórmula | Resultado | Interpretação |
> | :--- | :--- | :--- | :--- |
> | **Escolher 0** | $P(n, 0)$ | $1$ | Existe apenas um arranjo de zero objetos (o conjunto vazio). |
> | **Escolher 1** | $P(n, 1)$ | $n$ | Existem $n$ maneiras de pegar 1 objeto (cada objeto é uma opção). |
> | **Escolher Todos** | $P(n, n)$ | $n!$ | Arranjo de todos os objetos. Reflete o [[01 - Fundamentos da Contagem (PFC e Adição)#1. Princípio da Multiplicação (PFC)]]. |

*Exemplo:* Permutações de 3 objetos ($a, b, c$):
$$ P(3, 3) = 3! = 6 $$

---

## 2. Permutações com Repetições (Pág. 219)
*(Quando podemos reutilizar o objeto)*

Caso a gente queira usar os $n$ objetos quantas vezes quisermos (ex: senhas, palavras onde letras podem repetir).

> [!TIP] Raciocínio
> Temos $n$ escolhas para a 1ª posição, $n$ para a 2ª... até a $r$-ésima posição.

$$ P_{\text{rep}} = n^r $$

---

## 3. Permutações com Elementos Indistinguíveis
*(Eliminando repetições visuais, ex: Anagrama de "ARARA")*

Para cada grupo de $k$ elementos idênticos (indistinguíveis), as trocas entre eles não geram um novo resultado visual. Precisamos "descontar" essas trocas dividindo pelo fatorial da quantidade de repetições.

> [!SUCCESS] Fórmula Ajustada
> $$ P = \frac{n!}{k_1! \cdot k_2! \dots} $$
> Onde $k$ é a quantidade de vezes que um elemento se repete.