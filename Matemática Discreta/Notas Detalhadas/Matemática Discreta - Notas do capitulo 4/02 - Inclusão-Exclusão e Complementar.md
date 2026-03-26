---
tags:
  - matematica-discreta
  - contagem
  - macetes
  - conjuntos
  - pelo-menos-um
---
---
## Sumário
- [[#1. O Macete do "Pelo Menos Um"]]
- [[#2. Princípio da Inclusão e Exclusão (Pág. 208)]]
- [[#Relações Fundamentais]]
- [[#Exemplo Prático (Eleitores)]]

---

## 1. O Macete do "Pelo Menos Um"

> [!TIP] Estratégia do Complementar
> Sempre que o problema pedir **"pelo menos um..."**, provavelmente o caminho mais rápido é calcular o **Total** e subtrair pelo **Contrário** (Nenhum).
> 
> $$ \text{Total} - \text{Nenhum} = \text{Pelo Menos Um} $$

> [!EXAMPLE]- Dígitos Repetidos (Ex. 37, Pág. 203)
> Supondo que os 4 dígitos de um número de telefone têm que incluir **pelo menos um** dígito repetido. Quantos números existem? (Cada espaço: 0-9).
> 
> 1. **Total (Com ou sem repetição):**
>    $$ 10 \times 10 \times 10 \times 10 = 10.000 $$
> 
> 2. **O Contrário (NENHUMA repetição):**
>    $$ 10 \times 9 \times 8 \times 7 = 5.040 $$
> 
> 3. **Subtração:**
>    $$ 10.000 - 5.040 = 4.960 $$
> 
> **Resposta:** 4.960 números incluem pelo menos um dígito repetido.

---

## 2. Princípio da Inclusão e Exclusão (Pág. 208)

Sempre que dois conjuntos $A$ e $B$ se tocam, eles criam três pedaços: $A - B$, $A \cap B$, e $B - A$.

![[Figura 4.6.png]]

### Relações Fundamentais
*   $|A - B| = |A| - |A \cap B|$
*   $|A \cap B| = |A| - |A - B|$

> [!SUCCESS] Fórmula da União (2 Conjuntos)
> $$ |A \cup B| = |A| + |B| - |A \cap B| $$
> 
> *Explicação:* Somamos A e B, mas subtraímos a intersecção para não contá-la duas vezes.

> [!SUCCESS] Fórmula da União (3 Conjuntos)
> $$ |A \cup B \cup C| = |A| + |B| + |C| - |A \cap B| - |A \cap C| - |B \cap C| + |A \cap B \cap C| $$
> [[Figura 4.7.png|(Ver Figura 4.7)]]
> 

> [!NOTE] Diferença Simétrica (Nota Rápida)
> Para calcular elementos que pertencem só a A **ou** só a B (excluindo o meio):
> $$ |A \Delta B| = |A| + |B| - 2|A \cap B| $$
> Subtraímos a intersecção 2 vezes para remover a região do meio completamente.

### Exemplo Prático (Eleitores)
*Dados:* Total União = 35; Apoiam A = 14; Apoiam B = 26.
$$
\begin{aligned}
|A \cup B| &= |A| + |B| - |A \cap B| \\
35 &= 14 + 26 - |A \cap B| \\
|A \cap B| &= 5 \text{ eleitores apoiam ambos.}
\end{aligned}
$$