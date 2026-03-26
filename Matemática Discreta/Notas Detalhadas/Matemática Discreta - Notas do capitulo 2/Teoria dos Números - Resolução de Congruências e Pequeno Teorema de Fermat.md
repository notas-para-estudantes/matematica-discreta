---
tags:
  - matematica-discreta
  - Resíduos
  - Função
  - Phi-de-Euler
  - Lei-do-Cancelamento
  - Pequeno-Teorema-de-Fermat
---
---
## Sumário
- [[#1. Equações Lineares "Macete"]]
- [[#2. Simplificação e Lei do Cancelamento]]
- [[#3. Polinômios e Força Bruta]]
- [[#4. Algoritmo Estendido (Para Números Grandes)]]
- [[#5. Pequeno Teorema de Fermat (Potências Gigantes)]]

---

## 1. Equações Lineares "Macete"

Para resolver $ax \equiv b \pmod m$ sem fórmulas complexas quando os números são pequenos.

> [!TIP] Técnica de "Engordar o Número"
> Como não existe divisão direta, você soma o módulo $m$ ao resultado $b$ até encontrar um valor divisível por $a$.
>
> **Exemplo:** $3x \equiv 4 \pmod 5$
> 1. $4$ divide por 3? Não.
> 2. Soma o módulo: $4 + 5 = 9$.
> 3. $9$ divide por 3? Sim ($9 \div 3 = 3$).
> **Resposta:** $x \equiv 3 \pmod 5$.

---

## 2. Simplificação e Lei do Cancelamento

Como simplificar equações grandes antes de começar a resolver.

> [!WARNING] Regra de Ouro da Divisão
> **Cenário A (Coprimos):** Se você dividir a equação por um número que **não** tem fatores em comum com o módulo, o módulo **não muda**.
> * $100x \equiv 74 \pmod{127}$ (Divide por 2).
> * $\rightarrow 50x \equiv 37 \pmod{127}$.
>
> **Cenário B (Fator Comum):** Se o divisor tem fator comum com o módulo, você é **obrigado** a dividir o módulo também.
> * $2x \equiv 4 \pmod 6$ (Divide tudo por 2).
> * $\rightarrow x \equiv 2 \pmod 3$ (O módulo caiu!).

---

## 3. Polinômios e Força Bruta

Para resolver $f(x) \equiv 0 \pmod m$ com grau alto (ex: $x^4$).

> [!algoritmos] Estratégia
> 1. **Reduza os Coeficientes:** Se tiver algo como $312x$, tire o módulo de 312 logo de cara (ex: $312 \pmod 6 \equiv 0$, o termo some).
> 2. **Use Números Negativos:** $x=6$ é chato de calcular? Use $x \equiv -1$.
> 3. **Teste um por um:** Se o módulo é pequeno (ex: 7), teste $0, 1, 2, \dots$ até achar quem zera a conta.

---

## 4. Algoritmo Estendido (Para Números Grandes)

Quando não dá pra testar na mão (ex: $50x \equiv 37 \pmod{127}$).

> [!INFO] Processo
> 1. **Euclides (Desce):** Ache o MDC dividindo o maior pelo menor até sobrar 1.
> 2. **Euclides (Sobe):** Isole o resto e substitua de volta para escrever $1$ como combinação linear ($1 = A \cdot m + B \cdot a$).
> 3. **Ache o Inverso:** O coeficiente que multiplica o $a$ é o inverso modular.
> 4. **Multiplique:** $x \equiv b \cdot \text{inverso} \pmod m$.
> 5. [[Teoria dos Números - Equações Diofantinas Lineares#5. Algoritmo de Euclides (Números Grandes)|Exemplo do uso]]

> [!NOTE] Formatação da Resposta
> * **Congruência:** $x \equiv 49 \pmod{127}$
> * **Igualdade:** $x = 49 + 127k, \quad k \in \mathbb{Z}$

---

## 5. Pequeno Teorema de Fermat (Potências Gigantes)

Usado para calcular restos de potências absurdas como $3^{302} \pmod 5$.

> [!teorema] O Teorema
> Se $p$ é primo e a base $a$ não é múltiplo de $p$:
> $$a^{p-1} \equiv 1 \pmod p$$
> *Tradução: A cada $p-1$ potências, o número "reseta" para 1.*

> [!algoritmos] Algoritmo de Redução
> 1. **Ache o Ciclo:** Calcule $ciclo = p - 1$.
> 2. **Reduza o Expoente:** Faça $Expoente \pmod{ciclo}$.
> 3. **Calcule o Sobra:** O problema vira $a^{resto} \pmod p$.
>
> **Exemplo:** $3^{302} \pmod 5$
> * Ciclo: $5-1 = 4$.
> * Divisão: $302 \div 4$ deixa resto **2**.
> * Conta final: $3^2 = 9 \equiv 4 \pmod 5$.

> [!fail] Cuidado com Calculadoras
> Calculadoras científicas comuns (Windows) usam notação científica ($1,23 \times 10^{99}$) para números grandes, perdendo a precisão dos inteiros necessária para o `Mod`.
> **Solução:** Usar Python (`pow(a, b, m)`) ou aplicar Fermat na mão.

