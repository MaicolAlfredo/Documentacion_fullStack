## 10. Funciones

En la clase anterior terminamos de ver los tipos de datos primitivos: string, number, boolean, y los tres últimos, particulares de JavaScript: undefined, Null y NaN (Not a Number). Ahora vamos a empezar a trabajar con los tipos de datos compuestos o complejos. Comenzaremos con las funciones, porque los objetos y los arreglos suelen necesitar el uso de funciones. Por eso considero que lo mejor es empezar con este tipo de datos.

En los lenguajes de programación, generalmente, la mayoría de las acciones suceden dentro de funciones. ¿Qué es una función? Simplemente, es un bloque de código autocontenido, es decir, que tiene su propio contenido independiente del ámbito global. Hablamos de esto cuando vimos las variables y su alcance. Una función se define una sola vez y puede ejecutarse en cualquier momento. En otras palabras, es un fragmento de código que puedes declarar una vez y reutilizar tantas veces como sea necesario.

Además, una función puede o no recibir parámetros, que son datos separados por comas, y también puede devolver valores o no, según el caso.

Particularmente en JavaScript, las funciones son un tipo de dato especial, ya que también se consideran objetos. En el ámbito técnico de JavaScript, se dice que las funciones son "ciudadanos de primer orden" o "de primera clase". ¿Qué significa esto? Que las funciones en JavaScript son muy poderosas, ya que pueden asignarse como valores, pasarse como argumentos e incluso devolverse como resultado de otras funciones. Imagina que dentro de una función, en lugar de retornar una cadena de texto, un número o un valor booleano, puedes retornar la ejecución de otra función.

Desde ECMAScript 2015 (ES6), tenemos muchas características interesantes en el manejo de funciones. Un ejemplo de ello son las funciones flecha o arrow functions, que no veremos en este vídeo porque primero necesitamos entender otros conceptos, como la palabra reservada this.

Vamos a ver los conceptos básicos de una función y las diferentes formas de declararla o expresarla. Existen dos maneras principales de crear funciones en JavaScript: funciones declaradas y funciones expresadas. También veremos la diferencia entre usar una u otra.

Primero, observemos una función declarada. Para trabajar con una función declarada, usamos la palabra reservada function. Una función siempre llevará paréntesis y llaves {}, y dentro de las llaves estará el cuerpo de la función. Además, hay que darle un nombre. Por ejemplo, "estoEsUnaFunción". Como mencioné, una función es un bloque de líneas de código que se ejecutan al unísono.

Imaginemos que quiero que esta función ejecute varios mensajes en la consola, por ejemplo:

```js
function estoEsUnaFuncion() {
  console.log("uno");
  console.log("dos");
  console.log("tres");
}
```

La función ya está declarada, pero todavía no se ha ejecutado. Podemos pensar en ella como un jugador de fútbol que está en la banca: está listo, pero no ha entrado al campo. Para que la función se ejecute (o "entre al campo"), debemos invocarla.

Para invocar una función, basta con llamar su nombre seguido de paréntesis los paréntesis indican en los lenguajes de programación que una función se va a ejecutar, de esta forma:

```js
estoEsUnaFuncion(); //Invocacion de la funcion
```

Si solo llamamos al nombre sin paréntesis, como en estoEsUnaFuncion;, no se ejecutará. Los paréntesis indican que una función debe ejecutarse. En este caso, la salida en la consola será:

```
uno
dos
tres
```

Una función es un bloque de código autocontenido que se define una vez y se puede ejecutar en cualquier momento. Esto significa que, una vez declarada la función, puedes invocarla tantas veces como desees para que realice las mismas acciones.

Por ejemplo, si copio estoEsUnaFuncion() y la ejecuto varias veces, la función se ejecutará tantas veces como la invoque, repitiendo el código en su interior.

Aquí tienes un ejemplo de cómo se vería:

```js
function estoEsUnaFuncion() {
  console.log("uno");
  console.log("dos");
  console.log("tres");
}

//Invocamos la funcion cuatro veces
estoEsUnaFuncion();
estoEsUnaFuncion();
estoEsUnaFuncion();
estoEsUnaFuncion();
```

