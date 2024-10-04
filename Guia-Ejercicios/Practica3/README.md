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
    > $\int_{0}^{1} 0.75 (1-x²) dx = 0.75 * (x - \frac{x³}{3})\bigg|^{1}_{0} = 0.75 * 0.66 = 0.5$
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

> ![](/Guia-Ejercicios/Practica3/imgs/ej1d.png)

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

> - Si $0 \leq y \leq 5$
>
> $$F_Y(y) = \int_{-\infty}^y (\frac{1}{25} y)\space dy = \frac{1}{25} \int_{0}^y y \space dy = \frac{1}{25} \frac{y^{2}}{2} \bigg|^{y}_{0} = \frac{y²}{50}$$
>
> - Si $5 < y \leq 10$
>
> $$F_Y(y) = F_Y(5) + \int_{-\infty}^y \frac{2}{5}-(\frac{1}{25} y)\space dy = \frac{5²}{50} + \int_{5}^y \frac{2}{5}-(\frac{1}{25} y)\space dy = \frac{1}{2} + (\frac{2}{5} y-\frac{1}{50}y²) \bigg|_{5}^{y} =$$
>
> $$= \frac{1}{2} + (\frac{2}{5} y-\frac{1}{50}y² - (2 - \frac{1}{2})) = \frac{2}{5} y-\frac{1}{50}y² - 1$$
>
> La función acumulada queda así:
>
> ![](/Guia-Ejercicios/Practica3/imgs/ej4aAcumulada.png)

(b) Calcular $E(Y)$ y $V(Y)$.

> $$E(Y) = \mu_Y = \int_{-\infty}^{\infty} y \space f(y) \space dx = \int_{0}^{5} (y * \frac{1}{25} y) \space dy \space + \int_{5}^{10} [y * (\frac{2}{5}-\frac{1}{25} y)] \space dy = \int_{0}^{5} (\frac{1}{25} y²) \space dy \space + \int_{5}^{10} (\frac{2}{5}y-\frac{1}{25} y²) \space dy =$$
>
> $$=\frac{1}{25} \frac{y^3}{3} \bigg|^{5}_0 + (\frac{2}{5} \frac{y^2}{2} - \frac{1}{25} \frac{y^3}{3})  \bigg|_5^{10} = \frac{5}{3} - 0 + \frac{20}{3} - \frac{10}{3} = 5$$


> $$V(Y) = E(Y²) - E(Y)² = \int_{-\infty}^{\infty} y² \space f(y) \space dx = \int_{0}^{5} (y² * \frac{1}{25} y) \space dy \space + \int_{5}^{10} [y² * (\frac{2}{5}-\frac{1}{25} y)] \space dy =$$ 
>
> $$\int_{0}^{5} (\frac{1}{25} y³) \space dy \space + \int_{5}^{10} (\frac{2}{5}y²-\frac{1}{25} y³) \space dy - E(Y)² =$$
>
> $$=\frac{1}{25} \frac{y⁴}{4} \bigg|_0^5 + (\frac{2}{5} \frac{y³}{3} - \frac{1}{25} \frac{y⁴}{4}) \bigg|_5^{10} - E(Y)² = \frac{25}{4} - 0 + \frac{100}{3} - \frac{125}{12} - 5² = \frac{25}{6}$$
>

(c) Calcular $E(1/Y)$. ¿Qué conclusión saca respecto a la relación entre $E(1/Y)$ y $1/E(Y)$.

> $$E(\frac{1}{Y}) = \int_{-\infty}^{\infty} \frac{1}{y} \space f(y) \space dx = \int_{0}^{5} (\frac{1}{y} * \frac{1}{25} y) \space dy \space + \int_{5}^{10} [\frac{1}{y} * (\frac{2}{5}-\frac{1}{25} y)] \space dy = \int_{0}^{5} (\frac{1}{25} ) \space dy \space + \int_{5}^{10} (\frac{2}{5y}-\frac{1}{25}) \space dy =$$
>
> $$= \frac{y}{25} \bigg|_0^5 + (\frac{2}{5} ln(y) - \frac{y}{25}) \bigg|_5^{10} = \frac{1}{5} - 0 + \frac{2}{5}ln(10) - \frac{2}{5} - \frac{2}{5}ln(5) + \frac{1}{5} = \frac{2}{5}(ln(10)-ln(5)) = \frac{2}{5}ln(\frac{10}{5}) = \frac{2}{5}ln(2)$$
>

>$$\frac{1}{E(Y)} = \frac{1}{5}$$

