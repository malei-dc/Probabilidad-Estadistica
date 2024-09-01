# Práctica 1

## Introducción a la probabilidad y teoría de conjuntos

### 1) Dado equilibrado
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

### 2) Eventos
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

### 3) Computadora
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

### 4) Bolillero
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

### 5) Proveedora de software
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

### 6) Grupete
Un grupo de 60 alumnos será subdividido al azar en dos divisiones de 30 alumnos cada una. Cinco de esos alumnos son muy amigos: Alicia, Beto, Carmen, Diego y Eva.

(a) ¿Cuál es la probabilidad de que todos queden en la misma división?

> La cantidad de formas de dividir 60 alumnos en dos grupos de 30 es $\binom{60}{30}$ ya que al agarrar 30 alumnos automaticamente ubico el restante en el otro curso. Entonces para calcular la probabilidad de que el grupo entero quede junto simplemente los excluyo de la selección, es decir de 55 alumnos elijo 25 y ese va a ser un curso donde esté el grupo entero. Como hay dos posibles cursos, multiplico por dos. La cuenta queda:
>
>$$2*\frac{\binom{55}{25}}{\binom{60}{30}} \approx 0.0522$$

(b) ¿Cuál es la probabilidad de que sólo quede separado Diego?

> Acá tenemos que seleccionar 26 alumnos de 55 (excluyendo a diego). Pero no multiplicamos por dos ya que innevitablemente diego puede solo ir al curso contrario. La cuenta queda:
>
>$$\frac{\binom{55}{26}}{\binom{60}{30}} \approx 0.0301$$

### 7) Congreso
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

### 8) Negocio
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

> ESTA MAL, PREGUNTAR

### 9) Cuad unión
(a) Enunciar y probar una fórmula para $P(A_1 \cup A_2 \cup A_3 \cup A_4)$

> $$P(A_1 \cup A_2 \cup A_3 \cup A_4) = P(A_1) + P(A_2) + P(A_3) + P(A_4)$$
>
> $$- P(A_1 \cap A_2) - P(A_1 \cap A_3) - P(A_1 \cap A_4) - P(A_2 \cap A_3) - P(A_2 \cap A_4) - P(A_3 \cap A_4)$$
> 
> $$+ P(A_1 \cap A_2 \cap A_3) + P(A_1 \cap A_2 \cap A_4) + P(A_1 \cap A_3 \cap A_4) + P(A_2 \cap A_3 \cap A_4)$$
>
> $$- P(A_1 \cap A_2 \cap A_3 \cap A_4)$$
>
> Prueba: 
> 1. Primero, sumamos las probabilidades de los eventos individuales: $P(A_1) + P(A_2) + P(A_3) + P(A_4)$
> 2. Las intersecciones de dos eventos fueron contadas dos veces en el paso anterior, por lo que restamos las probabilidades de las intersecciones: $- [P(A_1 \cap A_2) + P(A_1 \cap A_3) + P(A_1 \cap A_4) + P(A_2 \cap A_3) + P(A_2 \cap A_4) + P(A_3 \cap A_4)]$
> 3. Las intersecciones de tres eventos fueron restadas una vez de más en el paso anterior, así que las sumamos nuevamente: $+ P(A_1 \cap A_2 \cap A_3) + P(A_1 \cap A_2 \cap A_4) + P(A_1 \cap A_3 \cap A_4) + P(A_2 \cap A_3 \cap A_4)$
> 4. Finalmente, la intersección de los cuatro eventos fue sumada una vez de más en el paso anterior, por lo que la restamos: $- P(A_1 \cap A_2 \cap A_3 \cap A_4)$

(b) Cuatro matrimonios deciden bailar un tango, eligiendo las mujeres a sus compañeros al azar.
1. ¿Cuál es la probabilidad de que la mujer $i$ (fijo) elija a su esposo como pareja de baile; $i=1,2,3,4$?

    > La probabilidad de que la mujer $i$ elija al azar y que resulte ser su esposo es de $\frac{1}{4} = 25\% $

2. ¿Cuál es la probabilidad de que al menos 1 mujer elija a su esposo?

    > Hmmm

(c) Estimar las probabilidades del item **b)** por medio de una simulación. Compare con los resultados obtenidos en **b)**.

