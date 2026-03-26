---
tags:
  - matematica-discreta
  - grafos
  - isomorfismo
  - homeomorfismo
  - planaridade
---
---
# Grafos Isomorfos
São grafos que possuem estruturas fundamentalmente iguais, diferenciando-se apenas pelos nomes dos vértices ou pelo desenho (cosmética).

Para serem isomorfos, é preciso que:
- Tenham a mesma quantidade de nós e arestas.
- Exista uma correspondência 1 para 1 (bijeção) entre os nós de um e de outro, de modo que as conexões (quem liga com quem) sejam preservadas.

![[Figura 6.15.png|400]]
_Figura 6.14->16_

> [!FAIL] Condições para Grafos NÃO serem Isomorfos
> Dois grafos **não** são isomorfos se diferirem em qualquer uma destas propriedades (invariantes):
>
> 1. Número de **nós** diferente.
> 2. Número de **arcos** (arestas) diferente.
> 3. Um possui **arcos paralelos** e o outro não.
> 4. Um possui um **laço** e o outro não.
> 5. Um possui um nó de **grau $k$** e o outro não (a sequência de graus não bate).
> 6. Um é **conexo** e o outro não.
> 7. Um possui um **ciclo** e o outro não.

---

# Homeomorfos
Dois grafos são ditos homeomorfos se ambos puderem ser obtidos do mesmo grafo por uma sequência de subdivisões elementares, nas quais um único arco $x-y$ é substituído por dois novos arcos, $x-v$ e $v-y$, ligando um novo nó $v$.

![[Figura 6.23.png]]
_Figura 6.23_

## Teorema de Kuratowski
Sabendo do Homeomorfos chegamos no Teorema de Kuratowski que diz:
**Um grafo será não planar se, e somente se, contiver um subgrafo homeomorfo a $K_5$ ou a $K_{3,3}$.**

> [!info] 📸 Figura 6.24
> Referência: Figura 6.24 (Pag. 356 mostra a análise detalhada de como chegar nesse resultado da imagem _d_, mas aqui não vamos se ater a isso)
> ![[Figura 6.24.png]]
> Referência: Judith L. Gersting

