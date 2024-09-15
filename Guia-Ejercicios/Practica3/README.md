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
> $$\int_{-\infty}^{\infty} 0.75(1-x²) = 0.75 \int_{-1}^{1} (1-x²)dx = 0.75 * (x - \frac{x³}{3}) |_{-1}^{+1} = 0.75 * (\frac{2}{3} - (-\frac{2}{3})) = 1$$
>
> Luego concluimos que es una función de densidad 

(b) Calcular:

- $P(X > 0)$
- $P(−0,5 < X < 0,5)$
- $P(|X| > 0,25)$

(c) Hallar $F_X$, la función de distribución acumulada de $X$.

(d) Graficar $f_X$ y $F_X$.