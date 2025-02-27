## Solución #7

// Inicialización del arreglo 'arr' en memoria
@16          // Dirección de memoria de arr[0]
M=1          // arr[0] = 1
@17          // Dirección de memoria de arr[1]
M=2          // arr[1] = 2
@18          // Dirección de memoria de arr[2]
M=3          // arr[2] = 3
@19          // Dirección de memoria de arr[3]
M=4          // arr[3] = 4
@20          // Dirección de memoria de arr[4]
M=5          // arr[4] = 5
@21          // Dirección de memoria de arr[5]
M=6          // arr[5] = 6
@22          // Dirección de memoria de arr[6]
M=7          // arr[6] = 7
@23          // Dirección de memoria de arr[7]
M=8          // arr[7] = 8
@24          // Dirección de memoria de arr[8]
M=9          // arr[8] = 9
@25          // Dirección de memoria de arr[9]
M=10         // arr[9] = 10

// Inicialización de sum = 0
@26          // Dirección de sum
M=0          // sum = 0

// Inicialización de j = 0
@27          // Dirección de j
M=0          // j = 0

// Comienzo del ciclo 'for'
(LOOP)
// Comprobar si j < 10
    @27          // Dirección de j
    D=M         // D = j
    @30          // Comparar con 10
    D=D-A       // D = j - 10
    @END         // Si j >= 10, salta a END
    D;JGE

// Cargar arr[j] en D
    @27          // Dirección de j
    D=M         // D = j
    @16          // Dirección de arr
    A=D+A       // A = arr + j
    D=M         // D = arr[j]

// Sumar arr[j] a sum
    @26          // Dirección de sum
    M=M+D       // sum = sum + arr[j]

// Incrementar j
    @27          // Dirección de j
    M=M+1       // j = j + 1

  @LOOP
  0;JMP

