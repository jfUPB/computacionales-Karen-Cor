## Solución #11
De los principales conceptos de esta unidad:

 -Manipulacion de punteros en arreglos: el arreglo almacena un conjunto de elementos del mismo tipo en ubicaciones consecutivas y los punteros permiten acceder a estos elementos y modificarlos

    ejemplo:
    @ARR      // Dirección del arreglo
    D=M       // Cargar dirección base de arr
    @I        // Índice i
    M=0       // Inicializar i en 0

    @SUMA     // Dirección de la variable suma
    M=0       // Inicializar suma en 0

    (LOOP)
    @I        // Cargar valor de i
    D=M
    @ARR      // Cargar la dirección base de arr
    A=D+A     // Apuntar a la dirección arr[i]
    D=M       // Cargar el valor arr[i]
    @SUMA     // Sumar el valor arr[i] a suma
    D=D+M
    @SUMA
    M=D       // Guardar el nuevo valor de suma
    @I
    D=M+1     // Incrementar i
    @I
    M=D       // Guardar el nuevo valor de i
    @LOOP     // Continuar el ciclo
    0;JMP


- Punteros y direcciones de memoria: se considera un puntero como una variable que almacena la dirección de memoria de otra variable. Lo que permite manipular datos a través de su ubicación en memoria y no solo con su valor.

      Ejemplo:
      int a = 10;
      int* p = &a;   // p apunta a la dirección de a
      *p = 20;       // Cambiar el valor de a a través del puntero


