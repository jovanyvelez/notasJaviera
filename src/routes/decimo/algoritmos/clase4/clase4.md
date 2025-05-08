
# Clase 4: Tipos de Datos e Información

## Objetivos de Aprendizaje
- Comprender los diferentes tipos de datos en C#
- Aprender a elegir el tipo de dato adecuado según la información
- Conocer la conversión entre tipos de datos
- Practicar con operaciones básicas según el tipo de dato

## 1. Introducción a los Tipos de Datos

En programación, un tipo de dato define qué clase de información puede contener una variable y cómo se almacena en la memoria. Elegir el tipo correcto es crucial para:

- Optimizar el uso de memoria
- Prevenir errores de operación
- Definir qué operaciones son posibles con ese dato
- Garantizar la precisión de los cálculos

## 2. Tipos de Datos Primitivos en C#

C# ofrece varios tipos de datos integrados, que podemos clasificar en:

### Tipos Enteros (para números sin decimales)

| Tipo     | Tamaño (bytes) | Rango                                       | Uso común                     |
|----------|----------------|---------------------------------------------|-------------------------------|
| `byte`   | 1              | 0 a 255                                     | Valores muy pequeños          |
| `sbyte`  | 1              | -128 a 127                                  | Enteros pequeños con signo    |
| `short`  | 2              | -32,768 a 32,767                            | Enteros pequeños              |
| `ushort` | 2              | 0 a 65,535                                  | Enteros pequeños sin signo    |
| `int`    | 4              | -2,147,483,648 a 2,147,483,647              | Uso general                   |
| `uint`   | 4              | 0 a 4,294,967,295                           | Enteros grandes sin signo     |
| `long`   | 8              | -9,223,372,036,854,775,808 a 9,223,372,036,854,775,807 | Enteros muy grandes |
| `ulong`  | 8              | 0 a 18,446,744,073,709,551,615              | Enteros muy grandes sin signo |

```csharp
byte edad = 16;
int poblacion = 126700000;
long distanciaEnKm = 384400;  // Distancia Tierra-Luna
```

### Tipos de Punto Flotante (para números con decimales)

| Tipo      | Tamaño (bytes) | Precisión                | Uso común                     |
|-----------|----------------|--------------------------|-------------------------------|
| `float`   | 4              | ~6-9 dígitos             | Menor precisión, ahorra memoria |
| `double`  | 8              | ~15-17 dígitos           | Precisión estándar para cálculos |
| `decimal` | 16             | 28-29 dígitos decimales  | Alta precisión (finanzas)     |

```csharp
float altura = 1.75f;  // La f es obligatoria para float
double pi = 3.14159265359;
decimal precioProducto = 299.99m;  // La m es obligatoria para decimal
```

### Tipo Lógico (para valores verdadero/falso)

| Tipo      | Tamaño (bytes) | Valores                  | Uso común                     |
|-----------|----------------|--------------------------|-------------------------------|
| `bool`    | 1              | `true` o `false`         | Condiciones y estados         |

```csharp
bool esMayorDeEdad = false;
bool haCompletadoCurso = true;
```

### Tipo Carácter (para un solo símbolo)

| Tipo      | Tamaño (bytes) | Descripción              | Uso común                     |
|-----------|----------------|--------------------------|-------------------------------|
| `char`    | 2              | Un solo carácter Unicode | Letras, dígitos, símbolos     |

```csharp
char letra = 'A';
char simbolo = '$';
char digito = '7';
```

### Tipo Cadena (para texto)

| Tipo      | Tamaño        | Descripción              | Uso común                     |
|-----------|---------------|--------------------------|-------------------------------|
| `string`  | Variable      | Secuencia de caracteres  | Texto, nombres, mensajes      |

```csharp
string nombre = "Ana";
string mensaje = "Bienvenido al curso de programación";
```

## 3. Tipos de Datos por Valor vs. por Referencia

En C#, los tipos de datos se dividen en dos categorías:

### Tipos por Valor
- Almacenan directamente sus datos
- Cada variable tiene su propia copia de los datos
- Incluyen: todos los tipos numéricos, bool y char
- Se guardan en la pila (stack) de memoria

### Tipos por Referencia
- Almacenan una referencia (dirección de memoria) donde se encuentran los datos
- Múltiples variables pueden referenciar los mismos datos
- Incluyen: string, arrays, clases
- Se guardan en el montón (heap) de memoria

## 4. Conversión entre Tipos de Datos

A menudo necesitamos convertir datos de un tipo a otro:

### Conversión Implícita (Automática)
- Se realiza cuando no hay pérdida de información
- El compilador la hace automáticamente
- Por ejemplo: `int` → `long`, `float` → `double`

```csharp
int num = 100;
long numGrande = num;  // Conversión implícita de int a long
```

### Conversión Explícita (Casting)
- Necesaria cuando puede haber pérdida de información
- Requiere sintaxis especial con paréntesis
- Por ejemplo: `double` → `int`, `long` → `int`

```csharp
double precio = 29.99;
int precioRedondeado = (int)precio;  // Conversión explícita (se pierde el decimal)
```

### Métodos de Conversión
- C# proporciona métodos para conversiones seguras:

```csharp
string edadTexto = "25";
int edad = Convert.ToInt32(edadTexto);  // Convierte string a int

double altura = 1.85;
string alturaTexto = altura.ToString();  // Convierte double a string
```

### Conversión con Parse
- Los tipos numéricos tienen métodos `Parse` para convertir desde string:

```csharp
string numeroTexto = "123.45";
double numero = double.Parse(numeroTexto);
```

### TryParse para Conversiones Seguras
- Evita excepciones si la conversión falla:

```csharp
string entrada = "abc";
int numero;
bool exito = int.TryParse(entrada, out numero);

if (exito)
    Console.WriteLine($"Conversión exitosa: {numero}");
else
    Console.WriteLine("La conversión falló");
```

## 5. Operaciones según Tipo de Dato

Cada tipo de dato permite diferentes operaciones:

### Operaciones con Enteros y Flotantes
- Aritméticas: `+`, `-`, `*`, `/`, `%` (módulo)
- Incremento/decremento: `++`, `--`
- Asignación combinada: `+=`, `-=`, `*=`, `/=`, `%=`

```csharp
int a = 10, b = 3;
int suma = a + b;        // 13
int resta = a - b;       // 7
int producto = a * b;    // 30
int cociente = a / b;    // 3 (división entera)
int residuo = a % b;     // 1 (resto de la división)

a++;                     // a ahora es 11
b--;                     // b ahora es 2
```

### Operaciones con Punto Flotante
- Similar a enteros, pero con resultados decimales
- La división produce resultados con decimales

```csharp
double x = 10.0, y = 3.0;
double division = x / y;  // 3.3333333333333335
```

### Operaciones con Cadenas
- Concatenación: `+`
- Interpolación: `$"...{variable}..."`
- Métodos: `Length`, `ToUpper()`, `ToLower()`, `Substring()`, etc.

```csharp
string nombre = "Juan";
string apellido = "Pérez";
string nombreCompleto = nombre + " " + apellido;  // "Juan Pérez"

// Interpolación
string saludo = $"Hola {nombre}, bienvenido!";

// Métodos
int longitud = nombre.Length;                   // 4
string mayusculas = nombre.ToUpper();           // "JUAN"
string subCadena = apellido.Substring(0, 2);    // "Pé"
```

### Operaciones con Booleanos
- Lógicas: `&&` (AND), `||` (OR), `!` (NOT)
- Comparación: `==`, `!=`, `<`, `>`, `<=`, `>=`

```csharp
bool condicion1 = true;
bool condicion2 = false;

bool resultadoAnd = condicion1 && condicion2;  // false
bool resultadoOr = condicion1 || condicion2;   // true
bool resultadoNot = !condicion1;               // false

bool comparacion = (5 > 3);                    // true
```

## 6. Demostración Práctica

### Ejemplo: Calculadora con Múltiples Tipos de Datos

```csharp
using System;

namespace DemostracionTiposDatos
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("*** DEMOSTRACIÓN DE TIPOS DE DATOS ***\n");

            // Trabajando con enteros
            int num1 = 10;
            int num2 = 3;

            Console.WriteLine("--- Operaciones con enteros ---");
            Console.WriteLine($"Suma: {num1} + {num2} = {num1 + num2}");
            Console.WriteLine($"Resta: {num1} - {num2} = {num1 - num2}");
            Console.WriteLine($"Multiplicación: {num1} * {num2} = {num1 * num2}");
            Console.WriteLine($"División: {num1} / {num2} = {num1 / num2}");  // División entera
            Console.WriteLine($"Módulo: {num1} % {num2} = {num1 % num2}");

            // Trabajando con punto flotante
            double decimal1 = 10.0;
            double decimal2 = 3.0;

            Console.WriteLine("\n--- Operaciones con decimales ---");
            Console.WriteLine($"Suma: {decimal1} + {decimal2} = {decimal1 + decimal2}");
            Console.WriteLine($"División: {decimal1} / {decimal2} = {decimal1 / decimal2}");  // División decimal

            // Conversiones
            Console.WriteLine("\n--- Conversiones entre tipos ---");

            int entero = 42;
            double doble = entero;  // Conversión implícita
            Console.WriteLine($"Conversión implícita de int a double: {entero} → {doble}");

            double pi = 3.14159;
            int piRedondeado = (int)pi;  // Conversión explícita
            Console.WriteLine($"Conversión explícita de double a int: {pi} → {piRedondeado}");

            string numeroTexto = "123";
            int numeroParsed = int.Parse(numeroTexto);
            Console.WriteLine($"Conversión de string a int mediante Parse: {numeroTexto} → {numeroParsed}");

            // String y char
            Console.WriteLine("\n--- Operaciones con strings y chars ---");

            string nombre = "María";
            char inicial = nombre[0];  // Acceder al primer carácter
            Console.WriteLine($"Primer carácter de {nombre}: {inicial}");
            Console.WriteLine($"Longitud de {nombre}: {nombre.Length} caracteres");
            Console.WriteLine($"En mayúsculas: {nombre.ToUpper()}");

            string apellido = "López";
            string nombreCompleto = nombre + " " + apellido;
            Console.WriteLine($"Concatenación: {nombreCompleto}");

            // Boolean
            Console.WriteLine("\n--- Operaciones con booleanos ---");

            bool condicion1 = true;
            bool condicion2 = false;

            Console.WriteLine($"{condicion1} AND {condicion2} = {condicion1 && condicion2}");
            Console.WriteLine($"{condicion1} OR {condicion2} = {condicion1 || condicion2}");
            Console.WriteLine($"NOT {condicion1} = {!condicion1}");

            Console.ReadLine();
        }
    }
}
```

## 7. Actividad Práctica

### Ejercicio 1: Calculadora de Índice de Masa Corporal (IMC)

```csharp
using System;

namespace CalculadoraIMC
{
    class Program
    {
        static void Main(string[] args)
        {
            // Declaración de variables
            string nombre;
            double peso;       // en kilogramos
            double altura;     // en metros
            double imc;
            string categoria;

            // Solicitar datos al usuario
            Console.WriteLine("*** CALCULADORA DE IMC ***\n");

            Console.Write("Ingrese su nombre: ");
            nombre = Console.ReadLine();

            Console.Write("Ingrese su peso en kilogramos: ");
            string pesoStr = Console.ReadLine();

            Console.Write("Ingrese su altura en metros: ");
            string alturaStr = Console.ReadLine();

            // Convertir string a double
            bool pesoValido = double.TryParse(pesoStr, out peso);
            bool alturaValida = double.TryParse(alturaStr, out altura);

            // Verificar conversiones exitosas
            if (!pesoValido || !alturaValida)
            {
                Console.WriteLine("Error: Los valores ingresados no son válidos.");
                Console.ReadLine();
                return;  // Terminar el programa
            }

            // Calcular IMC
            imc = peso / (altura * altura);

            // Determinar categoría de peso
            if (imc < 18.5)
                categoria = "Bajo peso";
            else if (imc < 25)
                categoria = "Peso normal";
            else if (imc < 30)
                categoria = "Sobrepeso";
            else
                categoria = "Obesidad";

            // Mostrar resultados
            Console.WriteLine("\n--- RESULTADOS ---");
            Console.WriteLine($"Nombre: {nombre}");
            Console.WriteLine($"Peso: {peso} kg");
            Console.WriteLine($"Altura: {altura} m");
            Console.WriteLine($"IMC: {imc:F2}");
            Console.WriteLine($"Categoría: {categoria}");

            Console.ReadLine();
        }
    }
}
```

### Ejercicio 2: Manipulación de Cadenas

```csharp
using System;

namespace ManipulacionCadenas
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("*** MANIPULACIÓN DE CADENAS ***\n");

            // Solicitar texto al usuario
            Console.Write("Ingrese una frase: ");
            string frase = Console.ReadLine();

            // Información básica
            Console.WriteLine("\n--- INFORMACIÓN DE LA CADENA ---");
            Console.WriteLine($"Texto original: \"{frase}\"");
            Console.WriteLine($"Longitud: {frase.Length} caracteres");
            Console.WriteLine($"En mayúsculas: {frase.ToUpper()}");
            Console.WriteLine($"En minúsculas: {frase.ToLower()}");

            // Búsqueda
            Console.Write("\nIngrese una palabra para buscar en la frase: ");
            string palabraBuscar = Console.ReadLine();

            bool contienePalabra = frase.Contains(palabraBuscar);
            Console.WriteLine($"¿La frase contiene \"{palabraBuscar}\"? {contienePalabra}");

            if (contienePalabra)
            {
                int posicion = frase.IndexOf(palabraBuscar);
                Console.WriteLine($"La palabra \"{palabraBuscar}\" comienza en la posición {posicion}");
            }

            // Reemplazo
            Console.Write("\nReemplazar palabra (ingrese palabra a reemplazar): ");
            string palabraOriginal = Console.ReadLine();

            Console.Write("Reemplazar por: ");
            string palabraReemplazo = Console.ReadLine();

            string nuevaFrase = frase.Replace(palabraOriginal, palabraReemplazo);
            Console.WriteLine($"Frase con reemplazo: \"{nuevaFrase}\"");

            // División
            Console.WriteLine("\n--- PALABRAS EN LA FRASE ---");
            string[] palabras = frase.Split(' ');
            Console.WriteLine($"La frase contiene {palabras.Length} palabras:");

            for (int i = 0; i < palabras.Length; i++)
            {
                Console.WriteLine($"Palabra {i+1}: {palabras[i]}");
            }

            Console.ReadLine();
        }
    }
}
```

