# Práctica 0: Combinatoria

## 1. Regla del producto

(a) ¿Cuántos números de dos cifras se pueden formar con los dı́gitos 1,2,3?

> Para formar números de dos cifras usando los dígitos 1,2,3 tenemos tres números para las decenas y tres números para las unidades. $Total= 3 \times 3 = 9$.

(b) ¿Cuántos números de dos cifras se pueden formar con los dı́gitos 0,1,2? (Recuerde, un número no puede empezar con 0)

> Siguiendo el mismo razonamiento de arriba, tengo entonces dos números posibles para las decenas y tres números posibles para las unidades. $Total = 2 \times 3 = 6$

(c) ¿Cuántos números de dos cifras se pueden formar con los dı́gitos 0,1,2,3?

> Siguiendo el mismo razonamiento de arriba, tengo entonces tres números posibles para las decenas y cuatro números posibles para las unidades. $Total = 3 \times 4 = 12$

(d) ¿Cuántos números pares de cuatro cifras se pueden formar con los dı́gitos 1,2,3,4?

> El razonamiento es similar a la de arriba solo que se agregan dígitos y la condición de que sea par permite a las unidades ser solo dos números posibles (2, 4). $Total = 4 \times 4 \times 4 \times 2 = 128$ 

(e) ¿Cuántos números de cuatro cifras distinas se pueden formar con los dı́gitos 1,2,3,4?

> Para las unidades tengo cuatro opciones, para las centenas 3, decenas 2 y unidades 1. $Total = 4 \times 3 \times 2 \times 1 = 24$

(f) ¿Cuántos números capicuas de cinco cifras distinas se pueden formar con los dı́gitos 1,2,3,4,5,6,7?

> Un número capicua es aquel que se lee igual de izquierda derecha y derecha izquierda. Entonces para el primer dígito podemos elegir entre siete números, el segundo entre seis números, el tercero entre cinco y los últimos dos uno solo correspondiendo a los dos anteriores que se eligió. $Total = 7 \times 6 \times 5 \times 1 \times 1 = 210$

(g) Una habitación tiene 6 puertas, de cuántas maneras puedo entrar por una puerta y salir por la otra?

> Entro por una de las 6 puertas que hay en la habitación y para salir no puedo usar la puerta por la que entré, hay 5 opciones. $Total = 6 \times 5 = 30$

## 2) Regla del producto (cont)

Sean $A$, $B$ y $C$ tres ciudades distintas. Suponga que hay cuatro rutas distintas que unen a $A$ con $B$ y $6$ que unen a $B$ con $C$.

(a) ¿Cuántas rutas existen de $A$ a $C$ pasando por $B$?

> $Total = 4 \times 6 = 24$

(b) ¿Cuántas rutas de ida y vuelta existen que vayan de $A$ a $C$ pasando por $B$?

> Como no especifica que sean rutas diferentes entre la ida y vuelta, en ambos casos el tramo de $A$ a $B$ tienen 4 opciones, de la misma forma para el tramo de $B$ a $C$. $Total = 4² \times 6² = 576$

## 3) Regla del producto (cont2)

(a) ¿Cuántos resultados pueden obtenerse al arrojar una moneda tres veces? 

> Cada tirada son dos resultados posibles. $Total = 2 \times 2 \times 2 = 8$

¿Y si se lanza un dado de 6 caras dos veces?

> Cada tirada son seis resultados posibles. $Total = 6 \times 6 = 36$

(b) ¿Cuántos números con cifras distintas, elegidas entre los dı́gitos 1 a 6, tienen las
siguientes propiedades:

- Tienen cinco cifras.

    > La primera cifra tiene seis opciones, la segunda cifra tiene cinco, y así... $Total = 6 \times 5 \times 4 \times 3 \times 2 = 720$ 

- Tienen 5 cifras y comienzan con 36.

    > Las primeras dos cifras están fijas y no se pueden volver a elegir, las sacamos de las opciones posibles. Entonces la primera cifra que elegimos tiene 4 opciones, y así... $Total = 4 \times 3 \times 2 = 24$

- Tienen 5 cifras y no comienzan con 1.

    > Que no comience con uno quiere decir que la primera cifra hay cinco opciones, luego en la segunda cifra hay también cinco opciones y ya en la tercera cifra hay cuatro opciones y así... $Total = 5 \times 5 \times 4 \times 3 \times 2 = 600$

(c) Se arrojan dos dados, uno rojo y otro blanco.

- Cuántos resultados distintos hay?

    > Suponiendo que son dados de seis caras, para el dado rojo hay seis posibles resultados, lo mismo para el dado blanco. $Total = 6 \times 6 = 36$

