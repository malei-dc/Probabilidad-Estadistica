# Práctica 2

## Variables aleatorias discretas, esperanza y varianza

### 1) Lote de artículos

De un lote que contiene $15$ artı́culos, de los cuales $4$ son defectuosos, se eligen $3$ artı́culos al azar con reposición. Si llamamos $X$ al número de artı́culos defectuosos entre los seleccionados,

(a) Hallar la función de probabilidad puntual asociada a X y graficarla usando R. (voy a usar python)

> $X:$ "número de artı́culos defectuosos entre los seleccionados". Sabemos que se pueden selecionar 0, 1, 2, 3 defectuosos por lo tanto $P_X = \{ 0,1,2,3 \}$
>
> Las probabilidad puntuales son:
>
> - $p_X(0) = P(X = 0) = (\frac{11}{15})^3 = 0.3943$
> - $p_X(1) = P(X = 1) = (\frac{11}{15})^2 * \frac{4}{15} * 3= 0.4302$
> - $p_X(2) = P(X = 2) = (\frac{4}{15})^2 * \frac{11}{15} *3 = 0.1563$
> - $p_X(3) = P(X = 3) = (\frac{4}{15})^3 = 0.0189$
>
> [Gráfico](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

(b) ¿Cuál es la probabilidad de que al menos 2 artı́culos sean defectuosos?

> Que sean al menos dos quiere decir de que sean 2 o 3 artículos, luego $P(X \geq 2) = P(X=2) + P(X=3) = 0.1563+ 0.0189 = 0.1752$

(c) Hallar la función de distribución acumulada de X y graficarla usando R.

> Función de distribución acumulada de X:
>
> - Si $x < 0 \rightarrow F_X(x) = P(X \leq x) = 0$ (Ya que no es posible tener un numero negativo)
> - Si $x = 0 \rightarrow F_X(0) = P(X \leq 0) = p_X(0) = 0.3943$
> - Si $0 < x < 1 \rightarrow F_X(x) = P(X \leq x) = p_X(0) = 0.3943$
> - Si $x = 1 \rightarrow F_X(1) = P(X \leq 1) = p_X(0) + p_X(1) = 0.3943 + 0.4302 = 0.8245$
> - Si $1 < x < 2 \rightarrow F_X(x) = P(X \leq x) = p_X(0) + p_X(1) = 0.3943 + 0.4302 = 0.8245$
> - Si $x = 2 \rightarrow F_X(2) = P(X \leq 2) = p_X(0) + p_X(1) + p_X(2) = 0.3943 + 0.4302 + 0.1563 = 0.9808$
> - Si $2 < x < 3 \rightarrow F_X(x) = P(X \leq 2) = p_X(0) + p_X(1) + p_X(2) = 0.3943 + 0.4302 + 0.1563 = 0.9808$
> - Si $x = 3 \rightarrow F_X(3) = P(X \leq 3) = p_X(0) + p_X(1) + p_X(2) + p_X(3) = 0.3943 + 0.4302 + 0.1563 + 0.0189 \approx 1$
>
> [Gráfico](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

(d) Estimar mediante una simulación las probabilidades calculadas en el item a).

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

### 2) Función de distribución

Sea $X$ una variable aleatoria con función de distribución:

![](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica2/imgs/ej2Funcion.png)

(a) Hallar la función de probabilidad puntual de $X$.

> - $p_X(1) = P(X = 1) = F_X(1) - F_X(1^-) = 0.3 - 0 = 0.3$
> - $p_X(3) = P(X = 3) = F_X(3) - F_X(3^-) = 0.4 - 0.3 = 0.1$
> - $p_X(6) = P(X = 6) = F_X(6) - F_X(6^-) = 0.6 - 0.4 = 0.2$
> - $p_X(12) = P(X = 12) = F_X(12) - F_X(12^-) = 1 - 0.6 = 0.4$
>
> Definimos $P_X$ como la función puntual:
>
> ![](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica2/imgs/ej2FuncionPuntual.png)

(b) Calcular de dos maneras: utilizando la función de distribución y utilizando la función de probabilidad puntual, las siguientes probabilidades:

- $P (3 < X \leq 6)$
- $P (3 \leq X \leq 6)$
- $P (X \geq 4)$
- $P (X \geq 6)$

> Usando la función de distribución:
>
> - $P(3 < X \leq 6) = F_X(6) - F_X(3) = 0.6 - 0.4 = 0.2$
> - $P(3 \leq X \leq 6) = F_X(6) - F_X(3^-) = 0.6 - 0.3 = 0.3$
> - $P(X \geq 4) = 1 - P (4 < X) = 1 - F_X(4^-) = 1 - 0.4 = 0.6$
> - $P(X \geq 6) = 1 - P(6 < X) = 1 - F_X(6^-) = 1 - 0.4 $
>
> Usando la función puntual:
>
> - $P(3 < X \leq 6) = P_X(6) = 0.2$
> - $P(3 \leq X \leq 6) = P_X(3) + P_X(6) = 0.1 + 0.2 = 0.3$
> - $P(X \geq 4) = P_X(6) + P_X(12) = 0.2 + 0.4$
> - $P(X \geq 6) = P_X(6) + P_X(12) = 0.2 + 0.4$

(c) Utilizando el comando sample, generar 5 realizaciones de esta variable aleatoria en R

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

(d) Mediante una simulación, estimar las probabilidades del item b).

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