> Ambos resultados dan distinto. En aplicaciones prácticas, esto significa que si tengo que tomar decisiones basadas en $Y$ y trabajo con valores esperados, necesito tener cuidado si las decisiones dependen de $\frac{1}{Y}$. Estas dos cantidades son distintas en general porque la esperanza de una función no lineal de una variable aleatoria (como $\frac{1}{Y}$) no es igual a la función aplicada a la esperanza de esa variable.

### 5) Puntos al azar

Se eligen $n$ puntos al azar en el intervalo $[0, 1]$ de forma independiente (con distribución uniforme). Sea $X$ = "Cantidad de puntos que caen en el intervalo $[0, p] \space (0 < p < 1)$. ¿Qué distribución tiene $X$?

> $X$ es una variable aleatoria discreta binomial $X \sim Bi(n,p)$ donde $p$ es $F(p)$ de que caiga en el intervalo correspondiente de la distribución uniforme. Esto se transforma en una discreta ya que cuando fijamos $p$, contamos las veces que caen en el intervalo o no caen. 

### 6) Distribución normal estandar

Sea $Z$ una v.a. con distribución $N(0, 1)$. Calcular:

> Usamos la tabla de distribución acumulada

1. $P(0 \leq Z \leq 2) =$

    > $= \phi(2) - \phi(0) = 0.9772 - 0.5000 = 0.4472$

2. $P(|Z| \leq 2,5)=$

    > $= P(-2.5 \leq Z \leq 2,5) = \phi(2.5) - \phi(-2.5) = \phi(2.5) - (1 - \phi(2.5)) = 0.9938 - 0.0062 = 0.9876$

3. $P(Z \geq −1,37)=$

    > $= 1 - P(Z \leq −1,37) = 1 - \phi(-1.37) = 1 - (1 - \phi(1.37)) = 0.9147$

4. $c$ tal que $P(Z < c) = 0,98$

    > Busco en la tabla el valor que más se aproxime a $0,9800$, en este caso $c = 2.05$

5. $c$ tal que $P(|Z| \leq c) = 0,90$

    > $P(|Z| \leq c) = P(-c \leq Z \leq c) = \phi(c) - \phi(-c) = \phi(c) - (1-\phi(c)) = 2 \phi(c) - 1 = 0.90 \Rightarrow \phi(c) = 0.95 \Rightarrow c = 1.64$

6. el valor $z_{\alpha}$ para $\alpha = 0.1, 0.05, 0.025, 0.01$, donde $z_{\alpha}$ se define como el valor tal que $P (Z > z_{\alpha} ) = \alpha$

    > Desarrollemos un poco: $P (Z > z_{\alpha} ) = 1 - P(Z \leq z_{\alpha}) = \alpha \Rightarrow P(Z \leq z_{\alpha}) = 1 - \alpha$ 
    >
    > - $P(Z \leq z_{\alpha}) = 1 - 0.1 = 0.9 \Rightarrow z_{\alpha} = 1.28$
    > - $P(Z \leq z_{\alpha}) = 1 - 0.05 = 0.95 \Rightarrow z_{\alpha} = 1.64$
    > - $P(Z \leq z_{\alpha}) = 1 - 0.025 = 0.975 \Rightarrow z_{\alpha} = 1.96$
    > - $P(Z \leq z_{\alpha}) = 1 - 0.01 = 0.99 \Rightarrow z_{\alpha} = 2.33$

### 7) Distribucion normal no estandar

Sea $X$ una v.a. con distribución $N(5, 0.25)$. Calcular:

> El truco para distribucion normal no estandar es transfomarlo en una estandar ya que nos gusta la tablita, de la siguiente forma:
>
> $$\text{Si } X \sim N(\mu, \sigma{²}) \text{ entonces } \frac{X-\mu}{\sigma} \sim N(0,1)$$
>
> En nuestro caso tenemos:
>
> $$X \sim N(5, 0.25) \Rightarrow Y = \frac{X - 5}{\sqrt{0.25}} = \frac{X - 5}{0.5} \sim N(0, 1)$$

1. $P(4.75 \leq X \leq 5.50) =$

    > $= F_X(5.50) - F_X(4.75) = \phi(\frac{5.50 - 5}{0.5}) - \phi(\frac{4.75 - 5}{0.5}) = \phi(1) - \phi(-0.5) = \phi(1) - (1 - \phi(0.5)) = 0.8413 - (1 - 0.6915) = 0.5328$

2. $P(|X| > 5.25) =$

    > $= 1 - P(|X| \leq 5.25) = 1 - P(-5.25 \leq X \leq 5.25) = 1 - (F_X(5.25) - F_X(-5.25)) = 1 - (\phi(\frac{5.25 - 5}{0.5}) - \phi(\frac{-5.25 - 5}{0.5})) = 1 - (\phi(0.5) - \phi(-20.5)) = 1 - (\phi(0.5) - (1 - \phi(20.5))) =$
    >
    > Como el valor de 20.5 es muy elevado, es $\phi(20.5) \approx 1$, por lo tanto queda:
    >
    >$= 1 - \phi(0.5) = 0.3085$

