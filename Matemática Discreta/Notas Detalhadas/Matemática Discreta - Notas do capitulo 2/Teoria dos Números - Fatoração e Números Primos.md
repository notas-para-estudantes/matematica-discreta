---
tags:
  - matematica-discreta
  - faculdade
  - capitulo-02
  - primos
  - fatoracao
  - algoritmos
  - definicao
  - hardware
---
---
Nota focada nos conceitos de primalidade, algoritmos de verificação e aplicações computacionais (Hardware e Criptografia).

---
## Sumário
- [[#1. Definições Básicas]]
- [[#2. Teorema Fundamental da Aritmética]]
- [[#3. Algoritmo de Verificação (Raiz Quadrada)]]
- [[#4. Crivo de Eratóstenes]]
- [[#5. Primos de Mersenne & Teste de Hardware]]
- [[#6. Distribuição e Teorema dos Números Primos]]

---

## 1. Definições Básicas

> [!INFO] Definição
> Seja $n$ um número inteiro positivo maior que 1 ($n > 1$).
> * **Primo:** Se, e somente se, os únicos fatores positivos de $n$ forem $1$ e $n$.
> * **Composto:** Se $n$ não for primo (possui divisores além de 1 e ele mesmo).
>
> **Exemplos:**
> * $7$ é primo.
> * $15$ é composto.

---

## 2. Teorema Fundamental da Aritmética

> [!TIP] O Teorema
> Todo inteiro positivo $n > 1$ pode ser escrito **univocamente** como um produto entre números primos.
>
> **Exemplos:**
> * $6 = 2 \cdot 3$
> * $10 = 2 \cdot 5$
> * $14 = 2 \cdot 7$
> * $15 = 3 \cdot 5$

---

## 3. Algoritmo de Verificação (Raiz Quadrada)

Método eficiente para verificar se um número é composto ou primo sem testar todos os antecessores.

> [!teorema] Regra da Raiz
> Se $n$ é um número composto, então $n$ tem obrigatoriamente um divisor primo menor ou igual a $\sqrt{n}$.
>
> **Lógica de Resolução:**
> 1. Calcule $\sqrt{n}$.
> 2. Teste a divisão apenas pelos primos menores ou iguais a esse valor.
> 3. Se nenhum dividir, o número é primo.

> [!EXAMPLE]- Exemplo Resolvido: 101 é primo?
> **Passo 1:** Limite
> $n < \sqrt{101} \cong 10,01$.
> O conjunto de primos a testar é $\{2, 3, 5, 7\}$.
>
> **Passo 2:** Testes
> * $101 \div 2$? Não (ímpar).
> * $101 \div 3$? Não ($1+0+1=2$).
> * $101 \div 5$? Não (não termina em 0 ou 5).
> * $101 \div 7$? Não ($101 = 70 + 31$).
>
> **Conclusão:** Como nenhum dos valores divide 101, então **101 é primo**.

---

## 4. Crivo de Eratóstenes

Algoritmo utilizado para encontrar **todos** os primos não excedentes a um valor $n$.

> [!algoritmos] Passo a Passo
> 1. **Limite:** Determine a raiz quadrada do valor limite arredondada para baixo. (Ex: para 101, o limite de corte é 10).
> 2. **Lista:** Crie uma lista de inteiros de 2 até $n$.
> 3. **Iteração 1:** Pegue o primeiro primo (2). Remova todos os seus múltiplos da lista (exceto ele mesmo).
> 4. **Iteração 2:** Pegue o próximo número não riscado (3). Remova todos os seus múltiplos.
> 5. **Repetição:** Continue pegando o próximo número disponível (5, 7...) e removendo seus múltiplos até atingir o limite calculado no passo 1.
> 6. **Resultado:** Os números que sobraram são primos.

---

## 5. Primos de Mersenne & Teste de Hardware

São primos encontrados na forma $M_p = 2^p - 1$, em que $p$ também é primo.

> [!INFO] Glossário Matemático
> * **$M_p$:** Abreviação para "Número de Mersenne". (Ex: $M_3 = 2^3 - 1 = 7$).
> * **Mod:** Resto da Divisão.

### Aplicações Práticas (Engenharia)

**1. Teste de Hardware (Stress Test):**
Calcular primos de Mersenne (ex: Prime95) obriga o processador a fazer cálculos pesados sem errar. Se a CPU errar 1 bit, o teste falha. É um "detector de mentiras" para hardware.

**2. Atalho de Verificação (Teste de Lucas-Lehmer):**
Números aleatórios gigantes demoram séculos para serem testados. Já os Primos de Mersenne têm um atalho exclusivo.

> [!algoritmos] Fórmula de Lucas-Lehmer
> $$S = (S^2 - 2) \pmod{M_p}$$
> *Tradução:* Eleve ao quadrado, tire 2, e pegue o resto da divisão por $M_p$.

### O Truque: Decimal vs Binário

A mágica está na geometria dos números e na otimização de CPU.

* **Em Decimal (Base 10 - Humanos):** O número máximo é 9 ($10^1 - 1$). Uma sequência de 9s (99, 999...) permite somar os dígitos para achar o resto da divisão.
* **Em Binário (Base 2 - Computadores):** O número máximo é 1 ($2^1 - 1$). Um Primo de Mersenne ($2^p - 1$) é sempre uma sequência pura de 1s (ex: `11111...`).

> [!TIP] Shift and Add
> Isso permite que o computador use o método **"Shift and Add"** (Deslocar e Somar) em vez de dividir.
>
> **Exemplo (Analogia Decimal com 999):**
> Para achar o resto de $1.234.567$ por $999$ ($10^3 - 1$):
> 1. Quebramos em blocos de 3: `001 | 234 | 567`
> 2. Somamos os blocos: $1 + 234 + 567 = 802$.
> Resultado: O resto é 802. O computador faz isso instantaneamente com o binário de Mersenne.

---

## 6. Distribuição e Teorema dos Números Primos

O **Teorema dos Números Primos (TNP)** descreve a distribuição assintótica. Ele nos dá uma fórmula para estimar quantos primos existem até um número $x$.

> [!teorema] Fórmula de Densidade
> Quantidade de Primos $\approx \frac{x}{\ln(x)}$
> *(Onde $\ln(x)$ é o logaritmo natural)*.
>
> **Interpretação:** Conforme $x$ aumenta (tende ao infinito), o erro percentual dessa estimativa diminui perto de zero.

> [!EXAMPLE] Exemplo Prático
> **Quantos primos existem até 1.000?**
> * **Real:** 168 primos.
> * **Estimativa:** $1000 / \ln(1000) \approx 1000 / 6.9 \approx 144$.
>
> O erro existe, mas para números da ordem de bilhões, é extremamente preciso para alocar memória.

### Probabilidade
Se quisermos saber a chance de um número aleatório $n$ ser primo:
$$Probabilidade \approx \frac{1}{\ln(n)}$$

* Perto de 100: ~21% são primos.
* Perto de 1 Bilhão: ~4% são primos.
* **Conclusão:** Os primos ficam mais raros à medida que os números crescem (curva logarítmica).