- Cuántos resultados distintos hay en que la suma es mayor a 9?

    >- El $10$ se puede formar como $6+4$ y $5+5$.
    >- El $11$ se puede formar como $5+6$.
    >- El $12$ se puede formar como $6+6$
    >
    > Cada combinación de números diferentes tiene dos formas ya que hay dos dados distinguibles, para las combinaciones de números iguales siempre uno es rojo y otro blanco. $Total = 6$

## 4) Permutación

(a) ¿De cuántas maneras distintas puede fotografiarse una familia de 5 personas puestas en hilera?

> La primera posición hay cinco personas como opción, la segunda posición cuatro, y así... $Total = 5! = 120$

(b) Mismo problema pero el padre y la madre estan siempre juntos.

> Considero el padre y la madre como una misma persona, además hay dos forma de emparejarlos juntos, padre primero o segundo. $Total = 4! \times 2 = 48$

(c) ¿De cuántas maneras distintas pueden sentarse 10 personan en una mesa circular? Sug: mesa circular implica que hay invariancia rotacional.

> En lugar de considerar todas las posiciones como distintas, podemos fijar una persona en un lugar específico y permutar las demás. Esto elimina las redundancias causadas por la rotación. Después de fijar a una persona, podemos permutar las otras 9 personas en los lugares restantes. $Total = 9! = 362880$

(d) ¿De cuántas maneras distintas pueden alinearse 8 parejas si cada marido debe ir con su esposa?

> El razonamiento es muy similar al punto b), cada pareja tiene dos formas, esposa primera o segunda. $Total = 8! \times 2^8 = 10.321.920$

(e) ¿Cuántos anagramas tiene la palabra CALOR? 

> Todas las letra son distintas, se puede pensar como permutar en linea cinco elementos distintos. $Total = 5! = 120$ 

¿Y la palabra ELEFANTE?

> A diferencia del caso anterior hay letras iguales, primero permuto como si fueran todos letras distintos y luego divido por la cantidad de letras que se repiten. $Total = \frac{8!}{3!} =6720$

¿La palabra ANANA?

> Con el mismo razonamiento anterior. $Total = \frac{5!}{3! \times 2!}=10$ 

## 5) Combinación
Utilizando el número combinatorio, calcular de cuántas formas se puede:

(a) elegir tres docentes para un curso de combinatoria, si hay disponibles 50 docentes.

> $Total = \binom{50}{3} = 19600$ 

(b) elegir simultaneamente tres docentes para un curso de algebra y cinco para uno de analisis, de un total de 50 docentes.

> $Total = \binom{50}{3} \times \binom{47}{5} = 30.065.204.400$

(c) conformar una comisión con un presidente, dos secretarios y cinco vocales de un total de 20 personas.

> $Total = \binom{20}{1} \times \binom{19}{2} \times \binom{17}{5} = 21.162.960$

(d) elegir 18 libros de una lista de 40 libros si un determinado libro debe estar siempre incluido.

> $Total = \binom{39}{17} = 51.021.117.810$

(e) Idem inciso anterior pero ahora excluyendo el libro.

> $Total = \binom{39}{18} = 62.359.143.990$

## 6) Bolas indistinguibles
Se tienen $n$ urnas diferentes. ¿De cuántas maneras diferentes se pueden colocar en ellas $m (n < m)$ bolas idénticas:

(a) sin restricción alguna en cuanto al número de bolas en cada urna;

> El número de maneras diferentes de colocar $m$ bolas idénticas en $n$ urnas diferentes, sin ninguna restricción en cuanto al número de bolas en cada urna, es: $\binom{m+n-1}{n-1} = \frac{(m+n-1)!}{(n-1)!m!}$

(b) si no puede haber ninguna urna vacı́a;

> Colocamos una bola en cada urna para asegurarnos de que ninguna quede vacía. Esto deja $m−n$ bolas restantes para distribuir sin restricciones entre las $n$ urnas. El problema que queda es equivalente al caso anterior: $\binom{m-n+n-1}{n-1} = \binom{m-1}{n-1} = \frac{(m-1)!}{(n-1)! (m-n)!}$

(c) si quedan exactamente $r (0 < r < n)$ urnas vacı́as?

> La forma de calcular esto es:
> 1. Elegir las urnas vacías: $\binom{n}{r}$.
> 2. Distribuir las bolas entre las $n−r$ urnas restantes: $\binom{m+n-r-1}{n-r-1}$
>
>Por lo tanto el número total de maneras es $\binom{n}{r} \times \binom{m+n-r-1}{n-r-1}$

