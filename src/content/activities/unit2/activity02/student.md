## Solución #2

¿En qué direcciones de memoria se implementan las variables i, sum?

R//:

- Basado en esta experiencia, ¿Cuál es la diferencia entre la dirección de una variable y su contenido?

R//: En pocas palabras, el contenido es lo que hay en la variable y la dirección es dónde está esa variable, un ejemplo seria que i podría estar en la dirección 16 y su contenido podría ser 1 al inicio del programa

- Explica cómo se implementa la condición i <= 100

R//: hay que tener en cuenta que la condición i <= 100 se implementa en el bucle LOOP:

Se carga el valor de i en el registro D.

Se resta 100 de D (D = i - 100).

Si D > 0, significa que i > 100, y el programa salta a END.

Si D <= 0, el bucle continúa sumando i a sum y luego incrementa i en 1.

el bucle se repite mientras i sea menor o igual a 100. Cuando i supera 100, el programa termina.

