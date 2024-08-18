# Clase 16-08-2024

## Ejercicio 1 
En cierto estado, 58 vertederos están clasificados según la concentración de 3 sustan-
cias quı́micas peligrosas: Arsénico, Bario y Mercurio. Supongamos que la concentración de cada una
se caracteriza como baja o alta. Si se elige un vertedero al azar, ¿cuál es la probabilidad de que tenga:

(a) alta concentración de Bario?

> Si definimos el conjunto $A$ como los vertedero que tienen alta concentración de Bario. Y tomamos en cuenta que $|S| = 58$ ya que son la cantidad de vertederos totales, $P(A) = \frac{|A|}{|S|} = \frac{1+4+3+8}{58} = 0.2758$.

(b) alta concentración de Mercurio y baja concentración tanto de Arsénico como de Bario?

> Definimos al conjunto $B$ como los vertederos que tienen alta concentración de Mercurio y baja concentración tanto de Arsénico como de Bario. Entonces $P(B) = \frac{|B|}{|S|} = \frac{10}{58} = 0.1724$

(c) baja concentración de una sustancia y alta de las otras dos?

> Definimos al conjunto $C$ como los vertederos que tienen baja concentración de una sustancia y alta de las otras dos. Entonces $P(C) = \frac{|C|}{|S|} = \frac{4+3+5}{58} = 0.2069$

## Ejercicio 2
Tenemos 3 cajas numeradas y 4 bolitas blancas que se distribuyen todas al azar. Calcular la probabilidad de que:

(a) la caja 1 tenga exactamente 2 bolitas,

> Primero debemos considerar cómo se distribuyen las 4 bolitas blancas entre las 3 cajas numeradas. Cada una de las 4 bolitas pueden ir en cualquiera de las 3 cajas, por lo tanto tenemos un espacio muestra de $|S|=3⁴$
>
> Para que la caja 1 tenga exactamente 2 bolitas, necesitamos elegir 2 de las 4 bolitas para colocar en la caja 1. El número de maneras de elegir 2 bolitas de 4 es dado por $\binom{4}{2}$. Las otras 2 bolitas restantes pueden ir en cualquiera de las 2 cajas restantes (caja 2 o caja 3), y cada una de estas 2 bolitas tiene 2 opciones de cajas, por lo que hay $2²$ maneras.
>
> Si definimos $A$ como el evento de que la caja 1 tenga exactamente 2 bolitas, tenemos que $|A| = \binom{4}{2} * 2² = 24$. Entonces $P(A)=\frac{|A|}{|S|}=\frac{24}{3⁴} = 0.2962$.

(b) la caja 2 no tenga bolitas,

> Si la caja 2 no tiene bolitas, se distribuyen las 4 bolitas entre solo la primera y la tercera caja. Luego si definimos el evento $B$ como la caja 2 no tiene bolitas, el numero de distribuciones favorables es $|B| = 2⁴$
>
> Nos queda que $P(B)=\frac{|B|}{|S|}=\frac{16}{81}=0.1975$.

(c) todas las cajas tengan al menos 1 bolita.

> 