---
tags:
  - matematica-discreta
  - Recorrência
  - teorema
---
---
# Princípio da Superposição

> [!TIP] Teorema: Princípio da Superposição
> Este princípio se aplica a **Relações de Recorrência Lineares e Homogêneas**.
> 
> Se $f(n)$ é uma solução para a recorrência e $g(n)$ também é uma solução, então qualquer **combinação linear** delas, da forma $a_n = C_1 \cdot f(n) + C_2 \cdot g(n)$, também será uma solução.
> (Onde $C_1$ e $C_2$ são constantes quaisquer).

### A Lógica "E"
Para que a combinação $a_n = C_1 \cdot f(n) + C_2 \cdot g(n)$ seja uma solução, **ambas** as partes ($f(n)$ **E** $g(n)$) devem ser soluções individualmente.

- **Solução + Solução = Solução**
- **Solução + Não-Solução = Não-Solução**
- **Não-Solução + Não-Solução = Não-Solução**

> [!EXAMPLE]- Aplicação Prática
> **Relação:** $a_n = 8a_{n-1} - 16a_{n-2}$
> 
> **Objetivo:** Verificar se $a_n = 2 \cdot 4^n + 3n \cdot 4^n$ é uma solução.
> 
> 1.  **Identificar as partes:**
>     - A primeira parte é $f(n) = 4^n$.
>     - A segunda parte é $g(n) = n \cdot 4^n$.
> 2.  **Verificar as partes individualmente:**
>     - Em um passo anterior, já provamos que $f(n) = 4^n$ **é solução**.
>     - Em um passo anterior, já provamos que $g(n) = n \cdot 4^n$ **é solução**.
> 3.  **Conclusão:**
>     - Como ambas as partes são soluções, o Princípio da Superposição garante que a combinação linear delas também **é uma solução**, sem a necessidade de fazer o cálculo completo.