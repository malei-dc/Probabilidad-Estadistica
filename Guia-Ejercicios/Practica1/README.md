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
>- $P(B) = \frac{|B|}{|S|} = \frac{36-21}{36} = 0.4166$. Similar al razonamiento de arriba, en este caso es contar la cantidad de formas tal que el segundo dado sea mayor igual que el primero. Si saco $1$ en el primer dado, tengo $6$. Si saco $2$ en el primer dado tengo $5$ y así. Queda $\sum_{i=1}^{6} i = 21$ 
>- $P(C) = \frac{|C|}{|S|} = \frac{6}{36} = 0.1666$. Dejando fijo el primer dado, solo hay 6 posibilidades para el segundo dado.

(d) Simular en R el experimento de tirar dos veces un dado equilibrado.

>En el archivo [Practica1.pynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica1.pynb)

(e) Simular 1000 veces en R el experimento de tirar dos veces un dado equilibrado y estimar las probabilidades de los sucesos definidos en 1b).

>En el archivo [Practica1.pynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica1.pynb)

(f) Describir los siguientes conjuntos:
1. $A \cap B$
2. $B \cup C$
3. $A \cap (B \cup C)$

>1. $A \cap B$: el conjunto en donde sucede $A$ y $B$, es decir, que pasa que suma de los dos números obtenidos es por lo menos 5 y el valor obtenido en el primer tiro es superior al obtenido en el segundo. Enumeremos los pares que cumplen ambas condiciones:
>
>>- Para $x_1=2$: $x_2=1$ (suma = 3, no cumple $A$)
>>- Para $x_1=3$: $x_2=1,2$ (suma = 4 y 5, solo (3,2)(3,2) cumple $A$)
>>- Para $x_1=4$: $x_2=1,2,3$ (suma = 5, 6, 7, todos cumplen $A$)
>>- Para $x_1=5$: $x_2=1,2,3,4$ (suma = 6, 7, 8, 9, todos cumplen $A$)
>>- Para $x_1=6$: $x_2=1,2,3,4,5$ (suma = 7, 8, 9, 10, 11, todos cumplen $A$)
>>
>> Sumando todas las conbinaciones nos queda que $|A \cap B| = 13$
>2. $B \cup C$: el conjunto donde sucede $B$ o $C$, es decir, que pasa que el valor obtenido en el primer tiro es superior al obtenido en el segundo o el valor obtenido en el primer tiro es un 4. Para calcular el tamaño de este conjunto podemos usar la fórmula de la unión de dos conjuntos: $|B \cup C| = |B| + |C| - |B \cap C| = 15 + 6 - 3 = 18$ (Los casos de $B \cap C$ son $x_1 = 4, x_2=1,2,3$)
>
>3. $A \cap (B \cup C)$: consiste en todos los pares $(x_1,x_2)$ donde la suma de los números es al menos 5 y, además, o bien el primer número es mayor que el segundo, o el primer número es un 4. Para calcular el tamaño de este conjunto podemos identificar las combinaciones posibles para $B \cup C$ y luego seleccionar solo aquellas combinaciones que también cumplen $A$.
>> Como calculamos anteriormente los casos de $B \cup C$ son:
>>- $(2,1)$ (suma = 3, no cumple $A$)
>>- $(3,1),(3,2)$ (suma = 4, solo (3,2) cumple $A$) 
>>- $(4,1),(4,2),(4,3),(4,4),(4,5),(4,6)$ (suma = 5, 6, 7, 8, 9, 10, todos cumplen $A$)
>>- $(5,1),(5,2),(5,3),(5,4)$ (suma = 6, 7, 8, 9, todos cumplen $A$)
>>- $(6,1),(6,2),(6,3),(6,4),(6,5)$ (suma = 7, 8, 9, 10, 11, todos cumplen $A$)
>>
>> Sumando todas las conbinaciones nos queda que $|A \cap (B \cup C)| = 16$


(g) Calcular las probabilidades de los sucesos definidos en 1f).

>1. $P(A \cap B) = \frac{|A \cap B|}{|S|} = \frac{13}{36} = 0.3611$
>2. $P(B \cup C) = \frac{|B \cup C|}{|S|} = \frac{18}{36} = 0.5$
>3. $P(A \cap (B \cup C)) = \frac{|A \cap (B \cup C|}{|S|} = \frac{16}{36} = 0.4444$

(h) Estimar las probabilidades de los sucesos definidos en 1f) mediante simulaciones. Comparar con los resultados obtenidos en 1g).

>En el archivo [Practica1.pynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica1.pynb)

## 2) Eventos
(a) Dados dos eventos $A$ y $B$ tales que se conocen $P(A \cup B)$ y $P(A \cap B)$, hallar una fórmula para la probabilidad de que ocurra exactamente uno de estos eventos.



(b) Una compañı́a constructora trabaja en dos proyectos diferentes. Sea $A$ el evento: “el primero de los proyectos se termina en la fecha del contrato” y definamos análogamente $B$ para el segundo proyecto. Si $P(A \cup B) = 0.9$ y $P (A \cap B) = 0.5$, ¿cuál es la probabilidad de que exactamente un proyecto se termine para la fecha de contrato?