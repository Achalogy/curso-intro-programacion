# Modulo 1 - STD

## Window y Linux

Linux y Windows son dos sistemas operativos ampliamente utilizados que presentan diferencias fundamentales en sus enfoques y estructuras. Linux es un sistema operativo de código abierto, lo que significa que su código fuente es accesible y modificable por cualquier persona. Esta característica fomenta la colaboración y la innovación, permitiendo que la comunidad de usuarios contribuya al desarrollo y mejora continua del sistema. Linux es conocido por su estabilidad, seguridad y eficiencia en entornos de servidores, siendo la elección preferida para muchos servidores web.

Por otro lado, Windows, desarrollado por Microsoft, es un sistema operativo propietario y de código cerrado. Aunque es ampliamente utilizado en entornos de escritorio, también se utiliza en servidores y otros dispositivos. Windows se caracteriza por su interfaz gráfica de usuario intuitiva y su amplio soporte de software, especialmente para aplicaciones de uso cotidiano. Sin embargo, la seguridad a veces ha sido un tema de debate, y la actualización periódica del sistema puede ser un proceso más intrusivo en comparación con el modelo más fluido de actualizaciones en Linux. En resumen, la elección entre Linux y Windows a menudo depende de las necesidades específicas del usuario, ya sea para entornos empresariales, desarrollo de software o simplemente el uso diario de una computadora.

- **Terminal:** Es una interfaz de texto que te permite interactuar con la computadora utilizando comandos.

- **Sistema de Archivos:** Organiza y almacena datos en la computadora. Los sistemas operativos utilizan una estructura de carpetas (directorios) y archivos.

Para abrir una terminal en windows, podemos usar distintas aplicaciones según la versión del sistema operativo. Si usas **PowerShell** o **Terminal** en una versión superior a _Windows 11_ también podrás usar comandos de Linux.

### Comandos Básicos:

- **ls (List):** Muestra los archivos y carpetas en el directorio actual.
- **cd (Change Directory):** Cambia el directorio.
- **mkdir (Make Directory):** Crea un nuevo directorio.
- **cp (Copy):** Copia archivos o directorios.
- **mv (Move):** Mueve o renombra archivos y directorios.
- **rm (Remove):** Elimina archivos o directorios (¡cuidado con este comando!).

### Sistema de Archivos:

**/:** Directorio raíz.
**/home: o ~** Contiene los directorios de usuarios en Linux.
**C:\Users:** Contiene los directorios de usuarios en Windows.

### Rutas Absolutas y Rutas Relativas:

**Absolutas:** Especifican la ruta completa desde el directorio raíz.
**Relativas:** Especifican la ruta desde el directorio actual.

## Plantilla Base

Nuestros programas iniciarán con la siguiente estructura:

```cpp
#include <iostream>
using namespace std;

int main(void) {
  // Lógica del código
  return 0;
}
```

Incluimos la librería _iostream_ y usaremos _std_ el cual incluye funcionalidades importantes como recibir y enviar datos por terminal.
La función _main_ será la función principal de nuestro programa, es decir, la función que se ejecutará al compilar el código.

Por ahora, todo el código que escribamos será dentro de las llaves de esta función _main_, es muy importante mantener una buena organización con estas llaves para conocer y controlar el correcto orden de ejecución del código.

## Variables y Tipos de Datos

Tenemos distintos tipos de datos que funcionan para cosas distintas, algunos de estos son los que toman valores numéricos, valores booleanos o en texto claro que podemos leer. Aun así, estos se deben almacenar en un espacio limitado de bits:

| Tipo de Dato   | `int`                               | `long long`                         | `double`                      | `bool`                       | `char`                            |
| -------------- | ----------------------------------- | ----------------------------------- | ----------------------------- | ---------------------------- | --------------------------------- |
| Descripción    | Número entero de tamaño 32-bit      | Número entero de tamaño 64-bit      | Números con Decimales         | Verdadero (1) o Falso (0)    | Caracter de 8-bit                 |
| Tamaño (bytes) | 4                                   | 8                                   | 8                             | 1                            | 1                                 |
| Rango          | $−2^{31} \text{ hasta } 2^{31} - 1$ | $−2^{63} \text{ hasta } 2^{63} - 1$ | `-1.7E+308` hasta `+1.7E+308` | 000 o 111 (`true` o `false`) | $−2^{7} \text{ hasta } 2^{7} - 1$ |

En C++, las variables son contenedores que almacenan valores. Los tipos de datos incluyen enteros (int), números de punto flotante (float), caracteres (char), booleanos (bool) y más. Estos tipos definen cómo se almacenan y operan los datos en la memoria. Recordemos que un número entero no incluye números de coma flotante (decimales), para eso tenemos float o double.

```c++
int numero;
float decimal;
char caracter;
string texto;
bool booleanos;
long long numero_grande;
// ... mucho más
```

## Operadores

### Operadores Aritméticos

En C++ podemos realizar operaciones matemáticas en variables numéricas muy similar a como lo haríamos en una calculadora, estos incluyen también el operador de módulo que devolverá el resto de la división entera de un número por otro. Estos operadores permiten realizar cálculos y manipular valores numéricos de manera eficiente en programas escritos en C++.

