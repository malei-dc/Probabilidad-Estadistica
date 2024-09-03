# Clase 23-08-24

## Ejercicio 1
Una persona juega al poker con un mazo de $52$ cartas. En una primera mano recibe $5$ cartas y luego puede realizar un cambio de a lo sumo $2$ cartas por otras del mazo.

(a) ¿Cuál es la probabilidad de sacar $5$ cartas del mismo palo en la primera mano?

> Primero calculamos la cantidad de manos de 5 cartas se pueden tener: $\binom{52}{5} = 2,598,960$
>
> Hay cuatro palos en el mazo, la cantidad de combinaciones de 5 cartas de un mismo palo es $\binom{13}{5}$ y como hay cuatro palos queda: $4 * \binom{13}{5} = 5148$
>
> Entonces, $P(manoCincoMismoPaloPrimeraMano) = \frac{4 * \binom{13}{5}}{\binom{52}{5}} = 0.001980$

(b) ¿Cúal es la probabilidad de que obtenga las $5$ cartas del mismo palo luego del cambio dado que en la primera mano recibió exactamente $4$ cartas del mismo palo?

> Analicemos, obtuvimos 4 cartas de un mismo palo, y tenemos la opción de cambiar a lo sumo 2 cartas, pero se quiere cambiar solo la carta que no es del palo correcto. Del mazo quedan 47 cartas y del mismo palo quedan 9 cartas, entonces $P(manoMismoPaloCambiandoUna) = \frac{9}{47} = 0.1914$

(c) ¿Cúal es la probabilidad de que obtenga las $5$ cartas del mismo palo luego del cambio dado que en la primera mano recibió exactamente $3$ cartas del mismo palo?

> Siguiendo la idea del punto anterior, solo que ahora en lugar de uno, hay combinaciones distintas de elegir 2 cartas en el mazo y del mismo palo. La cuenta queda:
>
> $$P(manoMismoPaloCambiandoDos) = \frac{\binom{10}{2}}{\binom{47}{2}} = \frac{45}{1081} = 0.04162


(d) ¿Cuál es la probabilidad de que obtenga todas del mismo palo?

> Como venimos calculando, la probabilidad de que obtenga todas del mismo palo es la suma de los tres escenarios: $P(manoCincoMismoPalo) = P(manoCincoMismoPaloPrimeraMano) + P(manoMismoPaloCambiandoUna) + P(manoMismoPaloCambiandoDos) = 0.0019 + 0.1914 + 0.0416 = 0.2349$

## Ejercicio 2
Una determinada enfermedad está presente en un 4% de la población. Existe un test para detectar la presencia de dicha enfermedad. Se sabe que la probabilidad de que el test de positivo si se lo realiza a una persona enferma es de $0,92$ y que la probabilidad de que el test de positivo si se lo realiza a una persona sana es $0,06$. Se elige a una persona al azar de la población y se realiza el test. Hallar la probabilidad de que:

> Sea $A:$ "test da positivo" y $B:$ "persona enferma"

(a) El test de positivo.

> Usamos el teorema de la probabilidad total: 
>
> $$P(A) = P(A|B) * P(B) + P(A|B^c) * P(B^c) =$$
>
> $$= 0.92 * 0.04 + 0.06 * 0.96 = 0.0944$$

(b) La persona esté enferma si el test dio positivo.

> Queremos calcular $P(B|A) = \frac{P(A|B) * P(B)}{P(A)} = \frac{0.92 * 0.04}{0.0944} = 0.3898$

## Ejercicio 3
La construcción de una escuela en el plazo programada está relacionada con los siguientes acontecimientos: $E=$ "la excavación se completa a tiempo", $C=$ "los cimientos se completan a tiempo", $S=$ "la estructura exterior se completa a tiempo". Se pueden suponer independientes y se sabe que $P(E) = 0,8$ , $P(C) = 0,7$ y $P(S) = 0,9$. Calcular:

(a) La probabilidad de que la escuela sea terminada en el plazo programado debido al cumplimiento de los plazos de las tres actividades.

> Como son independientes, calculamos $P(E \cap C \cap S) = 0.8 * 0.7 * 0.9 = 0.504$

(b) Que la excavación se complete a tiempo y no se complete a tiempo al menos una de las otras actividades.

> Hay dos posibilidades, que no se complete:
>
> - Los cimientos no se completan a tiempo
> - o la estructura exterior no se completa a tiempo
>
> Sea $A:$ "la excavación se complete a tiempo y no se complete a tiempo al menos una de las otras actividades".
>
> $$P(A) = P(E \cap C^c \cap S) + P(E \cap C \cap S^c) =$$
>
> $$= 0.8 * (1-0.7) * 0.9 + 0.8 * 0.7 * (1-0.9) = 0.272$$








