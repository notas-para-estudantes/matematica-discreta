---
tags:
  - matematica-discreta
  - contagem
  - casa-dos-pombos
---
---

## O Princípio da Casa dos Pombos (PCP)

> [!ABSTRACT] Definição (Pág. 212)
> Se mais de $k$ itens são colocados em $k$ caixas, então **pelo menos uma** caixa contém mais de um item.

Embora pareça óbvio, esse princípio garante a existência de repetições (colisões) sem precisar saber onde elas ocorrem.

## Exemplos de Aplicação

> [!EXAMPLE]+ Exemplo 43: Nomes e Letras
> **Pergunta:** Quantas pessoas têm que estar presentes em uma sala para garantir que duas delas têm o último nome começando com a mesma letra?
> 
> **Análise:**
> *   Caixas (k) = 26 letras do alfabeto (A $\to$ Z).
> *   Itens = Pessoas.
> 
> **Solução:** Se houver **27 pessoas** ($k+1$), garantimos que pelo menos 2 terão o nome iniciado com a mesma letra.

> [!EXAMPLE]+ Problema Prático 29: Dados
> **Pergunta:** Quantas vezes é preciso jogar um dado de modo a garantir que um mesmo valor apareça duas vezes?
> 
> **Análise:**
> *   Caixas (k) = 6 números possíveis no dado.
> 
> **Solução:** Basta jogar o dado **7 vezes**. Pelo menos um número irá se repetir.

---
