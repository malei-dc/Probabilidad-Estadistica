# Clase 16-08-2024

## Ejercicio 1 
En cierto estado, 58 vertederos están clasificados según la concentración de 3 sustan-
cias quı́micas peligrosas: Arsénico, Bario y Mercurio. Supongamos que la concentración de cada una
se caracteriza como baja o alta. Si se elige un vertedero al azar, ¿cuál es la probabilidad de que tenga:

(a) alta concentración de Bario?

> Si definimos el conjunto $A$ como los vertedero que tienen alta concentración de Bario. Y tomamos en cuenta que $|S| = 58$ ya que son la cantidad de vertederos totales, $P(A) = \frac{|A|}{|S|} = \frac{1+4+3+8}{58} = 0.2758$.

(b) alta concentración de Mercurio y baja concentración tanto de Arsénico como de Bario?

> Definimos al conjunto $B$ como los vertederos que tienen alta concentración de Mercurio y baja concentración tanto de Arsénico como de Bario. Entonces $P(B) = \frac{|B|}{|S|} = \frac{10}{58} = 0.1724$

(c) baja concentración de una sustancia y alta de las otras dos?

> Definimos al conjunto $C$ como los vertederos que tienen baja concentración de una sustancia y alta de las otras dos. Entonces $P(C) = \frac{|C|}{|S|} = \frac{4+3+5}{58} = 0.2069$

## Ejercicio 2
Tenemos 3 cajas numeradas y 4 bolitas blancas que se distribuyen todas al azar. Calcular la probabilidad de que:

(a) la caja 1 tenga exactamente 2 bolitas,

> Primero debemos considerar cómo se distribuyen las 4 bolitas blancas entre las 3 cajas numeradas. Cada una de las 4 bolitas pueden ir en cualquiera de las 3 cajas, por lo tanto tenemos un espacio muestral de $|S|=3⁴$ que representa la cantidad de distribuciones posibles de 4 bolitas en 3 cajas numeradas.
>
> Para que la caja 1 tenga exactamente 2 bolitas, necesitamos elegir 2 de las 4 bolitas para colocar en la caja 1. El número de maneras de elegir 2 bolitas de 4 es dado por $\binom{4}{2}$. Las otras 2 bolitas restantes pueden ir en cualquiera de las 2 cajas restantes (caja 2 o caja 3), y cada una de estas 2 bolitas tiene 2 opciones de cajas, por lo que hay $2²$ maneras.
>
> Si definimos $A$ como el evento de que la caja 1 tenga exactamente 2 bolitas, tenemos que $|A| = \binom{4}{2} * 2² = 24$. Entonces $P(A)=\frac{|A|}{|S|}=\frac{24}{3⁴} = 0.2962$

(b) la caja 2 no tenga bolitas,

> Si la caja 2 no tiene bolitas, se distribuyen las 4 bolitas entre solo la primera y la tercera caja. Luego si definimos el evento $B$ como la caja 2 no tiene bolitas, el numero de distribuciones favorables es $|B| = 2⁴$
>
> Nos queda que $P(B)=\frac{|B|}{|S|}=\frac{16}{81}=0.1975$

(c) todas las cajas tengan al menos 1 bolita.

> Vamos a usar el principio de inclusión-exclusión.
>1. Calculamos el número total de distribuciones posibles, sabemos que es $3⁴ =81$
>2. Restamos las configuraciones en las que al menos una caja está vacía. Si una caja está vacía, las 4 bolitas se distribuyen en 2 cajas, son $2⁴ = 16$ formas de hacerlo. Como hay 3 cajas entonces son $3*16=48$ formas
>3. Ahora tenemos que agregar las configuraciones en las que dos cajas están vacías (ya que estas fueron restadas dos veces). Si dos cajas están vacías, todas las bolitas deben estar en la caja restante. Hay exactamente 1 forma de hacer esto, y hay $\binom{3}{2}=3$ formas de elegir las dos cajas vacías.
>
> Si definimos $C$ como el evento que todas las cajas tengan al menos 1 bolita, la cantidad de distribuciones favorables son $|C|=81-48+3=36$.
>
> Luego $P(C)=\frac{|C|}{|S|}=\frac{36}{81}=0.4444$

## Ejercicio 3
Una empresa constructora trabaja en dos proyectos diferentes. Sea $A$ el evento: “el primero de los proyectos se termina en la fecha del contrato” y definamos análogamente $B$ para el segundo proyecto. Si $P (A \cup B) = 0,9$ y $P (A \cap B) = 0,5$, ¿cuál es la probabilidad de que exactamente un proyecto se termine para la fecha del contrato?

