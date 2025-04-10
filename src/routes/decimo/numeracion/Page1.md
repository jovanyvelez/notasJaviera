¡Absolutamente! Prepárense para un viaje fascinante al corazón de cómo "piensan" las computadoras. Como su profesor de Media Técnica, vamos a desentrañar los secretos de los sistemas numéricos que usan las máquinas y cómo representan la información. ¡Serán dos clases intensas pero súper interesantes! 🚀

Aquí tienen el material para el blog de la clase, listo para copiar y pegar:

---

# 💻 Mundos Numéricos: ¡El Lenguaje Secreto de las Computadoras! 🔢

¡Hola, futuros genios de la tecnología! 👋

¿Alguna vez se han preguntado cómo su teléfono, computadora o consola de videojuegos hacen todas esas cosas increíbles? 🤔 ¡Todo se reduce a números! Pero no solo los números que usamos todos los días. Las computadoras hablan en lenguajes numéricos especiales. En las próximas dos clases (¡prepárense,!), vamos a explorar estos sistemas y a entender cómo se guarda la información. ¡Abróchense los cinturones!

---

## 📅 Clase 1: Fundamentos y el Mundo Binario (180 Minutos)

**Objetivo:** Entender qué es un sistema numérico, dominar el sistema decimal y binario (conversiones y sumas básicas) e introducir el sistema octal.

---

### 📚 Tema 1: Sistema Decimal (Base 10) - ¡Nuestro Viejo Amigo! (Aprox. 30 min)

💡 **La Base Teórica:**

*   Este es el sistema que usamos a diario. Se llama "base 10" porque utiliza **diez dígitos**: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9.
*   La posición de cada dígito importa MUCHO. Cada posición representa una potencia de 10 (unidades, decenas, centenas...).
*   Ejemplo: El número `345` significa `(3 * 10^2) + (4 * 10^1) + (5 * 10^0)` = `(3 * 100) + (4 * 10) + (5 * 1)` = `300 + 40 + 5 = 345`.
*   Las operaciones (suma, resta, etc.) las conocemos bien, ¡pero recordar la base nos ayudará con los otros sistemas!

✅ **Problema Resuelto:**

*   **Pregunta:** Descompón el número `1207` en potencias de 10.
*   **Solución:**
    ```
    1207 = (1 * 10^3) + (2 * 10^2) + (0 * 10^1) + (7 * 10^0)
         = (1 * 1000) + (2 * 100) + (0 * 10) + (7 * 1)
         = 1000 + 200 + 0 + 7
         = 1207
    ```

🤔 **Problemas Propuestos:**

1.  Descompón el número `58` en potencias de 10.
2.  Descompón el número `9034` en potencias de 10.
3.  ¿Qué valor representa el dígito `6` en el número `7651`?

---

### 📚 Tema 2: Sistema Binario (Base 2) - ¡El Lenguaje de las Máquinas! (Aprox. 90 min)

💡 **La Base Teórica:**

*   ¡El sistema fundamental para las computadoras! Se llama "base 2" porque solo usa **dos dígitos**: 0 y 1.
*   Cada dígito binario se llama **Bit** (Binary Digit).
*   Las posiciones representan potencias de 2: `... 2^4 (16), 2^3 (8), 2^2 (4), 2^1 (2), 2^0 (1)`.
*   Un `1` significa "encendido" o "verdadero", y un `0` significa "apagado" o "falso". Así funcionan los circuitos electrónicos.

🔄 **Conversiones:**

1.  **Decimal a Binario:**
    *   **Método:** Divisiones sucesivas por 2. Dividimos el número decimal entre 2 repetidamente, anotando los restos (0 o 1). El número binario se forma leyendo los restos desde el último hasta el primero.
    *   **Ejemplo (Convertir 13 a Binario):**
        *   `13 / 2 = 6` (Resto `1`)
        *   `6 / 2 = 3` (Resto `0`)
        *   `3 / 2 = 1` (Resto `1`)
        *   `1 / 2 = 0` (Resto `1`)
        *   Leemos los restos de abajo hacia arriba: `1101`. Así que, `13_10 = 1101_2`. (El subíndice indica la base).

2.  **Binario a Decimal:**
    *   **Método:** Multiplicar cada bit por la potencia de 2 correspondiente a su posición y sumar los resultados.
    *   **Ejemplo (Convertir `10110_2` a Decimal):**
        *   Posiciones (de derecha a izquierda, empezando en 0): 0, 1, 2, 3, 4
        *   `10110_2 = (1 * 2^4) + (0 * 2^3) + (1 * 2^2) + (1 * 2^1) + (0 * 2^0)`
        *   `= (1 * 16) + (0 * 8) + (1 * 4) + (1 * 2) + (0 * 1)`
        *   `= 16 + 0 + 4 + 2 + 0 = 22`. Así que, `10110_2 = 22_10`.

