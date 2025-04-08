
# 🔢 Sistemas Numéricos y Representación de Datos en Computación

## 📚 Clase 1: Sistemas Numéricos (Binario, Octal y Decimal)

### 1️⃣ Sistema Binario

#### ¿Qué es el sistema binario?

El sistema binario es un sistema de numeración que utiliza únicamente dos dígitos: **0** y **1**. Es la base de toda la computación moderna, ya que los circuitos electrónicos solo pueden distinguir entre dos estados: encendido (1) y apagado (0).

#### Valor posicional en binario

En el sistema binario, cada posición tiene un valor de 2 elevado a una potencia, comenzando desde la derecha con 2^0.

```
... 2^5  2^4  2^3  2^2  2^1  2^0
... 32   16    8    4    2    1
```

#### Conversión de Decimal a Binario

Para convertir un número decimal a binario:
1. Divide el número entre 2.
2. Anota el residuo (0 o 1).
3. Divide el cociente entre 2.
4. Repite hasta que el cociente sea 0.
5. Lee los residuos de abajo hacia arriba.

**Ejemplo:** Convertir 25 a binario

```
25 ÷ 2 = 12 residuo 1
12 ÷ 2 = 6  residuo 0
6  ÷ 2 = 3  residuo 0
3  ÷ 2 = 1  residuo 1
1  ÷ 2 = 0  residuo 1
```

Leyendo los residuos de abajo hacia arriba: 25 en binario es **11001**.

#### Conversión de Binario a Decimal

Para convertir de binario a decimal, multiplica cada dígito por su valor posicional y suma todos los resultados.

**Ejemplo:** Convertir 10110 a decimal

```
1 × 2^4 + 0 × 2^3 + 1 × 2^2 + 1 × 2^1 + 0 × 2^0
1 × 16  + 0 × 8   + 1 × 4   + 1 × 2   + 0 × 1
= 16 + 0 + 4 + 2 + 0 = 22
```

#### 🧮 Operaciones en Binario

**Suma:**
```
  1 1 (acarreos)
  1 0 1
+ 0 1 1
-------
  1 0 0 0
```

**Resta:**
```
  1 0 1
- 0 1 1
-------
  0 1 0
```

**✅ Problema resuelto 1:** Suma 1101 + 1011 en binario.

```
    1 1 1 (acarreos)
    1 1 0 1
  + 1 0 1 1
  ---------
  1 1 0 0 0
```

Resultado: 1101 + 1011 = 11000 (en decimal: 13 + 11 = 24)

**✅ Problema resuelto 2:** Convierte 42 a binario.

```
42 ÷ 2 = 21 residuo 0
21 ÷ 2 = 10 residuo 1
10 ÷ 2 = 5  residuo 0
5  ÷ 2 = 2  residuo 1
2  ÷ 2 = 1  residuo 0
1  ÷ 2 = 0  residuo 1
```

Resultado: 42 en binario es **101010**.

### 2️⃣ Sistema Octal

#### ¿Qué es el sistema octal?

El sistema octal utiliza 8 dígitos (0-7) y es útil en computación porque cada dígito octal representa exactamente 3 dígitos binarios.

#### Valor posicional en octal

En el sistema octal, cada posición tiene un valor de 8 elevado a una potencia, comenzando desde la derecha con 8^0.

```
... 8^3  8^2  8^1  8^0
... 512   64    8    1
```

#### Conversión de Decimal a Octal

Similar al método para binario, pero dividiendo entre 8 en lugar de 2.

**Ejemplo:** Convertir 75 a octal

```
75 ÷ 8 = 9 residuo 3
9  ÷ 8 = 1 residuo 1
1  ÷ 8 = 0 residuo 1
```

Resultado: 75 en octal es **113**.

#### Conversión de Octal a Decimal

Multiplica cada dígito por su valor posicional y suma.

**Ejemplo:** Convertir 247 a decimal

```
2 × 8^2 + 4 × 8^1 + 7 × 8^0
2 × 64  + 4 × 8   + 7 × 1
= 128 + 32 + 7 = 167
```

#### Conversión entre Binario y Octal

Para convertir de binario a octal, agrupa los dígitos binarios de tres en tres desde la derecha y convierte cada grupo a su equivalente octal.

**Ejemplo:** Convertir 10110111 a octal

Agrupamos: 010 | 110 | 111
Convertimos: 2 | 6 | 7

Resultado: 10110111 en octal es **267**.

Para convertir de octal a binario, convierte cada dígito octal a 3 dígitos binarios.

**Ejemplo:** Convertir 357 a binario

3 → 011
5 → 101
7 → 111

Resultado: 357 en octal es **011101111** en binario, o simplificado: **11101111**.

**✅ Problema resuelto 3:** Convierte 275 octal a decimal.

```
2 × 8^2 + 7 × 8^1 + 5 × 8^0
2 × 64  + 7 × 8   + 5 × 1
= 128 + 56 + 5 = 189
```

