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

Sean $A$, $B$ y $C$ tres ciudades distintas. Suponga que hay cuatro rutas distintas que unen a $A$ con $B$ y 6 que unen a $B$ con $C$.

(a) ¿Cuántas rutas existen de $A$ a $C$ pasando por $B$?

(b) ¿Cuántas rutas de ida y vuelta existen que vayan de $A$ a $C$ pasando por $B$?