> $P(exactamente\_ uno\_ de\_ A\_ o\_ B)= P(A \cup B)  - P(B \cap A) = 0.9 - 0.5 = 0.4$
>
> El origen de la fórmula explicado en el [Ejercicio 2a de la práctica 1](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica1).

## Ejercicio 4
En una materia optativa, el 35 % de los asistentes estudia ingenierı́a, el 67 % prefiere Netflix y el 56 % toma café. El 27 % estudia ingenierı́a y prefiere Netflix, el 29 % prefiere Netflix y toma café y el 22 % estudia ingenierı́a y toma café. El 5 % no estudia ingenierı́a ni prefiere Netflix ni toma café. Si elige un asistente al azar, calcular la probabilidad de que:

(a) no tome café y prefiera Netflix,

> Vamos a nombrar cada evento con algún nombre:
> - $A$ = "Estudia ingenierı́a" $\rightarrow P(A) = 0.35$
> - $B$ = "Prefiere Netflix" $\rightarrow P(B) = 0.67$
> - $C$ = "Toma café" $\rightarrow P(C) = 0.56$
>> - $A \cap B$ = "Estudia ingenierı́a y prefiere Netflix" $\rightarrow P(A \cap B) = 0.27$ 
>> - $B \cap C$ = "Prefiere Netflix y toma café" $\rightarrow P(B \cap C) = 0.29$
>> - $A \cap C$ = "Estudia ingenierı́a y toma café" $\rightarrow P(A \cap C) = 0.22$
>>> - $A^c \cap B^c \cap C^c$ = "no estudia ingenierı́a ni prefiere Netflix ni toma café" $\rightarrow P(A^c \cap B^c \cap C^c) = 0.05$
>
> Queremos calcular $P(C^c \cap B)$. Usamos la relación que tenemos entre $B$.
>
> $$P(B) = P(B \cap C) \cup P(B \cap C^c) =  P(B \cap C) + P(B \cap C^c)$$
> $$0.67 = 0.29 +  P(B \cap C^c) \Rightarrow P(B \cap C^c) = 0.38$$

(b) solo tome café,

> Quiero calcular $P(C \cap A^c \cap B^c) = P(C) - P(C \cap A) - P(C \cap B) + P(A \cap B \cap C)$, como en (e) calculé que $P(A \cap B \cap C) = 0.15$ ya tengo todo lo que necesito para calcular el resultado:
>
> $$P(C \cap A^c \cap B^c) = P(C) - P(C \cap A) - P(C \cap B) + P(A \cap B \cap C)$$
> $$P(C \cap A^c \cap B^c) = 0.56 - 0.22 - 0.29 + 0.15 = 0.2$$

(c) solo estudie ingenierı́a,

> $$P(A \cap B^c \cap C^c) = P(A) - P(A \cap C) - P(A \cap B) + P(A \cap B \cap C)$$
> $$P(A \cap B^c \cap C^c) = 0.35 - 0.22 - 0.27 + 0.15 = 0.01$$

(d) estudie ingenierı́a o prefiera Netfix,

> Se quiere calcular $P(A \cup B) = P(A) + P(B) - P(A \cap B) = 0.35 + 0.67 - 0.27 = 0.75$

(e) posea las tres caracterı́sticas mencionadas.

> Queremos calcular $P(A \cap B \cap C)$. Usando la fórmula de inclusión-exclusión para $P(A \cup B \cup C)$ tenrmos:
>
> $$ P(A \cup B \cup C) = P(A)+P(B)+P(C)-P(A \cap B)-P(A \cap C)-P(C \cap B)+P(A \cap B \cap C)$$
>
> Como tenemos que $P(A^c \cap B^c \cap C^c) = P((A \cup B \cup C)^c) = 0.05 \Rightarrow P(A \cup B \cup C) = 1 - 0.05 = 0.95$ y con esto ya podemos despejar la fórmula:
>
> $$ P(A \cup B \cup C) = P(A)+P(B)+P(C)-P(A \cap B)-P(A \cap C)-P(C \cap B)+P(A \cap B \cap C)$$
> $$ 0.95 = 0.35+0.67+0.56-0.27-0.22-0.29+P(A \cap B \cap C)$$
> $$ P(A \cap B \cap C) = 0.15$$









