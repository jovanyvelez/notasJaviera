<script>
  import { createHighlighter } from 'shiki';

  let code = $state('');

  const code1csharp = `
    // Nombres válidos para variables
    int edad;
    double precioProducto;
    string nombreCompleto;
    bool estaActivo;

    // Nombres válidos para constantes
    const double PI = 3.14159;
    const int DIAS_SEMANA = 7;

    // Nombres no recomendados
    int a;  // No descriptivo
    string NombreDeUsuario;  // No sigue camelCase
    double _$$precio;  // Usa caracteres especiales
`
const code2csharp = `
  tipoDeDato nombreVariable;

`

const code3csharp = `
  nombreVariable = valor;

`

const code4csharp = `
  tipoDeDato nombreVariable = valor;

`

const code5csharp = `
  const tipoDeDato NOMBRE_CONSTANTE = valor;

`

const code6csharp = `
  const double PI = 3.14159;

`

const code7csharp = `
  {
    int x = 10;  // Solo accesible dentro de este bloque
  }
  // Aquí x ya no existe

`

const code8csharp = `
  static void MiMetodo()
  {
    int contador = 0;  // Solo accesible dentro de MiMetodo
  }

`

const code9csharp = `
class Programa
{
  static int contadorGlobal = 0;  // Accesible en todos los métodos de la clase

  static void Main()
  {
    contadorGlobal++;  // Podemos acceder aquí
  }
}
`
const code10csharp = `
using System;

namespace CalculadoraEdad
{
  class Program
  {
    // Constante a nivel de clase
    const int ANIO_ACTUAL = 2025;

    static void Main(string[] args)
    {
      // Declaración de variables
      string nombre;
      int anioNacimiento;
      int edad;

      // Solicitar datos al usuario
      Console.Write("¿Cuál es tu nombre? ");
      nombre = Console.ReadLine();

      Console.Write("¿En qué año naciste? ");
      anioNacimiento = Convert.ToInt32(Console.ReadLine());

      // Calcular la edad
      edad = ANIO_ACTUAL - anioNacimiento;

      // Mostrar resultado
      Console.WriteLine($"Hola {nombre}, tienes o cumplirás {edad} años en {ANIO_ACTUAL}.");

      // Variable local con ámbito de bloque
      {
        string mensaje = "Esta variable solo existe dentro de este bloque";
        Console.WriteLine(mensaje);
      }
      // Aquí "mensaje" ya no es accesible

      Console.ReadLine();
    }
  }
}
`
    
const code11csharp = `
class Estudiante
{
    // Estos son campos de clase
    string nombre;
    int edad;
    double promedio;

    void MostrarInfo()
    {
        // Podemos acceder a los campos desde cualquier método de la clase
        Console.WriteLine($"Nombre: {nombre}, Edad: {edad}, Promedio: {promedio}");
    }
}
`