➕ **Operaciones (Suma Binaria):**

*   Reglas básicas:
    *   `0 + 0 = 0`
    *   `0 + 1 = 1`
    *   `1 + 0 = 1`
    *   `1 + 1 = 0` (y te llevas 1 a la siguiente posición, como en la suma decimal cuando pasas de 9).
    *   `1 + 1 + 1 = 1` (y te llevas 1).

✅ **Problemas Resueltos:**

1.  **Convertir `25_10` a Binario:**
    ```
    25 / 2 = 12 (Resto 1)
    12 / 2 = 6  (Resto 0)
    6  / 2 = 3  (Resto 0)
    3  / 2 = 1  (Resto 1)
    1  / 2 = 0  (Resto 1)
    Resultado: 11001_2
    ```
2.  **Convertir `110101_2` a Decimal:**
    ```
    110101_2 = (1*2^5) + (1*2^4) + (0*2^3) + (1*2^2) + (0*2^1) + (1*2^0)
             = (1*32) + (1*16) + (0*8) + (1*4) + (0*2) + (1*1)
             = 32 + 16 + 0 + 4 + 0 + 1 = 53_10
    ```
3.  **Sumar `1011_2 + 110_2`:**
    ```
      1011  (Es 11 en decimal)
    +  110  (Es 6 en decimal)
    ------
      111 (Llevada) <- Pequeñas notas para las llevadas
      1011
    + 0110  (Alineamos por la derecha)
    ------
     10001  (Es 17 en decimal. ¡Funciona!)

    Paso a paso:
    - Columna derecha (2^0): 1 + 0 = 1
    - Siguiente (2^1): 1 + 1 = 0, me llevo 1
    - Siguiente (2^2): 0 + 1 + 1 (llevada) = 0, me llevo 1
    - Siguiente (2^3): 1 + 0 + 1 (llevada) = 0, me llevo 1
    - Última llevada: 1
    Resultado: 10001_2
    ```

🤔 **Problemas Propuestos:**

4.  Convierte `42_10` a binario.
5.  Convierte `19_10` a binario.
6.  Convierte `101010_2` a decimal.
7.  Convierte `1111_2` a decimal.
8.  Suma `11001_2 + 101_2`.
9.  Suma `1001_2 + 11_2`.

---

### 📚 Tema 3: Sistema Octal (Base 8) - Un Atajo Útil (Aprox. 60 min)

💡 **La Base Teórica:**

*   Usa **ocho dígitos**: 0, 1, 2, 3, 4, 5, 6, 7. (¡Nunca verás un 8 o 9 en octal!).
*   Las posiciones representan potencias de 8: `... 8^3 (512), 8^2 (64), 8^1 (8), 8^0 (1)`.
*   ¿Por qué usarlo? Es una forma más corta de representar números binarios, ya que `8 = 2^3`. Cada dígito octal corresponde exactamente a **3 bits** binarios.
    *   `0 = 000`
    *   `1 = 001`
    *   `2 = 010`
    *   `3 = 011`
    *   `4 = 100`
    *   `5 = 101`
    *   `6 = 110`
    *   `7 = 111`

🔄 **Conversiones:**

1.  **Binario a Octal:**
    *   **Método:** Agrupa los bits del número binario en grupos de 3, empezando por la derecha. Si el último grupo de la izquierda no tiene 3 bits, añade ceros a la izquierda. Convierte cada grupo de 3 bits a su dígito octal equivalente.
    *   **Ejemplo (Convertir `11010101_2` a Octal):**
        *   Agrupamos: `11 010 101`
        *   Añadimos cero a la izquierda: `011 010 101`
        *   Convertimos cada grupo: `011 = 3`, `010 = 2`, `101 = 5`
        *   Resultado: `325_8`.

2.  **Octal a Binario:**
    *   **Método:** Convierte cada dígito octal a su equivalente de 3 bits. Une los grupos.
    *   **Ejemplo (Convertir `742_8` a Binario):**
        *   `7 = 111`
        *   `4 = 100`
        *   `2 = 010`
        *   Unimos: `111 100 010`. Resultado: `111100010_2`.

