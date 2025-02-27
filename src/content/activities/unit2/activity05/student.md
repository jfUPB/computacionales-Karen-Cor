## Solución #5
```
// Inicialización de 'a' y 'b'
@0          // Dirección de memoria de 'a'
M=10         // 'a' = 10

@1          // Dirección de memoria de 'b'
M=5         // 'b' = 5

// Declaración del puntero 'p'
@2          // Dirección de memoria para 'p'
M=0         // Inicializamos 'p' en 0, aún no tiene valor

// Asignar la dirección de 'a' a 'p'
@0          // Dirección de 'a'
D=A         // Cargar la dirección de 'a' en D
@2          // Dirección de 'p'
M=D         // Guardar la dirección de 'a' en 'p'

// Leer el valor apuntado por 'p' (que es 'a') y asignarlo a 'b'
@2          // Dirección de 'p' (puntero)
D=M         // Cargar la dirección de 'a' (el valor de 'p')
@0          // Dirección de 'a'
D=M         // Cargar el valor de 'a' en D (ahora D = 10)
@1          // Dirección de 'b'
M=D         // Asignar el valor de 'a' (10) a 'b'
```
