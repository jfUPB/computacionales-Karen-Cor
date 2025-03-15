## Solución #9

```
// Inicializar variables
@1
M=1       // i = 1 (contador)
@0
M=0       // sum = 0 (acumulador)

// Inicio del ciclo
(LOOP)
@1
D=M       // D = i
@5
D=D-A     // D = i - 5
@END
D;JGT     // Si i > 5, salta a END

// Sumar i a sum
@1
D=M       // D = i
@0
M=D+M     // sum = sum + i

// Incrementar i
@1
M=M+1     // i = i + 1
@LOOP
0;JMP     // Repetir el ciclo

// Fin del ciclo
(END)
@0
D=M
@12
M=D       // Almacenar resultado en RAM[12]

// Bucle infinito para finalizar el programa
(INFINITE_LOOP)
@INFINITE_LOOP
0;JMP
```

![image](https://github.com/user-attachments/assets/d4cf775d-2ef4-4517-8c8f-cdf80b983fe1)
