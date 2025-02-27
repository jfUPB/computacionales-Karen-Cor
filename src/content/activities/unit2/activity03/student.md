## Solución #3

-Convierte la versión del for a ensamblador.

R//:
// Inicializamos sum = 0 y i = 1
@1          // Cargar 1 en A
D=A         // Guardar 1 en D
@I          // Dirección de i
M=D         // i = 1

@0          // Cargar 0 en A
D=A         // Guardar 0 en D
@SUMA       // Dirección de sum
M=D         // sum = 0

(LOOP)
@I          // Cargar i
D=M         // D = i
@100        // Cargar 100 en A
D=D-A       // D = i - 100
@END        // Si D es negativo, salir del ciclo
D;JGT       // Si i <= 100, sigue el ciclo

@I          // Cargar i
D=M         // D = i
@SUMA       // Dirección de sum
M=D+A       // sum += i

@I          // Cargar i
D=M         // D = i
@1          // Cargar 1 en A
D=D+A       // D = i + 1
@I          // Dirección de i
M=D         // i = i + 1

@LOOP       // Volver al ciclo
0;JMP       // Continuar
(END)


-Compara las versiones en ensamblador del while y del for. ¿Qué puedes concluir?

R//:
