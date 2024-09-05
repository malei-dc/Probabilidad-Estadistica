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