## Probabilidad condicional

### 10) Nivel de ingresos
Un estudio sobre la relación entre nivel de ingresos (A=alto, M=medio, B=bajo) y la preferencia por una de las tres grandes marcas de automóviles (Y,W,Z) da como resultado la siguiente tabla de probabilidades conjuntas.

| | B | M | A | | |  
|:---------:|:-----------:|:-----------:|:-----------:|:-----------:|:-----------:|
| Y | 0.10 | 0.13 | 0.02 || 0.25 |
| W | 0.20 | 0.12 | 0.08 || 0.40 |
| Z | 0.10 | 0.15 | 0.10 || 0.35 | 
| | | | | | |
| | 0.40 | 0.40 | 0.20 || 1.00 |

Esta tabla muestra por ejemplo que: 
- $P$(ingreso bajo y preferencia $Y$ ) = $P (B \cap Y ) = 0.10$
- $P$(ingreso bajo) = $P(B) = 0.40$
- $P$(preferencia $Y$) = $P(Y) = 0.25$

(a) En base a esta tabla calcular las siguientes probabilidades condicionales:

- $P(W|A)$

    > Tengo que calcular la probabilidad de que la persona tenga de preferencia $W$ siendo  alto su nivel de ingreso ($A$).
    >
    > $P(W|A) = \frac{P(W \cap A)}{P(A)} = \frac{0.08}{0.20} = 0.4$

- $P(M|Z)$

    > Tengo que calcular la probabilidad de que la persona tenga un nivel de ingreso $M$ siendo que tiene preferencia $Z$.
    >
    > $P(M|Z) = \frac{P(M \cap Z)}{P(Z)} = \frac{0.15}{0.35} = 0.4285$


- $P(Y^c|M)$

    > Tengo que calcular la probabilidad de que no tiene preferencia $Y$ siendo de ingresos medios ($M$).
    >
    > $P(Y^c|M) = \frac{P(Y^c \cap M)}{P(M)} = \frac{0.27}{0.40} = 0.675$

- $P(M|Y^c)$

    > Tengo que calcular la probabilidad de que sea de ingreso medio ($M$) sabiendo que no tiene de preferencia $Y$.
    >
    > $P(M|Y^c) = \frac{P(M \cap Y^c)}{P(Y^c)} = \frac{0.27}{0.75} = 0.36$

- $P(M|W \cup Z)$

    > Tengo que calcular la probabilidad de que de ingreso medio ($M$) sabiendo que tiene de preferencia a $W$ o $Z$.
    >
    > $P(M|W \cup Z) = \frac{P(M \cap (W \cup Z))}{P(W \cup Z)} = \frac{0.12+0.15}{0.75} = 0.36$

- $P(B \cup M|Z)$

    > Tengo que calcular la probabilidad de que alguien tenga los ingresos bajos o medio sabiendo que tiene la preferencia $Z$
    >
    > $P(B \cup M|Z) = \frac{P((B \cup M) \cap Z)}{P(Z)} = \frac{0.10 + 0.15}{0.35} = 0.7142$

(b) ¿Cuál es la probabilidad de que una persona elegida al azar prefiera la marca $Y$ o tenga un alto ingreso?

> $P(Y \cup A) = P(Y) + P(A) - P(Y \cap A) = 0.25 + 0.20 - 0.02 = 0.43$

### 11) Dos dados equilibrados
Una persona arroja dos dados equilibrados. Calcular la probabilidad de que la suma sea 7 dado que

> $S =$ "arroja dos dados equilibrados" $= \{ (x_1, x_2) | 1 \leq x_1, x_2 \leq 6 \} \rightarrow |S| = 36$
>
> $A =$ "la suma sea 7" $= \{ (x_1, x_2) | x_1 + x_2 = 7 \} = \{ (1, 6), (2, 5), (3, 4), (4, 3), (5, 2), (6, 1) \} \rightarrow |A|=6$ 

(a) la suma es impar.

> $B =$ "la suma es impar" $=\{ (x_1, x_2)|(x_1 \text{ impar } \land x_2 \text{ par }) \lor (x_2 \text{ impar } \land x_1 \text{ par }) \} \rightarrow |B| = 36/2 = 18$
>
> Queremos calcular $P(A|B)$, notar que $A \subset B$, así que $P(A \cap B) = \frac{6}{36} = 0.1666$
>
> $P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{6}{36}}{\frac{18}{36}} = \frac{1}{3} = 0.3333$

