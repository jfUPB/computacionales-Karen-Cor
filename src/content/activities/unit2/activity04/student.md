## Solución #4
```
// Inicialización de 'a' en memoria
@0          // Dirección de memoria de 'a'
M=10         // 'a' = 10

// Declaración del puntero 'p'
@1          // Dirección de memoria para 'p'
M=0         // Inicializamos 'p' en 0, aunque no es necesario todavía

// Asignar la dirección de 'a' a 'p'
@0          // Dirección de 'a'
D=A         // Cargar la dirección de 'a' en D
@1          // Dirección de 'p'
M=D         // Guardar la dirección de 'a' en 'p'

// Modificar el valor de 'a' a través del puntero 'p'
@1          // Dirección de 'p' (puntero)
D=M         // Cargar la dirección de 'a' (el valor que tiene 'p')
@0          // Dirección de 'a'
M=20        // Modificar el valor de 'a' a 20
```
