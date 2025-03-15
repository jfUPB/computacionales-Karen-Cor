## Solución #9

```csharp
using System;

class Program
{
    // Definir las variables globales para KBD y SCREEN
    const int SCREEN_WIDTH = 512;
    const int SCREEN_HEIGHT = 256;
    static ushort[] SCREEN = new ushort[(SCREEN_WIDTH * SCREEN_HEIGHT) / 16]; // 8192 posiciones de memoria
    static ushort KBD = 0; // Teclado, para representar la entrada

    static void Main()
    {
        // Escribir valores en la pantalla (en las primeras posiciones)
        for (int i = 0; i < 10; i++)
        {
            SCREEN[i] = 0xFFFF;  // Representa escribir 16 píxeles (valor 0xFFFF)
        }

        // Simulando que se presiona una tecla (asignamos un valor a KBD)
        KBD = 0x1;  // Tecla presionada (valor 0x1)

        // Verificar si una tecla ha sido presionada
        if (KBD == 0x1)
        {
            Console.WriteLine("Tecla presionada: 0x1");
        }

        Console.WriteLine("Programa completado.");
    }
}
```

El arreglo SCREEN tiene 8192 posiciones, cada una representando 16 píxeles. (se saca teniendo en cuenta la resolucion de la pantalla)


