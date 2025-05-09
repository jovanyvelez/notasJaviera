<script>
  import { createHighlighter } from 'shiki';

  let code = $state('');

  const code1csharp = `
    using System;

    namespace CalculadoraPromedio
    {
        class Program
        {
            static void Main(string[] args)
            {
                // Solicitar las notas al usuario
                Console.Write("Ingrese la primera nota: ");
                double nota1 = Convert.ToDouble(Console.ReadLine());

                Console.Write("Ingrese la segunda nota: ");
                double nota2 = Convert.ToDouble(Console.ReadLine());

                Console.Write("Ingrese la tercera nota: ");
                double nota3 = Convert.ToDouble(Console.ReadLine());

                // Calcular el promedio
                double promedio = (nota1 + nota2 + nota3) / 3;

                // Mostrar el resultado
                Console.WriteLine($"El promedio de las notas es: {promedio:F2}");
                Console.ReadLine();
            }
        }
    }

`
const code2csharp = `
  using System;

  namespace CalculadoraPromedioMejorada
  {
    class Program
    {
      static void Main(string[] args)
        {
          try
            {
              // Solicitar las notas al usuario
               Console.Write("Ingrese la primera nota: ");
               double nota1 = Convert.ToDouble(Console.ReadLine());

              Console.Write("Ingrese la segunda nota: ");
              double nota2 = Convert.ToDouble(Console.ReadLine());

              Console.Write("Ingrese la tercera nota: ");
              double nota3 = Convert.ToDouble(Console.ReadLine());

              // Calcular el promedio
              double promedio = (nota1 + nota2 + nota3) / 3;

              // Mostrar el resultado
              Console.WriteLine($"El promedio de las notas es: {promedio:F2}");
            }
            catch (FormatException)
            {
              Console.WriteLine("Error: Por favor ingrese solo valores numéricos.");
            }
            catch (Exception ex)
            {
              Console.WriteLine($"Error inesperado: {ex.Message}");
            }

            Console.ReadLine();
          }
      }
  }

`

const code3csharp = `
  using System;

  namespace ConversorTemperatura
  {
      class Program
      {
          static void Main(string[] args)
          {
              try
              {
                  // Solicitar la temperatura en Celsius
                  Console.Write("Ingrese la temperatura en grados Celsius: ");
                  double celsius = Convert.ToDouble(Console.ReadLine());

                  // Convertir a Fahrenheit
                  double fahrenheit = celsius * 9 / 5 + 32;

                  // Mostrar el resultado
                  Console.WriteLine($"{celsius}°C equivale a {fahrenheit:F1}°F");
              }
              catch (Exception ex)
              {
                  Console.WriteLine($"Error: {ex.Message}");
              }

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

# Clase 2: Pasos para la Solución de un Problema

## Objetivos de Aprendizaje
- Comprender el proceso de resolución de problemas en programación
- Aprender a analizar un problema antes de codificarlo
- Desarrollar algoritmos usando pseudocódigo y diagramas de flujo
- Implementar soluciones en C#

## 1. El Proceso de Resolución de Problemas

En programación, resolver un problema requiere un enfoque estructurado. Estos son los pasos fundamentales:

### Pasos para Resolver un Problema
1. **Definir el problema**: Entender claramente qué necesitamos resolver.
2. **Analizar el problema**: Identificar entradas, salidas y procesos necesarios.
3. **Diseñar una solución**: Crear un algoritmo usando pseudocódigo o diagramas de flujo.
4. **Implementar la solución**: Convertir el algoritmo en código (C# en nuestro caso).
5. **Probar la solución**: Verificar que funciona correctamente con diferentes casos.
6. **Depurar y optimizar**: Corregir errores y mejorar el rendimiento.

## 2. Definición y Análisis del Problema

### Ejemplo: Calcular el Promedio de Tres Notas

Vamos a aplicar los pasos para resolver este problema:

#### Definición
Necesitamos crear un programa que calcule el promedio de tres notas escolares.

#### Análisis
- **Entradas**: Tres notas (números decimales).
- **Proceso**: Sumar las tres notas y dividir el resultado entre 3.
- **Salidas**: El promedio calculado.

## 3. Diseño de la Solución

### Pseudocódigo

El pseudocódigo es una forma de escribir algoritmos usando lenguaje natural estructurado:

```
INICIO
    Escribir "Ingrese la primera nota:"
    Leer nota1

    Escribir "Ingrese la segunda nota:"
    Leer nota2

    Escribir "Ingrese la tercera nota:"
    Leer nota3

    promedio = (nota1 + nota2 + nota3) / 3

    Escribir "El promedio de las notas es:", promedio