### 3) Función distribución acumulda en código

Definir una función en R que, dados dos vectores $x = (x_1 , . . . , x_n )$ y $p = (p_1 , . . . , p_n )$ y un número real $t$, calcule $F_X (t)$, es decir, la probabilidad de que de la variable aleatoria discreta que toma valores $x_1 , . . . , x_n$ con probabilidades $p_1 , . . . , p_n$ respectivamente, sea menor o igual que $t$. Probarla con la variable aleatoria del ejercicio 2.

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

### 4) Demostración cálculo de probabilidad puntual con la función acumulada

Si $X$ es una v.a. discreta que toma sólo valores enteros, probar que para todo $k \in Z$:

$$p_X(k) = F_X(k) - F_X(k-1)$$

> De la definición de la probabilidad puntual tenemos que $p_X(k) = F_X(k) - F_X(k^-) = F_X(k) - F_X(lim_{h \rightarrow 0} k-h)$ como  $X$ solo toma valores en enteros, y como los enteros son un conjunto infinito numerable, entonces $F_X(lim_{h \rightarrow 0} k-h) = F_X(k-1)$ y por lo tanto llegamos a $p_X(k) = F_X(k) - F_X(k-1)$ como queriamos probar $\square$

### 5) Esperanza

Calcular la esperanza de la variable aleatoria definida en el ejercicio 1 utilizando la definición y estimarla usando una simulación. Comparar los resultados.

> $E(X) = \sum_{x \in R_X} x * p_X(x) = 0 * 0.3943 + 1 *  0.4302 + 2 * 0.1563 + 3 *  0.0189 \approx 0.7995$
>
> Simulación en el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

### 6) Función que calcula esperanza

Definir una función en R que, dados dos vectores $x = (x_1 , . . . , x_n )$ y $p = (p_1 , . . . , p_n )$ calcule la esperanza de la variable aleatoria discreta que toma valores $x_1 , . . . , x_n$ con probabilidades $p_1 , . . . , p_n$ respectivamente. Probar que funciona para la variable aleatoria $X$ del ejercicio 1.

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

### 7) Función que calcula la varianza

Definir una función en R que, dados dos vectores $x = (x_1 , . . . , x_n )$ y $p = (p_1 , . . . , p_n )$ calcule la varianza de la variable aleatoria discreta que toma valores $x_1 , . . . , x_n$ con probabilidades $p_1 , . . . , p_n$ respectivamente. Probar que funciona para la variable aleatoria $X$ del ejercicio 1.

