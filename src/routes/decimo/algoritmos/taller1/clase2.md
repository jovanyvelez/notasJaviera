Instrucciones Generales para los Alumnos
"Para cada ejercicio, crea un nuevo proyecto de consola en C#. Investiga el método de string que se sugiere o el que creas que mejor resuelve el problema. ¡No dudes en consultar la documentación de Microsoft sobre la clase String!"

fuente de consulta: 

Microsoft: 

https://learn.microsoft.com/en-us/dotnet/api/system.string.clone?view=net-9.0

Youtube:

https://www.youtube.com/watch?v=c0dD3uKN5KA&t=2061s
                 
https://www.youtube.com/watch?v=UETol82cPZk&list=PLdo4fOcmZ0oULFjxrOagaERVAMbmG20Xe&index=6
                 


Ejercicios Propuestos (C# String Methods)

1. Longitud de un Nombre

  Pide al usuario que ingrese su nombre completo.
  Muestra en consola cuántos caracteres tiene su nombre (incluyendo espacios).

  *Pista: Propiedad Length.*

2. Convertir a Mayúsculas

  Pide al usuario que ingrese una frase.
  Muestra la misma frase completamente en mayúsculas.
  *Pista: Método ToUpper().*

3. Convertir a Minúsculas

  Pide al usuario que ingrese una frase.
  Muestra la misma frase completamente en minúsculas.
  *Pista: Método ToLower().*

4. Verificar si Contiene una Palabra

  Pide al usuario que ingrese una frase.
  Luego, pide una palabra a buscar.
  Indica si la frase contiene o no la palabra buscada (true/false).
  *Pista: Método Contains().*

5. Extraer una Subcadena (Substring)

  Pide al usuario que ingrese una frase de al menos 10 caracteres.
  Extrae y muestra los caracteres desde el índice 2 hasta el índice 7 (es decir, 5 caracteres).
  *Pista: Método Substring(int startIndex, int length).*

6. Reemplazar Caracteres

  Pide al usuario que ingrese una frase que contenga la letra 'a'.
  Muestra la frase reemplazando todas las 'a' por una 'x'.
  *Pista: Método Replace(char oldChar, char newChar) o Replace(string oldValue, string newValue).*

7. Eliminar Espacios al Inicio y Final

  Pide al usuario que ingrese una frase con espacios extra al inicio y/o al final (ej: " hola mundo ").
  Muestra la frase sin esos espacios extra.
  *Pista: Método Trim().*

8. Verificar si Comienza Con...

  Pide al usuario que ingrese una dirección de email.
  Verifica si la dirección comienza con "admin@". Muestra true o false.
  *Pista: Método StartsWith(string value).*

9. Verificar si Termina Con...

  Pide al usuario que ingrese el nombre de un archivo (ej: "documento.txt").
  Verifica si el archivo termina con ".txt". Muestra true o false.
  *Pista: Método EndsWith(string value).*

10. Encontrar la Posición de un Carácter

  Pide al usuario que ingrese una palabra.
  Busca la primera aparición de la letra 'e' y muestra su índice (posición). Si no se encuentra, indica que no está.
  *Pista: Método IndexOf(char value). Devuelve -1 si no se encuentra.*


11. Comparar dos Strings Ignorando Mayúsculas/Minúsculas

  Pide al usuario que ingrese dos palabras.
  Compara si son iguales, ignorando si están en mayúsculas o minúsculas. Muestra "Son iguales" o "Son diferentes".
  *Pista: Método Equals(string value, StringComparison comparisonType) usando StringComparison.OrdinalIgnoreCase o convirtiendo ambas a un mismo caso antes de comparar con ==.*

12. Verificar si un String está Vacío o es Nulo

  Pide al usuario que ingrese un texto (puede presionar Enter sin escribir nada).
  Indica si el string ingresado es nulo o está vacío.
  *Pista: Método string.IsNullOrEmpty(string value).*

13. Rellenar un String (Padding)

  Pide al usuario un número (como texto, ej: "123").
  Muestra ese número rellenado con ceros a la izquierda hasta que tenga una longitud total de 5 caracteres (ej: "00123").
  *Pista: Método PadLeft(int totalWidth, char paddingChar).*

14. Buscar la Siguiente Ocurrencia de un Carácter:
  Pide al usuario una frase y un carácter a buscar (ej: frase "banana", carácter 'a').
  Encuentra la primera ocurrencia del carácter. Luego, busca la siguiente ocurrencia del mismo carácter a partir de la posición posterior a la primera encontrada. Muestra el índice de ambas.
  *Pista: Usa IndexOf(char value) y luego IndexOf(char value, int startIndex).*

15. Buscar la Siguiente Ocurrencia de un Carácter:
  Pide al usuario una frase y un carácter a buscar (ej: frase "banana", carácter 'a').
  Encuentra la primera ocurrencia del carácter. Luego, busca la siguiente ocurrencia del mismo carácter a partir de la posición posterior a la primera encontrada. Muestra el índice de ambas.
  *Pista: Usa IndexOf(char value) y luego IndexOf(char value, int startIndex).*

16. Encontrar la Última Posición de un Carácter:
  Pide al usuario que ingrese una frase que contenga la letra 'a' varias veces.
  Busca la última aparición de la letra 'a' y muestra su índice.
  *Pista: Método LastIndexOf(char value).*
  