Resultado: 275 en octal es **189** en decimal.

**✅ Problema resuelto 4:** Convierte 101101 binario a octal.

Agrupando de derecha a izquierda: 101 | 101
Convertimos: 5 | 5

Resultado: 101101 en binario es **55** en octal.

### 3️⃣ Sistema Decimal

El sistema decimal es nuestro sistema numérico cotidiano, que utiliza 10 dígitos (0-9).

#### Valor posicional en decimal

```
... 10^3  10^2  10^1  10^0
... 1000   100    10     1
```

**✅ Problema resuelto 5:** Convierte 129 decimal a octal y binario.

Decimal a octal:
```
129 ÷ 8 = 16 residuo 1
16  ÷ 8 = 2  residuo 0
2   ÷ 8 = 0  residuo 2
```

129 en octal es **201**.

Decimal a binario:
```
129 ÷ 2 = 64 residuo 1
64  ÷ 2 = 32 residuo 0
32  ÷ 2 = 16 residuo 0
16  ÷ 2 = 8  residuo 0
8   ÷ 2 = 4  residuo 0
4   ÷ 2 = 2  residuo 0
2   ÷ 2 = 1  residuo 0
1   ÷ 2 = 0  residuo 1
```

129 en binario es **10000001**.

### 🏆 Problemas Propuestos - Clase 1

1. Convierte 45 decimal a binario y octal.
2. Convierte 10101100 binario a decimal y octal.
3. Convierte 253 octal a decimal y binario.
4. Suma los siguientes números binarios: 10101 + 11011.
5. Resta los siguientes números binarios: 11100 - 10010.
6. Si tenemos 10110 en binario y 46 en octal, ¿cuál es mayor?
7. Convierte 87 decimal a binario utilizando el método de división.
8. Convierte 365 octal a decimal.
9. Realiza la suma en octal: 527 + 164.
10. Convierte 111001 binario a octal y decimal.

---

## 📚 Clase 2: Hexadecimal y Representación de Datos

### 1️⃣ Sistema Hexadecimal

#### ¿Qué es el sistema hexadecimal?

El sistema hexadecimal utiliza 16 dígitos: 0-9 y A-F (donde A=10, B=11, C=12, D=13, E=14, F=15). Es ampliamente utilizado en informática porque cada dígito hexadecimal representa exactamente 4 dígitos binarios.

#### Valor posicional en hexadecimal

Cada posición tiene un valor de 16 elevado a una potencia, comenzando desde la derecha con 16^0.

```
... 16^3   16^2   16^1   16^0
... 4096    256     16      1
```

#### Conversión de Decimal a Hexadecimal

Similar al método para binario y octal, pero dividiendo entre 16.

**Ejemplo:** Convertir 250 a hexadecimal

```
250 ÷ 16 = 15 residuo 10 (A)
15  ÷ 16 = 0  residuo 15 (F)
```

Resultado: 250 en hexadecimal es **FA**.

#### Conversión de Hexadecimal a Decimal

**Ejemplo:** Convertir 3F5 a decimal

```
3 × 16^2 + F × 16^1 + 5 × 16^0
3 × 256  + 15 × 16  + 5 × 1
= 768 + 240 + 5 = 1013
```

#### Conversión entre Binario y Hexadecimal

Para convertir de binario a hexadecimal, agrupa los dígitos binarios de cuatro en cuatro desde la derecha y convierte cada grupo a su equivalente hexadecimal.

**Ejemplo:** Convertir 10110111 a hexadecimal

Agrupamos: 1011 | 0111
Convertimos: B | 7

Resultado: 10110111 en hexadecimal es **B7**.

Para convertir de hexadecimal a binario, convierte cada dígito hexadecimal a 4 dígitos binarios.

**Ejemplo:** Convertir 2AF a binario

2 → 0010
A → 1010
F → 1111

Resultado: 2AF en hexadecimal es **001010101111** en binario.

#### 🧮 Operaciones en Hexadecimal

**Suma:**
```
  9 + 8 = 17 → 1 y acarreo 1

    1 (acarreo)
    9 F
  + 8 7
  -----
    A 6
```

**✅ Problema resuelto 6:** Convierte C5F hexadecimal a decimal.

```
C × 16^2 + 5 × 16^1 + F × 16^0
12 × 256 + 5 × 16  + 15 × 1
= 3072 + 80 + 15 = 3167
```

Resultado: C5F en hexadecimal es **3167** en decimal.

**✅ Problema resuelto 7:** Convierte 10110011 binario a hexadecimal.

Agrupamos: 1011 | 0011
Convertimos: B | 3

Resultado: 10110011 en binario es **B3** en hexadecimal.

### 2️⃣ Representación de Datos en la Computadora

#### 💻 Representación de Números Enteros

Los números enteros se representan típicamente en binario utilizando los siguientes formatos:

1. **Representación directa (sin signo):** Utiliza todos los bits para representar magnitud.
   Ejemplo: 01101001 representa el número 105.

2. **Complemento a 1:** Para números negativos, se invierten todos los bits.
   Ejemplo: El complemento a 1 de 00000101 (5) es 11111010 (-5).

3. **Complemento a 2 (más común):** Para números negativos, se invierten todos los bits y se suma 1.
   Ejemplo: El complemento a 2 de 00000101 (5) es 11111011 (-5).

#### 💻 Representación de Números Reales (punto flotante)

Los números de punto flotante se representan en formato IEEE 754, que consiste en:
- Un bit de signo (0 para positivo, 1 para negativo)
- Un exponente con sesgo
- Una mantisa (parte fraccionaria)

Un número de punto flotante simple (32 bits) tiene:
- 1 bit de signo
- 8 bits de exponente
- 23 bits de mantisa

**Ejemplo simplificado:** Para representar 5.25 en punto flotante:
1. Convertimos a binario: 101.01
2. Normalizamos: 1.0101 × 2^2
3. El exponente es 2, con sesgo 127: 127 + 2 = 129 = 10000001
4. La mantisa es 0101 (más ceros)
5. Resultado: 0 10000001 01010000000000000000000

#### 💻 Representación de Caracteres

**ASCII:** Utiliza 7 bits para representar 128 caracteres básicos.
- Ejemplo: 'A' = 65 (decimal) = 1000001 (binario)
- Ejemplo: '5' = 53 (decimal) = 0110101 (binario)

**Unicode (UTF-8):** Codificación variable que puede representar casi todos los caracteres de todos los idiomas.

#### 🎨 Representación de Colores

Los colores se representan típicamente en formato RGB (Rojo, Verde, Azul), con 8 bits (0-255) para cada canal.

**Ejemplo:** El color rojo puro sería:
- En decimal: (255, 0, 0)
- En hexadecimal: #FF0000
- En binario: 11111111 00000000 00000000

**✅ Problema resuelto 8:** Representar el número 25 en complemento a 2 usando 8 bits.

Para números positivos, la representación es la misma que la directa:
25 en binario es 00011001, que en 8 bits es: **00011001**

**✅ Problema resuelto 9:** Representar el número -14 en complemento a 2 usando 8 bits.

1. Valor positivo en binario: 14 = 00001110
2. Invertimos todos los bits: 11110001
3. Sumamos 1: 11110001 + 1 = 11110010

Resultado: -14 en complemento a 2 (8 bits) es **11110010**.

**✅ Problema resuelto 10:** Convertir el código de color #3A7F en decimal RGB.

\#3A7F en hexadecimal:
- 3 = 3 en decimal
- A = 10 en decimal
- 7 = 7 en decimal
- F = 15 en decimal

Como se utilizan solo 4 caracteres, asumimos el formato abreviado #RGB, que expandido sería #33AA77FF.
Esto corresponde al color RGB: **(51, 170, 255)**.

### 🏆 Problemas Propuestos - Clase 2

1. Convierte 214 decimal a hexadecimal.
2. Convierte AF3 hexadecimal a decimal.
3. Convierte 10111010 binario a hexadecimal.
4. Convierte B2F hexadecimal a binario.
5. Suma los siguientes números hexadecimales: 2AF + 18C.
6. Representa el número -37 en complemento a 2 usando 8 bits.
7. ¿Cuál es la representación decimal RGB del color #7DC4E3?
8. Convierte 237 decimal a binario, octal y hexadecimal.
9. Si el carácter 'P' tiene el código ASCII 80, ¿cuál es su representación en binario y hexadecimal?
10. ¿Qué número decimal representa el número binario 11111111 si se interpreta como:
    a) Número sin signo?
    b) Número con signo en complemento a 2?

## 📝 Resumen y Enlaces Útiles

Hemos explorado los distintos sistemas numéricos utilizados en informática:
- **Binario (base 2):** Utiliza solo 0 y 1, es la base de la computación.
- **Octal (base 8):** Utiliza dígitos 0-7, cada dígito representa 3 bits.
- **Decimal (base 10):** Nuestro sistema habitual, utiliza dígitos 0-9.
- **Hexadecimal (base 16):** Utiliza dígitos 0-9 y letras A-F, cada dígito representa 4 bits.

También hemos visto cómo se representan diferentes tipos de datos en los sistemas computacionales, desde números enteros y reales hasta caracteres y colores.

### 🔎 Herramientas Útiles

- Calculadoras de conversiones entre sistemas numéricos: [Calculadora Online](https://www.rapidtables.com/convert/number/index.html)
- Tablas de códigos ASCII: [Tabla ASCII](https://www.asciitable.com/)
- Conversor de colores: [Conversor de Colores](https://convertingcolors.com/)

¡Buena suerte con los problemas propuestos! Recuerden que la práctica constante es la clave para dominar estos conceptos. 💪