```cpp
int suma = a + b;
int diferencia = a - b;
int producto = a * b;

int cociente = a / b;
flot cociente = float(a) / float(b); // Para poder hacer operaciones entre enteros y tener decimales, debemos primero convertir los enteros a flotante.

int modulo = a % b; // Residuo
```

### Incrementos y Decrecimientos

En C++, los operadores de incremento (++) y decremento (--) se utilizan para aumentar o disminuir el valor de una variable numérica en uno, respectivamente. Por ejemplo, si tienes una variable llamada `contador` y utilizas el operador de incremento de la siguiente manera: `contador++`, aumentará el valor de `contador` en uno. De manera similar, el operador de decremento `contador--` disminuirá el valor de `contador` en uno. Estos operadores son comúnmente utilizados en bucles y otras estructuras de control de flujo para gestionar contadores y realizar iteraciones en programas en C++.

```cpp
int contador = 0;

contador++; // Aumentará +1 a la variable contador
contador--; // Reducirá -1 a la variable contador
```

### Operadores Lógicos

- **Operador AND _(&&)_:** Revisa si los dos operadores o condiciones son verdaderos, si esto ocurre, la expresión completa es true, de lo contrario, si uno es falso o los dos son falsos, la expresión completa será falso.

```cpp
// (expresion1 && expresion2)

int a = 5, b = 10;
if (a > 0 && b > 0) {
    cout << "Both values are positive." << endl;
}
```

- **Operador OR _(||)_:** Revisa si alguno de los dos operadores o condiciones es verdadero.

```cpp
// (expresion1 || expresion2)

int a = 5, b = -10;
if (a > 0 || b > 0) {
    cout << "At least one value is positive." << endl;
}
```

- **Operador NOT _(!)_:** Invierte el valor de una condición o expresión. Es decir, si la condición es verdadera, entonces el operador hará que sea falsa, y viceversa.

### Operadores relacionales

En C++, los operadores relacionales se utilizan para comparar valores y producir resultados booleanos. Algunos de los operadores relacionales comunes son:

- Equivale a _==_
- NO Equivale a _!=_
- Mayor que _>_
- Menor que _<_
- Mayor o igual que $\geq$
- Menor o igual que $\leq$

Estos operadores son fundamentales para construir condiciones y realizar comparaciones en programas escritos en C++.

### Operadores de Asignación

En C++, el operador de asignación compuesta += se utiliza para agregar el valor de la derecha al valor de la izquierda y asignar el resultado a la variable de la izquierda. Es una forma abreviada de escribir `variable = variable + valor`.
Además de +=, existen otros operadores de asignación compuesta como `-=` `(variable = variable - valor)`, `*=` `(variable = variable * valor)`, y `/=` `(variable = variable / valor)`, entre otros. Estos operadores proporcionan una forma concisa de realizar operaciones y actualizar el valor de la variable en un solo paso.

```cpp
int x = 15;

x += 3; // x toma el valor de 18 (15 + 3)
x -= 3; // x toma el valor de 12 (15 - 3)
x *= 3; // x toma el valor de 45 (15 * 3)
x /= 3; // x toma el valor de 5  (15 / 3)
x %= 7; // x toma el valor de 1  (15 % 7)
```

## Input - Output

Incluyendo la biblioteca _iostream_ podemos hacer uso de `cin` para esperar que el usuario escriba algo por consola. Este `cin` tomará lo que sea que el usuario escriba hasta un espacio o salto de línea (enter), por lo tanto, si quieres tomar más de un dato, y estos están separados por espacios o saltos de línea, tendrás que hacer más de un `cin`.

Con `cout` podremos escribir cosas por pantalla, este no incluye por defecto un salto de línea al final, así que si quieres que se vea más ordenado tendrás que agregar por tu cuenta un salto de línea. Esto se puede lograr con `"\n"` o con `endl`;

Podemos ejecutarlos más de una vez de la siguiente forma: `cout << "Hola, " << "Juan"` o:

```cpp
cout << "Hola, ";
cout << "Juan";
```

Cualquiera de las dos formas es valida. Un ejemplo de un programa simple en c++:

```cpp
#include <iostream>
using namespace std;

int main() {
  int a;
  int b;
  int c;

  cin >> a >> b >> c;

  cout << "La suma de los tres numeros es " << a + b + c << "\n";
  cout << "La suma de los tres numeros es " << a + b + c << endl; // Mismo ejemplo pero con endl
}
```

## Compilación y ejecución

Si estas usando un programa como Dev C++, Code::Blocks, o similares, debes buscar un botón que se encargue de la compilación y ejecución del código. De lo contrario, si estas usando G++, vas a tener que ejecutar una terminal/consola donde tengas el archivo que quiereas compilar. Usa el comando `cd` para navegar al directorio donde guardaste tu archivo y luego ejecuta `g++` para generar un archivo ejecutable.

```bash
cd ruta/del/directorio
g++ -o mi_programa mi_programa.cpp
```

Ahora tendrás un archivo con el nombre que hayas puesto luego de la flag `-o`, este lo puedes ejecutar con `./mi_programa`