const code12csharp = `
void CalcularPromedio()
{
    // Estas son variables locales
    double nota1 = 8.5;
    double nota2 = 9.0;
    double nota3 = 7.5;

    double promedio = (nota1 + nota2 + nota3) / 3;

    // Las variables locales solo existen dentro de este método
}
`
  const code13csharp = `
using System;

namespace ConversorDivisas
{
    class Program
    {
        // Constantes para tipos de cambio (valores de ejemplo)
        const double TIPO_CAMBIO_USD = 0.056;  // 1 MXN = 0.056 USD
        const double TIPO_CAMBIO_EUR = 0.052;  // 1 MXN = 0.052 EUR
        const double TIPO_CAMBIO_GBP = 0.045;  // 1 MXN = 0.045 GBP

        static void Main(string[] args)
        {
            // Declaración de variables
            double pesosMexicanos;
            double dolares;
            double euros;
            double libras;

            // Solicitar cantidad en pesos
            Console.Write("Ingrese la cantidad en pesos mexicanos: ");
            pesosMexicanos = Convert.ToDouble(Console.ReadLine());

            // Realizar conversiones
            dolares = pesosMexicanos * TIPO_CAMBIO_USD;
            euros = pesosMexicanos * TIPO_CAMBIO_EUR;
            libras = pesosMexicanos * TIPO_CAMBIO_GBP;

            // Mostrar resultados
            Console.WriteLine("--- Resultados de la conversión ---");
            Console.WriteLine($"{pesosMexicanos} MXN = {dolares:F2} USD");
            Console.WriteLine($"{pesosMexicanos} MXN = {euros:F2} EUR");
            Console.WriteLine($"{pesosMexicanos} MXN = {libras:F2} GBP");

            Console.ReadLine();
        }
    }
}
`
  const code14csharp = `
using System;

namespace CalculadoraGeometrica
{
    class Program
    {
        // Constante PI para cálculos de círculo
        const double PI = 3.14159;

        static void Main(string[] args)
        {
            int opcion;

            Console.WriteLine("*** Calculadora Geométrica ***");
            Console.WriteLine("1. Calcular área y perímetro de un cuadrado");
            Console.WriteLine("2. Calcular área y perímetro de un círculo");
            Console.WriteLine("3. Calcular área y perímetro de un triángulo");
            Console.Write("Elija una opción (1-3): ");

            opcion = Convert.ToInt32(Console.ReadLine());

            switch(opcion)
            {
                case 1:
                    CalcularCuadrado();
                    break;
                case 2:
                    CalcularCirculo();
                    break;
                case 3:
                    CalcularTriangulo();
                    break;
                default:
                    Console.WriteLine("Opción no válida.");
                    break;
            }

            Console.ReadLine();
        }

        static void CalcularCuadrado()
        {
            // Variables locales para este método
            double lado;
            double area;
            double perimetro;

            Console.Write("Ingrese la longitud del lado del cuadrado: ");
            lado = Convert.ToDouble(Console.ReadLine());

            area = lado * lado;
            perimetro = 4 * lado;

            Console.WriteLine($"Área del cuadrado: {area:F2}");
            Console.WriteLine($"Perímetro del cuadrado: {perimetro:F2}");
        }

        static void CalcularCirculo()
        {
            double radio;
            double area;
            double perimetro;

            Console.Write("Ingrese el radio del círculo: ");
            radio = Convert.ToDouble(Console.ReadLine());

            area = PI * radio * radio;
            perimetro = 2 * PI * radio;

            Console.WriteLine($"Área del círculo: {area:F2}");
            Console.WriteLine($"Perímetro del círculo: {perimetro:F2}");
        }

        static void CalcularTriangulo()
        {
            double baseTriangulo;
            double altura;
            double lado1, lado2, lado3;
            double area;
            double perimetro;

            Console.Write("Ingrese la base del triángulo: ");
            baseTriangulo = Convert.ToDouble(Console.ReadLine());

            Console.Write("Ingrese la altura del triángulo: ");
            altura = Convert.ToDouble(Console.ReadLine());

            Console.Write("Ingrese la longitud del primer lado: ");
            lado1 = Convert.ToDouble(Console.ReadLine());

            Console.Write("Ingrese la longitud del segundo lado: ");
            lado2 = Convert.ToDouble(Console.ReadLine());

            Console.Write("Ingrese la longitud del tercer lado: ");
            lado3 = Convert.ToDouble(Console.ReadLine());

            area = (baseTriangulo * altura) / 2;
            perimetro = lado1 + lado2 + lado3;

            Console.WriteLine($"Área del triángulo: {area:F2}");
            Console.WriteLine($"Perímetro del triángulo: {perimetro:F2}");
        }
    }
}
`

  const mycodigo = async (code) => {

    const highlighter = await createHighlighter({
      themes: ['catppuccin-mocha'],
      langs: ['csharp'],
    })


    const html = highlighter.codeToHtml(code, { lang: 'csharp', theme: 'catppuccin-mocha' });

    return html

  }

</script>

