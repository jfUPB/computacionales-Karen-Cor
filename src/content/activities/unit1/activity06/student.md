## Solución #6

¿Qué es el direccionamiento directo? ¿Cómo se usa en el lenguaje ensamblador Hack?

   R/: El direccionamiento directo es una forma de acceso a la memoria donde se
       especifica explícitamente la dirección de memoria que se desea utilizar. En
       el lenguaje ensamblador Hack, esto se logra utilizando la instrucción @ seguida
       de un número, que representa la dirección de memoria. Por ejemplo:
       
       @5    // Selecciona la dirección de memoria 5
       D=M   // Lee el valor almacenado en la dirección 5 y lo guarda en el registro D


¿Qué significa M=D en lenguaje ensamblador Hack? ¿Y D=M?

R/: Como se vio en el punto anterio, M=D es una instruccion que asigna el valor almacenado en el registro D a la direccion de memoria seleccionada actualmente (la que se guardo en el registro A). D=M hace lo contrario, toma el valor almacenado en la direccion de memoria actual y lo guarda en el registro D


Explica con tus palabras el concepto de “puntero” en el contexto de la memoria y proporciona un ejemplo
sencillo en lenguaje ensamblador Hack. (Puedes usar el ejemplo de la página 61 del documento como inspiración,
pero adáptalo a un caso más simple).

R/: Un puntero es un valor que almacena una dirección de memoria. En lugar de contener un dato, un puntero directamente "apunta" a la ubicación en la memoria donde ese dato está almacenado. Permitiendo acceder a los datos de manera indirecta. Para el ejemplo supondremos que en la direccion 3 esta almacenado el valor 10 (un puntero) y que en la direccion 10 esta almacenado el valor 42:

@3    // Selecciona la dirección 3
D=M   // Lee el valor en la dirección 3 (10) y lo guarda en D
A=D   // Usa el valor de D (10) como nueva dirección
D=M   // Lee el valor en la dirección 10 (42) y lo guarda en D

// Ahora el registro D contiene el valor 42, accedido indirectamente a través del puntero en la dirección 3