> En el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)
>
> Teniendo en cuenta que la $Var(X) = E(X^2) - (E(X)^2)$, lo calculamos para los valores de 
> $x = [0, 1, 2, 3]$ con la probabilidades asociadas de $p = [0.3943, 0.4302, 0.1563, 0.0192]$ 
>
> $$Var(X) = [0^2 * 0.3943 + 1^2 * 0.4302 + 2² * 0.1563 + 3² * 0.0192] - 0.8004^2 = 0.5875$$ 

## Distribuciones

### 8) Distribución de Bernoulli

Sea $X$ una v.a. con distribución Bernoulli de parámetro $p$.

(a) Calcular $E(X^k)$ para $k \in N$

> Que sea una v.a. con distribución Bernoulli quiere decir que toma solo dos valores (éxito y fracaso) con $p$ la probabilidad de éxito y $1-p$ la probabilidad de fracaso.
>
> $$E(X^k) = \sum_{x \in R_X} x^k * p_X(x) = 0^k * (1-p) + 1^k * p = p$$
 
(b) Mostrar que $V(X) = p(1 − p)$.

> Por definición: 
>
>$$V(X) = \sum_{x \in R_X} (x - E(X))² * p_X(x) =$$ 
>
>$$= (0 - p)² * (1-p) + (1-p)² * p =$$
>
>$$= p² * (1-p) + (1-p)² * p =$$
>
>$$= p * (1-p) * [p+1-p] = p * (1-p) \square$$ 
>
> Por fórmula: 
>
>$$Var(X) = E(X²) - E(X)^2 = p - p² = p * (1 - p)$$

### 9) Sistema de consulta

El 70% de las consultas de un sistema interactivo de computación requiere de acceso a bases de datos. Un sistema recibe 25 consultas independientes unas de otras,

(a) ¿cuál es la probabilidad de que:

1. exactamente 20 consultas requieran acceso a una base de datos?

    > Sabemos que el experimento $X$: "requiere de acceso a bases de datos" es binomial (require o no requiere). Notación: $X \sim Bi(25, 0.7)$ y para calcular la probabilidad puntual de 20 es: 
    >
    >$$P(X = 20) = p_X(20) = \binom{25}{20} * 0.7 ^{20} * (1-0.7)^5 = 0.1030$$
    >
    >$$P(X = 21) = p_X(21) = \binom{25}{21} * 0.7 ^{21} * (1-0.7)^4 = 0.0572$$
    >
    >$$P(X = 22) = p_X(22) = \binom{25}{22} * 0.7 ^{22} * (1-0.7)^3 = 0.0242$$
    >
    >$$P(X = 23) = p_X(23) = \binom{25}{23} * 0.7 ^{23} * (1-0.7)^2 = 0.0073$$
    >
    >$$P(X = 24) = p_X(24) = \binom{25}{24} * 0.7 ^{24} * (1-0.7) = 0.0014$$

2. el número de consultas que requieran acceso a una base de datos esté entre 20 y 24 inclusive? 

    >$$P(20 \leq X \leq 24) = \sum_{k=20}^{24} \binom{25}{k} * 0.7^{k} * 0.3^{25-k} =$$
    >
    >$$= 0.1030 + 0.0572 + 0.0242 + 0.0073 + 0.0014 = 0.1931$$

(b) Calcular el valor esperado y la varianza del número de consultas que requieren acceso a una base de datos.

> $E(X) = n * p = 25 * 0.7 = 17.5$
>
> $V(X) = n * p * (1-p) = 25 * 0.7 * 0.3 = 5.25$

### 10) Dos dados, uno desequilibrado

Se tienen dos dados, uno equilibrado y el otro cargado en el cual los números 1 y 2 tienen probabilidad 1/3 y el resto 1/12. Se elige un dado al azar y se lo arroja tres veces (independientemente). Sea X el número de veces que sale 1 ó 2.

(a) ¿Cuál es la distribución de X condicional a que se eligió el dado cargado?

> La distribución a que se eligió el dado cargados es un $X \sim Bi(3, \frac{2}{3})$ ya que se lanza 3 veces y la probabilidad en que salga 1 o 2 es la suma de $\frac{1}{3} + \frac{1}{3}$

