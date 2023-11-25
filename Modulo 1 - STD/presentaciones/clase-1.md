---
marp: true
theme: default
paginate: true
math: katex
---

# Introducción a la Programación

Introducción - STD 1

---

### Modulo 1 - STD

1. Variables y tipos de datos
2. Operadores
   - Operadores Aritmeticos
   - Incrementos y Decrecimientos
   - Operadores de Asignación
   - Operadores Lógicos
   - Operadores Relacionales
3. Input - Output
4. Compilación y ejecución

---

**STD** es por _Standar_, se refiere a este término cuando se quiere hablar de las funcionalidades básicas que tiene c++ por defecto. Esto incluye gran parte de lo que veremos en este curso de introducción a la Programación. Para empezar a programar en c++ es necesario el uso de un compilador.

> https://compiler.achalogy.dev/

![bg right:30% 80%](https://upload.wikimedia.org/wikipedia/commons/thumb/1/18/ISO_C%2B%2B_Logo.svg/1822px-ISO_C%2B%2B_Logo.svg.png)

---

# ¿Que podemos hacer con un programa en C++?

Lo primero y más básico es almacenar valores, estos se pueden almacenar en variables de diferente tipo. Tenemos tipos para numeros, para valores lógicos, para texto, caracteres y mucho más.

```c++
int numero;
float decimal;
char caracter;
string texto;
bool booleanos;
long long numero_grande;
// ... mucho más
```

---

# ¿Y para que queremos estos datos?

Podemos usar, por ejemplo, las variables de tipo númerico para hacer operaciones matemáticas.

```cpp
int suma = a + b;
int diferencia = a - b;
int producto = a * b;

int cociente = a / b;
flot cociente = float(a) / float(b);

int modulo = a % b; // Residuo
```

---

También tenemos algunos operadores que nos simplifican un poco el código que escribimos, por ejemplo, si necesitamos solo aumentar en $1$, podriamos hacerlo así:

```cpp
int contador = 0;

contador = contador + 1; // Aumentará +1 a la variable contador
```

Pero c++ nos ofrece formas más cortas para hacerlo:

```c++
int contador = 0; // Tener en cuenta el = 0

contador++; // Aumentará +1 a la variable contador
contador--; // Reducirá -1 a la variable contador
```

---

Si necesitamos aumentar en más de uno, podemos hacerlo con operadores de asignación:

```c++
int x = 15;

x += 3; // x toma el valor de 18 (15 + 3)
x -= 3; // x toma el valor de 12 (15 - 3)
```

Estos operadores evaluan el numero con la operación que esta antes del $=$ y el numero de la derecha:

```cpp
int x = 15;

x *= 3; // x toma el valor de 45 (15 * 3)
x /= 3; // x toma el valor de 5  (15 / 3)
x %= 7; // x toma el valor de 1  (15 % 7)
```

---

Con respecto a los valores Lógicos, estos solo toman dos posible valores **TRUE** o **FALSE** que en algunos casos pueden ser interpretados como _1 para true_ y _0 para false_.

```c++
true && true = true;
true && false = false;
true || false = true;
!true = false
```

Con esto podemos evaluar por ejemplo si dos numeros son mayores a 5:

```c++
int a = 6, b = 3;

a > 5 && b > 5; // Falso
a > 5 || b > 5; // Verdadero
```

---

Para comparar valores tenemos, nuevamente, los operadores que hemos usado toda la vida:

- Equivale a _==_
- NO Equivale a _!=_
- Mayor que _>_
- Menor que _<_
- Mayor o igual que $\geq$
- Menor o igual que $\leq$

---

## Input - Output

Incluyendo la biblioteca _iostream_ podemos hacer uso de `cin` para esperar que el usuario escriba algo por consola. Este `cin` tomará lo que sea que el usuario escriba hasta un espacio o salto de línea (enter), por lo tanto, si quieres tomar más de un dato, y estos están separados por espacios o saltos de línea, tendrás que hacer más de un `cin`.

```c++
int numero = 0;

cin >> numero;
```

---

## Input - Output

Con `cout` podremos escribir cosas por pantalla, este no incluye por defecto un salto de línea al final, así que si quieres que se vea más ordenado tendrás que agregar por tu cuenta un salto de línea. Esto se puede lograr con `"\n"` o con `endl`;

Podemos ejecutarlos más de una vez de la siguiente forma: `cout << "Hola, " << "Juan"` o:

```cpp
cout << "Hola, ";
cout << "Juan";
```

Adicionalmente si queremos mostrar por pantalla numeros de coma flotante, debemos establecer un máximo en la cantidad de números luego de la coma:

```c++
printf("%.2f", item);
```

---

Un ejemplo de un programa simple en c++:

```cpp
#include <iostream>
using namespace std;

int main() {
  int a;
  int b;
  int c;

  cin >> a >> b >> c;

  cout << "La suma de los tres numeros es " << a + b + c << endl;
}
```

---

# Compilación Manual (IMPORTANTE)

Si estas usando G++, vas a tener que ejecutar una terminal/consola donde tengas el archivo que quiereas compilar. Usa el comando `cd` para navegar al directorio donde guardaste tu archivo y luego ejecuta `g++` para generar un archivo ejecutable.

```bash
cd ruta/del/directorio
g++ -o mi_programa mi_programa.cpp
```

Ahora tendrás un archivo con el nombre que hayas puesto luego de la flag `-o`, este lo puedes ejecutar con `./mi_programa`.