(b) la suma es mayor que 6.

> $C =$ "la suma es mayor que 6" $= \{ (1, 6), (2, 6...5), (3, 6...4), (4, 6...3), (5, 6...2), (6,1...6) \} \rightarrow |C|= 1+2+3+4+5+6 = 21$
>
> Queremos calcular $P(A|C)$, notar que $A \subset C$, así que $P(A \cap C) = \frac{6}{36} = 0.1666$
>
> $P(A|C) = \frac{P(A \cap C)}{P(C)} = \frac{\frac{6}{36}}{\frac{21}{36}} = \frac{6}{21} = 0.2857$

(c) el número del segundo dado es par.

> $D =$ "el número del segundo dado es par" $= \{ (x_1, x_2| x_2 \text{ par}) \} \rightarrow |D| = 6*3 = 18$
>
> Queremos calcular $P(A|D)$, sabemos que $A \cap D = \{ (1, 6), (3, 4), (5, 2) \} $
> 
> $P(A|D) = \frac{P(A \cap D)}{P(D)} = \frac{\frac{3}{36}}{\frac{18}{36}} = \frac{1}{6} = 0.1666$

(d) el número de alguno de los dados es impar.

> $E =$ "el número de alguno de los dados es impar" $= \{ (x_1, x_2)| x_1 \text{ impar } \lor x_2 \text{ impar} \} \rightarrow |E| = 36 - |E^c| (\{ (x_1, x_2)| x_1 \text{ par } \land x_2 \text{ par } \} ) = 36 - (3*3) = 27$ 
>
> Queremos calcular $P(A|E)$, notar que $A \subset E$, así que $P(A \cap E) = \frac{6}{36} = 0.1666$
>
> $P(A|E) = \frac{P(A \cap E)}{P(E)} = \frac{\frac{6}{36}}{\frac{27}{36}} = \frac{2}{9} = 0.2222$

(e) los números de los dados son iguales.

> $F =$ "los números de los dados son iguales" $= \{ (x_1, x_2)| x_1 = x_2 \} \rightarrow |F| = 6$
>
> Sabemos que si los dos dados suman 7 no pueden ser numero iguales, por eso $P(A|F) = 0$, ya que $A \cap F = \emptyset$. 

(f) Estime las probabildades de los items anteriores por medio de una simulación.

>En el archivo [Practica1.ipynb](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica1/Practica1.ipynb)

### 12) Tres dados
Se lanzan 3 dados. Si ninguno muestra la misma cara, ¿cuál es la probabilidad de que haya salido exactamente un as?

> **Nota**: un "as" en dados quiere decir que sale el número $1$.
>
> $S =$ "Tiramos 3 dados" $= \{ (x_1, x_2, x_3)| 1 \leq x_1,x_2,x_3 \leq 6 \} \rightarrow |S| = 6 * 6 * 6 = 216$
>
> $A =$ "ninguno muestra la misma cara" $= \{ (x_1, x_2, x_3)| x_1 \neq x_2 \neq x_3 \} \rightarrow |S| = 6 * 5 * 4 = 120$
>
> $B =$ "haya salido exactamente un as" 
>
> Necesitamos calcular $P(B|A)$,  pero primero calculemos $A \cap B =$ "ninguno muestra la misma cara y salió exactamente un 1". Para calcular esto tengo en cuenta que el 1 puede salir en el primer dado, en el segundo o en el tercero y no pueden salir la misma cara en ninguno de los dados. $|A \cap B| = (1 * 5 * 4) + (5 * 1 * 4) + (5 * 4 * 1) = 60$
>
> $P(B|A) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{60}{216}}{\frac{120}{216}} = \frac{1}{2} = 0.5$

### 13) Computación online
Un sistema de computación on-line tiene 4 lı́neas de entrada para comunicación. Cada lı́nea cubre un porcentaje del tráfico de entrada y cada lı́nea tiene un porcentaje de mensajes que ingresan con error. La tabla a continuación describe estos porcentajes:

> Sea $S$ el evento de los mensajes que entran sin error por cualquier línea.

