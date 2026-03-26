---
tags:
  - matematica-discreta
  - contagem
  - combinação
  - combinação-simples
  - combinação-com-repetição
---
---
## Sumário
- [[#1. Combinações Simples (Pág. 215)]]
- [[#Casos Especiais]]
- [[#2. Combinações com Repetição (Pág. 219)]]

---

## 1. Combinações Simples (Pág. 215)

Se queremos selecionar $r$ objetos de um conjunto de $n$ objetos, mas **não nos importamos com a ordem**, trata-se de uma combinação.

> [!INFO] Relação com Permutação
> Para cada combinação (grupo), existem $r!$ maneiras de ordenar os objetos. Pelo [[01 - Fundamentos da Contagem (PFC e Adição)|Princípio da Multiplicação]], temos:
> 
> $$ C(n, r) \cdot r! = P(n, r) $$

> [!ABSTRACT] Definição e Fórmula
> Isolando $C(n,r)$, temos a fórmula oficial:
> 
> $$ C(n, r) = \frac{P(n, r)}{r!} = \frac{n!}{r!(n-r)!} \quad \text{para } 0 \le r \le n $$
> 
> **Notação Binomial:**
> $$ C(n, r) = \binom{n}{r} $$

### Casos Especiais

*   **$C(n, 0) = 1$**: Única maneira de escolher zero objetos (conjunto vazio).
*   **$C(n, 1) = n$**: Existem $n$ maneiras de selecionar 1 objeto unitário.
*   **$C(n, n) = 1$**: Única maneira de escolher todos os objetos (o próprio conjunto inteiro).

---

## 2. Combinações com Repetição (Pág. 219)

Para determinar o número de combinações com repetições de $r$ objetos escolhidos entre $n$ objetos distintos.
*(Recomendação: Ler explicação detalhada na pág. 219).*

> [!DANGER] A Fórmula
> $$ C(r + n - 1, r) = \frac{(r + n - 1)!}{r!(n-1)!} $$

> [!TIP] O Macete da Montagem
> Para facilitar o entendimento matemático e não decorar apenas letras:
> 1. Pegue o número de objetos totais ($n$).
> 2. **Some** por quanto a gente quer agrupar ($r$).
> 3. **Subtraia** 1.
> 4. Mantenha o $r$ na parte de baixo da combinação.
> 
> $$ \binom{n + r - 1}{r} $$