3. $c$ tal que $P(|X − 5| \leq c) = 0.90$

    > $P(-c \leq X − 5 \leq c) = P(\frac{-c + 5 - 5}{0.5} \leq X \leq \frac{c+5-5}{0.5}) = P(\frac{-c}{0.5} \leq X \leq \frac{c}{0.5}) = 0.9$
    >
    > Como tenemos una distribución normal, sabemos que es simétrica alrrededor de 0. Si $P(\frac{-c}{0.5} \leq X \leq \frac{c}{0.5}) = 0.9$ deja un 10% de la probabilidad fuera del intervalo $\frac{-c}{0.5} \leq X \leq \frac{c}{0.5}$ equitativamente en el lado negativo como en el positivo, por esto para cubrir el intervalo necesitamos encontrar $P(X \leq \frac{c}{0.5}) = 0.95$
    >
    > Usando la tabla: $\frac{c}{0.5} = 1.64 \Rightarrow c = 0.82$

4. el 90-percentil de $X$

    > Tenemos que buscar $P(X \leq x_{0.9})=0.9$ es decir $P(Y \leq \frac{x_{0.9} - 5}{0.5}) = 0.9$.
    >
    > Buscando en la tabla nos da que $\frac{x_{0.9} - 5}{0.5} = 1.28 \Rightarrow x_{0.9} = 5.64$

### 8) Cefálic

Se supone que en cierta población humana, el ı́ndice cefálic $I$ (anchura del cráneo expresada como porcentaje de la longitud) es una v.a. con distribución $N(\mu, \sigma^2 )$ . Si hay un 58 % de individuos con $I \leq 75$, un 38 % con $75 < I \leq 80$ y un 4 % con $I \geq 80$, hallar la función de densidad de $I$ y calcular $P (78 \leq I \leq 82)$.

> Notemos que no tenemos el valor de $\sigma$ y  $\mu$. Analicemos los datos de la consigna:
>
> - $P(I \leq 75) = 0.58 \Rightarrow \phi(\frac{75 - \mu}{\sigma}) = 0.58 \text{ usando la tabla tenemos que } \frac{75 - \mu}{\sigma} = 0.2$
> - $P(75 < I \leq 80) = 0.38 \Rightarrow \phi(\frac{80 - \mu}{\sigma}) - \phi(\frac{75 - \mu}{\sigma}) = 0.38 \Rightarrow \phi(\frac{80 - \mu}{\sigma}) - 0.58 = 0.38 \Rightarrow \phi(\frac{80 - \mu}{\sigma})  = 0.96 \text{ usando la tabla tenemos que } \frac{80 - \mu}{\sigma} = 1.75$
>
> Si despejamos $\sigma$ obtenemos en cada ecuación:
>
> - $\sigma = \frac{75-\mu}{0.2}$
> - $\sigma = \frac{80-\mu}{1.75}$
>
> Igualamos para despejar $\mu$:
>
> $$\frac{75-\mu}{0.2} = \frac{80-\mu}{1.75}$$
>
> $$131.25 - 1.75 \mu = 16 - 0.2 \mu$$
>
> $$115.25 = 1.55 \mu \Rightarrow \mu = 74.3548$$
>
> Reemplazamos $\mu$ para averiguar $\sigma$
>
> $$\sigma = \frac{80-75.3548}{1.75} = 3.2258$$
>
> $$\sigma² = 10.4058$$
>
> Entonces la función densidad es la de $I \sim N(74.3548, 10.4058)$
>
> ![](/Guia-Ejercicios/Practica3/imgs/ej8Densidad.png)
>
> Calcular $P (78 \leq I \leq 82)=$
>
> $$= F_I(82) - F_I(78) = \phi(\frac{82 - 74.3548}{3.2258}) - \phi(\frac{78 - 74.3548}{3.2258}) = \phi(2.37) - \phi(1.13) = 0.9911 - 0.8708 = 0.1203$$

### 9) Distancia intercuartil (IQR)

La distancia intercuartil (IQR) de una v.a. se define como la diferencia entre el tercer cuartil y el primer cuartil. Hallar la IQR de $Z$, una v.a. con distribución $N(0, 1)$.

> Tenemos que buscar $z_{0.25}$ y $z_{0.75}$ tales que $P(Z \leq z_{0.75}) = 0.75$ y $P(Z \leq z_{0.25}) = 0.25$
>
> $$\phi(z_{0.75})=0.75 \Rightarrow z_{0.75} = 0.67$$ 
>
> $$\phi(z_{0.25})=0.25 \Rightarrow 1 - \phi(z_{0.25}) = 1 - 0.25 = 0.75 \Rightarrow -z_{0.25} = -0.67$$
>
> Entonces IRQ = $0.67 - (-0.67) = 1.34$

