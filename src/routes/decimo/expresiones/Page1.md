<script>
  import { createHighlighter } from 'shiki';
  
  let code = $state('');

  const code1csharp = `
  // Ejemplo rápido en C#
  // resultado1 será 13
  resultado1 = 3 + 5 * 2; 
  /* 
    resultado2 será 16
    (¡Los paréntesis mandan!)
  */
  resultado2 = (3 + 5) * 2; 
  Console.WriteLine(resultado1);
  Console.WriteLine(resultado2);
  `
  const code2csharp = `
  int edadJuan = 16;
  bool esMayorEdad = edadJuan >= 18; // esMayorEdad será False

  int puntajeJuego = 1500;
  bool ganoPremio = puntajeJuego > 1000; // ganoPremio será True

  Console.WriteLine(esMayorEdad);
  Console.WriteLine(ganoPremio);
`
  const code3csharp = `
using System;

class Program
{
    static void Main(string[] args)
    {
        // Datos del estudiante
        double nota1 = 4.0;
        double nota2 = 2.5;
        double nota_examen_final = 3.5;
        int asistencia_porcentaje = 90;

        // Cálculos intermedios (Aritmética)
        double promedio_notas = (nota1 + nota2) / 2; // (4.0 + 2.5) / 2 = 3.25

        // Evaluaciones (Relacionales)
        bool aprobo_promedio = promedio_notas >= 3.0;        // 3.25 >= 3.0 -> True
        bool cumplio_asistencia = asistencia_porcentaje >= 80; // 90 >= 80 -> True
        bool perdio_final = nota_examen_final < 2.0;           // 3.5 < 2.0 -> False

        // Decisión final (Booleana)
        bool aprobo_materia = aprobo_promedio && cumplio_asistencia && (!perdio_final);
        //                     True         && True               && (NOT False)
        //                     True         && True               && True
        //                     True

        Console.WriteLine("¿Aprobó la materia? " + aprobo_materia); // Imprime True
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
            {@html value}
        {:catch error}
            <!-- promise was rejected -->
            <p>Something went wrong: {error.message}</p>
        {/await}
    </div>
{/snippet}



# ¡Qué Hubo, Parceras y Parceros! Desbloqueando el Poder de las Expresiones 🚀


¡Hola, futuros cracks de la tecnología de Medallo! 👋 ¿Alguna vez se han preguntado cómo un computador, un celular o hasta un videojuego "sabe" qué hacer? ¿Cómo decide si ganaste la partida, si puedes entrar a una red social o simplemente cómo suma dos números?

La respuesta está en algo fundamental que llamamos **expresiones**. Son como las frases básicas que las máquinas entienden para calcular, comparar y tomar decisiones. ¡Son los ladrillos con los que se construye casi todo en el mundo digital!

En este blog (¡y quizás en un par de sesiones bien bacanas!) vamos a desglosar tres tipos clave de expresiones. ¡Así que preparen el tinto, pónganse cómodos y activemos esas neuronas!

---


## Sesión 1 / Parte 1: Expresiones Aritméticas (¡A Calcular se Dijo!) 🧮

Empecemos por lo que seguro ya conocen del colegio, ¡pero con el toque tech! Las expresiones aritméticas son simplemente... ¡cálculos! Usan números y operadores para obtener un resultado numérico.

**¿Qué son?** Combinaciones de:
*   **Números (Operandos):** `5`, `10.5`, `-3`, etc.
*   **Operadores Aritméticos:** Los signos que nos dicen qué hacer.

**Los Operadores Más Comunes:**

| Operador |   Símbolo | Ejemplo          |Resultado | ¡Ojo Aquí! (Explicación)                                                |
| :------- |   :------ | :--------------- | --------:|  :-----------------------------------------------------------           |
| Suma     | `  +`     | `15 + 5`         |`20`      | --¡La de toda la vida!                                                    |
| Resta    | `  -`     | `10 - 7`         |`3`       | --Fácil, ¿no?                                                             |
| Multipli | `  *`     | `6 * 4`          |`24`      | --Usamos el asterisco `*`, no la 'x'.                                     |
| División | `  /`     | `20 / 4`         |`5.0`     | --¡Pilas! A menudo da decimales (números flotantes).                      |
| Módulo   | `  %`     | `10 % 3`         |`1`       | --El **residuo** de la división. 10 dividido 3 es 3 y sobra **1**. ¡Útil! |
| Potencia | `  **`    | `2 ** 3`         |`8`       | --Elevar un número a otro (2 * 2 * 2). En algunos lenguajes es `^`. |

**¡El Orden Importa! La Ley del PEMDAS (o PAPOMUDAS)**

Cuando tienes varias operaciones en una misma expresión, no puedes simplemente resolverlas de izquierda a derecha. Hay un orden sagrado que los computadores (¡y las matemáticas!) siguen. Seguro lo han escuchado como PEMDAS o a veces PAPOMUDAS en español. ¡Vamos a desglosarlo!

*   **P** - **Paréntesis** `()`: Primero resuelves lo que esté DENTRO de los paréntesis. Si hay paréntesis anidados (uno dentro de otro), empiezas por el más interno.
*   **E** - **Exponentes** `**` (o Potencias): Después de los paréntesis, calculas las potencias.
*   **M/D** - **Multiplicación** `*` y **División** `/` (¡y Módulo `%`!): Estas tienen la *misma prioridad*. Se resuelven de **izquierda a derecha** según aparezcan.
*   **A/S** - **Adición** `+` (Suma) y **Sustracción** `-` (Resta): Estas son las últimas y también tienen la *misma prioridad*. Se resuelven de **izquierda a derecha** según aparezcan.

**Veamos el ejemplo anterior:** `3 + 5 * 2`

1.  ¿Hay Paréntesis? No.
2.  ¿Hay Exponentes? No.
3.  ¿Hay Multiplicación/División? Sí, `5 * 2`. La resolvemos: `5 * 2 = 10`. La expresión ahora es `3 + 10`.
4.  ¿Hay Adición/Sustracción? Sí, `3 + 10`. La resolvemos: `3 + 10 = 13`.
5.  Resultado final: `13`. ¡Correcto! ✅

**Otro ejemplo:** `(10 + 2) / 3 * 2 ** 2`

1.  **Paréntesis:** `(10 + 2) = 12`. La expresión queda: `12 / 3 * 2 ** 2`.
2.  **Exponentes:** `2 ** 2 = 4`. La expresión queda: `12 / 3 * 4`.
3.  **Multiplicación/División (de izquierda a derecha):**
    *   Primero `12 / 3 = 4`. La expresión queda: `4 * 4`.
    *   Luego `4 * 4 = 16`.
4.  **Adición/Sustracción:** No hay.
5.  Resultado final: `16`.


{@render codigo(code1csharp)}


---

## Sesión 1 / Parte 2: Expresiones Lógicas Relacionales (¿Verdadero o Falso, Parcero?) 🤔✅❌

Ahora la cosa se pone interesante. Estas expresiones no calculan un número, ¡sino que **comparan** valores! El resultado SIEMPRE es uno de dos: **Verdadero** (`True`) o **Falso** (`False`).

**¿Qué son?** Comparaciones entre valores usando operadores relacionales.

**Los Operadores Relacionales:**

| Operador                 | Símbolo | Ejemplo                 | Resultado | ¡Ojo Aquí! (Explicación)                                  |
| :----------------------- | :------ | :---------------------- | :-------- | :-------------------------------------------------------- |
| Mayor que                | `>`     | `10 > 5`                | `True`    | ¿Es 10 más grande que 5? ¡Sí!                           |
| Menor que                | `<`     | `7 < 4`                 | `False`   | ¿Es 7 más pequeño que 4? ¡Nop!                          |
| Mayor o igual que        | `>=`    | `8 >= 8`                | `True`    | ¿Es 8 más grande o igual a 8? ¡Sí, es igual!            |
| Menor o igual que        | `<=`    | `6 <= 9`                | `True`    | ¿Es 6 más pequeño o igual a 9? ¡Sí!                     |
| Igual a                  | `==`    | `5 == 5` <br> `5 == '5'` | `True` <br> `False` | **¡CRUCIAL!** Doble igual `==` para comparar. Uno `=` es para asignar valor. ¡Pilas con comparar tipos distintos! |
| Diferente de / No igual | `!=`    | `10 != 5` <br> `4 != 4`  | `True` <br> `False` | ¿Son diferentes?                                          |

**¿Para qué sirven?** ¡Para tomar decisiones!
*   ¿`edad >= 18`? (¿Es mayor de edad?) -> `True` / `False`
*   ¿`nota_final >= 3.0`? (¿Pasó la materia?) -> `True` / `False`
*   ¿`contrasena_ingresada == contrasena_guardada`? (¿La clave es correcta?) -> `True` / `False`

{@render codigo(code2csharp)}

**En resumen:** Las expresiones relacionales comparan cosas y nos dicen si la comparación es `Verdadera` o `Falsa`. ¡Son la base de las decisiones en la programación!

---

**(Aquí podría terminar la Sesión 1 si decidimos dividir)**

---

## Sesión 2 / Parte 1: Expresiones Lógicas Booleanas (¡Conectando Ideas!) 🧠💡

¡Seguimos, parceros! Ya sabemos calcular (`Aritméticas`) y comparar (`Relacionales`). Ahora, ¿cómo conectamos varias comparaciones? Para eso usamos las expresiones **Booleanas**, que trabajan con los valores `True` y `False`.

**¿Qué son?** Combinaciones de valores `True`/`False` (o expresiones que resulten en `True`/`False`) usando operadores lógicos.

**Los Operadores Lógicos Principales:**

1.  **`AND` (y lógico):**
    *   Símbolos comunes: `AND`, `&&`
    *   **Resultado:** Es `True` **SOLAMENTE SI** *ambas* partes que conecta son `True`. Si una (o las dos) es `False`, el resultado es `False`.
    *   **Ejemplo:** Para ir a cine necesitas `tener_plata == True AND tener_tiempo == True`. Si falta una, no vas (`False`).
    *   **Tabla de Verdad (simplificada):**
        *   `True AND True` -> `True`
        *   `True AND False` -> `False`
        *   `False AND True` -> `False`
        *   `False AND False` -> `False`

2.  **`OR` (o lógico):**
    *   Símbolos comunes: `OR`, `||`
    *   **Resultado:** Es `True` **SI AL MENOS UNA** de las partes que conecta es `True`. Solo es `False` si *ambas* partes son `False`.
    *   **Ejemplo:** Puedes salir si `es_sabado == True OR es_festivo == True`. Con que una sea `True`, sales (`True`).
    *   **Tabla de Verdad (simplificada):**
        *   `True OR True` -> `True`
        *   `True OR False` -> `True`
        *   `False OR True` -> `True`
        *   `False OR False` -> `False`

3.  **`NOT` (no lógico):**
    *   Símbolos comunes: `NOT`, `!`
    *   **Resultado:** Invierte el valor de verdad. Lo que era `True` se vuelve `False`, y lo que era `False` se vuelve `True`.
    *   **Ejemplo:** Si `esta_lloviendo == True`, entonces `NOT esta_lloviendo` es `False`.
    *   **Tabla de Verdad:**
        *   `NOT True` -> `False`
        *   `NOT False` -> `True`

**Combinando con Relacionales:** ¡Aquí se pone poderoso!


**En resumen:** Las expresiones booleanas usan `AND`, `OR`, `NOT` para combinar o invertir valores `True`/`False`, permitiendo crear condiciones mucho más complejas y específicas.

---

## Sesión 2 / Parte 2: ¡Juntando Todo el Combo! (Combinando Expresiones) 🧩

¡Ahora sí, la mezcla final! Podemos usar los tres tipos de expresiones juntos para crear lógica súper útil. El computador evaluará primero las aritméticas, luego las relacionales y finalmente las booleanas (respetando paréntesis, claro).

**Ejemplo Complejo:** Imaginen que para aprobar una materia necesitan:
*   Promedio de notas >= 3.0
*   Asistencia >= 80%
*   Y NO haber perdido el examen final (nota_examen_final >= 2.0)


{@render codigo(code3csharp)}


¡Miren cómo usamos todo! Calculamos (`promedio_notas`), comparamos (`>=`, `<`), negamos (`NOT`) y conectamos (`AND`). ¡Así es como los programas toman decisiones elaboradas!
---

## ¡A Practicar, Pues! (Ejercicios) 💪

¡Ahora les toca a ustedes, parceros! Intenten resolver esto (pueden usar papel, mente o si ya saben algo de código, ¡háganle!):

**Aritméticas:**
1.  Calcula: `10 + 4 * 3 - 6 / 2`
2.  Calcula: `(5 + 3) * (10 % 3)`
3.  Calcula: `2 ** 4 / 8`

**Relacionales (Indica si es `True` o `False`):**
4.  `25 > 20`
5.  `100 == (50 * 2)`
6.  `'Hola' != 'hola'` (¡Pilas con mayúsculas!)
7.  `(10 + 5) <= 15`

**Booleanas (Indica si es `True` o `False`):**
8.  `True AND (10 > 5)`
9.  `(5 < 3) OR (20 == 20)`
10. `NOT (False OR True)`
11. `(True AND False) OR (NOT False)`

**¡El Reto Final!**
12. Escribe una **única expresión** que determine si alguien puede entrar a una fiesta. Condiciones: Debe ser mayor de edad (`edad >= 18`) Y (tener invitación (`tiene_invitacion == True`) O estar en la lista (`esta_en_lista == True`)).
    *   Prueba con: `edad = 17`, `tiene_invitacion = True`, `esta_en_lista = False` -> ¿Resultado?
    *   Prueba con: `edad = 20`, `tiene_invitacion = False`, `esta_en_lista = True` -> ¿Resultado?

---

## Conclusión: ¡Ya Son Unos Tesos de las Expresiones! 🏆

¡Felicitaciones! Han recorrido los fundamentos de las expresiones aritméticas, relacionales y booleanas. Estas ideas son la base para cosas más avanzadas como las estructuras de control (`if`, `else`, `while`) que veremos más adelante y que permiten a los programas tomar caminos diferentes según estas condiciones se cumplan o no.

¡No dejen de practicar! Jueguen con los números, las comparaciones y la lógica. ¡Mientras más lo hagan, más natural se volverá!

**¿Preguntas? ¿Dudas? ¡Comenten abajo o nos vemos en clase!**

**¡La buena, parceros! ¡Sigan aprendiendo!** 👨‍🏫👩‍🏫