En este caso, como invocamos estoEsUnaFuncion() cuatro veces, los mensajes "uno", "dos" y "tres" se imprimen en la consola cuatro veces. Esto muestra cómo podemos reutilizar el mismo bloque de código en cualquier momento con solo invocar la función.

Opcionalmente, una función puede aceptar parámetros y devolver valores. Por ejemplo, vamos a declarar una función llamada unaFuncionQueDevuelveValor. Aunque el nombre es algo largo, es explícito para que quede claro su propósito.

Cuando una función devuelve un valor, usamos la palabra reservada return. Por ejemplo:

```js
function unaFuncionQueDevuelveValor() {
  return "La funcion ha retornado una cadena de texto";
}
```

En este caso, la función unaFuncionQueDevuelveValor devuelve la cadena "La función ha retornado una cadena de texto" cuando se ejecuta. Una función puede devolver cualquier tipo de datos, ya sean primitivos o compuestos.

Para comprobar que realmente devuelve este valor, podemos asignar el resultado de la función a una variable y luego imprimirlo en la consola:

```js
let valorDeLaFuncion = unaFuncionQueDevuelveValor();
console.log(valorDeLaFuncion);
```

La salida en la consola será:

```
La funcion ha retornado una cadena de texto
```

Esto muestra que el valor retornado por la función se asigna correctamente a la variable valorDeFuncion.

Ejemplo de uso de return en una función con varios console.log

Supongamos que nuestra función tiene varios console.log y queremos ver cómo return afecta su ejecución.

```js
function otraFuncion() {
  console.log("uno");
  return 19; //Devuelve 19 y termina la funcion
  console.log("dos");
  console.log("tres");
}
```

Si ejecutamos otraFuncion() y observamos la consola:

```js
let resultado = otraFuncion();
console.log("valore retornado:", resultado);
```

La salida en la consola será:

```
uno
valor retornado: 19
```

Explicación: Al encontrar el primer return dentro de la función (en este caso, return 19;), el intérprete deja de ejecutar el resto del código que está debajo. Es decir, las líneas console.log("Dos") y console.log("Tres") no se ejecutan porque return termina la función y devuelve el valor inmediatamente.

Resumen:

Cuando la función encuentra un return, ignora cualquier línea de código que esté después de él y termina su ejecución, devolviendo el valor especificado. Esto hace que return sea una herramienta útil para controlar el flujo de una función y determinar el momento en que debe finalizar su ejecución.

Ahora, vamos a ver cómo una función también puede aceptar parámetros. Pero, ¿qué significa que una función acepte parámetros? Básicamente, es la manera en que una función puede recibir valores externos para trabajar con ellos internamente.

Por ejemplo, vamos a crear una función llamada saludar:

```js
function saludar() {}
```

En este caso, la función saludar aún no recibe ningún parámetro. Ahora vamos a modificarla para que reciba dos valores, que serán el nombre y la edad:

```js
function saludar(nombre, edad) {}
```

Aquí, nombre y edad son los parámetros de la función. Estos funcionan como variables dentro de la función, y los valores que se les asignen serán utilizados para ejecutar alguna acción específica. En este caso, vamos a usarlos para formar un mensaje de saludo.

Imaginemos que esta función, como su nombre indica, es para saludar. Vamos a usar template strings (cadenas con plantillas) para construir un mensaje. Los template strings permiten incrustar variables directamente en el texto utilizando el símbolo `${}`. Así, en nuestra función saludar, agregaremos un console.log que muestre el siguiente mensaje:

```js
function saludar(nombre, edad) {
  console.log(`Hola, mi nombre es ${nombre} y tengo ${edad} años`);
}
```

Con esta estructura, la función saludar puede recibir un nombre y una edad para usarlos en el mensaje de saludo.

Ejemplo de uso de la función con parámetros

Vamos a llamar a la función saludar pasándole dos argumentos: "Kenai" y 7. Imaginemos que queremos saludar a Kenai, que tiene 7 años:

```js
saludar("kenai", 7);
```

La salida en la consola será:

```
Hola mi nombre es kenai y tengo 7 años
```

Explicación: La función saludar ha recibido los valores "Kenai" como nombre y 7 como edad, y los ha insertado en el mensaje de saludo.

De esta forma, al aceptar parámetros, las funciones se vuelven más flexibles y reutilizables, ya que pueden adaptarse a diferentes valores y situaciones cada vez que se invocan.

Ahora, ¿qué pasa si ejecuto la función saludar() sin pasarle parámetros?

```js
saludar();
```

Nos dará como resultado:

```
Hola mi nombre es undefined y tengo undefined años.
```

Esto sucede porque, al no pasarle valores a nombre y edad, JavaScript asigna automáticamente el valor undefined a cada parámetro. En otros lenguajes, ya existía la posibilidad de asignar valores por defecto a los parámetros de una función, pero en JavaScript esta funcionalidad fue agregada a partir de ES6 (2015).

Para asignar un valor por defecto a los parámetros de una función en JavaScript, simplemente igualamos el parámetro a un valor deseado dentro de su declaración. Por ejemplo:

```js
function saludar(nombre = "Desconocido", edad = 0) {
  console.log(`Hola, mi nombre es ${nombre} y tengo ${edad} años`);
}
```

En esta versión, si llamamos a saludar sin pasarle argumentos, los parámetros nombre y edad tendrán automáticamente los valores "Desconocido" y 0, respectivamente.

Invocación sin pasar argumentos:

```js
saludar();
```

La salida será:

```
Hola, mi nombre es Desconocido y tengo 0 años.
```

la función utiliza los valores por defecto para nombre y edad, ya que no se le pasaron argumentos.

Esta característica es útil para manejar casos en los que algunos argumentos pueden ser opcionales.

Vamos a crear una función declarada:

```js
function funcionDeclara() {
  console.log(
    "Esto es una funcion declarada que puede invocarse en cualquier momento"
  );
}
```

Este tema se conoce como funciones declaradas versus funciones expresadas. Recuerden que JavaScript es un lenguaje interpretado, lo cual significa que no necesita una fase de compilación separada; en cambio, interpreta el código durante la ejecución.

Vean que aquí tenemos una función declarada llamada funcionDeclarada. Si ejecuto esta función después de su declaración, se ejecutará de manera lógica, ya que hemos declarado e invocado la función en el orden esperado. Por ejemplo:

```js
functionDeclarada(); // llamada despues de la declaracion
// salida: Esto es una funcion declarada que puede invocarse en cualquier momento
```

Invocación antes de la declaración

Sin embargo, ¿qué pasa si invocamos la función antes de declararla? Veamos el siguiente ejemplo:

```js
functionDeclarada();
function funcionDeclara() {
  console.log(
    "Esto es una funcion declarada que puede invocarse en cualquier momento"
  );
}
```

salida:

```
Esto es una funcion declarada que puede invocarse en cualquier momento
```

Explicación del comportamiento

¿Por qué esto es posible? Esto ocurre debido a un mecanismo en JavaScript llamado hoisting o elevación. Este mecanismo permite que las funciones declaradas se "eleven" o se muevan al comienzo de su ámbito, lo que permite que sean invocadas antes de su declaración física en el código.

JavaScript procesa primero las declaraciones de funciones y variables antes de ejecutar el código. Así, en este caso, JavaScript "eleva" la declaración de funcionDeclarada al comienzo del archivo o bloque de código, lo que permite que la función sea accesible en cualquier lugar del código, incluso antes de la línea donde se define.

Por lo tanto, si alguna vez escuchas a un colega decir "No importa dónde declares una función en el archivo, siempre puedes invocarla en cualquier parte", esto se debe a que JavaScript realiza un hoisting de las funciones declaradas.

Hay otra manera de declarar funciones en JavaScript, y es utilizando funciones expresadas, es decir, asignando una función a una variable de manera dinámica. Por ejemplo, en este caso, utilizaremos const para declarar la variable, ya que el valor asignado (el cuerpo de la función) no va a cambiar. Es una práctica común en JavaScript declarar funciones expresadas con const en lugar de let.

