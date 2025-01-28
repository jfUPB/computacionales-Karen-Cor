#### Actividad #1

```
@1
D=A
@2
D=D+A
@16
M=D
@6
0;JMP
```
@1 -> Carga el valor 1 en el registro A
D=A -> Mueve el valor de A al registro D
@2 -> Carga el valor 2 en el registro A
D=D+A -> Suma el valor actual de D con el valor de A, guardando el resultado en D
@16 -> Apunta a la dirección de memoria 16
M=D -> Almacena el valor de D en la posición de memoria 16
@6 -> Carga el valor 6 en el registro A
0;JMP -> Salta incondicionalmente a la instrucción en la posición 6 (bucle infinito)

- Suma los número 60 y 9 y guarda el resultado en la posición de memoria 6
R/:
```
@60
D=A
@9
D=D+A
@6
M=D
```
@60 -> Carga el valor 60 en el registro A
D=A -> Mueve el valor de A al registro D
@9 -> Carga el valor 9 en el registro A
D=D+A -> Suma el valor actual de D (60) con el valor de A (9), guardando el resultado (69) en D.
@6 -> Apunta a la posición de memoria 6.
M=D -> Almacena el valor de D (69) en la posición de memoria 6



- Has que el programa vuelva a comenzar desde la posición 0 una vez almacene el resultado de la operación.
R/:
```
@60
D=A
@9
D=D+A
@6
M=D
@0
0;JMP
```
Después de almacenar el resultado en la posición de memoria 6 (M=D), se añade una instrucción que redirige la ejecución de vuelta a la posición 0.
@0 -> Apunta a la posición de memoria 0.
0;JMP -> Salta incondicionalmente a la posición 0, reiniciando la ejecución del programa.


En resumen, solo tuve que cambiar los valores de suma y ajustar la posicion de memoria donde se almacenaban los resultados.