{#snippet codigo(code)}
    <div style="font-size: 1 rem">
        {#await mycodigo(code)}
            <!-- promise is pending -->
            <p>waiting for the promise to resolve...</p>
        {:then value}
            <!-- promise was fulfilled or not a Promise -->
            <small>{@html value}</small>
        {:catch error}
            <!-- promise was rejected -->
            <p>Something went wrong: {error.message}</p>
        {/await}
    </div>
{/snippet}

# Clase 3: Definición de Campos y sus Tipos

## Objetivos de Aprendizaje
- Comprender qué son las variables y constantes
- Aprender las reglas para nombrar campos
- Conocer los diferentes tipos de campos en C#
- Aplicar los conceptos en programas prácticos

## 1. Variables y Constantes: Almacenando Información

### ¿Qué son las Variables?

Las variables son espacios en la memoria de la computadora que almacenan datos que pueden cambiar durante la ejecución del programa. Podemos imaginarlas como cajas etiquetadas donde guardamos información.

#### Características de las Variables:
- Su valor puede cambiar durante la ejecución del programa
- Deben declararse antes de usarse
- Tienen un nombre único (identificador)
- Poseen un tipo de dato que determina qué información pueden almacenar

### ¿Qué son las Constantes?

Las constantes son similares a las variables, pero su valor no puede cambiar una vez asignado.

#### Características de las Constantes:
- Su valor se establece una sola vez y no puede modificarse
- Se utilizan para valores fijos en nuestro programa
- Hacen el código más legible y mantenible
- También tienen un tipo de dato asociado

## 2. Reglas para Nombrar Variables y Constantes

Para que nuestro código sea claro y profesional, debemos seguir ciertas reglas al nombrar nuestros campos:

### Reglas Sintácticas (obligatorias):
- Deben comenzar con una letra o guion bajo (_)
- No pueden contener espacios
- No pueden ser palabras reservadas del lenguaje (como `if`, `for`, `class`, etc.)
- Pueden contener letras, números y guion bajo (_)
- Son sensibles a mayúsculas y minúsculas (`edad` y `Edad` serían variables diferentes)

### Buenas Prácticas (recomendadas):
- Usar nombres descriptivos que indiquen su propósito
- En C#, se usa camelCase para variables (primera letra minúscula, cada palabra adicional inicia con mayúscula)
- Para constantes, se suele usar MAYÚSCULAS_CON_GUION_BAJO
- Evitar abreviaciones poco claras
- No usar caracteres especiales o acentos

### Ejemplos:

{@render codigo(code1csharp)}


## 3. Declaración y Asignación de Campos

### Declaración de Variables

En C#, la sintaxis para declarar una variable es:

{@render codigo(code2csharp)}


### Asignación de Valores

Podemos asignar un valor a una variable usando el operador de asignación `=`:

{@render codigo(code3csharp)}

### Declaración y Asignación Combinada

También podemos declarar y asignar en una sola línea:

{@render codigo(code4csharp)}

### Declaración de Constantes

Para declarar una constante, usamos la palabra clave `const`:

{@render codigo(code5csharp)}

## 4. Ámbito de las Variables (Scope)

El ámbito o scope determina dónde es accesible una variable:

### Ámbito de Bloque
Variables declaradas dentro de un bloque `{ }` solo son accesibles dentro de ese bloque.

{@render codigo(code7csharp)}

### Ámbito de Método
Variables declaradas dentro de un método solo existen dentro de ese método.

{@render codigo(code8csharp)}

### Ámbito de Clase
Variables declaradas a nivel de clase son accesibles por todos los métodos de esa clase.

{@render codigo(code9csharp)}

## 5. Demostración Práctica

### Ejemplo: Calculadora de Edad

{@render codigo(code10csharp)}


## 6. Campos de Clase vs. Variables Locales

### Campos de Clase (Atributos)

Son variables declaradas a nivel de clase, fuera de cualquier método:

{@render codigo(code11csharp)}


### Variables Locales

Son variables declaradas dentro de un método o bloque:

{@render codigo(code12csharp)}


## 7. Actividad Práctica

### Ejercicio 1: Conversor de Divisas Mejorado

Mejora el conversor de divisas de la clase anterior, utilizando constantes para los tipos de cambio:


{@render codigo(code13csharp)}



### Ejercicio 2: Calculadora de Área y Perímetro

Crea un programa que calcule el área y perímetro de diferentes formas geométricas usando constantes y variables:

{@render codigo(code14csharp)}


## 8. Repaso y Conclusiones

En esta clase hemos aprendido:
- Qué son las variables y constantes y cómo se utilizan
- Las reglas para nombrar campos en C#
- El concepto de ámbito o scope
- La diferencia entre campos de clase y variables locales
- Cómo aplicar estos conceptos en programas reales

## Tarea

1. Crea un programa que calcule el costo total de una compra. El programa debe:
   - Solicitar el precio de un producto
   - Solicitar la cantidad de unidades
   - Calcular el subtotal (precio × cantidad)
   - Aplicar un impuesto (utiliza una constante para el porcentaje de impuesto)
   - Mostrar el desglose: subtotal,

<style>
	@reference "tailwindcss";

	div {
		@apply flex text-xs sm:text-xl w-10/12;

	}
</style>