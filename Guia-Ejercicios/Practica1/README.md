# Práctica 1

## 1) Dado equilibrado
Se arroja dos veces un dado equilibrado, registrándose los resultados obtenidos.

(a) Definir un espacio muestral $S$ apropiado para este experimento.
  
> $S = \{ (x_1, x_2) / 1\leq x_1,x_2 \leq 6 \}$ Asumiendo que es un dado de seis caras.

(b) Describir el conjunto de elementos del espacio muestral que satisface que:
- $A$: la suma de los dos números obtenidos es por lo menos 5
- $B$: el valor obtenido en el primer tiro es superior al obtenido en el segundo
- $C$: el valor obtenido en el primer tiro es un 4

>- $A = \{ (x_1, x_2) / 1 \leq x_1,x_2 \leq 6 \land x_1+x_2 \geq 5 \}$
>- $B = \{ (x_1, x_2) / 1 \leq x_1,x_2 \leq 6 \land x_1 > x_2 \}$
>- $C = \{ (x_1, x_2) / 1 \leq x_1,x_2 \leq 6 \land x_1 = 4 \}$

(c) Calcular las probabilidades de los eventos definidos en 1b).

>- $P(A) = \frac{|A|}{|S|} = \frac{36-6}{36} = 0.8333$. Para sacar $|A|$ lo pienso por complemento, la suma de ambos dados sea menor a $5$, en este caso son $(1,1), (1,2), (1,3)$ esa cantidad multiplicado por dos ya que pueden alternar el orden de los números de cada dado.  
>- $P(B) = \frac{|B|}{|S|} = \frac{36-21}{36} = 0.4166$. Similar al razonamiento de arriba, en este caso es contar la cantidad de formas tal que el segundo dado sea mayor igual que el primero. Si saco $1$ en el primer dado, tengo $6$. Si saco $2$ en el primer dado tengo $5$ y así. Queda $\sum_{i=1}⁶i = 21$ 
>- $P(C) = \frac{|C|}{|S|} = \frac{6}{36} = 0.1666$. Dejando fijo el primer dado, solo hay 6 posibilidades para el segundo dado.

(d) Simular en R el experimento de tirar dos veces un dado equilibrado.

(e)Simular 1000 veces en R el experimento de tirar dos veces un dado equilibrado y estimar las probabilidades de los sucesos definidos en 1b).

(f) Describir los siguientes conjuntos:
1. $A \cap B$
2. $B \cup C$
3. $A \cap (B \cup C)$

(g) Calcular las probabilidades de los sucesos definidos en 1f).

(h) Estimar las probabilidades de los sucesos definidos en 1f) mediante simulaciones. Comparar con los resultados obtenidos en 1g).