### 10) Mediana de desviaciones absolutas (MAD)

La mediana de desviaciones absolutas (MAD) de una v.a. se define como la mediana del valor absoluto de la diferencia entre la variable aleatoria y su mediana. Hallar la MAD de $Z$, una v.a. con distribución $N(0, 1)$. Sugerencia: Hallar la f.d.a de $|Z|$.

> Dado que $Z$ es simétrica alrrededor del 0, la distribución de $|Z|$ se puede obtener:
>
> $$F_{|Z|}(z) = P(|Z| \leq z) = P(-z \leq Z \leq z) = \phi(z) - \phi(-z) = \phi(z) - (1 - \phi(z))$$
>
> Nos queda:
>
> $$F_{|Z|}(z) = 2 \phi(z) - 1 \text{ donde } \phi(z) \text{ es la f.d.a de la normal estándar}$$
>
> La mediana es el $50$-percentil, es decir el $F_{|Z|} = 0.5$, juntando con lo de arriba implica que:
>
> $$2 \phi(z) - 1 = 0.5 \Rightarrow \phi = 0.75$$
>
> Usando la tabla encontramos que:
>
> $$z \approx 0.67$$

### 11) Biblioteca

La biblioteca de una facultad dispone de una red de computadoras al alcance de los estudiantes. La proporción de tiempo que un usuario destina a búsqueda bibliográfica es una variable aleatoria $T$ con función de densidad

$$ f_T(t) = c(100 − t) I_{[0,100]}(t)$$

(a) Hallar el valor de la constante c

> Como sabemos que $\int_{-\infty}^{\infty}f_T(t)dx=1$ por ser función densidad, calculamos:
>
> $$\int_{-\infty}^{\infty}f_T(t)dt = \int_{0}^{100} c(100 − t) dt = c \int_{0}^{100} (100 − t) dt = c * (100t - \frac{t²}{2})\bigg|^{100}_0 = c * 10000 - 5000 = 1$$
>
> $$\Rightarrow c = \frac{1}{5000}$$

(b) Supóngase que de acuerdo con el porcentaje de tiempo destinado a las búsqueda bibliográfica el usuario es clasificado en distintas categorı́as. La clasificación se realiza de la siguiente manera: si T < 25 % el usuario es de tipo 1, si 25% <= T< 50% el usuario es tipo 2, si 50 % ≤ T < 75 % el usuario es tipo 3 y si T > 75 %, el usuario es de tipo es 4. Hallar la distribución del tipo de usuario.

> - Tipo 1: tenemos que $T<25$
>
> $$\int_{0}^{25} \frac{1}{5000}(100 − t) dt = \frac{1}{5000} * (100t - \frac{t²}{2})\bigg|^{25}_0 = \frac{7}{16}$$
>
> - Tipo 2: tenemos que $25 \leq T < 50$
>
> $$\int_{25}^{50} \frac{1}{5000}(100 − t) dt = \frac{1}{5000} * (100t - \frac{t²}{2})\bigg|^{50}_{25} = \frac{1}{5000} * (3750 - 2187.5) = \frac{5}{16}$$
>
> - Tipo 3: tenemos que $50 \leq T < 75$
>
> $$\int_{50}^{75} \frac{1}{5000}(100 − t) dt = \frac{1}{5000} * (100t - \frac{t²}{2})\bigg|^{75}_{50} = \frac{1}{5000} * (4687.5-3750) = \frac{3}{16}$$
>
> - Tipo 4: tenemos que $T \geq 75$
>
> $$\int_{75}^{100} \frac{1}{5000}(100 − t) dt = \frac{1}{16}$$
>
> pues es el complemento de todos los demás tipos

### 12) Diámetro de un tronco

El diámetro $D$ (expresado en dm) del tronco de cierta especie de árboles es una variable aleatoria con función de densidad

$$ f_D(x) = k x I_{[0,10]}(x)$$

(a) Hallar el valor de la constante $k$.

(b) ¿Cuál es la probabilidad de que el diámetro de un árbol de esa especie elegido al azar mida entre 4 y 6 dm?

(c) Idem (b) sabiendo que el diámetro mide más de 5 dm.

(d) En un área del bosque hay 3 árboles de esa especie. Calcular la probabilidad de que exactamente 2 de ellos tengan el diámetro entre 4 y 6 dm.

(e) ¿Cuántos árboles habrı́a que muestrear en el bosque para que la probabilidad de encontrar al menos uno cuyo diámetro mida entre 4 y 6 dm, sea mayor o igual que 0.99?