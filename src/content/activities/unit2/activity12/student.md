## Solución #12

CONDICIONALES
```csharp
using System;

class Program {
    static void Main() {
        int x = 10;
        if (x > 5) {
            Console.WriteLine("x es mayor que 5");
        }
    }
}
```
```
@10        // Cargar valor 10 en A
D=A        // D = 10
@5         // Cargar valor 5 en A
D=D-A      // D = 10 - 5
@IF_TRUE   // Si D > 0, saltar a la etiqueta IF_TRUE
D;JGT      // Si la comparación es mayor, saltar

@END       // Terminar
0;JMP      // No hacer nada

(IF_TRUE)
@OUTPUT    // Imprimir "x es mayor que 5"
0;JMP
```

CICLOS WHILE
```csharp
using System;

class Program {
    static void Main() {
        int i = 0;
        while (i < 5) {
            Console.WriteLine(i);
            i++;
        }
    }
}
```
```
@0         // Cargar valor 0 en A
D=A        // D = 0
@i
M=D        // i = 0

(LOOP)
@i
D=M        // D = i
@5
D=D-A      // D = i - 5
@END_WHILE
D;JGE      // Si i >= 5, terminar el ciclo

@i
D=M
@OUTPUT
0;JMP      // Imprimir valor de i

@i
M=M+1      // i = i + 1
@LOOP
0;JMP      // Volver a empezar el ciclo
```

CICLOS FOR
```csharp
using System;

class Program {
    static void Main() {
        for (int i = 0; i < 5; i++) {
            Console.WriteLine(i);
        }
    }
}
```
```
@0         // Cargar valor 0 en A
D=A        // D = 0
@i
M=D        // i = 0

(FOR_LOOP)
@i
D=M        // D = i
@5
D=D-A      // D = i - 5
@END_FOR
D;JGE      // Si i >= 5, terminar el ciclo

@i
D=M
@OUTPUT
0;JMP      // Imprimir valor de i

@i
M=M+1      // i = i + 1
@FOR_LOOP
0;JMP      // Volver al inicio del ciclo
```

ESCRITURA DE VARIABLES POR MEDIO DE PUNTEROS
```csharp
using System;

class Program {
    static void Main() {
        int a = 10;
        unsafe {
            int* p = &a;
            *p = 20;  // Modificar el valor de 'a' usando el puntero
        }
        Console.WriteLine(a);  // Imprime 20
    }
}
```
```
@10        // Cargar valor 10 en A
D=A        // D = 10
@a
M=D        // a = 10

@a         // Cargar la dirección de a
D=M        // D = dirección de a
@p
M=D        // p = dirección de a

@p         // Cargar el valor de p (dirección de a)
D=M        // D = &a
@a
M=D        // a = 20
```

LECTURA DE VARIABLES POR MEDIO DE PUNTERO
```csharp
using System;

class Program {
    static void Main() {
        int a = 10;
        unsafe {
            int* p = &a;
            int b = *p;  // Leer el valor de 'a' usando el puntero
            Console.WriteLine(b);  // Imprime 10
        }
    }
}
```
```
@10        // Cargar valor 10 en A
D=A        // D = 10
@a
M=D        // a = 10

@a         // Cargar la dirección de a
D=M        // D = &a
@p
M=D        // p = &a

@p         // Cargar el valor de p (dirección de a)
D=M        // D = &a
@a
D=M        // D = valor de a (10)
@b
M=D        // b = 10
```

MANIPULACION DE UN ARREGLO POR MEDIO DE PUNTEROS
```csharp
using System;

class Program {
    static void Main() {
        int[] arr = { 1, 2, 3, 4, 5 };
        unsafe {
            int* p = &arr[0];
            for (int i = 0; i < 5; i++) {
                Console.WriteLine(*(p + i));  // Accede a los elementos del arreglo
            }
        }
    }
}
```
```
@1         // Cargar valor 1 en A
D=A
@arr
M=D        // arr[0] = 1

@2         // Cargar valor 2 en A
D=A
@arr+1
M=D        // arr[1] = 2

@arr       // Cargar la dirección de arr[0]
D=M
@p
M=D        // p = &arr[0]

@p         // Cargar la dirección de arr[0]
D=M        // D = &arr[0]
@arr
M=D        // Acceder al arreglo y mostrar los valores
```

LLAMADO A FUNCIONES CON PARAMETROS
```csharp
using System;

class Program {
    // Función que recibe un parámetro y retorna su doble
    static int Doble(int num) {
        return num * 2;
    }

    static void Main() {
        int x = 5;
        int resultado = Doble(x);  // Llamado a la función con parámetro
        Console.WriteLine(resultado);  // Imprime 10
    }
}
```
```
// Llamado a función con parámetro (Doble)
@5         // Cargar 5 en A
D=A        // D = 5
@Doble     // Llamar a la función Doble
0;JMP

(Doble)    // Función Doble
@5         // Cargar 5
D=A        // D = 5
D=D+D      // D = D * 2 = 10
@RESULTADO
M=D        // Guardar el resultado
@END
0;JMP      // Volver al flujo principal

(END)
@RESULTADO
D=M        // Cargar el resultado
@OUTPUT
M=D        // Mostrar el resultado
```

LLAMADO A FUNCIONES CON RETORNO DE PARAMETROS
```csharp
using System;

class Program {
    // Función que intercambia dos valores
    static void Intercambiar(ref int a, ref int b) {
        int temp = a;
        a = b;
        b = temp;
    }

    static void Main() {
        int x = 5, y = 10;
        Intercambiar(ref x, ref y);  // Llamado a función que intercambia valores
        Console.WriteLine($"x = {x}, y = {y}");  // Imprime x = 10, y = 5
    }
}
```
```
// Intercambiar valores (por referencia)
@5        // Cargar valor 5
D=A       // D = 5
@X        // Guardar 5 en X
M=D

@10       // Cargar valor 10
D=A       // D = 10
@Y        // Guardar 10 en Y
M=D

@X        // Cargar el valor de X
D=M       // D = X (5)
@TEMP     // Guardar el valor de X en TEMP
M=D

@Y        // Cargar el valor de Y
D=M       // D = Y (10)
@X        // Guardar el valor de Y en X
M=D

@TEMP     // Cargar el valor de TEMP (5)
D=M       // D = TEMP
@Y        // Guardar el valor de TEMP en Y
M=D

@END
0;JMP     // Terminar
(END)
@X
D=M       // Cargar el valor de X
@OUTPUT
M=D       // Mostrar el valor de X

@Y
D=M       // Cargar el valor de Y
@OUTPUT2
M=D       // Mostrar el valor de Y
```