### Ejercicio 3: Conversiones de Tipos

```csharp
using System;

namespace ConversionesTipos
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("*** CONVERSIONES DE TIPOS ***\n");

            // String a números
            Console.Write("Ingrese un número entero: ");
            string entradaEntero = Console.ReadLine();

            Console.Write("Ingrese un número decimal: ");
            string entradaDecimal = Console.ReadLine();

            try
            {
                // Conversiones con Parse
                int numero = int.Parse(entradaEntero);
                double decimal1 = double.Parse(entradaDecimal);

                Console.WriteLine("\n--- Resultados con Parse ---");
                Console.WriteLine($"El entero multiplicado por 2: {numero * 2}");
                Console.WriteLine($"El decimal multiplicado por 3: {decimal1 * 3}");

                // Conversiones con Convert
                int numero2 = Convert.ToInt32(entradaEntero);
                double decimal2 = Convert.ToDouble(entradaDecimal);

                Console.WriteLine("\n--- Resultados con Convert ---");
                Console.WriteLine($"El entero multiplicado por 2: {numero2 * 2}");
                Console.WriteLine($"El decimal multiplicado por 3: {decimal2 * 3}");
            }
            catch (FormatException)
            {
                Console.WriteLine("\nError: El formato de entrada no es válido.");
            }
            catch (OverflowException)
            {
                Console.WriteLine("\nError: El número es demasiado grande o pequeño para el tipo de dato.");
            }

            // Conversiones con TryParse
            Console.WriteLine("\n--- Conversiones seguras con TryParse ---");

            Console.Write("Ingrese un valor (cualquier tipo): ");
            string entrada = Console.ReadLine();

            if (int.TryParse(entrada, out int resultadoInt))
                Console.WriteLine($"Se pudo convertir a int: {resultadoInt}");
            else if (double.TryParse(entrada, out double resultadoDouble))
                Console.WriteLine($"Se pudo convertir a double: {resultadoDouble}");
            else if (bool.TryParse(entrada, out bool resultadoBool))
                Console.WriteLine($"Se pudo convertir a bool: {resultadoBool}");
            else
                Console.WriteLine("No se pudo convertir a ningún tipo numérico o booleano.");

            Console.ReadLine();
        }
    }
}
```

## 8. Repaso y Conclusiones

En esta clase hemos aprendido:
- Los principales tipos de datos en C# y cuándo usarlos
- La diferencia entre tipos por valor y tipos por referencia
- Cómo realizar conversiones entre diferentes tipos
- Las operaciones disponibles según el tipo de dato
- Técnicas para manejar errores en las conversiones

## Tarea

1. Crea un programa que solicite al usuario distintos tipos de información (nombre, edad, altura, si tiene licencia de conducir) y luego muestre un resumen con el tipo de dato correcto para cada información.

2. Desarrolla una calculadora que realice las cuatro operaciones básicas (suma, resta, multiplicación y división) entre dos números. El programa debe manejar correctamente la división por cero y garantizar que los resultados sean precisos.

3. Implementa un conversor de unidades que pueda:
   - Convertir entre diferentes unidades de longitud (metros, pulgadas, pies)
   - Convertir entre diferentes unidades de peso (kilogramos, libras)
   - Convertir entre diferentes unidades de temperatura (Celsius, Fahrenheit)
   El programa debe utilizar constantes para los factores de conversión.

## Recursos Adicionales

- [Documentación oficial de tipos en C#](https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/builtin-types/built-in-types)
- [Conversiones de tipo en C#](https://docs.microsoft.com/es-es/dotnet/csharp/programming-guide/types/casting-and-type-conversions)
- [Operadores en C#](https://docs.microsoft.com/es-es/dotnet/csharp/language-reference/operators/)
- [Tutorial interactivo de tipos de datos](https://www.tutorialspoint.com/csharp/csharp_data_types.htm)

---

¡Felicidades! Has completado el módulo de conceptos básicos. En las próximas clases comenzaremos a explorar las estructuras de control para crear programas más complejos e interactivos.
