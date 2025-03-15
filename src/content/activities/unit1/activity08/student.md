## Solución #8

```
@5        // Carga la dirección de memoria 5 en el registro A
D=M       // Carga el valor almacenado en la dirección 5 en el registro D
@10       // Carga el valor 10 en el registro A
D=D-A     // Resta 10 del valor en D (D = valor en 5 - 10)
@12       // Si D < 0 (es decir, valor en 5 < 10), salta a la línea 12
D;JLT     
@0        // Carga el valor 0 en el registro A
D=A       // Copia el valor 0 al registro D
@7        // Carga la dirección de memoria 7 en el registro A
M=D       // Almacena el valor de D (0) en la dirección de memoria 7
@16       // Salta a la línea 16 (final del programa)
0;JMP
@1        // Carga el valor 1 en el registro A
D=A       // Copia el valor 1 al registro D
@7        // Carga la dirección de memoria 7 en el registro A
M=D       // Almacena el valor de D (1) en la dirección de memoria 7
@16       // Salta a la línea 16 (final del programa)
0;JMP
```

Caso #1, <10

![Caso1puntoocho](https://github.com/user-attachments/assets/5d5eca63-c682-48ea-b6c6-6eab058d221e)



Caso #2, >10

![caso2puntoocho](https://github.com/user-attachments/assets/c20e15d2-5e60-4931-a7be-6603fa7cb826)
