# Práctica 3

## Variables aleatorias continuas

### 1) Función densidad

Sea X una v.a. con función de densidad:

![](/Guia-Ejercicios/Practica3/imgs/ej1Densidad.png)

(a) Verificar que $f_X$ es realmente una función de densidad.

> Para ver que una $f_X$ es realmente una función densidad tiene que cumplir dos cosas:
>
> - $f(x) \geq 0,  \forall x \in R$
>   > $f: R \rightarrow [-1, 1]$ si $x \in [-1, 1]$, entonces $0.75 (1-x²) \geq 0$, luego $f(x) \geq 0, \forall x \in R$
> - $\int_{-\infty}^{\infty} f(x)dx = 1$
>
> $$\int_{-\infty}^{\infty} 0.75(1-x²) = 0.75 \int_{-1}^{1} (1-x²)dx = 0.75 * (x - \frac{x³}{3}) \bigg|_{-1}^{+1} = 0.75 * (\frac{2}{3} - (-\frac{2}{3})) = 1$$
>
> Luego concluimos que es una función de densidad 

(b) Calcular:

- $P(X > 0)$
    > $\int_{0}^{1} 0.75 (1-x²) dx = 0.75 * (x - \frac{x³}{3})\bigg|¹_0 = 0.75 * 0.66 = 0.5$
- $P(−0,5 < X < 0,5)$
    > $\int_{-0.5}^{0.5} 0.75 (1-x²) dx = 0.75 * (x - \frac{x³}{3})\bigg|^{0.5}_{-0.5} = 0.75 * (\frac{11}{24} - (-\frac{11}{24}))= \frac{11}{16}$
- $P(|X| > 0,25)$
    >$P(|X| > 0,25) = 1 - P(|X| \leq 0,25) = 1 - \int_{-0.25}^{0.25} 0.75 (1-x²) dx = 1 - 0.75 * (x - \frac{x³}{3})\bigg|^{0.25}_{-0.25} = 1 - 0.75 * (\frac{47}{192} - (-\frac{47}{192})) = \frac{81}{128}$

(c) Hallar $F_X$, la función de distribución acumulada de $X$.

> - Para $x \in (-\infty, -1], F_X(x)=0$ 
> - Para $x \in [-1, 1]$ integramos $f_X(t) = 0.75 (1-t²):$
>
>   $$F_X(x) = \int_{-1}^{x} 0.75 (1-t²) dt = 0.75 * (t - \frac{t³}{3})\bigg|^{x}_{-1} = 0.75 * (x-\frac{x³}{3} - (-\frac{2}{3})) = 0.75 * (x-\frac{x³}{3} +\frac{2}{3})$$
>
> - Para $x \in [1, \infty), F_X(x) = 1$

(d) Graficar $f_X$ y $F_X$.

![](/Guia-Ejercicios/Practica3/imgs/ej1d.png)

### 2) Función distribución

Sea $X$ una v.a. continua con función de distribución

![](/Guia-Ejercicios/Practica3/imgs/ej2Distribucion.png)

(a) ¿Cuál es el valor de $\sigma$?

(b) Calcular, usando $F_X(x)$,

- $P(X \leq 1)$
- $P (0,5 \leq X \leq 1)$
- $P (0,5 < X \leq 1|X < 1)$

(c) Hallar la mediana $\tilde{\mu}$ de esta distribución.

(d) Encontrar la función de densidad $f_X(x)$.

(e) Graficar $f_X$ y $F_X$ . Agregar la recta vertical $x = \tilde{\mu}$.