|Línea|% de mensajes que entra por la Lı́nea|% de mensajes sin error|
|:---------:|:-----------:|:-----------:|
|1|$P(L_1) =$ 40%|$P(S/L_1) =$ 99.8%|
|2|$P(L_2) =$ 30%|$P(S/L_2) =$ 99.9%|
|3|$P(L_3) =$ 10%|$P(S/L_3) =$ 99.7%|
|4|$P(L_4) =$ 20%|$P(S/L_4) =$ 99.2%|

(a) ¿Cuál es la probabilidad de que al elegir al azar un mensaje, éste haya ingresado sin error?

> Tenemos que calcular $P(S)$. Usamos el teorema de la probabilidad total ya que $L_1, L_2, L_3, L_4$ son particiones de nuestro espacio muestral $S$.
>
> $$P(S) = P(L_1) * P(S/L_1) + P(L_2) * P(S/L_2) + P(L_3) * P(S/L_3) + P(L_4) * P(S/L_4) = $$
>
> $$= 0.4 * 0.998 + 0.3 * 0.999 + 0.1 * 0.997 + 0.2 * 0.992 = 0.997 $$

(b) ¿Cuál es la probabilidad de que, si el mensaje entró con error, haya ingresado por la lı́nea 1?

> Sea $S^c$ el evento de los mensajes que entran con error por cualquier línea. $P(S^c) = 1 - P(S) = 1 - 0.997 = 0.003$
>
> Quiero calcular $P(L_1|S^c) = \frac{P(S^c|L_1)*P(L_1)}{P(S^c)} = \frac{(1-0.998)*0.4}{0.003} = 0.2666$

### 14) Caja con tres monedas
Una caja contiene tres monedas, una de las cuales tiene dos caras, otra tiene dos cruces (o cecas) y la tercera es una moneda normal. Se extrae de la caja una moneda al azar y se arroja, obteniéndose una cara.

(a) ¿Cuál es la probabilidad de haber elegido la moneda con dos caras?

> - $M_1:$ "elegir moneda dos caras"
> - $M_2:$ "elegir moneda dos cruces"
> - $M_3:$ "elegir moneda normal"
> - $X:$ "obtener cara al tirar una moneda"
>
> Sabemos que la probabilidad de que salga cara con una moneda de caras es 1 y la probabilidad de que salga cara en una moneda normal es 0.5. Calculamos usando el teorema de la probabilidad total $P(X) = P(X|M_1) * P(M_1) + P(X|M_2) * P(M_2) + P(X|M_3) * P(M_3) = 1 * \frac{1}{3} + 0 * \frac{1}{3} + 0.5 * \frac{1}{3} = \frac{1}{2} = 0.5$
>
> Calculamos usando el teorema de bayes $P(M_1|X) = \frac{P(X|M_1) * P(M_1)}{P(X)} = \frac{1 * \frac{1}{3}}{\frac{1}{2}} = \frac{2}{3}$

(b) Si se arroja nuevamente la moneda extraı́da, ¿cuál es la probabilidad de obtener otra vez cara?

> Sabemos de la primera tirada: 
> - $P(M_1|X) = \frac{2}{3}$
> - $P(M_3|X) = \frac{1}{3}$ (haciendo complemento de arriba, no consideramos $M_2$ ya que no puede salir cara)
>
> Sea $Y:$ "sale cara en la segunda tirada"
>
> La probabilidad de volver a sacar cara es la suma de probabilidad de sacar cara en respectivos monedas por la probabilidad de la moneda que haya sido sacada sabiendo que la primera tirada fue cara.
>
> $$P(Y) = P(X|M_1) * P(M_1|X) + P(X|M_3) * P(M_3|X) = 1 * \frac{2}{3} + 0.5 * \frac{1}{3} = \frac{5}{6} = 0.8333$$

### 15) Enfermedad
Una enfermedad afecta a una de cada 500 personas de cierta población. Se usa un examen radiológico para detectar posibles enfermos. Se sabe que la probabilidad de que el examen aplicado a un enfermo lo muestre como tal es 0.90 y que la probabilidad
de que el examen aplicado a una persona sana la muestre como enferma es 0.01. 

Calcular la probabilidad de que una persona esté realmente enferma si su examen dio positivo.