Veamos un ejemplo:

```js
const funcionExpreseda = function () {
  console.log("Esto es una funcion expresada");
};
```

Aquí, funcionExpresada es una función asignada a una variable constante. Como es una función expresada, no es necesario darle un nombre en la declaración (function). En este caso, el nombre de

la función ya está dado por la variable funcionExpresada. Este tipo de función sin nombre explícito en la declaración se conoce como función anónima.

Arrow Functions

Para programadores más experimentados, cabe mencionar que también podemos definir esta función utilizando arrow functions. Por ejemplo:

```js
const funcionExpreseda = () => {
  console.log("Esto es una funcion expresada con arrow function");
};
```

Aquí, estamos usando la sintaxis de arrow function, introducida en ES6, que es una forma más concisa de escribir funciones en JavaScript. Sin embargo, en este curso estamos comenzando desde lo básico, y el objetivo es avanzar paso a paso hasta llegar a un nivel avanzado, de modo que si estás aprendiendo por primera vez, puedas adquirir las habilidades necesarias para trabajar como programador web.

Simplemente, estamos creando una función sin nombre, por eso se llama función anónima; es una función que no tiene nombre y que estamos asignando como valor a una variable. Observa el siguiente ejemplo:

```js
const funcionExpreseda = function () {
  console.log("Esto es una funcion expresada");
};
```

Para invocar esta función, usamos:

```js
funcionExpreseda(); // salida: Esto es una funcion expresada
```

Si intentamos invocar funcionExpresada antes de definirla, el resultado será un error:

```js
funcionExpresada(); //Error: Uncaught ReferenceError: funcionExpresada is not defined
```

Esto se debe a que, al utilizar funciones expresadas, no podemos acceder a la función antes de su inicialización. A diferencia de las funciones declaradas, JavaScript no eleva (o realiza el "hoisting" de) las funciones expresadas.

Diferencias entre Funciones Declaradas y Expresadas

La diferencia entre declarar una función (como función declarada) y crear una función como función expresada (asignada a una variable) radica en cómo el hoisting funciona en JavaScript. Al declarar una función con function nombreFuncion() {}, JavaScript permite que sea invocada en cualquier parte del código, incluso antes de que esté declarada en el archivo. En cambio, al crear una función expresada, esta no puede invocarse antes de su inicialización, lo que evita errores de referencia si el código no está ordenado.

Buenas Prácticas

Ambas opciones son válidas en JavaScript. Sin embargo, es recomendable ordenar el código, de modo que las funciones sean declaradas antes de su invocación, especialmente en aplicaciones grandes o complejas. Esto hace que el código sea más legible y predecible. Además, con la creciente popularidad de librerías y frameworks reactivos como Angular, Vue, y ReactJS, se ha vuelto más común utilizar funciones expresadas, pues esto ayuda a evitar errores de referencia y hace que el código esté más estructurado.

Si declaramos las funciones como expresadas, estamos obligándonos a inicializarlas antes de su uso, lo cual es una buena práctica en JavaScript, dado que es un lenguaje interpretado. Las funciones expresadas no se pueden utilizar hasta que hayan sido inicializadas, lo que puede evitar errores en la ejecución.

Conceptos Vistos

En este repaso hemos cubierto varios conceptos clave sobre funciones en JavaScript:

Cómo crear una función.

Qué es una función y cómo funciona.

Uso de parámetros y valores por defecto en funciones.

Cómo retornar valores de una función y el uso de la palabra clave return.

Diferencias entre funciones declaradas y expresadas.

Aún hay muchos temas avanzados sobre funciones en JavaScript, como funciones anidadas, closures, patrones de escritura, y arrow functions, una característica útil introducida en el estándar ECMAScript 2015. Sin embargo, los fundamentos que hemos cubierto te permitirán avanzar y entender mejor los tipos de datos compuestos, como los arreglos y objetos, los cuales también pueden contener funciones como valores. Por eso, era importante establecer primero una base sólida sobre las funciones.

En los próximos temas, abordaremos conceptos como arreglos y objetos para ver cómo estos tipos de datos pueden trabajar en conjunto con funciones.
