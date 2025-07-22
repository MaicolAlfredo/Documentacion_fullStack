## 21. Arrow Functions

Las _arrow functions_ son una implementación que ha mejorado, sobre todo, la manera en que escribimos código. Es más expresivo y sintético. Incluso, para alguien que no conozca mucho la sintaxis del lenguaje de programación, resulta claro y se entiende el tipo de expresiones que podemos lograr con las arrow functions o funciones flecha. Además, hay varias características que iremos viendo a lo largo de este vídeo. Primero, es una nueva forma de definir funciones anónimas, y muy importante, funciones anónimas que sean expresadas. Recuerden que veremos la diferencia entre funciones declaradas y expresadas en la clase particular sobre funciones. Sin embargo, las funciones flecha son una nueva forma de definir una función anónima. Recuerden que cuando creamos una función expresada, esta se genera cuando a una variable le asignamos el valor de una función anónima.

```js
const saludar = function () {
  console.log("Hola");
};

saludar();
```

salida en la terminal

```bash
Hola
```

ahora cuál es la característica que al no ser una función declarada recuerde que una función declarada es simplemente sería:

```js
function saludar() {
  console.log("Hola");
}

saludar();
```

Cuando se tiene una función declarada, la invocación puede realizarse incluso antes de que la función esté declarada. Esto es posible porque JavaScript realiza el proceso de hoisting también en las funciones. Sin embargo, cuando se tiene una función expresada, por ejemplo, si se intenta invocar antes de la declaración, esto producirá un error, porque aún no se ha declarado esa función expresada guardada en la variable. Recuerden que todo esto ya lo hemos visto con más detalle en la clase sobre funciones. Muy bien, ahora, una arrow function simplemente requiere quitar la palabra function y, entre el paréntesis y la llave, declarar un igual y un mayor que (=>), que es lo que forma la flecha. Observen que así se ha logrado que la función siga funcionando, valga la redundancia. Es, entonces, una nueva manera de expresar.

```js
const saludar = () => {
  console.log("Hola");
};

saludar();
```

Ahora bien, cuando tu función tiene una sola línea de instrucción, como en este caso console.log("hola"), se pueden omitir las llaves y dejar la arrow function directamente así. Entonces, es a lo que me refiero cuando digo que se vuelve más expresivo.

```js
const saludar = () => console.log("Hola");
saludar();
```

Para recibir parámetros, una arrow function simplemente requiere que los pongamos entre paréntesis. Por ejemplo, imaginen que aquí voy a saludar a una persona; entonces, pido el nombre, y luego, acá, "Hola", y saludamos a lo que el usuario nos pase.

```js
const saludar = (nombre) => console.log(`Hola ${nombre} `);
saludar("Irma");
```

Cuando una arrow function no recibe parámetros, entonces, forzosamente, tenemos que incluir los paréntesis, como el primer caso. En cambio, cuando una arrow function recibe un parámetro, ya no es necesario poner los paréntesis. Observen cómo, de nueva cuenta, la expresión se vuelve más concisa. La variable saludar es igual a una arrow function que recibe como parámetro "nombre" y que lo transforma en esta sintaxis. Y ahora, esto también es un retorno implícito.

```js
const saludar = (nombre) => console.log(`Hola ${nombre} `);
saludar("Irma");
```

Vamos a crear una variable que se llame `sumar`. La voy a expresar como una función anónima que recibe como parámetros (a, b). Dentro de la función, declaramos `return a + b`. Para que esto se muestre en la consola, debo incluir la ejecución de mi función sumar dentro de un `console.log(sumar(2, 3))`. Ahí está. En la programación funcional, donde solemos enviar parámetros, transformarlos en una instrucción de código y luego devolverlos, las _arrow functions_ juegan un papel muy importante. Esto se debe a que nos permiten realizar ese retorno implícito y tener todo en una sola línea de código. De esta forma, así como nos evitamos escribir la palabra `function`, también podemos evitar escribir la palabra `return`.