(b) Hallar una expresión general para $p_X(k)$.

> Elegimos un dado al azar, así que hay $\frac{1}{2}$ de probabilidad de elegir cada uno, y son casos disjuntos.
>
> Sea $D_c$: "salga 1 o 2 con el dado cargado" tenemos una probabilidad de $\frac{2}{3}$
>
> Sea $D_n$: "salga 1 o 2 con el dado no cargado" tenemos una probabilidad de $\frac{1}{3}$
>
> Usando el teorema de la probabilida total:
>
> $$p_X(k) = P(X=k|D_c) * P(D_c) + P(X=k|D_n) * P(D_n)$$
>
> $$p_X(k) = [\binom{3}{k} (\frac{2}{3})^k (\frac{1}{3})^{3-k} * \frac{1}{2}] + [\binom{3}{k} (\frac{1}{3})^k (\frac{2}{3})^{3-k} * \frac{1}{2}] =$$
>
> $$= \binom{3}{k} * \frac{1}{2} * [(\frac{2}{3})^k (\frac{1}{3})^{3-k} + (\frac{1}{3})^k (\frac{2}{3})^{3-k}] $$

### 11) Residuos en Río Reconquista

Para verificar si se cumplen las normas establecidas para arrojar residuos al rı́o Reconquista, un inspector visita al azar 10 de las 50 industrias establecidas a orillas de dicho rı́o.

(a) Si en realidad 35 industrias no cumplen con alguna de las normas, ¿cuál es la distribución del número de industrias visitadas que están en infracción? Calcular la probabilidad de que 6 de las industrias visitadas estén en infracción.

> Tenemos $N$ = 50 fábricas, de los cuales $D$ = 35 cumplen alguna de las normas, y se visita al azar $n$ = 10. Entonces sea $X$ tiene distribución hipergeometrica $X \sim H(10, 50, 35)$
>
> $$p_X(x) = \frac{\binom{D}{x}\binom{N-D}{n-x}}{\binom{N}{n}}$$
>
> $$p_X(6) = \frac{\binom{35}{6}\binom{50-35}{10-6}}{\binom{50}{10}} = \frac{\binom{35}{6}\binom{15}{4}}{\binom{50}{10}} = 0.2156$$

(b) Si hay 500 industrias de las cuales 350 están en infracción, aproximar la distribución de **(a)** por una más simple. Calcular nuevamente la probabilidad de que 6 de las industrias visitadas estén en infracción.

> Puedo aproximar sabiendo que de 500 industrias 350 andan en infracción y elijo al azar 10, sea $Y$ la distribución aproximada de $X$, defino $X \sim Y \sim Bi(10, 0.7)$ ya que $p = \frac{350}{500} = 0.7$ y $n = 10$.
>
> $$p_Y(y) = \binom{n}{y} * p^y * (1-y)^{n-y}$$
>
> $$p_Y(6) = \binom{10}{6} * 0.7^6 * (1-0.7)^{10-6} = 0.2001$$

(c) Sea $X$ el número de fábricas que están en infracción entre las 10 visitadas. Calcular $E(X)$ y $V(X)$ para las distribuciones exacta **(a)** y aproximada **(b)**.

> En en punto **(a)** con $X \sim H(10, 50, 35)$
>
>  $$E(X) = n \frac{D}{N} \Rightarrow E(X) = 10 * \frac{35}{50} = 7$$
>
>  $$V(X) = (\frac{N-n}{N-1})n \frac{D}{N}(1-\frac{D}{N}) \Rightarrow V(X) = (\frac{50-10}{50-1}) * 7 * (1-\frac{35}{50}) = 1.7142$$

> En en punto **(b)** con $Y \sim Bi(10, 0.7)$
>
> $$E(Y) = np \Rightarrow E(Y) = 10 * 0.7 = 7$$
>
> $$V(Y) = np(1-p) \Rightarrow V(Y) = 10 * 0.7 * 0.3 = 2.1$$

