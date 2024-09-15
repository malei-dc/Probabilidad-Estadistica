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

## Distribución Geométrica

Cuenta la cantidad de experimentos hasta obtener el primer éxito.

### Ejercicio 1

Un juego consiste en lanzar un dado justo o equilibrado. Se gana 100 dólares si sale seis, pero se tiene que pagar 10 dólares cada vez que se lanza el dado. Si llegamos al juego con 30 dólares, ¿cuál es la probabilidad de perder todo el dinero antes de ganar?

> Sea $X$: "sacar 6 en un dado equilibrado", queremos calcular la probabilidad de que salga a partir de la cuarta tirada, ya que queremos ver la probabilidad de perder todo el dinero. $X \sim G(\frac{1}{6})$
>
> Usando la función distribución puntuales:
>
> $$P(X > 3) = 1 - (p_X(1) + p_X(2) + p_X(3)) = 1 - (\frac{1}{6} + \frac{5}{6}\frac{1}{6}+ (\frac{5}{6})²\frac{1}{6}) = 0.5787$$
>
> Razonamiento: si tiro mas de tres veces el dado, pierdo los 30 dolares porque cuesta 10 la tirada.

### Ejercicio 2

El costo de efectuar un experimento es de $1000. Si el experimento falla, se incurre en un costo adicional de $300 debido a cambios que deben efectuarse antes de que se intente de nuevo. Si la probabilidad de éxito en cualquiera de los ensayos es de 0.2, los ensayos son independientes y los experimentos continuan hasta obtener el primer éxito, ¿cuál es el costo esperado del procedimiento completo?

> Sea $X$: "el experimento", sabemos que $X \sim G(0.2)$, necesitamos aproximar el $x$ para calcular el costo esperado. Para esto usamos el concepto de la esperanza que representa el número promedio de ensayos necesarios para obtener el primer éxito.
>
> $$E(X) = \frac{1}{p} = \frac{1}{0.2} = 5$$
>
> Entonces si hacermos $4 * 1300 + 1000 = 6200$ donde es el costo esperado del experimento ya que el último experimento se espera un éxito.

## Distribución Binomial Negativa

Cuenta la cantidad de experimentos hasta obtener el k-ésimo éxito.

### Ejercicio 1 

Lucas y Miguel disputan la final de un campeonato de ajedrez. El primero que gane 6 partidas (no hay tablas) resulta ganador. La probabilidad de que Lucas ganar cada partida es 3/4. ¿Cuál es la probabilidad de que Lucas gane el campeonato en la novena partida?

> Definimos $X$: "numero de partidas hasta que Lucas gane 6 partidas". Es $X \sim BN(6, 0.75)$, por lo tanto, para calcular la probabilidad de que Lucas gane en la novena partida es:
>
> $$P(X = 9) = \binom{9-1}{6-1} 0.75^6 (1-0.75)^{9-6} = 0.1557$$

## Distribución Hipergeométrica

- $N =$ población.
- $D =$ cantidad de éxitos en la población
- Cada individuo o elemento puede ser clasificado como éxito o fracaso.

Se extrae una muestra de tamaño $n$: $X$ = número de éxitos en la muestra de tamaño $n$.

### Ejercicio 1

Lotes con 40 componentes cada uno que contengan 3 ó mas componentes defectuosos se consideran inaceptables. El procedimiento para detectar si un lote es inaceptable o no, es seleccionar 5 componentes al azar y rechazar el lote si se encuentra un componente defectuoso. ¿Cuál es la probabilidad de que en la muestra se encuentre un componente defectuoso, si en todo el lote hay 3 efectuosos?.

> Sea $X$: "número de comoponente defectuoso en 5 seleccionados", es una distribución $X \sim H(5, 40, 3)$. Para descartar el lote entero alcanza a encontra 1 defectuoso en los 5 que selecciono. Entonces usando la probabilidad puntual calculo:
>
> $$P(X = 1) = \frac{\binom{3}{1} \binom{40-3}{5-1}}{\binom{40}{5}} = \frac{198135}{658008} = 0.3011$$
>
> Hay una probabilidad de 30.11% de que se encuentre un componente defectuoso.

## Distribución Poisson

Si se cumple las condiciones, entonces el número de ocurrencias del evento en un perı́odo de longitud $t$ tiene distribución de Poisson de parámetro $\lambda = \sigma t$.

### Ejercicio 1

Una máquina que envasa comprimidos en un laboratorio farmacéutico tiene en promedio 1,5 fallas por dı́a. Hallar la probabilidad de que en una semana de trabajo tenga menos de 6 fallas.

> La variable aleatoria $X$, que representa el número de fallas en una semana, sigue una distribución de Poisson con parámetro $\lambda$, que es la tasa esperada de fallas en una semana. Para calcular $\lambda$
>
> - La tasa esperada $\lambda$ en una semana de trabajo (7 días) es: 
>    - $\lambda = 1.5 Fallas * 7 Dia = 10.5$ fallas por samama
>
> Aplicando la fórmula de probabilidad de Poisson es: $P(X=k) = \frac{\lambda ^k e^{-\lambda}}{k!}$ Donde $X \sim P(10.5)$ y $k$ es el número de fallas que estamos considerando. Queremos calcular:
>
> $$P(X < 6) = P(X = 0) + P(X = 1) + P(X = 2) + P(X = 3) + P(X = 4) + P(X = 5) =$$
>
> $$= \frac{10.5 ^0 e^{-10.5}}{0!} + \frac{10.5 ^1 e^{-10.5}}{1!} + \frac{10.5 ^2 e^{-10.5}}{2!} + \frac{10.5 ^3 e^{-10.5}}{3!} + \frac{10.5 ^4 e^{-10.5}}{4!} + \frac{10.5 ^5 e^{-10.5}}{5!} = $$
>
> $$= e^{-10.5} * (\frac{10.5^0}{0!} + \frac{10.5¹}{1!} + \frac{10.5²}{2!} + \frac{10.5³}{3!} + \frac{10.5⁴}{4!} + \frac{10.5⁵}{5!})$$
>
> $$= e^{-10.5} * (1 + 10.5 + 55.125 + 192.9375 + 506.4609 + 1063.5679) = e^{-10.5} * 1829.5914 = 0.0503$$

### Ejercicio 2

En un estudio ecológico realizado en un lago, se encontró que habı́a, en promedio, 2 microorganismos por cm3. Si se toman muestras de 3 cm3, hallar la probabilidad de encontrar 9 o más microorganismos.

> Es una distribución $X \sim P(6)$ ya que en 3 cm3 en promedio deberia ser 6 microorganismos.
>
> Calculo usando la fórmula $P(X=k) = \frac{\lambda ^k e^{-\lambda}}{k!}$:
>
> $$P(X \geq 9) = 1 - P(X < 9) = 1 - [P(X = 0) + P(X = 1)+ P(X = 2)+ P(X = 3)+P(X = 4)+P(X = 5)+P(X = 6)+P(X = 7)+P(X = 8)] =$$
>
> $$= 1 - [e^{-6} * (\frac{6^0}{0!}+\frac{6^1}{1!}+\frac{6^2}{2!}+\frac{6^3}{3!}+\frac{6^4}{4!}+\frac{6^5}{5!}+\frac{6^6}{6!}+\frac{6^7}{7!}+\frac{6^8}{8!})] = 1 - [e^{-6} * 341.8] = 1-0.8472=0.1527$$
