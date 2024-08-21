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

>En el archivo [Practica1.pynb](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica1/Practica1.ipynb)

(e) Simular 1000 veces en R el experimento de tirar dos veces un dado equilibrado y estimar las probabilidades de los sucesos definidos en 1b).

>En el archivo [Practica1.ipynb](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica1/Practica1.ipynb)

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

>En el archivo [Practica1.ipynb](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica1/Practica1.ipynb)

## 2) Eventos
(a) Dados dos eventos $A$ y $B$ tales que se conocen $P(A \cup B)$ y $P(A \cap B)$, hallar una fórmula para la probabilidad de que ocurra exactamente uno de estos eventos.

> Vamos a descomponer el problema. La probabilidad de que ocurra solamente $A$ pero no $B$ es $P(A \cap B^c)$, analogamente se puede hacer para el evento $B$. Entonces la probabilidad de que ocurra exactamente uno de estos eventos es la suma de $P(A \cap B^c)+P(B \cap A^c)$ 
>
> Por otro lado podemos expresar $P(A \cap B^c) = P(A) - P(A \cap B)$ y $P(B \cap A^c) = P(B) - P(B \cap A)$. Entonces: 
>
> $$P(exactamenteUno)= P(A) - P(A \cap B) +  P(B) - P(B \cap A)$$ 
>
> $$P(exactamenteUno)= P(A) +  P(B) - 2P(B \cap A)$$
>
> Sabemos también que la relación de $P(A \cup B) = P(A)+P(B)-P(A\cap B)$, despejando $P(A)+P(B)$ nos queda:
>
> $$P(A)+P(B) = P(A \cup B) +  P(A\cap B)$$
>
> Reemplazando $P(A)+P(B)$ en la fórmula de la probabilidad de exactamente uno de los eventos nos queda:
>
> $$ P(exactamenteUno)= P(A \cup B) +  P(A\cap B) - 2P(B \cap A) $$
>
> $$ P(exactamenteUno)= P(A \cup B)  - P(B \cap A)$$

(b) Una compañı́a constructora trabaja en dos proyectos diferentes. Sea $A$ el evento: “el primero de los proyectos se termina en la fecha del contrato” y definamos análogamente $B$ para el segundo proyecto. Si $P(A \cup B) = 0.9$ y $P (A \cap B) = 0.5$, ¿cuál es la probabilidad de que exactamente un proyecto se termine para la fecha de contrato?

> Por **(a)** sabemos que: $P(exactamenteUno)= P(A \cup B)  - P(B \cap A) = 0.9 - 0.5 = 0.4$

## 3) Computadora
Supongamos que cuando una computadora se “cuelga” (no responde), el 75% de las veces se debe a problemas de memoria y el 15 % de las veces a problemas de software y que el 15 % de las veces se debe a problemas que no son ni de memoria ni de software. Si una computadora se cuelga,

(a) ¿cuál es la probabilidad de que estos dos problemas ocurran simultáneamente?

>- $P(A) = 0.75 \rightarrow$ "Probabilidad de problemas de memoria"
>- $P(B) = 0.15 \rightarrow$ "Probabilidad de problemas de software"
>- $P(A^c \cap B^c) = 0.15 \rightarrow$ "Probabilidad de problemas no son ni de memoria ni de software"
>
> Quiero calcular $P(A\cap B)$, vamos a usar la formula de $P(A \cup B)=P(A)+P(B)-P(A\cap B)$. Teniendo $P(A^c \cap B^c) = P((A \cup B)^c) = 1 - P(A \cup B) = 0.15 \Rightarrow P(A \cup B) = 0.85$. Entonces reemplazando en la fórmula nos queda:
>
> $$ P(A \cup B)=P(A)+P(B)-P(A\cap B)$$
>
> $$ 0.85 = 0.75 + 0.15 - P(A\cap B)$$
>
> $$ P(A\cap B) = 0.05$$

(b) ¿cuál es la probabilidad de que ocurra un problema de software y no de memoria?

> Queremos saber $P(B \cap A^c) = P(B) - P(B \cap A) = 0.15 - 0.05 = 0.10$ 

## 4) Bolillero
De un bolillero que contiene $5$ bolillas numeradas $1, 2, 3, 4, 5$ se extrae una al azar, sea la número $k$. Se eliminan las bolillas cuyo número es mayor que $k$ de la urna y se hace una segunda extracción al azar entre las bolillas $1$ a $k$, sea la número $j$. Se eliminan las bolillas cuyo número es mayor que $j$ de la urna y se hace una tercera extracción al azar entre las bolillas $1$ a $j$.

(a) Describir un espacio muestral adecuado para este experimento y determinar el número de elementos que posee.

