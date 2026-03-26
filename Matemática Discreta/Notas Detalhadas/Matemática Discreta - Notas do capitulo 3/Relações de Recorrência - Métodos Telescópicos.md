---
tags:
  - matematica-discreta
  - Recorrência
  - metodo-resolucao
  - telescopico
---
---
# Métodos Telescópicos para Relações de Recorrência

Métodos telescópicos são uma técnica para resolver **recorrências lineares de primeira ordem com coeficientes não constantes**, ou seja, quando o multiplicador do termo anterior depende de $n$.

O nome vem da ideia de que, ao expandir a equação, os termos intermediários se cancelam em cadeia, como um telescópio que se fecha, deixando apenas as "pontas" da equação.

Existem duas variações principais:

1.  [[Relações de Recorrência - Métodos Telescópicos#1. Produto Telescópico (Para Casos Homogêneos)|Produto Telescópico]]
2.  [[Relações de Recorrência - Métodos Telescópicos#2. Soma Telescópica (Para Casos Não-Homogêneos)|Soma Telescópica]]

---

## 1. Produto Telescópico (Para Casos Homogêneos)

> [!INFO] Quando Usar:
> Ideal para recorrências **homogêneas**, onde cada termo é um múltiplo do termo anterior.
> **Forma da Equação:** $a_n = f(n) \cdot a_{n-1}$

> [!TIP] A Ideia Central:
> A estratégia é escrever a equação para cada termo até o caso base e depois **multiplicar todas as equações**. Isso cria um efeito dominó onde os termos intermediários ($a_{n-1}, a_{n-2}, \dots$) em ambos os lados da igualdade se cancelam.

**Passo a Passo:**
1. **Listar as Equações:** Escreva a recorrência para $a_n, a_{n-1}, \dots$ até chegar ao caso base.
2. **Multiplicar:** Multiplique o lado esquerdo de todas as equações entre si, e faça o mesmo para o lado direito.
3. **Cancelar:** Cancele os termos idênticos que aparecem em ambos os lados.
4. **Isolar e Substituir:** Isole o termo $a_n$ e substitua o valor da condição inicial.

> [!EXAMPLE]- Exemplo Prático: Resolver $a_n = n \cdot a_{n-1}$, com $a_0 = 5$.
> 1.  **Listar as Equações:**
>     $a_n = n \cdot a_{n-1}$
>     $a_{n-1} = (n-1) \cdot a_{n-2}$
>     ...
>     $a_1 = 1 \cdot a_0$
> 
> 2.  **Multiplicar e Cancelar:**
>     $$ (a_n \cdot \cancel{a_{n-1}} \cdot \dots \cdot \cancel{a_1}) = (n \cdot (n-1) \cdot \dots \cdot 1) \cdot (\cancel{a_{n-1}} \cdot \dots \cdot \cancel{a_1} \cdot a_0) $$
> 
> 3.  **Isolar e Substituir:**
>     $a_n = n! \cdot a_0$
>     $a_n = n! \cdot 5$

---

## 2. Soma Telescópica (Para Casos Não-Homogêneos)

> [!INFO] Quando Usar:
> Projetado para recorrências **não-homogêneas**, que possuem um termo extra $g(n)$.
> **Forma da Equação:** $a_{n+1} = c(n) \cdot a_n + g(n)$

> [!TIP] A Ideia Central:
> O objetivo é encontrar um **"Fator de Soma"**, $F(n)$, para dividir a equação inteira. Esse fator é escolhido de forma inteligente para que, após a divisão, a equação se transforme em algo da forma $y_{n+1} - y_n = h(n)$. Ao somar os termos de uma equação como essa, o lado esquerdo se cancela em cadeia (telescopa).

**Passo a Passo:**
1.  **Identificar as Partes:** Na equação $a_{n+1} = c(n) \cdot a_n + g(n)$, identifique $c(n)$ e $g(n)$.
2.  **Encontrar o Fator de Soma:** É o termo que, ao dividir a equação, fará com que o coeficiente de $a_n$ se "encaixe" com o denominador de $a_{n+1}$.
3.  **Dividir e Simplificar:** Divida toda a equação pelo Fator de Soma.
4.  **Substituir por $y_n$:** Defina uma nova variável $y_n$ para simplificar a notação, resultando em $y_{n+1} = y_n + h(n)$.
5.  **Resolver a Soma:** Resolva $y_n$ expressando-o como uma soma: $y_n = y_{\text{inicial}} + \sum h(k)$.
6.  **Desfazer a Substituição:** Substitua a definição original de $y_n$ de volta na equação e isole $a_n$.

> [!EXAMPLE]- Exemplo Prático: Resolver $x_{n+1} = (n+1)x_n + n$, com $x_1 = 1$.
> 1.  **Identificar Partes:** $c(n) = n+1$ e $g(n) = n$.
> 
> 2.  **Fator de Soma:** A parte homogênea é $x_{n+1} = (n+1)x_n$. O fator que simplifica isso é $(n+1)!$.
> 
> 3.  **Dividir e Simplificar:**
>     $$ \frac{x_{n+1}}{(n+1)!} = \frac{(n+1)x_n}{(n+1)!} + \frac{n}{(n+1)!} \implies \frac{x_{n+1}}{(n+1)!} = \frac{x_n}{n!} + \frac{n}{(n+1)!} $$
> 
> 4.  **Substituir por $y_n$:** Seja $y_n = \frac{x_n}{n!}$. A equação se torna:
>     $$ y_{n+1} = y_n + \frac{n}{(n+1)!} $$
> 
> 5.  **Resolver a Soma:**
>     $y_n = y_1 + \sum_{k=1}^{n-1} \frac{k}{(k+1)!}$. Como $y_1 = \frac{x_1}{1!} = 1$, e usando o truque $\frac{k}{(k+1)!} = \frac{1}{k!} - \frac{1}{(k+1)!}$, a soma se torna telescópica:
>     $$ \sum_{k=1}^{n-1} \left( \frac{1}{k!} - \frac{1}{(k+1)!} \right) = 1 - \frac{1}{n!} $$
>     Portanto, $y_n = 1 + \left(1 - \frac{1}{n!}\right) = 2 - \frac{1}{n!}$.
> 
> 6.  **Desfazer a Substituição:**
>     $$ \frac{x_n}{n!} = 2 - \frac{1}{n!} \implies x_n = 2(n!) - 1 $$