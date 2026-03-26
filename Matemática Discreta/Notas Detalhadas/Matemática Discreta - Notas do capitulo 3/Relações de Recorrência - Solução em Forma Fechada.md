---
tags:
  - matematica-discreta
  - Recorrência
  - conceito-chave
---
---
# Solução em Forma Fechada e Métodos de Resolução

> [!INFO] Definição: Solução em Forma Fechada
> Uma **solução em forma fechada** para uma relação de recorrência é uma fórmula que nos permite calcular qualquer termo da sequência, S(n), diretamente, substituindo o valor de *n*, sem a necessidade de calcular os termos anteriores.
> 
> **Exemplo:** S(n) = 2^n
> 
> Ao encontrarmos uma solução em forma fechada, dizemos que **resolvemos** a relação de recorrência.

> [!TIP] Técnica: Expandir, Conjecturar e Verificar
> É um método intuitivo para encontrar a solução em forma fechada de relações de recorrência lineares de primeira ordem.
> 
> 1.  **Expandir:** Use a relação de recorrência repetidamente para substituir os termos anteriores (S(n-1), S(n-2), etc.), expandindo a expressão.
> 2.  **Conjecturar:** Observe o padrão que emerge da expansão e formule uma hipótese (uma conjectura) de qual seria a solução em forma fechada. O padrão geralmente se torna claro quando a expansão atinge o caso base (S(1)).
> 3.  **Verificar:** Use **Indução Matemática** para provar formalmente que a fórmula conjecturada está correta para todos os valores de *n*.
> 
> _Referência: Página 149 do livro._