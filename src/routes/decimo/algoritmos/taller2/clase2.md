# Instrucciones Generales para los Alumnos:

  Para cada ejercicio, crea un nuevo proyecto de consola en C#. Lee atentamente el problema y utiliza las sentencias if, else if y else para tomar decisiones basadas en la entrada del usuario o en valores predefinidos. Recuerda cómo leer datos de la consola (Console.ReadLine()) y cómo convertirlos al tipo de dato necesario (ej: int.Parse()).

  Fuentes de Consulta:
  https://learn.microsoft.com/en-us/dotnet/csharp/language-reference/statements/selection-statements

  https://www.youtube.com/watch?v=c0dD3uKN5KA&t=2376s

  https://www.youtube.com/watch?v=c0dD3uKN5KA&t=2742s

  https://www.youtube.com/watch?v=c0dD3uKN5KA&t=2923s
  

## Ejercicios Propuestos (C# If Statements):

### 1. Mayor de Edad:
Pide al usuario que ingrese su edad.
Si la edad es 18 o mayor, muestra "Eres mayor de edad".
  * Estructura: if simple.

### 2. Aprobado o Reprobado:
Pide al usuario que ingrese una calificación numérica (ej: 7).
Si la calificación es 5 o mayor, muestra "Aprobado". De lo contrario, muestra "Reprobado".
  * Estructura: if-else.

### 3. Positivo, Negativo o Cero:
Pide al usuario que ingrese un número entero.
Muestra si el número es "Positivo", "Negativo" o "Cero".
  * Estructura: if-else if-else.

### 4. Contraseña Simple:
Pide al usuario que ingrese una contraseña.
Si la contraseña es exactamente "CSharp123", muestra "Acceso concedido". De lo contrario, muestra "Acceso denegado".
  * Estructura: if-else (comparación de strings).

### 5. ¿Es Fin de Semana?:
Pide al usuario que ingrese un día de la semana (ej: "Lunes", "Sábado").
Si el día es "Sábado" o "Domingo", muestra "Es fin de semana". De lo contrario, muestra "Es día laboral".
  * Estructura: if (con operador || OR) -else.

### 6. Descuento por Edad:
Pide al usuario su edad.
Si la edad es menor de 12 años o mayor de 65 años, muestra "Tienes descuento". De lo contrario, muestra "No tienes descuento".
  * Estructura: if (con operador || OR) -else.

### 7. Acceso VIP:
Pide al usuario su nombre y su edad.
Si el nombre es "Admin" Y la edad es mayor de 30, muestra "Acceso VIP concedido". De lo contrario, muestra "Acceso regular".
  * Estructura: if (con operador && AND) -else.

### 8. Temperatura Adecuada:
Pide al usuario que ingrese la temperatura actual en grados Celsius.
Si la temperatura está entre 20 y 25 (ambos inclusive), muestra "Temperatura agradable". Si es menor de 20, muestra "Hace frío". Si es mayor de 25, muestra "Hace calor".
  * Estructura: if-else if-else (con operador && AND para el rango).

### 9. Número Par o Impar:
Pide al usuario que ingrese un número entero.
Muestra si el número es "Par" o "Impar".
Pista: usa el operador módulo %.
  * Estructura: if-else.

### 10. Comparar dos Números:
Pide al usuario que ingrese dos números enteros, A y B.
Muestra si "A es mayor que B", "B es mayor que A" o "A y B son iguales".
  * Estructura: if-else if-else.

### 11. Longitud de Nombre:
Pide al usuario que ingrese su primer nombre.
Si la longitud del nombre es menor de 3 caracteres, muestra "Nombre demasiado corto". Si tiene 7 caracteres o más, muestra "Nombre largo". De lo contrario (entre 3 y 6 caracteres), muestra "Nombre de longitud adecuada".
  * Estructura: if-else if-else (usando la propiedad .Length de un string).

### 12. Vocal o Consonante (Simplificado):
Pide al usuario que ingrese una sola letra (minúscula).
Si la letra es 'a', 'e', 'i', 'o', o 'u', muestra "Es una vocal". De lo contrario, muestra "Es una consonante".
  * Estructura: if (con múltiples || OR) -else. Asume que el usuario ingresará una sola letra minúscula.


### 13. Elección de Menú Simple:
Muestra un menú: "1. Ver Saldo", "2. Realizar Depósito". Pide al usuario que ingrese una opción (1 o 2).
Si elige 1, muestra "Consultando saldo...". Si elige 2, muestra "Accediendo a depósitos...". Si elige cualquier otra cosa, muestra "Opción no válida".
  * Estructura: if-else if-else.
### 14. Divisible por 3 y 5:
Pide al usuario un número entero.
Si el número es divisible por 3 Y por 5, muestra "Divisible por 3 y 5". De lo contrario, muestra "No cumple la condición".
Pista: Un número es divisible por otro si el residuo de la división es 0.
  * Estructura: if (con && AND) -else.

### 15. ¿Misma Letra Inicial y Final?:
Pide al usuario que ingrese una palabra de al menos 2 letras.
Verifica si la primera letra de la palabra es igual a la última letra. Muestra "La primera y última letra son iguales" o "La primera y última letra son diferentes".
Pista: palabra[0] para la primera letra, palabra[palabra.Length - 1] para la última. Para simplificar, pueden asumir que se ingresará una palabra de al menos 2 letras.
  * Estructura: if-else.

### 16. Bono por Ventas:
Pide al usuario el monto de sus ventas mensuales.
Si las ventas son mayores a 1000, muestra "¡Felicidades! Recibes un bono".
(No hay else necesario aquí si solo se quiere mostrar el mensaje de bono).
  * Estructura: if simple.