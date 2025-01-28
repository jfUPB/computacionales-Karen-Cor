## Actividad #4

¿Cuál es la función de cada tipo de instrucción?

  R/: A-instruction, establece el valor del registro A. Puede representar una dirección de memoria o un valor
      constante. Es fundamental para operaciones que requieren acceso a memoria o para usar valores inmediatos
      en cálculos. C-instruction realiza cálculos, mueve datos entre registros, o manipula la memoria.
      La instruccion A prepara el escenario para una instrucción C, diseñada para manipular una cierta
      ubicación de memoria de datos, al establecer primero A en la dirección de esa ubicación.
      

¿Cómo se representa cada tipo de instrucción en binario?

  R/:
  
  - A instruction:
  
  Comienza con 0 seguido de un número binario de 15 bits que representa el valor o la dirección.
  
  Ejemplo: @5 se representa como 0000000000000101.
      
  - C instruction:
  
  Comienza con 111, seguido de:
  
  comp: especifica la operación (6 bits).
  
  dest: indica dónde se almacena el resultado (3 bits).
  
  jump: define la condición de salto (3 bits).
  
  Ejemplo: D=D+A se representa como 1110000010010000.


Proporciona al menos 3 ejemplos de cada tipo de instrucción, explicando qué hace cada una. Puedes usar
las tablas de las páginas 67 y 69 del documento como referencia para los códigos de operación (comp),
destinos (dest) y saltos (jump).

  R/:

  - A instruction
  
  @100: Carga el valor 100 en el registro A.

  @SCREEN: Apunta a la dirección de memoria correspondiente a la pantalla (habitualmente 16384).

  @15: Asigna el valor 15 al registro A.

  - C instruction:
  
  D=M: Carga en el registro D el valor almacenado en la dirección de memoria apuntada por A.
  
  M=D+1: Suma 1 al valor de D y almacena el resultado en la dirección de memoria apuntada por A.
  
  0;JMP: Realiza un salto incondicional a la dirección contenida en el registro A.
