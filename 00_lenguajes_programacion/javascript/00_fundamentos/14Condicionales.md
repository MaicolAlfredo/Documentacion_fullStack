## 14. Condicionales 33:55

En la clase anterior vimos diferentes tipos de operadores: incremento y decremento, aritméticos, lógicos y relacionales. Les mencioné que en esta clase comenzaríamos a estudiar las estructuras de control, iniciando con las condicionales.

¿Qué es una estructura de control?

Una estructura de control es un mecanismo que permite controlar el flujo de ejecución de tu programa. Hasta ahora, todas las líneas de código que hemos escrito son estructuras secuenciales, es decir, se ejecutan una después de otra de forma lineal. Sin embargo, llegará un momento en el que necesitemos tomar decisiones en función de una condición o repetir ciertas acciones.

En las estructuras de control tenemos tres tipos principales:

1. Secuenciales: Se ejecutan una línea tras otra.

2. Condicionales: Dependiendo de la evaluación de una condición, se ejecutan unas acciones u otras.

3. Repetitivas (loops): Permiten repetir un bloque de código varias veces (las veremos en la próxima clase).

Estructuras condicionales: if-else

Un if-else nos permite tomar decisiones en función de una condición. Si esta condición se cumple, se ejecutan ciertas acciones; de lo contrario, se ejecutan otras.

Ejemplo: Mayoría de edad

```js
let edad = 17;

if (edad >= 18) {
  console.log("Eres mayor de edad");
} else {
  console.log("Eres menor de edad");
}
```

En este ejemplo:

- Si edad es mayor o igual a 18, se imprime "Eres mayor de edad".
- Si no, se imprime "Eres menor de edad".

Condicionales anidadas: if-else-if

Las condicionales se pueden anidar para evaluar múltiples condiciones.

Ejemplo: Saludos según la hora

```js
let hora = 5;

if (hora >= 0 && hora <= 5) {
  console.log("Dejame dormir");
} else if (hora >= 6 && hora <= 11) {
  console.log("Buenos días");
} else if (hora >= 12 && hora <= 18) {
  console.log("Buenas tardes");
} else {
  console.log("Buenas noches");
}
```

En este caso:

1. Si la hora está entre 0 y 5, se imprime "Déjame dormir".
2. Si está entre 6 y 11, se imprime "Buenos días".
3. Si está entre 12 y 18, se imprime "Buenas tardes".
4. En cualquier otro caso, se imprime "Buenas noches".

Operador ternario

El **operador ternario** es una forma simplificada de escribir un if-else en una sola línea.

Sintaxis:

```
condicion ? expresión_si_verdadero : expresión_si_falso
```

Ejemplo: Mayoría de edad con operador ternario.

```js
let edad = 17;
console.log(edad >= 18 ? "Eres mayor de edad" : "Eres menor de edad");
```

Estructura switch-case

La estructura switch-case es útil cuando necesitamos evaluar diferentes valores para una misma variable.

Sintaxis:

```js
switch (variable) {
  case valor1:
    //código a ejecutar si variable === valor 1
    break;
  case valor2:
    //código a ejecutar si variable === valor 2
    break;
  default:
    //Código a ejecutar si ningún caso coincide
    break;
}
```

Ejemplo : Clasificacion de frutas

```js
let fruta = "Manzana";

switch (fruta) {
  case "Manzana":
    console.log("Es una manzana");
    break;
  case "Plátano":
    console.log("Es un plátano");
  case "naranja":
    console.log("Es una naranja");
    break;
  default:
    console.log("Fruta no reconocida");
    break;
}
```

En este caso:

- Si fruta es "manzana", imprime "Es una manzana".
- Si fruta es "plátano", imprime "Es un plátano".
- Si no coincide con ninguno de los casos, imprime "Fruta no reconocida".

Importante:

- break: Detiene la ejecución dentro del switch y evita que se ejecuten los demás casos.
- default: Es opcional y se ejecuta si ninguno de los casos coincide.

Con estas estructuras de control básicas (if-else, operador ternario y switch-case), podemos empezar a tomar decisiones en nuestros programas. En la próxima clase, veremos las estructuras repetitivas para realizar acciones de manera iterativa.