```js
const sumar = function (a, b) {
  return a + b;
};

console.log(sumar(2, 3));
```

salida en la terminal:

```
5
```

Entonces, miren, esto quedaría de la siguiente manera: la función sumar recibe dos parámetros (a, b), y podemos devolver la suma de estos dos parámetros sin la necesidad de declarar return. La escritura se vuelve más expresiva en las arrow functions.

```js
const sumar = (a, b) => a + b;
```

Cuando una función expresada en forma de arrow function tiene varias líneas de código, entonces hay que respetar el cuerpo de la función, como si fuera una función normal. En este caso, al tener más de una línea de código, ya no se puede hacer un retorno implícito, por lo que, forzosamente, tiene que llevar llaves.

```js
const funcionDeVariasLineas = () => {
  console.log("Uno");
  console.log("Dos");
  console.log("Tres");
};

funcionDeVariasLineas();
```

Las arrow functions también son muy interesantes, por ejemplo, en los arreglos para iterar sobre los elementos. Tengo un arreglo que se llama números, el cual será igual a un arreglo que contiene estos números. Debo iterar sobre cada uno de los números de ese arreglo e imprimirlos en pantalla. Para ello, tenemos el método forEach de los arreglos. ¿Qué es lo que hace el método forEach? El método forEach recibe una función donde puede recibir el elemento que está recorriendo del arreglo, la posición (elemento, índice), y dentro de la función declarar algo.

También puedo transformarlo a una arrow function, lo que resulta más expresivo, limpio y legible en el código.

```js
const numeros = [1, 2, 3, 4, 5];

/* numeros.forEach(function (el, index) {
console.log(`El elemento ${el} esta en la posicion ${index}`);
}); */
numeros.forEach((el, index) => {
  console.log(`${el} esta en la posicion ${index}`);
});
```

Otra característica muy importante de las arrow functions es la gestión del this. Recuerden que, en los objetos, vimos una palabra reservada que se llama this, y this hace referencia al objeto o al contexto en el que nos encontramos. En JavaScript, existen distintos tipos de contextos; por ejemplo, está el contexto global, al crear una función ahí existe un contexto, al crear un objeto ahí existe un contexto, e incluso al crear un bloque, como por ejemplo de llaves, ahí se está creando un contexto. Esto es muy importante, sobre todo cuando pasemos a la parte de programación orientada a objetos; lo entenderán más a detalle, por ejemplo, cuando hagamos nuestros primeros constructores de prototipos. Una de las características que tienen las funciones es que capturan el objeto desde el contexto en el que se encuentran. ¿A qué me refiero con esto? Quiero que vean que, por ejemplo, si creo una función declarada que se llame perro y envío a la consola el objeto this, como la función existe dentro del contexto del navegador, this se vuelve el objeto window, que es el objeto del DOM que representa la ventana del navegador.

```js
function Perro() {
  console.log(this);
}

Perro();
```

Pero, por ejemplo, imaginen que en lugar de tener una función, tengo un objeto. Por ejemplo, perro tendrá "nombre" y una función que se llame ladrar que, dentro, tenga un console.log(this). Observen cómo this en este contexto es el objeto, a diferencia del ejemplo anterior, donde directamente imprime el console.log(this). Aquí me está indicando que this hace referencia a este objeto, y me está devolviendo el objeto que tiene dos propiedades: nombre y ladrar, que es una función.

```js
const perro = {
  nombre: "kenai",
  ladrar: function () {
    console.log(this);
  },
};

perro.ladrar();
```

Ahora bien, ¿qué pasa si transformo el método ladrar del objeto a una arrow function? Observen cómo el objeto this ya no es el objeto perro, sino que vuelve a comportarse como la función Perro. Justamente por eso les puse una función declarada que se llama Perro, para que vieran cómo la función pertenece al contexto global. Por eso, dentro de la función, this es el objeto window. Entonces, para que al llegar a esta parte entendieran un poco el concepto de lo que hacen las arrow functions: las arrow functions tienen la capacidad de capturar el contexto del objeto en el que se encuentran. Por lo tanto, hay que tener mucho cuidado con utilizar arrow functions para declarar métodos dentro de objetos literales, porque podemos tener este pequeño problema.

