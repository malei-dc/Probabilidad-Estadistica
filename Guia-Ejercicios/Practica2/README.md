# Práctica 2

## Variables aleatorias discretas

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

![](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/imgs/ej2Funcion.png)

(a) Hallar la función de probabilidad puntual de $X$.

> - $p_X(1) = P(X = 1) = F_X(1) - F_X(1^-) = 0.3 - 0 = 0.3$
> - $p_X(3) = P(X = 3) = F_X(3) - F_X(3^-) = 0.4 - 0.3 = 0.1$
> - $p_X(6) = P(X = 6) = F_X(6) - F_X(6^-) = 0.6 - 0.4 = 0.2$
> - $p_X(12) = P(X = 12) = F_X(12) - F_X(12^-) = 1 - 0.6 = 0.4$
>
> Definimos $P_X$ como la función puntual:
>
> ![Función puntual](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/imgs/ej2FuncionPuntual.png)

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

> Simulación en el archivo [Practica2.ipynb](https://github.com/malei-dc/PyE/tree/main/Guia-Ejercicios/Practica2/Practica2.ipynb)