3.  **Decimal a Octal:**
    *   **Método:** Divisiones sucesivas por 8. Similar a Decimal a Binario, pero dividiendo por 8.
    *   **Ejemplo (Convertir `150_10` a Octal):**
        *   `150 / 8 = 18` (Resto `6`)
        *   `18 / 8 = 2` (Resto `2`)
        *   `2 / 8 = 0` (Resto `2`)
        *   Leemos los restos de abajo hacia arriba: `226`. Resultado: `226_8`.

4.  **Octal a Decimal:**
    *   **Método:** Multiplicar cada dígito octal por la potencia de 8 correspondiente a su posición y sumar.
    *   **Ejemplo (Convertir `371_8` a Decimal):**
        *   `371_8 = (3 * 8^2) + (7 * 8^1) + (1 * 8^0)`
        *   `= (3 * 64) + (7 * 8) + (1 * 1)`
        *   `= 192 + 56 + 1 = 249`. Resultado: `249_10`.

✅ **Problemas Resueltos:**

1.  **Convertir `10111001_2` a Octal:**
    ```
    Agrupamos: 10 111 001
    Añadimos cero: 010 111 001
    Convertimos:  2   7   1
    Resultado: 271_8
    ```
2.  **Convertir `513_8` a Binario:**
    ```
    5 = 101
    1 = 001
    3 = 011
    Unimos: 101 001 011
    Resultado: 101001011_2
    ```
3.  **Convertir `99_10` a Octal:**
    ```
    99 / 8 = 12 (Resto 3)
    12 / 8 = 1  (Resto 4)
    1  / 8 = 0  (Resto 1)
    Resultado: 143_8
    ```
4.  **Convertir `106_8` a Decimal:**
    ```
    106_8 = (1 * 8^2) + (0 * 8^1) + (6 * 8^0)
          = (1 * 64) + (0 * 8) + (6 * 1)
          = 64 + 0 + 6 = 70_10
    ```

🤔 **Problemas Propuestos:**

10. Convierte `1110101_2` a octal.
11. Convierte `604_8` a binario.
12. Convierte `55_10` a octal.
13. Convierte `237_8` a decimal.
14. Convierte `77_8` a binario y luego a decimal. ¿Coincide si conviertes `77_8` directamente a decimal?

---

**Fin de la Clase 1.** ¡Buen trabajo! Hemos sentado las bases. En la próxima clase, nos sumergiremos en el hexadecimal, veremos más operaciones y conectaremos todo con cómo las computadoras representan datos reales. ¡Descansen esas neuronas! 🧠💤

---
---

## 📅 Clase 2: Hexadecimal, Operaciones y Representación de Datos (180 Minutos)

**Objetivo:** Dominar el sistema hexadecimal (conversiones y sumas), entender su relación con el binario y comprender cómo se representan los datos (números y texto) en una computadora.

---

### 📚 Tema 4: Sistema Hexadecimal (Base 16) - ¡El Favorito de los Programadores! (Aprox. 90 min)

💡 **La Base Teórica:**

*   Usa **dieciséis dígitos**: 0, 1, 2, 3, 4, 5, 6, 7, 8, 9, y luego... ¡letras!
    *   `A = 10` (en decimal)
    *   `B = 11`
    *   `C = 12`
    *   `D = 13`
    *   `E = 14`
    *   `F = 15`
*   Las posiciones representan potencias de 16: `... 16^3 (4096), 16^2 (256), 16^1 (16), 16^0 (1)`.
*   ¿Por qué usarlo? Es aún más compacto que el octal para representar números binarios, ya que `16 = 2^4`. Cada dígito hexadecimal corresponde exactamente a **4 bits**.
*   ¡Se usa muchísimo en programación! Para colores web (ej. `#FF0000` es rojo), direcciones de memoria, etc.

🔄 **Conversiones:**

1.  **Binario a Hexadecimal:**
    *   **Método:** Agrupa los bits del número binario en grupos de 4, empezando por la derecha. Añade ceros a la izquierda si es necesario. Convierte cada grupo de 4 bits a su dígito hexadecimal equivalente (0-9, A-F).
    *   **Ejemplo (Convertir `1101101011_2` a Hexadecimal):**
        *   Agrupamos: `11 0110 1011`
        *   Añadimos ceros: `0011 0110 1011`
        *   Convertimos: `0011 = 3`, `0110 = 6`, `1011 = B` (¡porque 1011 es 8+2+1 = 11 en decimal, y 11 es B!)
        *   Resultado: `36B_16`.