### 12) Ruleta
Una rueda de ruleta está dividida en 38 secciones, de las cuales 18 son rojas, 18 son negras y las 2 restantes son verdes. Sea $X$ el número necesario de juegos hasta obtener una sección verde en jugadas independientes.

(a) ¿Cuál es la probabilidad de que sean necesarias al menos 4 jugadas?

> Se repite hasta que sea verde, entonces es una distribución geométrica $X \sim G(p)$ con $p = \frac{2}{38} = 0.0526$
>
> $P(x \geq 4) = 1 - F_X(4^-) = 1 - F_X(3) = 1 - [1 - (1-0.0526)^3] = 0.8503$

(b) Hallar la función de distribución acumulada de la v.a. $X$.

> ![](https://github.com/malei-dc/PyE/blob/main/Guia-Ejercicios/Practica2/imgs/ej12eAcumulada.png)

(c) Si fueron necesarias 7 o más jugadas, ¿cuál es la probabilidad de que se necesiten al menos 10 jugadas? Comparar con **(a)**.

> La distribución geométrica tiene la propiedad de falta de memoria ([Explicación](https://github.com/malei-dc/PyE/blob/main/Apuntes/OlvidoGeometrica.pdf))
>
> Teniendo en cuenta esta propiedad y la función distribución acumulada de la geométrica, calculamos: 
>
> $$P(X \geq 10 | X \geq 7) = P(X > 9 | X > 6) = P(X > 3) = P(X \geq 4) = 1 - P(X \leq 3) = 1 - F_X(3) = 0.8503$$
>
> Ya calculado en el punto **(a)**

(d) ¿Cuál es la probabilidad de que sea necesario un número impar de jugadas?

> Sea $I = \{ n \in N | impar \} \subset X$
>
> Sabemos entonces que $P(I) = p_X(1) + p_X(2) + \dots + p_X(2k+1)$, calculamos
>
> $$P(I) = \sum_{i = 0}^{\infty} p * (1-p)^{2i} = \sum_{i = 0}^{\infty} 0.0526 * (1-0.0526)^{2i} = 0.0526 * \sum_{i = 0}^{\infty} (0.8975)^{i} =$$
>
> Como $\sum_{i = 0}^{\infty} (0.8975)^{i}$ es una serie geométrica: $\sum_{i = 0}^{\infty} r^{i}$ para $|r| < 1$ se puede aplicar la fórmula de $\sum_{i = 0}^{\infty} r^{i} = \frac{1}{1-r}$, lo cual queda:
>
> $$= 0.0526 * \sum_{i = 0}^{\infty} (0.8975)^{i} = 0.0526 * \frac{1}{1-0.8975} \approx 0.5131$$

(e) Hallar $E(X)$ y $V(X)$ .

> $$E(X) = \frac{1}{p} = \frac{1}{0.0526} = 19$$
>
> $$V(X) = \frac{1-p}{p²} = \frac{1-0.0526}{0.0526²} = 342$$

### 13) Ruleta parte 2

Si en el ejercicio anterior se define $Y$: "número de juegos hasta obtener exactamente tres secciones verdes",

(a) ¿qué distribución tiene la v.a. $Y$ ?

> En este caso $Y \sim BN(r, p)$ donde $r$ indica obtener hasta la r-sima sección verde (en este caso 3) y $p$ la probabilidad (en este caso $\frac{2}{38}$). 

(b) ¿cuál es la probabilidad de que se requieran exactamente 5 jugadas?

> Teniendo que $Y \sim BN(3, \frac{2}{38})$ queremos calcular la probabilidad puntual en el valor 5 dada la fórmula:
>
> $$P(X = k) = \binom{k-1}{r-1} p^r (1-p)^{k-r}$$
>
> Reemplazando obtenemos:
>
> $$P(X = 5) = \binom{5-1}{3-1} (\frac{2}{38})^3 (1-\frac{2}{38})^{5-3} = \binom{4}{2} * 0.0526^3 * 0.9473² = 0.0007851$$

(c) hallar $E(Y)$ y $V(Y)$ .

> $$E(Y) = \frac{r}{p} = \frac{3}{\frac{2}{38}}=57$$
>
> $$V(Y) = \frac{r(1-p)}{p²} = \frac{3 * (1-\frac{2}{38})}{(\frac{2}{38})²} = 1026$$

### 14) Motor de búsqueda

Con el fin de encontrar una palabra clave, un motor de búsqueda de internet explora una secuencia de sitios de la WEB en orden aleatorio. Al iniciar la búsqueda, el motor elige, al azar y con igual probabilidad, una entre dos secuencias posibles de sitios. Se sabe que el 10% de los sitios de la primera secuencia contienen esta palabra clave, mientras que sólo el 5% de los sitios de la segunda contienen dicha palabra.

(a) Si la búsqueda termina ni bien se encuentra un sitio que contenga la palabra clave, ¿cuál es la probabilidad de que más de 5 sitios deban ser explorados?

> Tenemos dos secuencias que se eligen al azar con igual probabilidad. $S_1, S_2$ con $P(S_i) = 0.5$. 
>
> Sea $X$: "encuentra un sitio que contenga la palabra clave"
>
> Tenemos que $X \sim G(p)$ en donde $p$ depende de la secuencia que andamos buscando.
>
> - $X|S_1 \sim G(0.1)$
> - $X|S_2 \sim G(0.05)$
>
> Queremos encontrar $P(X > 5)$, usando el teorema de la probabilidad total tenemos:
>
> $$ P(X > 5) = P(S_1) * P(X > 5 | S_1) + P(S_2) * P(X > 5 | S_2) =$$
>
> Para $P(X > k) = 1 - F_X(k)$ es decir le resto el valor acumulado hasta $k$
> 
> $$= 0.5 * [1-(1-(1-0.1)⁵)] + 0.5 * [1-(1-(1-0.05)⁵)] = 0.295245 + 0.3868 = 0.6821$$

(b) Si se sabe que el motor de búsqueda encontró la palabra clave en la sexta visita ¿cuál es la probabilidad de que la haya encontrado en la segunda secuencia?

> $$P(S_2|X=6) = \frac{S_2 \cap (X=6)}{P(X=6)} = \frac{P(X = 6 | S_2) * P(S_2)}{P(S_1) * P(X = 6 | S_1) + P(S_2) * P(X = 6 | S_2)} =$$
>
> $$=\frac{p_{X_2}(6) * P(S_2)}{P(S_1) * p_{X_1}(6) + P(S_2) * p_{X_2}(6)} = \frac{[(1-0.05)^{6-1} * 0.05] * 0.5}{0.5 * [(1-0.1)^{6-1} * 0.1] + 0.5 * [(1-0.05)^{6-1} * 0.05]} = \frac{0.0193445}{0.0295245+0.0193445} = 0.3958$$ 

(c) Si la búsqueda termina cuando se encuentran 2 sitios que contenga la palabra clave ¿cuál es la probabilidad de que deban explorarse exactamente 10 sitios?

> En este caso es una distribucion de binomial negativa $X \sim BN(r, p)$ donde $r = 2$ y $p$ depende de la secuencia que se esté buscando.
>
> - $X_1 \sim BN(2, 0.1)$
> - $X_2 \sim BN(2, 0.05)$
>
> Usando el teorema de la probabilidad total y la función de probabilidad puntual de lla binomial negativa:
>
> $$P(X = k) = P(X_1 = k) * P(S_1) + P(X_2 = k) * P(S_2) = p_{X_1} (k) * P(S_1) + p_{X_2}(k) * P(S_2)$$
>
> Reemplazando nos queda:
>
> $$P(X = 10) = p_{X_1}(10) * P(S_1) + p_{X_2}(10) * P(S_2) =$$
>
> $$= [\binom{10-1}{2-1} 0.1² * (1-0.1)^8] * 0.5 + [\binom{10-1}{2-1} 0.05² * (1-0.05)^8] * 0.5 = 0.0268$$

### 15) Minorista

Un minorista ha verificado que la demanda semanal de cajones de cierto producto es una v.a. con distribución de Poisson de parámetro $\lambda = 2$. Completa su existencia los lunes por la mañana de manera de tener 4 cajones al principio de la semana. Al efectuar un análisis de la actividad de su negocio, se le plantean las siguientes preguntas:

(a) ¿Cuál es la probabilidad de vender todo su stock durante la semana?

> $$P(X = k)= \frac{e^{-\lambda}\lambda^k}{k!} \Rightarrow P(X = 4)= \frac{e^{-2}2^4}{4!} = 0.0902$$

(b) ¿Cuál es la probabilidad de que sea incapaz de cumplir con un pedido por lo menos?

> $$P(X \geq 5) = 1 - P(X < 5) = 1 - [P(X=0)+P(X=1)+P(X=2)+P(X=3)+P(X=4)]=$$
>
> $$= 1-[e^{-2} * (\frac{2^0}{0!}+\frac{2^1}{1!}+\frac{2^2}{2!}+\frac{2^3}{3!}+\frac{2^4}{4!})] = 1-[e^{-2} * 7] = 0.0526$$

(c) ¿Cuál es la distribución del número de cajones vendidos en una semana?

>El número de cajones vendidos en una semana sigue una distribución de Poisson. Esto es porque, según la descripción del problema, la demanda semanal de cajones de cierto producto se modela como una variable aleatoria con distribución de Poisson de parámetro $\lambda = 2$. La distribución es $X \sim P(2)$

(d) ¿Con cuántos cajones deberı́a iniciar la semana a fin de que la probabilidad de cumplir con todos sus pedidos fuese mayor o igual que 0.99?

> Sabemos por el item anterior que $P(X \leq 4) \approx 0.9474$
>
> Calculamos: 
>
> $$P(X=5) = \frac{e^{-2}2^5}{5!} = 0.0360$$
>
> $$P(X=6) = \frac{e^{-2}2^6}{6!} = 0.0120$$
>
> $$P(X \leq 6) = P(X \leq 4) + P(X=5) + P(X=6) = 0.9474 + 0.0360 + 0.0120 = 0.9954 > 0.99$$
>
> Para que la probabilidada de cumplir con todos sus pedidos sea mayor o igual que 0.99 tiene que iniciar la semana con 6 cajones

### 16) Bibliotecario

Un bibliotecario ubica 1000 libros en un cierto dı́a. Si la probabilidad de que un libro cualquiera sea mal ubicado es 0.001 y los libros se ubican en forma independiente, ¿cuál es la distribución aproximada del número de libros mal ubicados en ese dı́a? 

> La distribución es de $X \sim Bi(1000,0.001)$. Pero se puede aproximar con una distribución Poisson con parametro $\lambda = n * p = 1 \Rightarrow Y \sim P(1)$

> La distribución binomial $X \sim Bi(n,p)$ puede aproximarse por una distribución de Poisson con parámetro $\lambda = n⋅p$ cuando se cumplen las siguientes condiciones:
>
> 1. $n$ es grande: El número de ensayos $n$ debe ser grande (en este caso, $n=1000$).
> 2. $p$ es pequeño: La probabilidad de éxito $p$ debe ser pequeña (en este caso, $p=0.001$).
> 3. $np$ es de tamaño moderado: El producto $n⋅p=λ$ debe ser de tamaño moderado (en este caso, $np=1000×0.001=1$).

Utilizando esta distribución, calcular la probabilidad de que

(a) por lo menos un libro sea mal ubicado ese dı́a.

> $$P(Y \geq 1) = 1 - P(X=0) = 1 - \frac{e^{-1}1^0}{0!} = 1 - \frac{1}{e} = 0.6321$$

(b) exactamente 3 libros sean mal ubicados ese dı́a. Comparar con el valor exacto.

> $$P(Y = 3) = \frac{e^{-1}1^3}{3!} = 0.0613$$
>
> Donde el valor exactos es:
>
> $$P(X = 3) = \binom{1000}{3} 0.001³(1-0.001)^{997} = 0.0.612$$