> Sea $A =$ "una persona enferma" y $B =$ "el examen sale positivo". Sabemos que $P(B|A) = 0.9$ y que $P(B|A^c)=0.01$ 
>
> Queremos calcular $P(A|B) = \frac{P(A \cap B)}{P(B)}$ como sabemos que $P(A) = \frac{1}{500} = 0.002 > 0$ podemos aplicar la regla del producto en el numerador $= \frac{P(B|A) * P(A)}{P(B)}$ en el denominador aplicamos el teorema de la probabilidad total, nos queda entonces $= \frac{P(B|A) * P(A)}{P(B|A) * P(A) + P(B|A^c) * P(A^c)} = \frac{0.9 * 0.002}{0.9 * 0.002 + 0.01 * (1-0.002)} = 0.1528$.
>
> De hecho esto de aplicar en el numerador la regla del producto y en el denominador el teorema de la probabilidad total se llama **teorema de bayes**

### 16) Tres cajas
Hay tres cajas $A, B$ y $C$ con 20 piezas cada una, conteniendo 20, 15 y 10 piezas buenas respectivamente. La probabilidad de elegir la caja $A$ es igual a la de elegir la caja $B$, y la de elegir la caja $C$ es igual a la suma de esas dos probabilidades. Eligiendo al azar una caja se extraen con reposición dos piezas que resultan ser buenas. Hallar la probabilidad condicional de que provengan de la caja $A$.

> Sean $A =$ "elegir caja A", $B =$ "elegir caja B" y $C =$ "elegir caja C". Sabemos que $P(A) + P(B) + P(C) = 1$, como nos dicen que $P(A) = P(B)$ y $P(C) = P(A) + P(B)$ reemplazando en la cuenta nos da:
>
>$$P(A) + P(B) + P(C) = P(A) + P(B) + (P(A) + P(B)) = 4 * P(A) = 1 \rightarrow P(A) = \frac{1}{4}$$
>
> Y con esto sabemos que $P(B) = \frac{1}{4}$ y $P(C) = \frac{1}{2}$.
>
> Definimos el evento $X = $ "extrae dos piezas buenas", teniendo en cuenta que es con reposición y sabiendo la cantidad de piezas buenas en cada caja, aplicamos el teorema de bayes, donde extraer dos piezas buenas es el producto de la relacion de pieza buena con pieza totales dos veces por la chance de elegir respectiva caja.
>
> $$P(A|X) = \frac{P(X|A) * P(A)}{P(X|A) * P(A) + P(X|B) * P(B) + P(X|C) * P(C)} = \frac{1 * \frac{1}{4}}{1 * \frac{1}{4} + (\frac{15}{20})^2 * \frac{1}{4} + (\frac{10}{20})^2 * \frac{1}{2}} = 0.4848$$

### 17) Dos urnas
Se dispone de dos urnas, cuyo contenido es el siguiente:

- Urna $A$: 5 bolitas rojas y 3 blancas.
- Urna $B$: 1 bolita roja y 2 blancas.

Se arroja un dado equilibrado. Si sale 3 ó 6 se extrae una bolita de la urna $A$ y se la coloca en $B$, luego se saca una bolita de $B$. En caso contrario el proceso se hace a la inversa.

(a) Hallar la probabilidad de que ambas bolitas sean rojas.

> Sean $A =$ "sale 3 o 6" y $X_i =$ "sacar bolita roja en extracción $i$".
>
> Sabemos que $P(A) = \frac{1}{3}$ y que $P(A^c) = \frac{2}{3}$. Para calcular $P(X_i)$ va a depende de $A$, es decir si sale el 3 o 6 entonces $P(X_1)= \frac{5}{8}$ ya que en la urna A hay 5 bolitas rojas de 8, siguiendo los paso, si colocamos una bolita de la urna $A$ a $B$, si es una bolita roja entonces $P(X_2)= \frac{1}{2}$ ya que habría 2 bolitas rojas de cuatro, si no, sería $P(X_2)= \frac{1}{4}$. Y así con los casos para $A^c$
> 
> Aplicamos regla de producto para todas las etapas sabiendo que $P(X_1 \cap X_2) > 0$ para cualquier caso ya que hay al menos una bolita roja en cada urna.
>
> $$P(X_1 \cap X_2) = P(X_1 \cap X_2 \cap A) + P(X_1 \cap X_2 \cap A^c)$$
>
> $$= P(X_2 | (X_1 \cap A)) * P(X_1|A) * P(A) + P(X_2 | (X_1 \cap A^c)) * P(X_1|A^c) * P(A^c)$$
>
> $$= \frac{2}{4} * \frac{5}{8} * \frac{1}{3} + \frac{6}{9} * \frac{1}{3} * \frac{2}{3} = \frac{109}{432} = 0.2523$$ 