2.  **Hexadecimal a Binario:**
    *   **Método:** Convierte cada dígito hexadecimal a su equivalente de 4 bits. Une los grupos.
    *   **Ejemplo (Convertir `A5D_16` a Binario):**
        *   `A (10) = 1010`
        *   `5 = 0101`
        *   `D (13) = 1101`
        *   Unimos: `1010 0101 1101`. Resultado: `101001011101_2`.

3.  **Decimal a Hexadecimal:**
    *   **Método:** Divisiones sucesivas por 16. Recuerda convertir los restos 10-15 a A-F.
    *   **Ejemplo (Convertir `48879_10` a Hexadecimal):**
        *   `48879 / 16 = 3054` (Resto `15` -> `F`)
        *   `3054 / 16 = 190` (Resto `14` -> `E`)
        *   `190 / 16 = 11` (Resto `14` -> `E`)
        *   `11 / 16 = 0` (Resto `11` -> `B`)
        *   Leemos de abajo hacia arriba: `BEEF`. Resultado: `BEEF_16`. (¡Sí, como la carne! 😄)

4.  **Hexadecimal a Decimal:**
    *   **Método:** Multiplicar cada dígito hexadecimal (recordando A=10, B=11...) por la potencia de 16 correspondiente y sumar.
    *   **Ejemplo (Convertir `2C5_16` a Decimal):**
        *   `2C5_16 = (2 * 16^2) + (C * 16^1) + (5 * 16^0)`
        *   `= (2 * 256) + (12 * 16) + (5 * 1)`
        *   `= 512 + 192 + 5 = 709`. Resultado: `709_10`.

➕ **Operaciones (Suma Hexadecimal):**

*   Funciona como la suma decimal, pero ¡recuerda que la base es 16!
*   Suma los dígitos de la columna. Si el resultado es 15 o menos, escríbelo (usando A-F si es 10-15).
*   Si el resultado es 16 o más, réstale 16 y anota el resultado. Te llevas 1 a la siguiente columna.
*   **Ejemplo (`A7 + 3E`):**
    ```
       A7_16  (A=10)
    +  3E_16  (E=14)
    ------
       1 (Llevada)
       A7
    +  3E
    ------
       E5_16

    Paso a paso:
    - Columna derecha (16^0): 7 + E (14) = 21.  21 es mayor que 15.  21 - 16 = 5. Escribo 5 y me llevo 1.
    - Columna izquierda (16^1): A (10) + 3 + 1 (llevada) = 14. 14 es E en hexadecimal. Escribo E.
    Resultado: E5_16
    ```

✅ **Problemas Resueltos:**

1.  **Convertir `11110100011_2` a Hexadecimal:**
    ```
    Agrupamos: 111 1010 0011
    Añadimos ceros: 0111 1010 0011
    Convertimos:   7    A    3
    Resultado: 7A3_16
    ```
2.  **Convertir `F09_16` a Binario:**
    ```
    F (15) = 1111
    0 = 0000
    9 = 1001
    Unimos: 1111 0000 1001
    Resultado: 111100001001_2
    ```
3.  **Convertir `1000_10` a Hexadecimal:**
    ```
    1000 / 16 = 62 (Resto 8)
    62  / 16 = 3  (Resto 14 -> E)
    3   / 16 = 0  (Resto 3)
    Resultado: 3E8_16
    ```
4.  **Convertir `1B4_16` a Decimal:**
    ```
    1B4_16 = (1 * 16^2) + (B * 16^1) + (4 * 16^0)
           = (1 * 256) + (11 * 16) + (4 * 1)
           = 256 + 176 + 4 = 436_10
    ```
5.  **Sumar `1F5_16 + A3_16`:**
    ```
      1 (Llevada)
      1F5
    +  A3  (Alineamos) => + 0A3
    -----
      298_16

    Paso a paso:
    - Columna 16^0: 5 + 3 = 8.
    - Columna 16^1: F (15) + A (10) = 25.  25 - 16 = 9. Escribo 9, me llevo 1.
    - Columna 16^2: 1 + 0 + 1 (llevada) = 2.
    Resultado: 298_16
    ```

🤔 **Problemas Propuestos:**

15. Convierte `10110010101001_2` a hexadecimal.
16. Convierte `BAD_16` a binario. (¡Sí, "malo" en inglés! 😄)
17. Convierte `255_10` a hexadecimal.
18. Convierte `CAFE_16` a decimal. (¡Otro nombre divertido!)
19. Suma `FFE_16 + 1A_16`.
20. Suma `8C9_16 + 4D5_16`.

---

### 📚 Tema 5: Representación de Datos en la Computadora (Aprox. 60 min)

💡 **La Base Teórica:**