FIN
```

### Diagrama de Flujo

Los diagramas de flujo representan visualmente los pasos de un algoritmo:

```
[Inicio] → [Ingrese la primera nota] → [Leer nota1] → [Ingrese la segunda nota] →
[Leer nota2] → [Ingrese la tercera nota] → [Leer nota3] →
[Calcular promedio = (nota1 + nota2 + nota3) / 3] → [Mostrar promedio] → [Fin]
```

## 4. Implementación en C#

Ahora convertimos nuestro algoritmo en código C#:

{@render codigo(code1csharp)}
### Explicación del Código
- `Convert.ToDouble()`: Convierte la entrada del usuario (texto) a un número decimal.
- `{promedio:F2}`: Formatea el promedio para mostrar solo 2 decimales.

## 5. Prueba y Depuración

Para probar nuestro programa:
1. Prueba con valores normales: 7.5, 8.0, 6.5
2. Prueba con valores extremos: 0, 0, 0 o 10, 10, 10
3. Prueba con valores inválidos: ¿Qué pasa si el usuario ingresa texto en lugar de números?

### Manejo de Errores

Mejoremos nuestro código para manejar entradas incorrectas:

{@render codigo(code2csharp)}
## 6. Otro Ejemplo: Conversor de Temperatura

Vamos a aplicar el proceso completo para resolver otro problema: convertir de Celsius a Fahrenheit.

### Definición y Análisis
- **Problema**: Convertir una temperatura de Celsius a Fahrenheit.
- **Entrada**: Temperatura en grados Celsius (número decimal).
- **Proceso**: Aplicar la fórmula F = C * 9/5 + 32
- **Salida**: Temperatura en grados Fahrenheit.

### Pseudocódigo
```
INICIO
    Escribir "Ingrese la temperatura en grados Celsius:"
    Leer celsius

    fahrenheit = celsius * 9/5 + 32

    Escribir "La temperatura en grados Fahrenheit es:", fahrenheit
FIN
```

### Implementación en C#

{@render codigo(code3csharp)}
## 7. Actividad Práctica

### Ejercicio 1: Calculadora de Área de un Rectángulo

Aplica el proceso de resolución de problemas para crear un programa que calcule el área de un rectángulo.

1. **Define el problema**: Calcular el área de un rectángulo dada su base y altura.
2. **Analiza**: Entradas (base, altura), Proceso (multiplicar), Salida (área).
3. **Diseña**: Crea un pseudocódigo o diagrama de flujo.
4. **Implementa**: Escribe el código en C#.
5. **Prueba**: Verifica con diferentes valores.

### Ejercicio 2: Conversor de Moneda

Crea un programa que convierta una cantidad de pesos mexicanos a dólares estadounidenses.

1. **Define el problema**: Convertir pesos a dólares usando una tasa de cambio.
2. **Analiza**: Entradas (cantidad en pesos, tasa de cambio), Proceso (división), Salida (cantidad en dólares).
3. **Diseña**: Crea un pseudocódigo o diagrama de flujo.
4. **Implementa**: Escribe el código en C#.
5. **Prueba**: Verifica con diferentes cantidades y tasas.

## 8. Repaso y Conclusiones

En esta clase hemos aprendido:
- Los pasos fundamentales para resolver problemas en programación
- Cómo analizar un problema identificando entradas, procesos y salidas
- Diseñar soluciones usando pseudocódigo
- Implementar y probar soluciones en C#
- Manejar errores básicos en nuestros programas

## Tarea

1. Desarrolla un programa que calcule el perímetro y área de un círculo dado su radio.
2. Escribe el pseudocódigo, haz un diagrama de flujo e implementa en C# un programa que convierta una cantidad de segundos a formato horas:minutos:segundos.
3. Crea un programa que calcule el índice de masa corporal (IMC) de una persona a partir de su peso en kg y su altura en metros.

## Recursos Adicionales

- [Técnicas de resolución de problemas en programación](https://www.freecodecamp.org/news/how-to-think-like-a-programmer-lessons-in-problem-solving-d1d8bf1de7d2/)
- [Herramientas para crear diagramas de flujo](https://app.diagrams.net/)
- [Ejercicios de algoritmos para practicar](https://www.hackerrank.com/domains/algorithms)

---

¡En la próxima clase aprenderemos sobre tipos de datos e información en C#!


<style>
	@reference "tailwindcss";

	div {
		@apply flex justify-around text-xs sm:text-xl w-10/12;

	}
</style>