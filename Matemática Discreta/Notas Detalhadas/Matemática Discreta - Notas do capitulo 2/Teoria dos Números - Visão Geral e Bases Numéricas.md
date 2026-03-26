---
tags:
  - matematica-discreta
  - capitulo-02
  - bases-numericas
  - algoritmos
---
---
# 🔢 Bases Numéricas e Conversão

> [!INFO] Definição: Base Numérica
> Um sistema de numeração é um método sistemático para representar números utilizando um conjunto de símbolos (dígitos). A **base** $b$ determina quantos símbolos diferentes são usados e o valor posicional de cada dígito.

## 1. Decimal para Base Qualquer (Divisões Sucessivas)

Para transformar da base $10$ para uma base $b$, utilizamos o método das divisões sucessivas.

> [!TIP] Algoritmo
> 1. Divida o número decimal pela base destino $b$.
> 2. Armazene o **resto**.
> 3. Use o **quociente** como o novo número a ser dividido.
> 4. Repita até que o quociente seja $0$.
> 5. O resultado é a leitura dos restos do **último para o primeiro**.

> [!EXAMPLE]- Exemplo Resolvido: $169_{10} \to \text{Hexadecimal } (16)$
> Dividimos 169 por 16 sucessivamente:
>
> $$
> \begin{align*}
> 169 \div 16 &= 10 \quad (\text{Resto } \mathbf{9}) \\
> 10 \div 16 &= 0 \quad (\text{Resto } \mathbf{10})
> \end{align*}
> $$
>
> **Conversão dos dígitos:**
> * O resto $10$ em Hexadecimal vale $\mathbf{A}$.
> * O resto $9$ vale $\mathbf{9}$.
>
> **Leitura (de baixo para cima):**
> $$A9_{16}$$

---

## 2. Base Qualquer para Decimal (Soma de Potências)

Para converter de uma base $b$ qualquer para a base $10$, utilizamos a expansão polinomial (Soma de Potências).

> [!TIP] Fórmula Geral
> Dado um número $d_n d_{n-1} \dots d_1 d_0$ na base $b$, seu valor decimal é:
> $$N = d_n \cdot b^n + d_{n-1} \cdot b^{n-1} + \dots + d_1 \cdot b^1 + d_0 \cdot b^0$$

> [!EXAMPLE]- Exemplo Resolvido: $234_5 \to \text{Base } 10$
> Aplicando a soma de potências (da direita para esquerda, começando do 0):
>
> $$
> \begin{align*}
> N &= 2 \cdot 5^2 + 3 \cdot 5^1 + 4 \cdot 5^0 \\
> N &= 2 \cdot 25 + 3 \cdot 5 + 4 \cdot 1 \\
> N &= 50 + 15 + 4 \\
> N &= 69_{10}
> \end{align*}
> $$

---

## 3. Conversão Direta (Binário ↔ Hexa ↔ Octal)

Como estas bases são potências de 2 ($16=2^4$ e $8=2^3$), podemos evitar a base 10 e fazer a conversão direta por agrupamento.

> [!TIP] Regra do Agrupamento
> * **Binário $\to$ Hexa:** Agrupar bits de **4 em 4**.
> * **Binário $\to$ Octal:** Agrupar bits de **3 em 3**.
> * *Obs: Sempre comece agrupando da direita para a esquerda.*

> [!EXAMPLE]- Exemplo: $110101_2 \to \text{Hexadecimal}$
> Separamos em grupos de 4 bits (completando com zeros à esquerda se necessário):
>
> | Grupo 2 | Grupo 1 |
> | :---: | :---: |
> | `0011` | `0101` |
> | $3$ | $5$ |
>
> $$\text{Resultado} = 35_{16}$$

> [!EXAMPLE]- Exemplo Inverso: $A9_{16} \to \text{Binário}$
> Convertemos cada dígito Hexa para seus 4 bits correspondentes individualmente.
>
> * $\mathbf{A} \ (10_{10}) = 1010$
> * $\mathbf{9} = 1001$
>
> $$\text{Resultado} = 10101001_2$$

---

## 4. O Cenário Genérico (Base A $\to$ Base C)

> [!WARNING] Cuidado!
> Não existe conversão direta segura entre duas bases que não sejam potências uma da outra (ex: Base 5 para Base 7). Tentar fazer direto geralmente leva a erros.

**O Algoritmo "Ponte":**
Devemos usar a Base 10 como intermediária.

1.  **Passo A:** Base $A \to$ Base $10$ (Soma de Potências).
2.  **Passo B:** Base $10 \to$ Base $C$ (Divisões Sucessivas).

$$\text{Base } A \xrightarrow{\text{Polinômio}} \text{Decimal} \xrightarrow{\text{Divisão}} \text{Base } C$$