*   Ya sabemos que las computadoras usan **bits** (0s y 1s).
*   Los bits se agrupan en **Bytes**. Normalmente, **1 Byte = 8 bits**.
*   Con 8 bits, podemos representar `2^8 = 256` valores diferentes (desde `00000000` hasta `11111111` en binario).
*   **¿Cómo se representan los números?**
    *   **Enteros sin signo:** Directamente. El binario `00000001` es 1, `00000010` es 2, ..., `11111111` es 255 (usando 1 byte).
    *   **Enteros con signo:** Se usan diferentes métodos (como "complemento a dos") para representar números positivos y negativos dentro del mismo número de bits. (No entraremos en detalle hoy, ¡pero es importante saber que existe!).
    *   **Números Reales (con decimales):** Usan un formato llamado "punto flotante" (como IEEE 754), que guarda el signo, una parte principal (mantisa) y un exponente. ¡Es más complejo!
*   **¿Cómo se representa el texto?**
    *   Se asigna un número único a cada letra, dígito o símbolo.
    *   **ASCII (American Standard Code for Information Interchange):** Un código antiguo pero fundamental. Usa 7 u 8 bits. Por ejemplo:
        *   'A' es el número decimal 65 (`01000001` en binario, `41` en hexadecimal).
        *   'a' es el número decimal 97 (`01100001` en binario, `61` en hexadecimal).
        *   '0' (el carácter, no el valor) es 48 (`00110000` en binario, `30` en hexadecimal).
    *   **Unicode (y UTF-8):** Un estándar moderno que incluye caracteres de CASI TODOS los idiomas del mundo (¡incluyendo emojis! 😎). Usa un número variable de bytes. UTF-8 es el más común en la web y es compatible con ASCII para los caracteres básicos.
*   **¿Por qué vimos Hexadecimal?** ¡Porque es una forma súper cómoda de representar Bytes! Un byte (8 bits) se puede escribir exactamente con **dos** dígitos hexadecimales.
    *   Ejemplo: El byte `11001011` en binario.
        *   Separamos: `1100 1011`
        *   Convertimos: `1100 = C`, `1011 = B`
        *   El byte es `CB_16` en hexadecimal. ¡Mucho más corto y fácil de leer!

✅ **Ejemplo Práctico:**

*   La palabra "Hola" en ASCII:
    *   'H' = 72 decimal = `48` hex = `01001000` binario
    *   'o' = 111 decimal = `6F` hex = `01101111` binario
    *   'l' = 108 decimal = `6C` hex = `01101100` binario
    *   'a' = 97 decimal = `61` hex = `01100001` binario
*   En la memoria de la computadora (simplificado), "Hola" podría verse como la secuencia de bytes: `48 6F 6C 61` (en hexadecimal).

🤔 **Preguntas para Reflexionar (No hay cálculos aquí, ¡solo pensar!):**

21. Si 1 Byte tiene 8 bits, ¿cuántos bits tiene 1 Kilobyte (KB)? (Pista: Kilo en informática suele ser 1024, no 1000). ¿Y 1 Megabyte (MB)?
22. ¿Por qué crees que es útil tener un estándar como Unicode para representar texto en lugar de que cada país invente el suyo?
23. ¿Puedes encontrar el código ASCII (en decimal o hexadecimal) de tu inicial? Puedes buscar "tabla ASCII" en internet. ¿Cuál sería su representación binaria de 8 bits?

---

### ✨ Resumen y Próximos Pasos (Aprox. 30 min)

*   ¡Hemos cubierto muchísimo terreno!
    *   Entendemos los sistemas Decimal, Binario, Octal y Hexadecimal.
    *   Sabemos convertir números entre estas bases.
    *   Podemos realizar sumas básicas en binario y hexadecimal.
    *   Comprendemos que las computadoras usan binario (bits y bytes) para representar TODO: números, texto, imágenes, sonido...
    *   Vimos cómo ASCII y Unicode asignan números a los caracteres.
    *   Entendemos la utilidad del Octal y Hexadecimal como formas compactas de escribir números binarios.
*   **¡La práctica hace al maestro!** Hagan los problemas propuestos. Jueguen con una calculadora de programador (Windows la tiene, y hay muchas online) para verificar conversiones.
*   Estos conceptos son la BASE de muchas áreas de la informática y la tecnología. ¡Ahora tienen una visión más profunda de cómo funciona el mundo digital!

---

¡Felicidades por completar este intensivo de sistemas numéricos! 🥳 Espero que les haya parecido interesante y útil. ¡Cualquier duda, pregúntenla en clase o en los comentarios del blog! ¡Nos vemos! 👋

---
