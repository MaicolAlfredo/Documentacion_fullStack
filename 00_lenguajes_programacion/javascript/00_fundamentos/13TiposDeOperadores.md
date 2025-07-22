## 13. Tipos de Operadores 29:44

- [Concepto detrás del módulo](#concepto-detrás-del-módulo)
- [Un igual, dos iguales y tres iguales](#un-igual-dos-iguales-y-tres-iguales)
- [Operadores de Incremento y Decremento](#operadores-de-incremento-y-decremento)
- [Uso en Bucles](#uso-en-bucles)
- [Operadores Lógicos en JavaScript](#operadores-lógicos-en-javascript)

Ya en la sesión anterior terminamos de revisar todos los tipos de datos básicos en JavaScript. Recuerden que hemos pasado por los valores primitivos, como:

- Cadenas (strings)
- Números (numbers)
- Booleanos (booleans)
- Undefined
- NaN
- Null

También vimos valores compuestos, como los objetos, los arreglos y las funciones.

Les mencioné anteriormente que las clases (class) me las voy a reservar para cuando entremos en la parte de paradigmas de programación de este curso, donde exploraremos la programación orientada a objetos. Por ahora, creo que con lo que hemos aprendido podemos comenzar a trabajar.

Un concepto que es importante en todos los lenguajes de programación son los operadores. Existen diferentes tipos de operadores, y vamos a comenzar revisando los operadores aritméticos.

Los operadores aritméticos incluyen:

- Suma (+)
- Resta (-)
- Multiplicación (\*)
- División (/)
- Módulo (%)
- Agrupación mediante paréntesis (()), que se utilizan para definir el orden de ejecución.

Recuerden cuando estudiaban matemáticas básicas, que las operaciones dentro de los paréntesis se ejecutan primero. Luego siguen raíces y potencias, después multiplicaciones y divisiones, y finalmente sumas y restas, todo de izquierda a derecha.

Este orden de operaciones es respetado por los lenguajes de programación, y JavaScript no es ninguna excepción.

Generalmente, en nuestros estudios primarios, siempre nos enseñan que hay cuatro operaciones básicas: la suma, la resta, la multiplicación y la división. Sin embargo, rara vez se nos habla del módulo.

Por ejemplo, si creamos una variable para calcular 5 entre 2, ustedes podrían decir:

"Bueno, 5 entre 2 es igual a 2.5".

Veamos cómo funciona en JavaScript:

```js
let division = 5 / 2;
console.log(division); //2.5
```

Como esperábamos, la división devuelve 2.5.

Ahora, ¿qué sucede si utilizamos el símbolo de porcentaje (%)? Este operador aritmético se llama módulo, y lo que hace es devolvernos el residuo de una división.

```js
let modulo = 5 % 2;
console.log(modulo); // 1
```

En este caso, 5 % 2 devuelve 1, porque 1 es el residuo que queda al dividir 5 entre 2.

### Concepto detrás del módulo

Cuando realizamos la operación 5 / 2, obtenemos un cociente de 2 y un residuo de 1. El operador módulo (%) se encarga únicamente de devolver ese residuo, ignorando cualquier parte fraccionaria del cociente.

Esto es diferente de la división tradicional, que sí incluye la parte decimal o fraccionaria del resultado.

Por ejemplo:

```js
let division = 10 / 3;
let modulo = 10 % 3;

console.log(division); // 3.333
console.log(modulo); // 1
```

En este caso:

- 10 / 3 devuelve 3.333... como cociente.
- 10 % 3 devuelve 1, que es el residuo de la división.

El operador módulo es útil en muchas aplicaciones, como determinar si un número es par o impar:

```js
let numero = 7;

if (numero % 2 === 0) {
  console.log(`${numero} es par`);
} else {
  console.log(`${numero} es impar`);
}

// Resultado: "7 es impar"
```

Ahora vamos a explorar los operadores relacionales.

Estos operadores nos permiten comparar ciertos valores y determinar si cumplen con una relación específica. A continuación, detallamos los operadores principales y sus usos:

1. Mayor que (>): Compara si un valor es mayor que otro.
2. Menor que (<): Compara si un valor es menor que otro.
3. Mayor o igual que (>=): Verifica si un valor es mayor o igual a otro.
4. Menor o igual que (<=): Verifica si un valor es menor o igual a otro.
5. Igualdad (==): Compara si dos valores son iguales, sin importar el tipo de dato.
6. Estrictamente igual (===): Compara si dos valores son iguales y también del mismo tipo.
7. Diferente de (!=): Compara si dos valores son diferentes, sin importar el tipo de dato.
8. Estrictamente diferente (!==): Compara si dos valores son diferentes y también de distinto tipo.

Ejemplos de los operadores relacionales:

Mayor y menor que (> y <):

```js
console.log(10 > 5); // true
console.log(3 < 7); // true
console.log(5 > 8); // false
```

Mayor o igual que y menor o igual que (>= y <=)

```js
console.log(10 >= 10); // true
console.log(5 <= 10); // true
console.log(8 >= 12); // false
```

igualdad (==) vs. Estrictimante igual (===)

```js
console.log(5 == "5"); // true (compara solo valores, no tipos)
console.log(5 === "5"); // false (compara valores y tipos)

console.log("true" == true); // false
console.log(true === true); //true
```

Diferente de (!=) vs. Estrictamente diferente (!==):

```js
console.log(5 != "5"); // false (compara solo valores, ignora tipos)
console.log(5 !== "5"); // true (compara valores y tipos)
console.log(10 != 20); // true
console.log(10 !== 20); // true
```

Notas importantes:

- Los operadores relacionales siempre devuelven un valor booleano (true o false), dependiendo de si la comparación es verdadera o falsa.

- El uso de === y !== es preferido sobre == y != en JavaScript porque evita problemas con la conversión automática de tipos (coerción).

Con esto hemos cubierto los operadores relacionales y cómo se usan en comparación de valores. 😊

### Un igual, dos iguales y tres iguales

Es muy importante entender la diferencia entre un signo igual (=), dos iguales (==) y tres iguales (===) en JavaScript. Desde que comenzamos a trabajar con variables, aprendimos que:

1. Un igual (=): Se utiliza para la asignación de valores. Es decir, lo que está del lado derecho de la expresión se evalúa y el resultado se asigna a la variable que está del lado izquierdo.

Ejemplo de asignación (=):

```js
let a = 5; // Se asigna el valor 5 a la variable "a'
console.log(a): // Salida: 5
```

2. Dos iguales (==): Se usan para la comparación de valores. Este operador realiza una comparación menos estricta, porque permite la conversión de tipos (coerción). Por ejemplo, compara un número con una cadena y considera que son iguales si el valor es el mismo, incluso si los tipos no coinciden.
   Ejemplo de comparación con ==:

```js
let b = "5"; //string
console.log(b == 5); // true, porque realiza una conversión implícita.
```

3. Tres iguales (===): Se utilizan para la comparación estricta, ya que verifican tanto el valor como el tipo de los datos. Si los tipos no coinciden, el resultado será false.
   Ejemplo de comparación estricta con ===:

```js
let c = "5"; //string
console.log(c === 5); // false, porque los tipos no coinciden.
```

| Operador | Propósito              | Comportamiento                                |
| -------- | ---------------------- | --------------------------------------------- |
| =        | Asignación             | Asigna el valor de la derecha a la izquierda. |
| ==       | Comparación de valores | Realiza coerción de tipos si es necesario.    |
| ===      | Comparación estricta   | No realiza coerción; compara valores y tipos. |

En JavaScript, la buena práctica nos dice que siempre utilicemos la comparación estricta (===). El operador de comparación débil (==) es considerado una mala práctica, ya que realiza una conversión implícita de tipos (coerción), lo que puede generar resultados inesperados y errores difíciles de rastrear.

### Operadores de Incremento y Decremento

Los operadores de incremento (++) y decremento (--) son herramientas esenciales en JavaScript que permiten modificar el valor de una variable, generalmente utilizada para controlar flujos, bucles o contadores en la programación. Estos operadores incrementan o disminuyen el valor de una variable en una unidad.

Ejemplo con Incremento:

```js
let incremento = 5; // Declaramos una variable con valor inicial 5

incremento++;
console.log(incremento); // 6
```

Pre-Incremento vs Post-Incremento

- Post-Incremento (x++): Utiliza el valor actual de la variable y luego incrementa.
- Pre-Incremento (++x): Incrementa primero y luego utiliza el nuevo valor.

```js
let a = 10;
console.log(a++); //imprime 10, luego incrementa a 11
console.log(a); // imprime 11

let b = 10;
console.log(++b); // Incrementa a 11 y luego imprime 11
console.log(b); // Imprime 11
```

Ejemplo con Decremento

```js
let decremento = 10; // Declaramos una variable con valor inicial 10

decremento--;
console.log(decremento); //9

--decremento; // Disminuye el valor en 1 antes de usarlo
console.log(decremento); // 8
```

### Uso en Bucles

Estos operadores son muy comunes en bucles, como en un for:

```js
for (let i = 0; i < 5; i++) {
  console.log(`Iteración: ${i}`);
}
```

Resumen

- x++ y x--: Operadores de post-incremento y post-decremento.
- ++x y --x: Operadores de pre-incremento y pre-decremento.

Estos operadores son ideales para manejar contadores de forma concisa y clara, especialmente en estructuras de control como bucles.

### Operadores Lógicos en JavaScript

En JavaScript, principalmente contamos con tres tipos de operadores lógicos que nos permiten realizar evaluaciones combinadas de condiciones y devolver un valor booleano. Estos son:

1. AND (&&): Retorna true si ambas condiciones son verdaderas.
2. OR (||): Retorna true si al menos una de las condiciones es verdadera.
3. NOT (!): Niega (invierte) el valor de la condición.

Ejemplo del operador AND (&&):

```js
let edad = 25;
let tieneLicencia = true;

// Ambas condiciones deben ser verdaderas
if (edad >= 18 && tieneLicencia) {
  console.log("Puedes conducir.");
} else {
  console.log("No puedes conducir.");
}
```

Ejemplo del operador OR (||):

```js
let esEstudiante = true;
let tieneDescuento = false;

// Al menos una condición debe ser verdadera
if (esEstudiante || tieneDescuento) {
  console.log("Tienes acceso al descuento.");
} else {
  console.log("No tienes acceso al descuento.");
}

// Salida: "Tienes acceso al descuento."
```

Ejemplo del operador NOT (!):

```js
let estalloviendo;
// Niega el valor
if (!estalloviend) {
  console.log("Puedes salir sin paraguas.");
} else {
  console.log("Es mejor llevar un paraguas.");
}
// Salida: "Es mejor llevar un paraguas."
```

Combinación de Operadores Lógicos

También puedes combinar estos operadores para realizar evaluaciones más complejas.

```js
let edad = 20;
let esSocio = true;
let tieneInvitacion - false;
// Combinación de operadores
if ((edad >= 18 && esSocio) || tieneInvitacion) {
console. log("Puedes ingresar al evento.");
} else {
console.log("No puedes ingresar al evento.");
}
// Salida: "Puedes ingresar al evento."
```

Resumen

- && (AND): Todas las condiciones deben ser verdaderas.

- || (OR): Al menos una condición debe ser verdadera.

- ! (NOT): Invierte el valor de la condición.

Estos operadores son esenciales para construir lógica condicional en cualquier programa.

En este video hemos visto operadores aritméticos, operadores relacionales, operadores de incremento y decremento, entre ellos los operadores unarios, y cuándo es mejor utilizarlos y cuándo no. Finalmente, hemos visto los operadores lógicos.
