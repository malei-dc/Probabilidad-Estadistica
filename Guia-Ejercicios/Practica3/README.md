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

> $$Lim_{x \rightarrow 2^-} \frac{x³}{\sigma} = 1 \Rightarrow \frac{8}{\sigma} = 1 \Rightarrow \sigma = 8$$

(b) Calcular, usando $F_X(x)$,

- $P(X \leq 1) =$
    > $= F_X(1) = \frac{1}{8}$
- $P (0,5 \leq X \leq 1)=$
    > $= F_X(1) - F_X(0.5) = \frac{1}{8} - \frac{1}{64} = \frac{7}{64}$
- $P (0,5 < X \leq 1|X < 1) =$
    > $= \frac{F_X(1) - F_X(0.5)}{F_X(1)} = \frac{7}{8}$

(c) Hallar la mediana $\tilde{\mu}$ de esta distribución.

> La mediana de la distribución es el 50-percentil, es decir, tenemos que buscar $x_{0.50}$ tal que $F_X(x_{0.50}) = 0.5$.
>
> $$F_X(x_{0.5}) = 0.5 \Leftrightarrow \frac{x_{0.5}³}{8} = 0.5 \Leftrightarrow x_{0.5} = \sqrt[3]{4} = \tilde{\mu}$$

(d) Encontrar la función de densidad $f_X(x)$.

> Para encontrar $f_X(x)$ derivamos $F_X(x)$ por tramos. Dicho esto, el único caso interesante es cuando $0 \leq x < 2$ pues la derivación de numeros constantes es $0$.
>
> $$f_X(x) = (F_X(x))' = \frac{x³}{8} \frac{d}{dx} = \frac{3x²}{8}$$
>
> Por esto la función densidad es:
>
>![](/Guia-Ejercicios/Practica3/imgs/ej2dDensidad.png)

(e) Graficar $f_X$ y $F_X$ . Agregar la recta vertical $x = \tilde{\mu} $.

> Graficos en el archivo [practica3.ipynb](/Guia-Ejercicios/Practica3/practica3.ipynb)

### 3) Distribución uniforme

Sea $U$ una v.a. con distribución $U[0, \sigma]$ , para $\sigma > 0$.

(a) Hallar la función de distribución acumulada de $U$.

> - Si $x < 0$ entonces debe valer $F_U(x)=0$.
> - Si $0 \leq x \leq \sigma$ entonces vale $F_U(x) = \frac{x - 0}{\sigma -0}$.
> - Si $x > \sigma$ entonces debe valer $F_U(x)=1$.

(b) Si $P(1 \leq U \leq 3) = 0,5$, ¿qué valores puede tomar $\sigma$?

> - Caso $\sigma \geq 3$
>
> $$P(1 \leq U \leq 3) = F_U(3) - F_U(1) = \frac{3}{\sigma}-\frac{1}{\sigma} = 0.5 \Leftrightarrow \sigma = 4$$
>
> - Caso $1 \leq \sigma < 3$
>
> $$P(1 \leq U \leq 3) = F_U(3) - F_U(1) = 1 - \frac{1}{\sigma} = 0.5 \Leftrightarrow \frac{1}{\sigma} = 0.5 \Leftrightarrow \sigma = 2$$
>
> - Caso $\sigma < 1$, imposible pues:
>
> $$P(1 \leq U \leq 3) = F_U(3) - F_U(1) = 1 - 1 =0 \neq 0.5$$ 

(c) Para $\sigma$ hallados en el item **(b)** estimar la $P(U^2 < 2)$.

> $$P(U^2 < 2) = P(U < \sqrt{2}) = F_U(\sqrt{2}) = \frac{\sqrt{2}}{\sigma}$$
>
> Caso $\sigma = 4$
>
> $$P(U^2 < 2) = P(U < \sqrt{2}) = F_U(\sqrt{2}) = \frac{\sqrt{2}}{4}$$
>
> Caso $\sigma = 2$
>
> $$P(U^2 < 2) = P(U < \sqrt{2}) = F_U(\sqrt{2}) = \frac{\sqrt{2}}{2}$$

### 4) Esperanza y varianza de continuas

Consideremos una v.a. $Y$ con función de densidad

![](/Guia-Ejercicios/Practica3/imgs/ej4Densidad.png)

(a) Calcular la función de distribución de $Y$.

> 

(b) Calcular $E(Y)$ y $V(Y)$.

(c) Calcular $E(1/Y)$. ¿Qué conclusión saca respecto a la relación entre $E(1/Y)$ y $1/E(Y)$.