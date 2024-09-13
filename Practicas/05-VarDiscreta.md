# Clase 30-08-24

## Ensayos Bernoulli

### Preguntas: 

1. ¿Cuál es la cantidad de éxitos en los primeros $n$ ensayos?

    > La cantidad de éxitos en los primeros nn ensayos de una serie de ensayos de Bernoulli con probabilidad de éxito $p$ sigue una distribución binomial. Si llamamos $X$ al número de éxitos, entonces:
    >
    > $$X \sim Binomial(n,p)$$
    >
    > Donde la probabilidad de obtener exactamente $k$ éxitos en $n$ ensayos está dada por:
    >
    > $$P(X=k) = \binom{n}{k}p^k(1-p)^{n-k} $$

2. En $n$ ensayos, ¿cuál es el número de éxitos más probable?

    > Para una binomial $Bi(n,p)$, el valor más probable de $k$, el número de éxitos, es aproximadamente:
    >
    > $$k^* = \lfloor (n+1) * p \rfloor$$
    >
    > Donde $\lfloor * \rfloor$ quiere decir la parte entera. Ese valor maximiza la probabilidad de $P(X=k)$
 
3. ¿Cuántos experimentos hay que realizar para observar el primer éxito?

    > El número de experimentos necesarios para observar el primer éxito sigue una distribución geométrica con parámetro $p$, la probabilidad de éxito en cada ensayo. Si llamamos $Y$ al número de experimentos hasta el primer éxito, entonces:
    >
    > $$Y \sim G(p)$$
    >
    > La probabilidad de que el primer éxito ocurra en el ensayo $k$ es:
    >
    > $$P(Y = k) = (1-p)^{k-1}p

4. ¿Cuánto experimentos hay que realizar para observar el $k$-ésimo éxito?

    > Esto es una generalización del caso anterior. El número de experimentos necesarios para observar el $k$-ésimo éxito sigue una distribución binomial negativa. Si llamamos $Z$ al número de experimentos hasta el $k$-ésimo éxito, entonces:
    >
    > $$Z \sim BN(k, p)$$
    >
    > La probabilidad de que el $k$-ésimo éxito ocurra en el ensayo $n$-ésimo es:
    >
    > $$P(Z=n) = \binom{n-1}{k-1}p^k(1-p)^{n-k}

### La distribución Binomial

Consiste en hacer $n$ repeticiones de ensayos con la probabilidad $p$ 

#### Ejercicio 1

Una cadena de tiendas compra cierto tipo de dispositivo electrónico a un fabricante, el cual le indica que la tasa de dispositivos defectuosos es de 3 %.

- El inspector de la cadena elige 20 artı́culos al azar de un cargamento. ¿Cuál es la probabilidad de que haya al menos un artı́culo defectuoso entre los 20 artı́culos del cargamento?

    > Notemos que los dispositivos pueden ser defectuosos o no defectuosos y la probabilidad de que lo sea es de 0.03.
    > Esto nos indica que es una distribución binomial. Definimos $X$: "elige un dispositivo defectuoso". Siendo $X \sim Bi(20, 0.03)$. Luego usando propiedades y la probabilidad puntual calculamos:
    >
    > $P(X \geq 1) = 1 - P(X < 1) = 1 - P(X = 0) = 1 - p_X(0) = 1 - \binom{20}{0} * 0.03^0 * (1-0.03)^{20} = 0.4562$

- Supongamos que la cadena recibe 10 cargamentos en un mes y que el inspector prueba aleatoriamente 20 dispositivos por cargamento. ¿Cuál es la probabilidad de que haya exactamente 3 cargamentos que contengan al menos un dispositivo defectuoso entre los 20 seleccionados y probados?

    > Acá vemos que hay varias partes, vayamos de a poco. En un cargamento se eligen al azar 20 dispositivos, para saber cuál es la probabilidad de que en un cargamento haya al menos uno defectuoso ya lo calculamos arriba. Ese será nuestra $p$, definimos un nuevo $Y$: "cantidad de cargamentos que tienen al menos uno defectuoso" donde $Y \sim Bi(10, 0.4562)$. Calculamos usando la probabilidad puntual de una distribución binomial.
    >
    > $P(Y = 3) = \binom{10}{3}0.4562^3 (1-0.4562)^7 = 0.1602$

#### Ejercicio 2

Un avión se mantendrá en vuelo mientras funcionen al menos 50 % de los motores. Si cada motor del avión en vuelo puede fallar con una probabilidad $1 − p$ independientemente de los demás, ¿para qué valores de $p \in (0, 1)$ es más seguro un avión de 4 motores que uno de 2?

> Definimos las variables claves:
>
> - Para un avión de 4 motores, al menos 2 motores deben funcionar.
> - Para un avión de 2 motores, al menos 1 motor debe funcionar.
>
> $p$ es la probabilidad de que un motor funcione, entonces $1 - p$ es la probabilidad de que un motor falle. Definimos $X \sim Bi(4, p)$ como la variable aleatoria de distribución binomial que representa a un avióń de 4 motores y $Y \sim Bi(2, p)$ con 2 motores.
>
> Calculamos las probabilidades:
>
> $$P(X \geq 2) = 1 - P(X < 2) = 1 - p_X(0) - p_X(1) = 1 - \binom{4}{0}p^0(1-p)^4 - \binom{4}{1}p^1(1-p)^3 =$$
>
> $$= 1 - (1-p)^4 - 4p(1-p)^3$$
>
> $$P(X \geq 1) = 1 - P(X < 1) = 1 - p_X(0) = 1 - \binom{2}{0}p^0(1-p)^2 = 1- (1-p)²$$
>
> Comparamos. Para que el avión de 4 motores sea más seguro que el de 2 tiene que pasar que $P(X \geq 4) > P(Y \geq 1)$, reemplazando tenemos:
>
> $$1 - (1-p)^4 - 4p(1-p)^3 >  1- (1-p)²$$
>
> $$(1-p)² >  (1-p)^4 + 4p(1-p)^3$$
>
> $$(1-p)² > (1-p)²[(1-p)^2 + 4p(1-p)]$$
>
> $$1 > 1 -2p + p² + 4p - 4p²$$
>
> $$1 > 1 + 2p - 3p²$$
>
> $$0 > p(2 - 3p)$$
>
> $$0>2-3p \Rightarrow p > \frac{2}{3}$$
>

> El avión de 4 motores es más seguro cuando $p > \frac{2}{3} \square$


#### Ejercicio 3

Si la probabilidad de éxito es $p = 0,01$, ¿cuántos ensayos se deben realizar para asegurar que la probabilidad de que ocurra por lo menos un éxito sea al menos $\frac{1}{2}$?

> La probabilidad de tener al menos un éxito es el complemento de no tener ningún exito: $P(alMenosUnE) = 1 - P(ningunE) = 1 - 0.99^n$
>
> Como queremos que esa probabilidad sea al menos $\frac{1}{2}$ plantemos la desigualdad:
>
> $$1 - 0.99^n \geq 0.5 \Rightarrow 0.99^n \leq 0.5$$
>
> $$ln(0.99^n) \leq ln(0.5)$$
>
> $$n * ln(0.99) \leq ln(0.5)$$
>
> Como $ln(0.99)$ es negativo, se da vuelta la desigualdad
>
> $$n \geq \frac{ln(0.5)}{ln(0.99)} \approx 68.96$$
>
> Por lo tanto, se necesita realizar al menos 69 ensayos para que la probabilidad de tener al menos un éxito sea al menos de 0.5