#matematica-discreta #capitulo-02 #MDC #Relação-de-Bézout #divisibilidade #definicao #teorema

---
Nota focada em Equações Diofantinas Lineares — condição de existência, solução geral e métodos de resolução.

---

## Sumário

- [[#1. Definição]]
- [[#2. Condição de Existência]]
- [[#3. Solução Geral]]
- [[#4. Resolvendo no Olhômetro]]
- [[#5. Algoritmo de Euclides (Números Grandes)]]
- [[#6. Acelerando com Módulo]]

---

## 1. Definição

> [!INFO] Definição
> **Equações Diofantinas Lineares** são equações do formato:
> $$ax + by = c$$
> onde $a$, $b$, $c \in \mathbb{Z}$ e buscamos soluções inteiras para $x$ e $y$.

> [!EXAMPLE] Exemplo do dia a dia
> *"De quantos modos podemos comprar selos de R$5 e de R$3, gastando R$50?"*
> Isso se traduz diretamente em $5x + 3y = 50$.

---

## 2. Condição de Existência

> [!teorema] Teorema
> A equação $ax + by = c$ admite solução inteira **se, e somente se**:
> $$\text{mdc}(a, b) \mid c$$

> [!EXAMPLE]- Exemplo Condição de Existência
> Verifique se as equações abaixo possuem ao menos uma solução:
>
> **a)** $3x + 5y = 223$
> $$\text{mdc}(3, 5) = 1 \mid 223 \quad \checkmark \text{ (possui solução)}$$
>
> **b)** $6x + 9y = 20$
> $$\text{mdc}(6, 9) = 3 \nmid 20 \quad \times \text{ (não possui solução)}$$

> [!EXAMPLE] Exemplo — Para quais valores de $c$ a equação admite solução?
> Para quais $c \in \mathbb{Z}$ a equação $30x + 42y = c$ admite soluções inteiras?
>
> $$\text{mdc}(30, 42) = 6 \mid c \implies c = 6k, \quad k \in \mathbb{Z}$$
>
> $$c \in \{\ldots, -6, 0, 6, 12, 18, \ldots\}$$

---

## 3. Solução Geral

> [!teorema] Fórmula da Solução Geral
> Seja $(x_0, y_0)$ uma solução particular de $ax + by = c$, com $\text{mdc}(a,b) = 1$. Então **todas** as soluções inteiras são da forma:
> $$x = x_0 + bt$$
> $$y = y_0 - at$$
> para $t \in \mathbb{Z}$.

> [!TIP] Como usar
> 1. Verifique que $\text{mdc}(a,b) \mid c$
> 2. Encontre **qualquer** par $(x_0, y_0)$ que satisfaça a equação
> 3. Plugue na fórmula — pronto, você tem todas as infinitas soluções

---

## 4. Resolvendo no Olhômetro

Quando os números são pequenos, dá pra encontrar $(x_0, y_0)$ de cabeça.

> [!EXAMPLE] Exemplo — Solução Geral Simples
> Quais as soluções inteiras de $4x + 6y = 10$?
>
> Divide tudo por $2$:
> $$2x + 3y = 5$$
>
> De cabeça: $2(1) + 3(1) = 5$, logo $x_0 = 1,\ y_0 = 1$.
>
> Solução geral:
> $$x = 1 + 3t \qquad y = 1 - 2t, \quad t \in \mathbb{Z}$$

> [!EXAMPLE] Exemplo — Problema dos Selos
> De quantas maneiras podemos comprar selos de R$10 e de R$14, gastando R$100?
>
> $$10x + 14y = 100 \xrightarrow{\div 2} 5x + 7y = 50$$
>
> De cabeça: $5(3) + 7(5) = 50$, logo $x_0 = 3,\ y_0 = 5$.
>
> Solução geral:
> $$x = 3 + 7t \qquad y = 5 - 5t, \quad t \in \mathbb{Z}$$

---

## 5. Algoritmo de Euclides (Números Grandes)

> [!TIP] Quando usar
> Quando não dá pra encontrar $(x_0, y_0)$ de cabeça — ex: $97x + 43y = 1$. Veja a explicação completa do algoritmo [[Teoria dos Números - Resolução de Congruências e Pequeno Teorema de Fermat#4. Algoritmo Estendido (Para Números Grandes)|Aqui]].

> [!algoritmos] Passo a Passo
> 1. Aplique o Algoritmo de Euclides para encontrar o $\text{mdc}$
> 2. Isole os restos em cada passo
> 3. Substitua de baixo pra cima até expressar $1 = ax_0 + by_0$
> 4. Os coeficientes encontrados são $(x_0, y_0)$
> 5. Plugue na fórmula da solução geral

> [!EXAMPLE] Exemplo — $97x + 43y = 1$
>
> $\text{mdc}(97, 43) = 1 \mid 1 \quad \checkmark$
>
> **Algoritmo de Euclides:**
> $$97 = 43 \cdot 2 + 11$$
> $$43 = 11 \cdot 3 + 10$$
> $$11 = 10 \cdot 1 + 1$$
>
> **Isolando os restos:**
> $$11 = 97 - 43 \cdot 2$$
> $$10 = 43 - 11 \cdot 3$$
> $$1 = 11 - 10 \cdot 1$$
>
> **Substituindo de baixo pra cima:**
> $$1 = 11 - (43 - 11 \cdot 3) = 11 \cdot 4 - 43$$
> $$1 = (97 - 43 \cdot 2) \cdot 4 - 43 = 97 \cdot 4 - 43 \cdot 9$$
>
> Logo $x_0 = 4,\ y_0 = -9$.
>
> **Solução geral:**
> $$x = 4 + 43t \qquad y = -9 - 97t, \quad t \in \mathbb{Z}$$

---

## 6. Acelerando com Módulo

> [!TIP] Ideia
> Podemos usar **congruência modular** como atalho para encontrar $(x_0, y_0)$ sem precisar do Algoritmo de Euclides.

> [!algoritmos] Passo a Passo
> Para $ax + by = c$, escolha $m = b$ (ou $m = a$):
> 1. Reduza a equação $\pmod{m}$ — o termo $by$ some
> 2. Resolva $ax \equiv c \pmod{m}$ usando o inverso multiplicativo
> 3. Escreva $x = x_0 + mt$
> 4. Substitua na equação original para encontrar $y$

> [!EXAMPLE] Exemplo — $5x + 3y = 37$
>
> $\text{mdc}(5,3) = 1 \mid 37 \quad \checkmark$
>
> Reduzindo $\pmod{3}$:
> $$5x + 3y \equiv 37 \pmod{3} \implies 2x \equiv 1 \pmod{3}$$
>
> Multiplicando os dois lados por $2$ (inverso de $2 \pmod 3$ é o próprio $2$, pois $2 \cdot 2 = 4 \equiv 1$):
> $$4x \equiv 2 \pmod{3} \implies x \equiv 2 \pmod{3}$$
>
> Logo $x = 2 + 3t$.
> Substituindo na equação original:
> $$5(2 + 3t) + 3y = 37 \implies 3y = 27 - 15t \implies y = 9 - 5t$$
>
> **Solução geral:** $x = 2 + 3t,\quad y = 9 - 5t,\quad t \in \mathbb{Z}$

> [!EXAMPLE] Exemplo — Problema dos Selos ($5x + 3y = 50$)
>
> Reduzindo $\pmod{3}$:
> $$2x \equiv 2 \pmod{3} \implies x \equiv 1 \pmod{3}$$
>
> Logo $x = 1 + 3t$. Substituindo:
> $$5(1 + 3t) + 3y = 50 \implies 3y = 45 - 15t \implies y = 15 - 5t$$
>
> **Solução geral:** $x = 1 + 3t,\quad y = 15 - 5t,\quad t \in \mathbb{Z}$
>
> Como $x \geq 0$ e $y \geq 0$:
>
> | $t$ | $x$ | $y$ | Válido? |
> |-----|-----|-----|---------|
> | $0$ | $1$ | $15$ | ✅ |
> | $-1$ | $-2$ | $20$ | ❌ |
> | $1$ | $4$ | $10$ | ✅ |
> | $2$ | $7$ | $5$ | ✅ |
> | $3$ | $10$ | $0$ | ✅ |
> | $4$ | $13$ | $-5$ | ❌ |
>
> **Logo, há 4 formas de comprar os selos.**