```js
const perro = {
  nombre: "kenai",
  ladrar: () => {
    console.log(this);
  },
};

perro.ladrar();
```

Observen que una función normal respeta el contexto en el que se encuentra. Entonces, para esta función, this es el objeto. Pero esa es una de las características que vienen a romper las arrow functions: cuando cambio esta función de anónima normal a una arrow function, tiene la capacidad de saltarse el contexto en el que está (que, en este caso, es el objeto) y heredar o reconocer el contexto donde se encuentra su objeto padre en el que ha sido declarado. Entonces, esa es una parte muy importante de las arrow functions. Es muy importante porque, por ejemplo, cuando estamos trabajando en React y creamos un componente basado en clases y luego generamos métodos que queremos asociar a algún evento de ese componente, de repente, el código indica: "Oye, no encuentro el objeto this". Entonces, hay que hacer un proceso que se llama enlazar el contexto a través, por ejemplo, de bind, call, apply, que son funciones que nos permiten enlazar otros contextos a un método o a un objeto. Por ejemplo, ahí es muy cómodo que, para no tener que estar enlazando cada uno de los métodos en el constructor de la clase, es más fácil utilizar una arrow function. Entonces, esto es justamente así: si tú sabes cómo funcionan perfectamente todo esto del contexto de this y las arrow functions, le puedes sacar mucho provecho. Por ejemplo, aquí, en la arrow function dentro del objeto, no me sirve mucho. Imaginen que quisiera aquí hacer que muestre un mensaje que diga "Kenai ladra". No puedo ponerle this.nombre porque la arrow function está ignorando el contexto del objeto y se está yendo directamente al contexto donde se encuentra ese objeto, que, en este caso, es window, la ventana del navegador.

Pero recuerden también que, incluso en la clase anterior, donde estuve hablando de nuevas características de los objetos literales, realmente no se debería crear un método a partir de una arrow function dentro de un objeto literal. No es una buena práctica porque, aparte, tenemos este problema del contexto `this`. Entonces, recuerden la clase anterior, yo les dije que los métodos en un objeto literal simplemente se crean así:` ladrar() {...}`. Quiero que vean que cuando defino este método `ladrar` con la nueva sintaxis (que es quitar los dos puntos y quitar la palabra function) y no lo hago con la arrow function, sino con esta nueva expresión, observen cómo esta forma de expresar los métodos en los objetos literales sí reconoce el contexto donde se encuentran. Vean que, nuevamente aquí, `this` vuelve a ser el objeto en sí mismo.

```js
const perro = {
  nombre: "kenai",
  ladrar() {
    console.log(this);
  },
};
perro.ladrar();
```

Bueno, pues, prácticamente esas son las arrow functions. Entonces, de ahora en adelante, cada vez que me veas utilizar en el curso, por ejemplo, métodos de los arreglos como forEach, map, reduce, filter o, por ejemplo, más adelante, cuando veamos los temporizadores: setTimeout y setInterval (que son funciones que reciben otras funciones como parámetros), en lugar de estar generando funciones anónimas, ahora me verán ejecutar estas nuevas sintaxis, que son las funciones flecha o las arrow functions. También, cuando lleguemos a la parte de la programación orientada a objetos, por ejemplo, todo este contexto que les di, esta explicación de, por ejemplo, un componente de clase en React, ahí lo vamos a entender bien, porque cuando lleguemos a la parte de programación orientada a objetos, voy a empezar con prototipos, funciones constructoras, y ya luego llegaremos a ver lo que son las clases en JavaScript. Ahí también veremos el uso de funciones anónimas o las arrow functions, y ahí veremos qué es lo que nos conviene.
