## 15. Ciclos (Loops)

En el video anterior vimos las estructuras de control que nos ayudan a trabajar con condiciones: if-else, el operador ternario (una simplificación de if-else), estructuras anidadas y el switch. Ahora, abordaremos las estructuras repetitivas (ciclos o bucles), que nos permiten controlar el flujo de nuestra programación repitiendo ciertas acciones mientras se cumple una condición.

Ahora vamos a ver las otras estructuras de control que nos van a permitir controlar el flujo de nuestra programación, y estos son los ciclos o bucles, también conocidos como estructuras repetitivas. Hagan de cuenta que esto es como cuando necesitamos que, dependiendo de que se evalúe cierta condición, tengamos la necesidad de que ciertas líneas de código se ejecuten repetidamente hasta que se cumpla una condición. Sin embargo, aquí también entra en juego el incremento o decremento de alguna variable que modifica ese valor y que hace que dichas líneas de código se repitan hasta que la variable en cuestión alcance el valor deseado, momento en el que el ciclo se detiene.

Vamos a ver primero el while y el do-while. Aunque actualmente estas estructuras están cayendo mucho en desuso, ya que son más propias de una programación imperativa o estructurada. Por otro lado, JavaScript, al ser un lenguaje multi-paradigma, se está orientando cada vez más hacia una programación declarativa. Esto es especialmente evidente cuando trabajamos con paradigmas como la programación orientada a objetos o la programación funcional, donde generalmente buscamos escribir un código más declarativo que imperativo.

Es importante que conozcan estas estructuras, pero en la práctica, cada vez se utilizan menos.

Ciclo while

La primera estructura que vamos a ver es el while:

Ejemplo básico:

```js
let contador = 0;

while (contador < 10) {
  console.log(contador); //Imprime los números de 0 al 9
}
```

Es muy importante entender que este tipo de estructuras repetitivas, también llamadas bucles o ciclos, necesitan que sus iteraciones (cada vuelta que se hace dentro del ciclo repetitivo) incluyan un incremento o decremento en la variable de control. De lo contrario, el ciclo podría ser infinito.

Por ejemplo, para que el ciclo funcione correctamente, debemos incrementar el valor de la variable contador en cada iteración:

```js
let contador = 0;

while (contador < 10) {
  console.log(contador); //Imprime los números de 0 al 9
  contador++;
}
```

En este caso, el ciclo imprime los números del 0 al 9. En cada iteración, la variable contador aumenta en 1. Cuando contador llega a 10, la condición (contador < 10) deja de cumplirse, y el ciclo se detiene.

Existe una variante llamada do-while. Hoy en día, es raro encontrarnos con el uso de bucles controlados mediante while, y hacerlo con do-while es todavía menos común.

Ejemplo de código con do-while:

```js
let contador = 10;

do {
  console.log("do while:" + contador);
  contador++;
} while (contador < 10);
```

¿Cuál es la diferencia entre usar while y do-while?

1. En un while, antes de ejecutar las líneas de código dentro del bucle, la condición debe cumplirse. Si no se cumple, el código no se ejecutará ni una sola vez.

2. En un do-while, el bloque de código dentro del do siempre se ejecuta al menos una vez, incluso si la condición no se cumple. Esto se debe a que la evaluación de la condición ocurre al final del ciclo.

**Explicación del ejemplo:**

En el código anterior:

- Inicialmente, la variable contador tiene un valor de 10.
- Se ejecuta el bloque dentro del do, que imprime do while: 10.
- Luego, la variable contador se incrementa en 1.
- Finalmente, se evalúa la condición (contador < 10). Como contador ahora vale 11, la condición no se cumple, y el bucle termina.

Por lo tanto, el bucle ejecuta su contenido una sola vez, independientemente de que la condición no se cumpla desde el principio.

### for

Ahora, el ciclo o bucle más utilizado es una estructura llamada for. Este ciclo consta de tres partes principales. Cuando trabajamos con el ciclo while, necesitamos:

1. Declarar e inicializar una variable, por ejemplo: let contador = 0.

2. Definir una condición que controle el ciclo, como: (contador < 10).

3. Realizar un incremento o decremento, por ejemplo: contador++;.

El ciclo for agrupa estas tres partes dentro de una sola línea de código, permitiendo un control más eficiente del flujo de programación.

**Estructura del ciclo for:**

Dentro de los paréntesis del for, se deben especificar las siguientes partes, separadas por punto y coma:

1. Inicialización: Declaración e inicialización de la variable que controlará el ciclo.let a = 5; // Se asigna el valor 5 a la variable "a'
   console.log(a): // Salida: 5
2. Condición: Evaluación que determina si el ciclo continúa.
3. Incremento/Decremento: Operación que modifica la variable de control en cada iteración.

El bloque dentro de las llaves {} contiene las sentencias que se ejecutarán en cada iteración del ciclo.

Ejemplo básico de un ciclo for:

```js
for (let i = 0; i < 10; i++) {
  console.log("for: " + i);
}
```

Explicación:

1. Inicialización: let i = 0 define e inicializa la variable i con el valor 0.
2. Condición: i < 10 verifica si el valor actual de i es menor que 10. Si es verdadero, el ciclo continúa; de lo contrario, finaliza.
3. Incremento: i++ aumenta el valor de i en 1 después de cada iteración.