> $S = \{(x_1, x_2, x_3) / 1 \leq x_3 \leq x_2 \leq x_1 \leq 5 \}$ 
> - Si $x_1 = 5:$
>   - $x_2$ puede ser 1, 2, 3, 4 o 5.
>   - Si $x_2=5$, $x_3$ puede ser 1, 2, 3, 4 o 5.
>   - Si $x_2=4$, $x_3$ puede ser 1, 2, 3, o 4.
>   - Si $x_2=3$, $x_3$ puede ser 1, 2, o 3.
>   - Si $x_2=2$, $x_3$ puede ser 1, o 2.
>   - Si $x_2=1$, $x_3$ puede ser 1.
>   - Secuencias: $(5,5,5), (5,5,4), (5,5,3), (5,5,2), (5,5,1), (5,4,4), (5,4,3), (5,4,2), (5,4,1), (5,3,3), (5,3,2), (5,3,1), (5,2,2), (5,2,1), (5,1,1)$. Con un total de 15 posibilidades.
> - Hay que hacer lo mismo para $x_1 = 4, 3, 2, 1$, por suerte se puede tirar un par de lineas de código para que lo haga :)
>
> Todas las secuencias están en el archivo [Practica1.ipynb](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica1/Practica1.ipynb) y el cálculo de todas las combinaciones posibles es $|S| = 35$.


(b) ¿Es razonable suponer equiprobabilidad en este espacio? ¿Qué probabilidad le asignarı́a al $(3,2,1)$?

> No realmente, ya que se define equiprobabilidad cuando los $n$ sucesos elementales tienen igual probabilidad, en este caso solo aplica al sacar tres veces $5$ ya que al tener que retirar las bolillas mayores al número que se extrajo, cambia la probabilidad en cada caso. Por ejemplo para la secuencia $(3,2,1)$ calculamos la probabilidad:
>
> $$P((3,2,1)) = P(x_1 = 3) * P(x_2 = 2) * P(x_3 = 1) = \frac{1}{5} * \frac{1}{3} * \frac{1}{2} = \frac{1}{30} $$
>
> Incluso para secuencias diferentes no va a tener la misma probabilidad:
> 
> $$P((5,5,5)) = P(x_1 = 5) * P(x_2 = 5) * P(x_3 = 5) = \frac{1}{5} * \frac{1}{5} * \frac{1}{5} = \frac{1}{125}$$

## 5) Proveedora de software
Una firma proveedora de software ha ofrecido sus servicios a $3$ empresas. Se definen los eventos $A_i =$ {la empresa i realiza una compra a esta firma} , para $i = 1, 2, 3$. Se sabe que:

- $P(A_1) = 0.22$
- $P(A_2) = 0.25$
- $P(A_3) = 0.28$
- $P(A_1 \cap A_2) = 0.11$
- $P(A_1 \cap A_3) = 0.05$
- $P(A_2 \cap A_3) = 0.07$
- $P(A_1 \cap A_2 \cap A_3) = 0.01$

Expresar en palabras los siguientes eventos y calcular sus probabilidades:

- $A_1 \cup A_2$
    > "La empresa $1$ o $2$ realizan una compra". 
    >
    >$$P(A_1 \cup A_2) = P(A_1) + P(A_2) - P(A_1 \cap A_2) = 0.22 + 0.25 - 0.11 = 0.36$$

- $A_1^c \cap A_2^c$
    > "La empresa 1 no compra y la empresa 2 no compra". 
    >
    >$$P(A_1^c \cap A_2^c) = P((A_1 \cup A_2)^c) = 1 - P(A_1 \cup A_2) = 1 - 0.36 = 0.64$$

- $A_1 \cup A_2 \cup A_3$
    > "La empresa 1 compra o la 2 compra o la 3 compra".
    >
    >$$P(A_1 \cup A_2 \cup A_3) = P(A_1) + P(A_2) + P(A_3) - P(A_1 \cap A_2) - P(A_1 \cap A_3) - P(A_2 \cap A_3) + P(A_1 \cap A_2 \cap A_3) = $$
    >
    >$$= 0.22 + 0.25 + 0.28 - 0.11 - 0.05 - 0.07 + 0.01 = 0.53$$
    >

- $A_1^c \cap A_2^c \cap A_3^c$
    > "Ninguno compra"
    >
    > $$P(A_1^c \cap A_2^c \cap A_3^c) = P((A_1 \cup A_2 \cup A_3)^c) = 1 - P(A_1 \cup A_2 \cup A_3) = 1 - 0.53 = 0.47$$
    >

- $A_1^c \cap A_2^c \cap A_3$
    > "Solamente 3 compra".
    >
    >$$P(A_1^c \cap A_2^c \cap A_3) =  P(A_3) - P(A_3 \cap A_2) - P(A_3 \cap A_1) + P(A_3 \cap A_2 \cap A_1) = 0.28 - 0.07 - 0.05 + 0.01 = 0.17$$
    >

- $(A_1^c \cap A_2^c ) \cup A_3$
    > "1 y 2 no compran o bien 3 compra"
    >
    >$$P((A_1^c \cap A_2^c ) \cup A_3) = P((A_1 \cup A_2)^c \cup A_3) = (1-P(A_1 \cup A_2)) +P(A_3) - P(A_1^c \cap A_2^c \cap A_3) = $$
    >
    >$$= 1-(P(A_1) + P(A_2) - P(A_1 \cap A_2)) + P(A_3) - P(A_1^c \cap A_2^c \cap A_3) =$$
    >
    >$$= 1- (0.22 + 0.25 - 0.11) +0.28 - 0.17 = 0.75$$
    >