(b) Si ambas bolitas son rojas, ¿cuál es la probabilidad de que haya salido 3 ó 6?

> Pide $P(A|(X_1 \cap X_2)) = \frac{P(A \cap X_1 \cap X_2)}{P(X_1 \cap X_2)} = \frac{P(X_2 | (X_1 \cap A)) * P(X_1|A) * P(A)}{P(X_1 \cap X_2)} = \frac{\frac{2}{4} * \frac{5}{8} * \frac{1}{3}}{\frac{109}{432}} = \frac{45}{109} = 0.4128$

### 18) Generalización urnas
Se tienen $(n + 1)$ urnas numeradas $0, 1, . . . , n$. La urna $i$ contiene $i$ bolitas blancas y $(n − i)$ bolitas negras. Se elige al azar una urna y de ella se extrae una bolita al azar. Sugerencia: usar $\sum_{i=1}^{n} i = \frac{n * (n+1)}{2}$

> Tenemos urnas $U_i$ con bolitas $(B = Blancas, N = Negras)$
>
> - $i = 0 \rightarrow U_0(B=0, N=n-0)$
> - $i = 1 \rightarrow U_1(B=1, N=n-1)$
> - $i = 2 \rightarrow U_2(B=2, N=n-2)$
> - ...
> - $i = n \rightarrow U_n(B=n, N=n-n)$ 

(a) Calcular la probabilidad de que la bolita extraı́da sea blanca.

> Usamos el teorema de la probabilidad total ya que vemos que hay $n+1$ particiones del espacio muestral. 
>
>$$P(B) = \sum_{i = 0}^{n}P(B|U_i) * P(U_i) = \sum_{i = 0}^{n} \frac{i}{n} * \frac{1}{n+1} = \sum_{i = 0}^{n} i * \frac{1}{n*(n+1)} =$$
>
> Acá es donde usamos la sugerencia de la suma de gauss
>
>$$= \frac{n * (n+1)}{2} * \frac{1}{n*(n+1)} = \frac{1}{2} = 0.5$$

(b) Si la bolita extraı́da es blanca, calcular la probabilidad de que provenga de la urna i, (i = 0,1, . . . , n).

> $P(U_i|B) = \frac{P(B \cap U_i) * P(U_i)}{P(B)} = \frac{\frac{i}{n} * \frac{1}{n+1}}{\frac{1}{2}} = \frac{2i}{n*(n+1)}$

### 19) Independencia de sucesos
Se extrae al azar una bolita de una urna que contiene 9 bolitas de las cuales 3 son blancas, 3 son negras y 3 son rojas. Las bolitas están numeradas 1, 2 y 3 dentro de cada color y además las siguientes bolitas están rayadas: número uno color blanco, número dos color negro y número tres color rojo. Sean los sucesos:

- $A$: la bolita es número uno.
- $B$: la bolita es blanca.
- $C$: la bolita es rayada.

> Notar que $P(A) = \frac{1}{3}$, $P(B) = \frac{1}{3}$ y $P(C) = \frac{1}{3}$

(a) ¿Son independientes de a pares los sucesos $A$, $B$ y $C$?

> Para ver que los sucesos de a pares son independiente tenemos que calcular la probabilidad de cada par y ver que sea igual que al producto de sus probabilidades individuales. Es decir:
>
> - $P(A|B) = \frac{P(A \cap B)}{P(B)} = \frac{\frac{1}{9}}{\frac{1}{3}} \rightarrow P(A \cap B)= P(A|B) * P(B) = \frac{1}{3} * \frac{1}{3} = \frac{1}{9} = P(A) * P(B)$
> - $P(A|C) = \frac{P(A \cap C)}{P(C)} = \frac{\frac{1}{9}}{\frac{1}{3}} \rightarrow P(A \cap C)= P(A|C) * P(C) = \frac{1}{3} * \frac{1}{3} = \frac{1}{9} = P(A) * P(C)$
> - $P(B|C) = \frac{P(A \cap C)}{P(C)} = \frac{\frac{1}{9}}{\frac{1}{3}} \rightarrow P(B \cap C)= P(B|C) * P(C) = \frac{1}{3} * \frac{1}{3} = \frac{1}{9} = P(B) * P(C)$
>
> Con esto conluimos que los sucesos de a pares son independientes entre sí.

