# Clase 1: ¡Bienvenidos al Universo del Código, Futuros Tesos!

## ¡Qué onda, parceros y parceras de Medellín! 🚀

¡Bienvenidos a este viaje alucinante al mundo de la programación! Si alguna vez te has preguntado cómo funcionan tus videojuegos favoritos, las apps que usas en el celular o las páginas web que visitas, ¡estás en el lugar correcto! Aquí vamos a aprender a darle instrucciones a la computadora para que haga cosas increíbles. Y lo mejor, ¡lo haremos en C# (se pronuncia "Si Sharp"), un lenguaje súper poderoso!

### Objetivos de la Clase:

*   Entender qué es un algoritmo y por qué son la base de todo.
*   Conocer los pasos esenciales para resolver un problema como un pro.
*   Tener un primer contacto con C# y nuestro entorno de desarrollo.
*   ¡Escribir nuestro primer programa: el legendario "Hola Mundo"!

### Duración Estimada:

3 horas (con un merecido descanso pa' estirar las piernas y tomar alguito).

### Materiales Necesarios:

*   Tu compu con Windows (o la posibilidad de usar una máquina virtual).
*   Visual Studio Community (¡es gratis!) instalado. Si no lo tienes, ¡fresco!, parte de la clase será guiarte. (O Visual Studio Code con las extensiones de C#).
*   ¡Muchas ganas de aprender y curiosidad!

---

## Desarrollo de la Clase:

### 1. ¿Qué Rayos es Programar? (Tiempo Estimado: 30 min)

*   **Charla introductoria:** Pensemos en la programación como darle una receta a la computadora. Si la receta está bien escrita, ¡el plato (programa) sale delicioso!
*   **¿Qué es un algoritmo?**
    *   Definición sencilla: Una secuencia de pasos lógicos y ordenados para resolver un problema o alcanzar un objetivo. ¡Como los pasos para prepararte un buen chocolate con quesito!
    *   Ejemplos cotidianos:
        1.  Receta de cocina (arepas, sancocho).
        2.  Instrucciones para llegar de tu casa al colegio.
        3.  Cómo ganar una partida de tu videojuego favorito.
*   **¿Y un programa?** Es un algoritmo escrito en un lenguaje que la computadora entiende. Nosotros usaremos C#.
*   **¿Por qué C#?** Es un lenguaje moderno, potente, usado en muchas empresas (¡oportunidades laborales, ojo!), y sirve para hacer desde apps de escritorio, web, hasta videojuegos con Unity. Empezaremos con "aplicaciones de consola", que son como el chat básico para hablarle al PC.

### 2. ¡A Resolver Problemas se Dijo! (Tiempo Estimado: 45 min)

No importa si es un problema matemático o cómo organizar la fiesta del barrio, ¡hay pasos clave!

*   **Paso 1: Entender el Problema.**
    *   ¿Qué me están pidiendo? ¿Cuál es el objetivo?
    *   ¿Qué información necesito (entradas)?
    *   ¿Qué resultado debo entregar (salidas)?
    *   Ejemplo: "Necesito un programa que salude al usuario por su nombre".
        *   Entrada: El nombre del usuario.
        *   Salida: Un saludo personalizado.
*   **Paso 2: Diseñar la Solución (El Algoritmo).**
    *   Pensar los pasos lógicos. Se puede usar "pseudocódigo" (escribir los pasos en español, como si le explicaras a un amigo) o diagramas de flujo (lo veremos más adelante).
    *   Ejemplo (pseudocódigo para el saludo):
        1.  INICIO
        2.  Preguntar al usuario: "¿Cómo te llamas?"
        3.  Leer el nombre que el usuario escribe.
        4.  Mostrar en pantalla: "¡Hola, [nombre que escribió el usuario]! ¡Qué chévere tenerte aquí!"
        5.  FIN
*   **Paso 3: Escribir el Código (¡Programar!).**
    *   Traducir nuestro diseño (algoritmo) al lenguaje de programación (C# en nuestro caso).
*   **Paso 4: Probar y Corregir Errores (¡Testear y Debuggear!).**
    *   ¿Funciona como esperaba? ¿Hay errores (bugs)? ¡A corregirlos! Es normal equivocarse, ¡así se aprende!
*   **Paso 5: Documentar y Mantener (Para los pros).**
    *   Explicar qué hace nuestro código (comentarios) y mejorarlo con el tiempo.

### 3. Nuestro Laboratorio: Visual Studio (Tiempo Estimado: 45 min)

*   Breve tour por Visual Studio (o VS Code, según lo que usen).
    *   Cómo crear un nuevo proyecto de "Aplicación de Consola (.NET)".
    *   Ventanas principales: Explorador de soluciones, Editor de código, Ventana de salida/Errores.
    *   El archivo `Program.cs`: ¡Aquí vivirá nuestro código!
*   **¡Manos a la obra!** Crear el primer proyecto.

*(Descanso de 15 minutos - ¡A estirar esas piernas y tomar aguita!)*

### 4. ¡El Primer Grito al Mundo Digital!: `Hola Mundo` en C# (Tiempo Estimado: 45 min)

*   Vamos a analizar la estructura básica de un programa en C#:
    ```csharp
    // Esto es un comentario, la compu lo ignora, ¡pero nos ayuda a entender!
    using System; // Le decimos a C# que vamos a usar cosas de la "biblioteca" System

    namespace MiPrimerPrograma // Es como una carpeta para organizar nuestro código
    {
        class Program // Es el plano principal de nuestra aplicación
        {
            static void Main(string[] args) // ¡Este es el punto de partida! Aquí empieza todo.
            {
                // ¡Aquí va la magia!
                Console.WriteLine("¡Hola Mundo desde Medellín, pues!"); // Muestra un mensaje en la consola
                Console.WriteLine("¡Esto de programar está muy bacano!");
            }
        }
    }
    ```
*   **Explicación breve de cada parte:**
    *   `using System;`: Como cuando necesitas herramientas de una caja, `System` tiene herramientas básicas.
    *   `namespace MiPrimerPrograma`: El nombre de nuestro proyecto, ayuda a organizar.
    *   `class Program`: Por ahora, piensa que todo programa en C# vive dentro de una "clase".
    *   `static void Main(string[] args)`: El método **Principal**. Es la puerta de entrada. La computadora busca `Main` para empezar a ejecutar.
    *   `Console.WriteLine("TEXTO");`: ¡La instrucción estrella de hoy! Escribe lo que pongas entre comillas en la pantalla (la consola).
*   **¡A correrlo!** Apretar el botón de "Play" (Iniciar) en Visual Studio y ver la magia.
*   **Pequeño Reto:** Modifica el programa para que diga tu nombre y algo que te guste de Medellín.

### 5. Resumen y Siguientes Pasos (Tiempo Estimado: 15 min)

*   Recapitulación: ¿Qué es un algoritmo? ¿Pasos para resolver problemas? ¿Nuestro primer programa?
*   Preguntas y respuestas. ¡No hay preguntas bobas!
*   Avance de la próxima clase: ¡Vamos a aprender sobre variables y tipos de datos para que nuestros programas sean más inteligentes!

---
### Desafío Extra (¡Pa' los que quieran más candela!):

1.  Haz que el programa `Hola Mundo` imprima tres líneas diferentes:
    *   Tu nombre.
    *   El barrio donde vives.
    *   Tu comida paisa favorita.
2.  Investiga qué significa `static` y `void` en la línea `static void Main(string[] args)`. ¡No te preocupes si no lo entiendes del todo aún, es solo para los curiosos!

---