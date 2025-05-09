<script>
  import { createHighlighter } from 'shiki';

  let code = $state('');

  const code1csharp = `
using System;

namespace CalculadoraPOO
{
    // Clase principal del programa
    class Program
    {
        static void Main(string[] args)
        {
            // Creamos una instancia de la calculadora
            Calculadora miCalculadora = new Calculadora();

            // Creamos una instancia del menú y le pasamos la calculadora
            MenuCalculadora menu = new MenuCalculadora(miCalculadora);

            // Ejecutamos el menú
            menu.Ejecutar();
        }
    }

    // Clase para la calculadora
    class Calculadora
    {
        // Métodos para realizar operaciones
        public double Sumar(double a, double b)
        {
            return a + b;
        }

        public double Restar(double a, double b)
        {
            return a - b;
        }

        public double Multiplicar(double a, double b)
        {
            return a * b;
        }

        public double Dividir(double a, double b)
        {
            if (b == 0)
                throw new DivideByZeroException("No se puede dividir por cero.");

            return a / b;
        }

        // Método para obtener el símbolo de la operación
        public string ObtenerSimboloOperacion(string operacion)
        {
            switch (operacion)
            {
                case "Suma": return "+";
                case "Resta": return "-";
                case "Multiplicación": return "*";
                case "División": return "/";
                default: return "";
            }
        }
    }

    // Clase para manejar el menú y la interacción con el usuario
    class MenuCalculadora
    {
        private Calculadora _calculadora;

        // Constructor que recibe una calculadora
        public MenuCalculadora(Calculadora calculadora)
        {
            _calculadora = calculadora;
        }

        // Método para ejecutar el menú
        public void Ejecutar()
        {
            bool continuar = true;

            Console.WriteLine("¡Bienvenido a la Calculadora POO!");

            while (continuar)
            {
                // Mostrar opciones del menú
                MostrarMenu();

                // Obtener opción del usuario
                string opcion = Console.ReadLine();

                if (opcion == "5")
                {
                    Console.WriteLine("¡Gracias por usar la calculadora!");
                    continuar = false;
                    continue;
                }

                try
                {
                    // Obtener números del usuario
                    double[] numeros = ObtenerNumeros();
                    double resultado = 0;
                    string nombreOperacion = "";

                    // Realizar operación según la opción
                    switch (opcion)
                    {
                        case "1":
                            resultado = _calculadora.Sumar(numeros[0], numeros[1]);
                            nombreOperacion = "Suma";
                            break;
                        case "2":
                            resultado = _calculadora.Restar(numeros[0], numeros[1]);
                            nombreOperacion = "Resta";
                            break;
                        case "3":
                            resultado = _calculadora.Multiplicar(numeros[0], numeros[1]);
                            nombreOperacion = "Multiplicación";
                            break;
                        case "4":
                            resultado = _calculadora.Dividir(numeros[0], numeros[1]);
                            nombreOperacion = "División";
                            break;
                        default:
                            Console.WriteLine("Opción no válida. Intenta de nuevo.");
                            continue;
                    }

                    // Mostrar el resultado
                    MostrarResultado(nombreOperacion, numeros[0], numeros[1], resultado);
                }
                catch (FormatException)
                {
                    Console.WriteLine("Error: Debes ingresar números válidos.");
                }
                catch (DivideByZeroException ex)
                {
                    Console.WriteLine($"Error: {ex.Message}");
                }
                catch (Exception ex)
                {
                    Console.WriteLine($"Error inesperado: {ex.Message}");
                }

                Console.WriteLine("Presiona cualquier tecla para continuar...");
                Console.ReadKey();
                Console.Clear();
            }
        }

        // Método para mostrar el menú
        private void MostrarMenu()
        {
            Console.WriteLine("==== MENÚ DE CALCULADORA ====");
            Console.WriteLine("1. Sumar");
            Console.WriteLine("2. Restar");
            Console.WriteLine("3. Multiplicar");
            Console.WriteLine("4. Dividir");
            Console.WriteLine("5. Salir");
            Console.Write("Selecciona una opción (1-5): ");
        }

        // Método para obtener los números del usuario
        private double[] ObtenerNumeros()
        {
            double[] numeros = new double[2];

            Console.Write("Ingresa el primer número: ");
            numeros[0] = Convert.ToDouble(Console.ReadLine());

            Console.Write("Ingresa el segundo número: ");
            numeros[1] = Convert.ToDouble(Console.ReadLine());

            return numeros;
        }

        // Método para mostrar el resultado
        private void MostrarResultado(string operacion, double num1, double num2, double resultado)
        {
            string simbolo = _calculadora.ObtenerSimboloOperacion(operacion);
            Console.WriteLine($"Resultado de la {operacion}: {num1} {simbolo} {num2} = {resultado}");
        }
    }
}
  `

    const code2csharp = `

    using System;

    namespace CalculadoraFuncional
    {
        class Program
        {
            static void Main(string[] args)
            {
                bool continuar = true;

                Console.WriteLine("¡Bienvenido a la Calculadora Funcional!");

                while (continuar)
                {
                    // Mostrar menú
                    MostrarMenu();

                    // Obtener la operación elegida
                    string opcion = Console.ReadLine();

                    if (opcion == "5")
                    {
                        Console.WriteLine("¡Gracias por usar la calculadora!");
                        continuar = false;
                        continue;
                    }

                    // Solicitar los números
                    Console.Write("Ingresa el primer número: ");
                    double num1 = Convert.ToDouble(Console.ReadLine());

                    Console.Write("Ingresa el segundo número: ");
                    double num2 = Convert.ToDouble(Console.ReadLine());

                    // Realizar la operación según la opción elegida
                    double resultado = 0;

                    switch (opcion)
                    {
                        case "1":
                            resultado = Sumar(num1, num2);
                            MostrarResultado("Suma", num1, num2, resultado);
                            break;
                        case "2":
                            resultado = Restar(num1, num2);
                            MostrarResultado("Resta", num1, num2, resultado);
                            break;
                        case "3":
                            resultado = Multiplicar(num1, num2);
                            MostrarResultado("Multiplicación", num1, num2, resultado);
                            break;
                        case "4":
                            if (num2 == 0)
                            {
                                Console.WriteLine("Error: No se puede dividir por cero.");
                            }
                            else
                            {
                                resultado = Dividir(num1, num2);
                                MostrarResultado("División", num1, num2, resultado);
                            }
                            break;
                        default:
                            Console.WriteLine("Opción no válida. Intenta de nuevo.");
                            break;
                    }

                    Console.WriteLine("Presiona cualquier tecla para continuar...");
                    Console.ReadKey();
                    Console.Clear();
                }
            }

            // Funciones para operaciones matemáticas
            static double Sumar(double a, double b)
            {
                return a + b;
            }

            static double Restar(double a, double b)
            {
                return a - b;
            }

            static double Multiplicar(double a, double b)
            {
                return a * b;
            }

            static double Dividir(double a, double b)
            {
                return a / b;
            }

            // Función para mostrar menú
            static void MostrarMenu()
            {
                Console.WriteLine("==== MENÚ DE CALCULADORA ====");
                Console.WriteLine("1. Sumar");
                Console.WriteLine("2. Restar");
                Console.WriteLine("3. Multiplicar");
                Console.WriteLine("4. Dividir");
                Console.WriteLine("5. Salir");
                Console.Write("Selecciona una opción (1-5): ");
            }

            // Función para mostrar resultado
            static void MostrarResultado(string operacion, double num1, double num2, double resultado)
            {
                Console.WriteLine($"Resultado de la {operacion}: {num1} {ObtenerSimboloOperacion(operacion)} {num2} = {resultado}");
            }

            // Función para obtener el símbolo de la operación
            static string ObtenerSimboloOperacion(string operacion)
            {
                switch (operacion)
                {
                    case "Suma": return "+";
                    case "Resta": return "-";
                    case "Multiplicación": return "*";
                    case "División": return "/";
                    default: return "";
                }
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


# Calculadora en C#: Enfoque Funcional vs Programación Orientada a Objetos

En este artículo, exploraremos dos enfoques diferentes para desarrollar una aplicación de calculadora en consola utilizando C#. Veremos cómo implementar la misma funcionalidad mediante programación con funciones y mediante programación orientada a objetos (POO). Este contenido está dirigido a estudiantes de programación entre 15 y 17 años que estén comenzando a entender los diferentes paradigmas de programación.

## Introducción

Una calculadora es un excelente proyecto para principiantes, ya que incluye varias operaciones básicas y proporciona una interfaz de usuario sencilla. En nuestro caso, desarrollaremos una calculadora de consola que puede:

- Sumar dos números
- Restar dos números
- Multiplicar dos números
- Dividir dos números
- Mostrar un menú interactivo
- Manejar errores básicos

Veamos cada enfoque de programación por separado.

## Enfoque 1: Calculadora usando Programación Funcional

En la programación funcional, organizamos nuestro código en funciones que realizan tareas específicas. Veamos cómo implementar nuestra calculadora usando este enfoque:

{@render codigo(code2csharp)}



### Explicación del enfoque funcional

En este enfoque, todas las operaciones están implementadas como funciones estáticas dentro de la clase `Program`:

1. **Función principal (`Main`)**: Controla el flujo del programa y la interacción con el usuario.
2. **Funciones de operaciones matemáticas**: `Sumar()`, `Restar()`, `Multiplicar()` y `Dividir()` que realizan los cálculos básicos.
3. **Funciones de UI**: `MostrarMenu()` y `MostrarResultado()` que gestionan la interfaz de usuario.

Este enfoque es directo y fácil de entender para principiantes. Cada función realiza una tarea específica y el flujo del programa sigue una estructura lineal. Las operaciones matemáticas están claramente definidas como funciones independientes que aceptan dos parámetros y devuelven un resultado.

## Enfoque 2: Calculadora usando Programación Orientada a Objetos (POO)

En la programación orientada a objetos, organizamos nuestro código en clases que representan entidades con propiedades y comportamientos. Veamos cómo implementar la misma calculadora usando este enfoque:

{@render codigo(code1csharp)}


### Explicación del enfoque orientado a objetos

En este enfoque, el código está organizado en tres clases diferentes, cada una con una responsabilidad específica:

1. **Clase `Program`**: Punto de entrada de la aplicación. Solo crea las instancias necesarias y pone en marcha el programa.
2. **Clase `Calculadora`**: Contiene toda la lógica de cálculo. Sus métodos realizan las operaciones matemáticas.
3. **Clase `MenuCalculadora`**: Gestiona la interfaz de usuario y la interacción con el usuario.

Características importantes de este enfoque:

- **Encapsulamiento**: Cada clase encapsula datos y comportamientos relacionados. Por ejemplo, `Calculadora` maneja solo los cálculos matemáticos.
- **Separación de responsabilidades**: La interfaz de usuario está separada de la lógica de negocio.
- **Manejo de excepciones**: Implementa un manejo de errores más robusto usando bloques try-catch.
- **Estado interno**: La clase `MenuCalculadora` mantiene una referencia a una instancia de `Calculadora` como un campo privado (`_calculadora`).
- **Métodos privados vs públicos**: Los métodos internos como `MostrarMenu()` son privados, mientras que la interfaz pública como `Ejecutar()` es pública.

## Comparación entre ambos enfoques

| Aspecto | Enfoque Funcional | Enfoque POO |
|---------|-------------------|-------------|
| **Organización** | Todo en una clase, separado en funciones | Múltiples clases con responsabilidades específicas |
| **Complejidad** | Simple, directo, fácil de entender | Más estructurado pero con mayor complejidad inicial |
| **Escalabilidad** | Limitada para proyectos grandes | Mejor para proyectos que crecerán con el tiempo |
| **Manejo de errores** | Básico, con verificaciones condicionales | Avanzado, usando excepciones |
| **Reutilización** | Funciones reutilizables | Clases completas reutilizables |
| **Abstracción** | Baja, todo está expuesto | Alta, detalles internos ocultos |

## Ventajas del enfoque funcional

1. **Simplicidad**: Es más fácil de entender para principiantes.
2. **Menos código**: Generalmente requiere menos líneas de código para implementaciones simples.
3. **Flujo lineal**: El flujo del programa es más directo y fácil de seguir.
4. **Menor curva de aprendizaje**: No requiere comprender conceptos avanzados de POO.

## Ventajas del enfoque orientado a objetos

1. **Modularidad**: El código está organizado en componentes lógicos (clases).
2. **Mantenibilidad**: Es más fácil mantener y actualizar el código a largo plazo.
3. **Extensibilidad**: Facilita añadir nuevas funcionalidades sin modificar el código existente.
4. **Encapsulamiento**: Oculta los detalles de implementación y expone solo lo necesario.
5. **Reutilización**: Las clases pueden reutilizarse en otros proyectos o partes del mismo.

## Conclusión

Ambos enfoques tienen sus ventajas y aplicaciones. El enfoque funcional es excelente para comenzar a programar y para aplicaciones simples, mientras que el enfoque orientado a objetos brinda beneficios significativos para aplicaciones más complejas y para el desarrollo profesional de software.

Para los estudiantes que están aprendiendo programación, es valioso comprender ambos paradigmas y saber cuándo aplicar cada uno según las necesidades del proyecto.

A medida que desarrolles más aplicaciones, podrás combinar aspectos de ambos enfoques para crear código más eficiente y mantenible.

## Ejercicios propuestos

1. Añade una operación de potencia a ambas versiones de la calculadora.
2. Implementa un historial de operaciones en la versión POO.
3. Modifica la calculadora funcional para que maneje excepciones.
4. Extiende la calculadora POO para que soporte operaciones con números complejos.


# 10 Ejercicios de Programación Funcional en C#

## Ejercicio 1: Conversor de Monedas
Crear una aplicación que permita convertir entre diferentes monedas.

**Funciones a desarrollar:**
- `MostrarMenuMonedas()`: Muestra las opciones de monedas disponibles
- `ConvertirDeDolarA(double cantidad, string monedaDestino)`: Convierte de dólares a otra moneda
- `ConvertirADolar(double cantidad, string monedaOrigen)`: Convierte de cualquier moneda a dólares
- `ObtenerTasaCambio(string moneda)`: Retorna la tasa de cambio de la moneda especificada
- `MostrarResultadoConversion(double cantidadOriginal, string monedaOrigen, double cantidadConvertida, string monedaDestino)`

## Ejercicio 2: Calculadora de Estadísticas
Desarrollar una aplicación que calcule estadísticas básicas de un conjunto de números.

**Funciones a desarrollar:**
- `CalcularPromedio(double[] numeros)`: Calcula el promedio de un arreglo de números
- `CalcularMediana(double[] numeros)`: Calcula la mediana de un arreglo de números
- `EncontrarMinimo(double[] numeros)`: Encuentra el valor mínimo del arreglo
- `EncontrarMaximo(double[] numeros)`: Encuentra el valor máximo del arreglo
- `CalcularDesviacionEstandar(double[] numeros)`: Calcula la desviación estándar
- `MostrarEstadisticas(double[] numeros)`: Muestra todas las estadísticas calculadas

## Ejercicio 3: Gestor de Tareas
Crear una aplicación para gestionar tareas pendientes.

**Funciones a desarrollar:**
- `MostrarMenuTareas()`: Muestra el menú de opciones para gestionar tareas
- `AgregarTarea(List<string> tareas)`: Agrega una nueva tarea a la lista
- `EliminarTarea(List<string> tareas, int indice)`: Elimina una tarea por su índice
- `MarcarComoCompletada(List<string> tareas, List<string> tareasCompletadas, int indice)`: Mueve una tarea a la lista de completadas
- `MostrarTareas(List<string> tareas, string titulo)`: Muestra la lista de tareas con un título

## Ejercicio 4: Calculadora de Geometría
Desarrollar una aplicación que calcule áreas y perímetros de diferentes figuras geométricas.

**Funciones a desarrollar:**
- `MostrarMenuFiguras()`: Muestra el menú de figuras disponibles
- `CalcularAreaCirculo(double radio)`: Calcula el área de un círculo
- `CalcularPerimetroCirculo(double radio)`: Calcula el perímetro de un círculo
- `CalcularAreaRectangulo(double base, double altura)`: Calcula el área de un rectángulo
- `CalcularPerimetroRectangulo(double base, double altura)`: Calcula el perímetro de un rectángulo
- `CalcularAreaTriangulo(double base, double altura)`: Calcula el área de un triángulo
- `CalcularPerimetroTriangulo(double lado1, double lado2, double lado3)`: Calcula el perímetro de un triángulo
- `MostrarResultadoGeometria(string figura, string calculo, double resultado)`

## Ejercicio 5: Conversor de Unidades
Crear una aplicación que convierta entre diferentes unidades de medida.

**Funciones a desarrollar:**
- `MostrarMenuUnidades()`: Muestra el menú de categorías de unidades
- `MostrarMenuLongitud()`: Muestra el menú de unidades de longitud
- `MostrarMenuPeso()`: Muestra el menú de unidades de peso
- `MostrarMenuVolumen()`: Muestra el menú de unidades de volumen
- `ConvertirLongitud(double valor, string unidadOrigen, string unidadDestino)`: Convierte entre unidades de longitud
- `ConvertirPeso(double valor, string unidadOrigen, string unidadDestino)`: Convierte entre unidades de peso
- `ConvertirVolumen(double valor, string unidadOrigen, string unidadDestino)`: Convierte entre unidades de volumen
- `MostrarResultadoConversion(double valorOriginal, string unidadOrigen, double valorConvertido, string unidadDestino)`

## Ejercicio 6: Analizador de Texto
Desarrollar una aplicación que analice un texto ingresado por el usuario.

**Funciones a desarrollar:**
- `ContarPalabras(string texto)`: Cuenta el número de palabras en el texto
- `ContarCaracteres(string texto, bool incluirEspacios)`: Cuenta el número de caracteres
- `ContarVocales(string texto)`: Cuenta el número de vocales en el texto
- `ContarConsonantes(string texto)`: Cuenta el número de consonantes en el texto
- `EncontrarPalabraMasLarga(string texto)`: Encuentra la palabra más larga del texto
- `MostrarEstadisticasTexto(string texto)`: Muestra todas las estadísticas calculadas del texto

## Ejercicio 7: Generador de Contraseñas
Crear una aplicación que genere contraseñas aleatorias según criterios del usuario.

**Funciones a desarrollar:**
- `MostrarMenuOpciones()`: Muestra opciones para la generación de contraseñas
- `GenerarContraseña(int longitud, bool incluirMayusculas, bool incluirNumeros, bool incluirEspeciales)`: Genera una contraseña según los parámetros
- `EvaluarSeguridadContraseña(string contraseña)`: Evalúa la seguridad de una contraseña
- `MostrarContraseñaGenerada(string contraseña, string nivelSeguridad)`

## Ejercicio 8: Calculadora de Fechas
Desarrollar una aplicación que realice operaciones con fechas.

**Funciones a desarrollar:**
- `MostrarMenuFechas()`: Muestra el menú de operaciones con fechas
- `CalcularDiferenciaEntreFechas(DateTime fecha1, DateTime fecha2)`: Calcula días entre dos fechas
- `SumarDiasAFecha(DateTime fecha, int dias)`: Suma un número de días a una fecha
- `RestarDiasAFecha(DateTime fecha, int dias)`: Resta un número de días a una fecha
- `ObtenerDiaSemana(DateTime fecha)`: Obtiene el día de la semana de una fecha
- `VerificarAñoBisiesto(int año)`: Verifica si un año es bisiesto
- `MostrarResultadoOperacionFecha(string operacion, string resultado)`

## Ejercicio 9: Juego de Adivinanza de Números
Crear un juego donde el usuario debe adivinar un número generado aleatoriamente.

**Funciones a desarrollar:**
- `GenerarNumeroAleatorio(int min, int max)`: Genera un número aleatorio en un rango
- `EvaluarIntento(int numeroSecreto, int intento)`: Evalúa si el intento es correcto, mayor o menor
- `CalcularPuntaje(int intentosRealizados, int intentosMaximos)`: Calcula el puntaje según los intentos
- `MostrarPista(int numeroSecreto, int intento)`: Muestra una pista según la distancia al número secreto
- `MostrarResultadoJuego(bool adivinado, int numeroSecreto, int intentos, int puntaje)`

## Ejercicio 10: Simulador de Préstamos
Desarrollar una aplicación que calcule cuotas y total a pagar de un préstamo.

**Funciones a desarrollar:**
- `CalcularCuotaMensual(double montoPrestamo, double tasaInteresAnual, int plazoMeses)`: Calcula la cuota mensual
- `CalcularTotalAPagar(double cuotaMensual, int plazoMeses)`: Calcula el monto total a pagar
- `CalcularTotalIntereses(double totalAPagar, double montoPrestamo)`: Calcula el total de intereses
- `GenerarTablaPagos(double montoPrestamo, double tasaInteresAnual, int plazoMeses)`: Genera una tabla de amortización
- `MostrarResumenPrestamo(double montoPrestamo, double tasaInteresAnual, int plazoMeses, double cuotaMensual, double totalAPagar, double totalIntereses)`


<style>
	@reference "tailwindcss";

	div {
		@apply flex text-xs sm:text-xl;

	}
</style>