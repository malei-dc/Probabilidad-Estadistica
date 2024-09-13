# Clase 30-08-24

## Ensayos Bernoulli

Preguntas: 

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

- Supongamos que la cadena recibe 10 cargamentos en un mes y que el inspector prueba aleatoriamente 20 dispositivos por cargamento. ¿Cuál es la probabilidad de que haya exactamente 3 cargamentos que contengan
al menos un dispositivo defectuoso entre los 20 seleccionados y probados?