Este código imprimirá en la consola los números del 0 al 9. Cuando i alcance el valor 10, la condición será falsa, y el ciclo se detendrá.

Imagínense que tengo un arreglo de números:

```js
let numeros = [10, 20, 30, 40, 50];
```

Recuerden que en la clase de arreglos vimos que los arreglos tienen un método llamado forEach. Este método recibe una función y permite recorrer y realizar operaciones con cada uno de los elementos del arreglo.

El método forEach es una forma más declarativa de ejecutar un ciclo, ya que abstrae detalles como la inicialización, la condición y el incremento. Sin embargo, también podemos recorrer los elementos de un arreglo utilizando un ciclo for, lo cual es un enfoque más imperativo.

Al usar un ciclo for, necesitamos:

Declarar una variable que controle la posición en el arreglo (por ejemplo, i).

Definir una condición basada en la longitud del arreglo (numeros.length), ya que la cantidad de iteraciones dependerá del número de elementos del arreglo.

Incrementar la variable de control para avanzar a la siguiente posición en el arreglo.

Recuerden que los índices de los arreglos en JavaScript comienzan en 0. Por lo tanto, si un arreglo tiene 5 elementos, las posiciones irán de 0 a 4. Esto se refleja al utilizar la propiedad length del arreglo, que siempre devuelve el número total de elementos, no su último índice.

Ejemplo de ciclo for para recorrer un arreglo:

```js
let numeros = [10, 20, 30, 40, 50];

for (let i = 0; i < numeros.length; i++) {
  console.log(numeros[i]);
}
```

Explicación:

1. Inicialización: let i = 0 establece que comenzaremos en la posición 0 del arreglo.
2. Condición: i < numeros.length asegura que el ciclo se ejecute mientras i sea menor que el número total de elementos en el arreglo.
3. Incremento: i++ aumenta el valor de i en 1 en cada iteración, moviéndose al siguiente elemento del arreglo.

El resultado en la consola será:

```
10
20
30
40
50
```

Desde ECMAScript 2015 (también conocido como ECMAScript 6), surgieron nuevas variantes del ciclo for, llamadas for-of y for-in. Estas variantes están diseñadas para manejar escenarios específicos de iteración.

Ciclo for-in:

El ciclo for-in permite recorrer o iterar las propiedades de un objeto. Es especialmente útil cuando queremos acceder a las claves (nombres de las propiedades) de un objeto.

Ejemplo con un objeto:

```js
const jon = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
};

for (const propiedad in jon) {
  console.log(propiedad);
}
```

Resultado en la consola:

```
nombre
apellido
edad
```

Explicación:

1. Objeto: El objeto jon tiene tres propiedades: nombre, apellido y edad.
2. for-in: Este ciclo recorre las claves del objeto (nombre, apellido, edad) y las imprime en cada iteración.

Si deseas acceder a los valores de las propiedades junto con sus nombres, puedes usar la notación de corchetes ([]) para obtener el valor asociado a cada clave:

Ejemplo para acceder tanto a las claves como a los valores:

```js
for (const propiedad in jon) {
  console.log(`${propiedad}:${jon[propiedad]}`);
}
```

Resultado en la consola:

```
nombre: Jon
apellido: Mircha
edad:35
```

Nota: Aunque el ciclo for-in también puede recorrer índices en un arreglo, no es la opción más recomendada para este propósito. Para arreglos, es mejor usar un ciclo for-of o métodos como forEach.

Ciclo for-of

El ciclo for-of es una variante del for que utiliza la palabra reservada of en lugar de in. La principal diferencia entre for-in y for-of radica en que:

- for-in recorre las propiedades de un objeto.
- for-of recorre los elementos de cualquier objeto que sea iterable en JavaScript.

Ejemplo con un arreglo:

```js
let numeros = [10, 20, 30, 40, 50];

for (const elemento of numeros) {
  console.log(elemento);
}
```

Resultado en la consola:

```
10
20
30
40
50
```

Explicación:

Arreglo: numeros es un arreglo que contiene varios elementos.

for-of: Este ciclo recorre directamente cada elemento del arreglo y los imprime en cada iteración.

El ciclo for-of no se limita a los arreglos; también funciona con otros elementos iterables en JavaScript, como cadenas de texto, mapas (Map), conjuntos (Set), e incluso generadores.

Ejemplo con una cadena de texto:

```js
let cadena = "hola mundo";

for (const caracter of cadena) {
  console.log(caracter);
}
```

Resulado en la consola:

```
h
o
l
a

m
u
n
d
o
```

Explicación:

1. Cadena de texto: Las cadenas son elementos iterables, lo que significa que podemos recorrer cada uno de sus caracteres.
2. for-of: Este ciclo extrae cada carácter de la cadena y lo imprime en la consola en cada iteración.

Diferencias clave:

1. for-in:

- Diseñado para recorrer las propiedades de un objeto.
- Ejemplo: Recorrer las claves de un objeto.

2. for-of:

- Diseñado para recorrer los elementos de cualquier objeto iterable.
- Ejemplo: Recorrer elementos de un arreglo o caracteres de una cadena.

Ambas variantes son útiles, pero su aplicación depende del tipo de dato que se esté trabajando.

Nota: Evita usar for-in para recorrer arreglos, ya que podría devolver índices en lugar de elementos. En cambio, for-of es más apropiado para este caso.