(b) ¿Son independientes los sucesos A, B y C?

> Para ver si los tres son independientes hay que ver $P(A \cap B \cap C) = \frac{1}{9} \neq \frac{1}{27} = P(A) * P(B) * P(C)$

### 20) Sistema de componentes  
Considérese un sistema de componentes conectados como lo muestra la Figura 1. Los componentes 1 y 2 están conectados en paralelo, de manera que el subsistema funciona si y sólo si cualquiera de ellos funciona; en cambio los componentes 3 y 4 están conectados en serie y por lo tanto este subsistema funciona si y sólo si ambos funcionan. El sistema funciona si al menos uno de los dos subsistemas funciona. Si los componentes trabajan independientemente y la probabilidad de que un componente cualquiera funcione es 0.9,

(a) calcular la probabilidad de que el sistema funcione.

> Sea el evento $C_i:$ "el componente $i$ funciona" y sabiendo $P(C_i) = 0.9$ siendo independientes. Necesitamos calcular $P(S)$ siendo que el sistema funciona cuando los dos subistemas funciona.
>
> $$P(S) = P((C_1 \cup C_2) \cup (C_3 \cap C_4)) =$$
>
> $$= P(C_1 \cup C_2) + P(C_3 \cap C_4) - P((C_1 \cup C_2) \cap (C_3 \cap C_4))=$$
>
> $$= P(C_1) + P(C_2) - P(C_1 \cap C_2) + P(C_3 \cap C_4) - [P((C_1 \cap C_3 \cap C_4) \cup (C_2 \cap C_3 \cap C_4))]=$$
>
> $$= P(C_1) + P(C_2) - P(C_1 \cap C_2) + P(C_3 \cap C_4) - [P(C_1 \cap C_3 \cap C_4) + P(C_2 \cap C_3 \cap C_4) - P(C_1 \cap C_3 \cap C_4 \cap C_2)]=$$
>
> $$= 0.9 + 0.9 - 0.9 * 0.9 + 0.9 * 0.9 - (0.9 * 0.9 * 0.9 + 0.9 * 0.9 * 0.9 - 0.9 * 0.9 * 0.9 * 0.9) = 0.9981$$

(b) calcular la probabilidad de que el componente 1 no funcione si se sabe que el sistema sı́ funciona.

> $P(C_1^c | S) = 1 - P(C_1|S) = 1 - \frac{P(S|C_1) * P(C_1)}{P(S)} = 1 - \frac{1 * 0.9}{0.9981}= 0,09828$

### 21) $n$ sucesos independientes
Sean $S_1 , . . . , S_n$ sucesos independientes tales que $P(S_i) = p_i$.

(a) Expresar en función de los $p_i$ la probabilidad de que de los $S_i$ ocurra:

- ninguno.

    > $P((\bigcup_{i=1}^n S_i)^c) = P(\bigcap_{i=1}^n S_i^c) = \prod_{i = 1}^n P(S_i^c) = \prod_{i = 1}^n (1 - p_i)$

- al menos uno.

    > Que al menos uno de los sucesos $S_i$ ocurra es el complemento de la situación en el que **ningún** suceso ocurra.
    >
    > $P(((\bigcup_{i=1}^n S_i)^c)^c) = 1 - P(\bigcap_{i=1}^n S_i^c) = 1 - \prod_{i = 1}^n P(S_i^c) = 1 - \prod_{i = 1}^n (1 - p_i)$  

- exactamente uno.

    > Preguntar!!

(b) Para $k = 0, . . . , n$, hallar la probabilidad de que ocurran exactamente $k$ de los sucesos $S_i$ en el caso en que $P(S_i) = p$ para todo $i$.

> 
