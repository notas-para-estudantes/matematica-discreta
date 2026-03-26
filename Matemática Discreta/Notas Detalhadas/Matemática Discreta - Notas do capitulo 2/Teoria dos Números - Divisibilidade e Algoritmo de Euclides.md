---
tags:
  - matematica-discreta
  - faculdade
  - capitulo-02
  - divisibilidade
  - algoritmos
  - definicao
  - teorema
---
---
## Sumário
- [[#1. Conceito de Divisibilidade]]
- [[#2. Propriedades e Teoremas (Linearidade)]]
- [[#3. Algoritmo da Divisão (Euclides)]]
- [[#4. Como Calcular (Cuidado com Negativos!)]]

---
# Teoria dos Números - Divisibilidade e Algoritmo de Euclides

Base fundamental para aritmética modular e criptografia. O foco aqui é entender a estrutura dos números inteiros ($\mathbb{Z}$) e como o computador processa divisões inteiras (div e mod).

---

## 1. Conceito de Divisibilidade

Diferente da divisão real (que gera vírgula $2,5$), na matemática discreta focamos se a divisão é **exata**.

> [!INFO] Definição Formal
> Sejam $a$ e $b$ inteiros, com $a \neq 0$.
> Dizemos que **$a$ divide $b$** (notação: $a \mid b$) se existir um inteiro $c$ tal que:
> $$b = a \cdot c$$
>
> * **Terminologia:**
> 	* $a$ é **fator** ou **divisor** de $b$.
> 	* $b$ é **múltiplo** de $a$.
> 	* Se a divisão não for exata, escrevemos $a \nmid b$.

> [!EXAMPLE]- Exemplo: Verificação
> **Problema:** Determine se $3 \mid 7$ e se $3 \mid 15$.
>
> 1. **Para $3 \mid 7$:**
>    $7 = 3 \cdot c$? Não existe $c$ inteiro (pois $7/3 = 2,33...$).
>    $\therefore 3 \nmid 7$.
>
> 2. **Para $3 \mid 15$:**
>    $15 = 3 \cdot 5$. Onde $c=5$ (inteiro).
>    $\therefore 3 \mid 15$.

---

## 2. Propriedades e Teoremas (Linearidade)

Estas regras permitem simplificar contas complexas sem dividir números gigantes.

> [!TIP] Teoremas Fundamentais
> Sejam $a, b, c, m, n \in \mathbb{Z}$.
>
> 1. **Soma (Linearidade):**
>    Se $a \mid b$ e $a \mid c \implies a \mid (b + c)$.
>    *(Se $a$ divide as partes, divide o todo).*
>
> 2. **Multiplicação:**
>    Se $a \mid b \implies a \mid (b \cdot c)$ para todo $c$.
>    *(Se $a$ divide um fator, divide qualquer múltiplo dele).*
>
> 3. **Transitividade:**
>    Se $a \mid b$ e $b \mid c \implies a \mid c$.
>    *(Ponte lógica).*
>
> 4. **Corolário (Combinação Linear):**
>    Se $a \mid b$ e $a \mid c \implies a \mid (mb + nc)$.
>    *(Essa é a base para o Algoritmo de Euclides e Equações Diofantinas).*

---

## 3. Algoritmo da Divisão (Euclides)

O teorema mais importante para programação. Garante que **toda divisão inteira produz um resto único**.

> [!INFO] O Teorema
> Para qualquer inteiro $a$ (dividendo) e um inteiro positivo $d$ (divisor), existem inteiros únicos $q$ (quociente) e $r$ (resto) tais que:
> $$a = d \cdot q + r$$
> **Regra de Ouro:** $0 \leq r < d$
> *(O resto nunca pode ser negativo e deve ser menor que o divisor).*

### Estrutura da Divisão

| Termo | Símbolo | Fórmula Computacional | Significado |
| :--- | :---: | :--- | :--- |
| **Dividendo** | $a$ | Input | O valor a ser dividido. |
| **Divisor** | $d$ | Input | O tamanho do bloco. |
| **Quociente** | $q$ | `a div d` | Quantos blocos cheios cabem. |
| **Resto** | $r$ | `a mod d` | O que sobra (sempre positivo). |

---

## 4. Como Calcular (Cuidado com Negativos!)

Em linguagens como C ou Java, o operador `%` pode dar resto negativo. Na matemática discreta, **o resto DEVE ser positivo**.

> [!metodo-resolucao] Receita para Divisão com Negativos
> **Caso:** Dividir $a = -11$ por $d = 3$.
>
> 1. **Regra:** Encontre um múltiplo de $d$ que seja **menor ou igual** a $a$.
>    *(Pense na reta numérica: você deve ir para a esquerda de -11).*
>
> 2. **Tentativa Errada (Pensamento positivo):**
>    $3 \times (-3) = -9$.
>    $-9$ é maior que $-11$. **Erro!** O resto seria $-2$ (Proibido).
>
> 3. **Tentativa Correta (Desça mais um):**
>    $3 \times (-4) = -12$.
>    $-12$ é menor que $-11$. **Ok!**
>
> 4. **Calcule o Resto (A diferença para subir):**
>    $r = a - (d \cdot q)$
>    $r = -11 - (-12)$
>    $r = -11 + 12 = 1$
>
> **Resposta Final:**
> $q = -4$
> $r = 1$
>
> **Prova Real:**
> $$-11 = 3 \cdot (-4) + 1$$