## 6) Grupete
Un grupo de 60 alumnos será subdividido al azar en dos divisiones de 30 alumnos cada una. Cinco de esos alumnos son muy amigos: Alicia, Beto, Carmen, Diego y Eva.

(a) ¿Cuál es la probabilidad de que todos queden en la misma división?

> La cantidad de formas de dividir 60 alumnos en dos grupos de 30 es $\binom{60}{30}$ ya que al agarrar 30 alumnos automaticamente ubico el restante en el otro curso. Entonces para calcular la probabilidad de que el grupo entero quede junto simplemente los excluyo de la selección, es decir de 55 alumnos elijo 25 y ese va a ser un curso donde esté el grupo entero. Como hay dos posibles cursos, multiplico por dos. La cuenta queda:
>
>$$2*\frac{\binom{55}{25}}{\binom{60}{30}} \approx 0.0522$$

(b) ¿Cuál es la probabilidad de que sólo quede separado Diego?

> Acá tenemos que seleccionar 26 alumnos de 55 (excluyendo a diego). Pero no multiplicamos por dos ya que innevitablemente diego puede solo ir al curso contrario. La cuenta queda:
>
>$$\frac{\binom{55}{26}}{\binom{60}{30}} \approx 0.0301$$

## 7) Congreso
De un grupo de 6 mujeres y 4 hombres se deben elegir 3 personas para que los representen en tres congresos a desarrollarse en mayo, junio y septiembre.

(a) Suponiendo que una persona puede ir a más de un congreso, calcular la probabilidad de que
1. a los dos primeros congresos vayan mujeres.
    
    > **NOTA**: asumo que se eligen 1 persona por congreso, antes había entendido que iba 3 persona a cada congreso hasta que leí **(b)**.
    >
    > $P$("a los dos primeros congresos vayan mujeres") = $\frac{6}{10} * \frac{6}{10} * \frac{10}{10} = 0.36$

2. a los dos primeros congresos vayan mujeres y al tercero un hombre.

    > $P$("a los dos primeros congresos vayan mujeres y al tercero un hombre") = $\frac{6}{10} * \frac{6}{10} * \frac{4}{10} = 0.144$

3. haya por lo menos una mujer entre las 3 personas elegidas.

    > $P$("haya por lo menos una mujer entre las 3 personas elegidas") = $1 - P$("van al congreso todos hombres") = $1- \frac{4}{10} * \frac{4}{10} * \frac{4}{10} = 0.936$

(b) Si a cada congreso debe ir una persona diferente, calcular las mismas probabilidades que en **(a)** y además la probabilidad de que haya exactamente una mujer entre las 3 personas elegidas.

1. a los dos primeros congresos vayan mujeres.
    
    > $P$("a los dos primeros congresos vayan mujeres") = $\frac{6}{10} * \frac{5}{9} * \frac{8}{8} = 0.3333$

2. a los dos primeros congresos vayan mujeres y al tercero un hombre.

    > $P$("a los dos primeros congresos vayan mujeres y al tercero un hombre") = $\frac{6}{10} * \frac{5}{9} * \frac{4}{8} = 0.166$

3. haya por lo menos una mujer entre las 3 personas elegidas.

    > $P$("haya por lo menos una mujer entre las 3 personas elegidas") = $1 - P$("van al congreso todos hombres") = $1- \frac{4}{10} * \frac{3}{9} * \frac{2}{8} = 0.9666$

4. haya exactamente una mujer entre las 3 personas elegidas.

    >Elijo una mujer y dos hombres multiplicando por 3 para alternar congresos $\rightarrow P$("haya exactamente una mujer entre las 3 personas elegidas") = $3 * \frac{4}{10} * \frac{3}{9} * \frac{6}{8} = 0.3$

## 8) Negocio
En un negocio hay $6$ productos de cierto tipo, $3$ de ellos vencidos y $3$ que están dentro del periodo de validez. Si un supervisor, que no sabe cuántos envases válidos o vencidos hay, los revisa, ¿cuál es la probabilidad de que

(a) los tres primeros envases revisados contengan los productos vencidos?

> $P$("los tres primeros envases revisados contengan los productos vencidos") = $\frac{3}{6} * \frac{2}{5} * \frac{1}{4} = 0.05$

(b) necesite revisar exactamente i envases para encontrar los tres que contienen los productos vencidos? (hacerlo para i = 4, 5, 6).

> Datos:
>- El número total de maneras de seleccionar 3 productos de los 6 disponibles es $\binom{6}{3}$. 
>- Si en el $i$-esimo envase encuentro el único vencido que falta entre $6-i+1$ envases
>   - Si $i = 4$ tengo que encontrar el vencido entre 3 $\rightarrow P(4)= \frac{1}{3} = 0.3333$
>   - Si $i = 5$ tengo que encontrar el vencido entre 2 $\rightarrow P(5)= \frac{1}{2} = 0.5$
>   - Si $i = 6$ tengo que encontrar el vencido entre 1 $\rightarrow P(6)= \frac{1}{1} = 1$