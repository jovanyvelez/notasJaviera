<script>
  import { createHighlighter } from 'shiki';

  let code = $state('');

  const code1csharp = `
  using System;

    namespace MiPrimerPrograma
    {
        class Program
        {
            static void Main(string[] args)
            {
                Console.WriteLine("¡Hola Mundo!");
                
                // Espera a que el usuario presione Enter
                Console.ReadLine(); 
            }
        }
    }

`
const code2csharp = `
  using System;

  namespace SaludoPersonalizado
  {
      class Program
      {
          static void Main(string[] args)
          {
            Console.Write("¿Cómo te llamas? ");
            string nombre = Console.ReadLine();
            Console.WriteLine($"¡Hola {nombre}! Bienvenido/a al mundo de la programación.");
            Console.ReadLine();
          }
      }
  }

`

const code3csharp = `
  using System;

  namespace CalculadoraSimple
  {
      class Program
      {
          static void Main(string[] args)
          {
            Console.Write("Ingresa el primer número: ");
            int num1 = Convert.ToInt32(Console.ReadLine());

            Console.Write("Ingresa el segundo número: ");
            int num2 = Convert.ToInt32(Console.ReadLine());

            int suma = num1 + num2;
            Console.WriteLine($"La suma de {num1} y {num2} es: {suma}");
            Console.ReadLine();
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
    <div>
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


# Clase 1: Introducción a la Programación y Conceptos Básicos

## Objetivos de Aprendizaje
- Comprender qué es la programación y su importancia
- Familiarizarse con los conceptos básicos de algoritmia
- Conocer el entorno de desarrollo de C#
- Crear tu primer programa en C#

## 1. ¿Qué es la Programación?

La programación es el proceso de crear un conjunto de instrucciones que le dicen a una computadora cómo realizar una tarea. Estas instrucciones se escriben en un lenguaje que la computadora puede entender, llamado lenguaje de programación.

### ¿Por qué Aprender a Programar?

- **Resolución de problemas**: La programación te enseña a dividir problemas complejos en partes más pequeñas y manejables.
- **Creatividad**: Puedes crear aplicaciones, juegos, sitios web y más.
- **Demanda laboral**: Los programadores son muy solicitados en el mercado laboral actual.
- **Automatización**: Puedes automatizar tareas repetitivas para ahorrar tiempo.

### Lenguajes de Programación

Existen muchos lenguajes de programación, cada uno con sus propias características y usos:

- **C#**: Un lenguaje versátil desarrollado por Microsoft, que usaremos en este curso.
- **Python**: Conocido por su simplicidad y legibilidad.
- **JavaScript**: El lenguaje principal para desarrollo web.
- **Java**: Usado en aplicaciones empresariales y Android.

## 2. ¿Qué es un Algoritmo?

Un algoritmo es una secuencia de pasos bien definidos que resuelven un problema específico. En nuestra vida diaria, seguimos algoritmos sin darnos cuenta:

- Recetas de cocina
- Instrucciones para llegar a un lugar
- Pasos para resolver un problema matemático

### Características de un Buen Algoritmo

- **Precisión**: Cada paso debe estar claramente definido.
- **Determinismo**: Dado el mismo input, siempre produce el mismo output.
- **Finitud**: Debe terminar después de un número finito de pasos.
- **Efectividad**: Cada paso debe ser realizable.

## 3. Entorno de Desarrollo para C#

Para programar en C#, utilizaremos Visual Studio:

### Instalación de Visual Studio Community

1. Descarga Visual Studio Community desde el sitio oficial de Microsoft.
2. Durante la instalación, selecciona el paquete "Desarrollo de escritorio .NET".
3. Completa la instalación siguiendo las instrucciones.

### Componentes Principales de Visual Studio

- **Editor de código**: Donde escribirás tus programas.
- **Depurador**: Te ayuda a encontrar y corregir errores.
- **Explorador de soluciones**: Organiza los archivos de tu proyecto.
- **Consola**: Donde verás la salida de tus programas.

## 4. Tu Primer Programa en C#

Vamos a crear el clásico "¡Hola Mundo!" en C#:



{@render codigo(code1csharp)}

### Explicación del Código

- `using System;`: Importa la biblioteca System que contiene funcionalidades básicas.
- `namespace MiPrimerPrograma`: Un contenedor para organizar tu código.
- `class Program`: Una clase que contiene tu código.
- `static void Main(string[] args)`: El punto de entrada de tu programa.
- `Console.WriteLine("¡Hola Mundo!");`: Imprime texto en la consola.
- `Console.ReadLine();`: Espera a que el usuario presione Enter.

## 5. Actividad Práctica

### Ejercicio 1: Personaliza tu Hola Mundo
Modifica el programa para que solicite tu nombre y luego muestre un saludo personalizado.

<div  style="display: flex; align-items: center; width:10%">
{@render codigo(code2csharp)}
</div>
### Ejercicio 2: Calculadora Simple
Crea un programa que pida dos números al usuario y muestre su suma.



{@render codigo(code3csharp)}

## 6. Repaso y Conclusiones

En esta primera clase hemos aprendido:
- Qué es la programación y por qué es importante
- El concepto de algoritmo y sus características
- Cómo configurar nuestro entorno de desarrollo para C#
- Crear nuestros primeros programas en C#

## Tarea

1. Instala Visual Studio Community en tu computadora.
2. Crea un programa que solicite tu edad y muestre cuántos años tendrás en 10 años.
3. Investiga qué otros tipos de aplicaciones se pueden crear con C# (además de aplicaciones de consola).

## Recursos Adicionales

- [Documentación oficial de C#](https://docs.microsoft.com/es-es/dotnet/csharp/)
- [Tutorial interactivo de C#](https://dotnet.microsoft.com/learn/dotnet/hello-world-tutorial/intro)
- [Ejercicios de práctica](https://www.w3resource.com/csharp-exercises/)

---

¡Nos vemos en la próxima clase donde aprenderemos sobre los pasos para la solución de problemas!


<style>
	@reference "tailwindcss";

	div {
		@apply flex text-xs sm:text-xl w-10/12;

	}
</style>