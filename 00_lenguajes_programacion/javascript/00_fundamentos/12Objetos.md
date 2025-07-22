## 12. Objetos

En la clase anterior nos habíamos quedado viendo los arreglos, que son un tipo de datos compuesto. Ya hemos estudiado funciones y arreglos, y ahora vamos a ver los objetos. Los objetos son una parte muy importante de JavaScript. Existe una frase entre los desarrolladores que dice que "en JavaScript, todo es un objeto". Esto es en gran medida cierto, y se puede ver en algunos ejemplos.

Por ejemplo, cuando vimos los valores primitivos, enseñé una forma (aunque ya no se utiliza con frecuencia) de crear una cadena de texto usando el constructor String. Si quisiera declarar una variable que sea una cadena de esta manera, podría hacerlo así:

```js
let a = new string("Hola mundo");
```

Aquí estamos creando una instancia de un objeto String en lugar de solo definir una cadena literal. Si imprimimos esto en la consola, veríamos que, aunque para nosotros parece una simple cadena de texto, en realidad es un objeto que deriva del prototipo de la clase String.

```js
console.log(a); // Muestra:[String: 'Hola mundo' ]
```

Este objeto a tiene una serie de propiedades y métodos propios de String, como length, toUpperCase(), entre otros, los cuales pueden ser utilizados de inmediato.

Explicación:

- Al usar new String("Hola mundo"), estamos inicializando una nueva instancia del objeto String.

- Aunque el valor subyacente de a es una cadena de texto, en realidad es un objeto String, lo cual se evidencia cuando inspeccionamos a en la consola.

Este ejemplo muestra por qué se dice que en JavaScript "todo es un objeto". Aunque String es un tipo de dato primitivo, JavaScript lo convierte en un objeto temporalmente para permitir el acceso a métodos y propiedades, como length y toUpperCase().

Recuerden lo que comentamos en la clase anterior cuando hablábamos sobre los arreglos. Al inicio de esa clase, les hice un paréntesis sobre que podemos utilizar let o const al declarar variables de valores de tipo compuesto, como objetos y arreglos. En la clase 4, vimos el concepto de lo que es una constante y su uso en JavaScript.

Es importante señalar que sí podemos utilizar const para definir objetos. Por ejemplo, si declaro mi variable b como un objeto de la siguiente manera:

```js
const b = {};
```

Una vez que b ha sido declarada como un objeto, puedo modificar las propiedades internas de b a lo largo de mi programa, pero seguirá siendo el mismo objeto en memoria. Al utilizar const con un objeto, estamos asegurándonos de que la variable b siempre haga referencia a ese mismo objeto inicial, evitando que le asignemos un nuevo valor u objeto completamente diferente.

Ejemplo:

```js
const b = { nombre: "Juan" };
b.edad = 31; //Esto es valido, ya que solo estamos modificado el contendido
console.log(b); // muestra:{nombre:"juan",edad:31}

//Esto provocaria un error:
b = { nombre: "Ana" }; // Error: Assignament to constant variable.
```

Al declarar objetos (o arreglos) con const, estamos evitando que se cambie la referencia a ese objeto en memoria, pero podemos modificar su contenido interno sin problema.

Algunos de ustedes, especialmente aquellos que vienen de otros lenguajes tipados, pueden sentir conflicto al declarar arreglos u objetos con const y podrían preferir let. Esto puede ser subjetivo y depender de lo que les resulte más cómodo. Sin embargo, usar const es una buena práctica cuando trabajamos con objetos que no deseamos reasignar, pues clarifica la intención de que esa referencia no cambiará.

En resumen, al declarar un objeto con const, evitamos que otra referencia reemplace el objeto original en memoria, pero permitimos la modificación de sus propiedades internas.

Así como en la clase anterior vimos que, si coloco corchetes cuadrados ([]) en la consola, JavaScript me indica que es un arreglo vacío, ocurre algo similar si utilizo un par de llaves ({}). Vean que, al hacer esto en la consola, JavaScript lo interpreta como un objeto vacío.

```js
console.log([]); // Salida: []
// JavaScript interpreta esto como un arreglo vacío
console.log({}); // Salida: {}
// JavaScript interpreta esto como un objeto vacío
```

Esto demuestra que los corchetes ([]) se asocian con arreglos y las llaves ({}) con objetos en JavaScript.

Un objeto es una colección de pares de llave-valor. Si has trabajado con CSS, hago esta comparación porque muchos estudiantes, cuando comienzan a programar, piensan que HTML y CSS fue para ellos su primer contacto con la programación. Al empezar a ver las características de los objetos en JavaScript, a menudo dicen: “Profe, esto se parece a una regla de CSS”, y, en cierto sentido, tienen razón. Al escribir un objeto, defines una llave (similar a una propiedad en CSS) y le asignas un valor. En JavaScript, estos pares llave-valor están separados por comas.

Voy a crear un objeto con mis datos, por lo que he nombrado el objeto como jon. Un objeto puede tener diferentes propiedades o valores; recuerden que se trata de pares de llave-valor. En este caso, la estructura es "llave: valor". Un objeto en JavaScript puede tener cualquier tipo de dato como valor de una llave, ¡incluso una función!

Además, un objeto puede contener dentro de sí mismo otro objeto como una propiedad. Veamos el ejemplo completo:

```js
const jon = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
  pasatiempo: ["correr", "hacer ejercicio"],
  soltero: false,
  contacto: {
    email: "jonmircha@gmail.com",
    twitter: "@jonmircha",
  },
  saludar: function () {
    console.log("Hola");
  },
};

// Ejemplo de uso
console.log(jon); // Imprime el objeto completo
jon.saludar(); // Ejecuta la función "saludar" del objeto
console.log(jon.contacto); // Imprime el objeto de contacto interno
console.log(jon.nombre); // Accede y muestra el nombre "Jon"
```

En este ejemplo:

- nombre, apellido, edad, y soltero son propiedades del objeto jon con distintos tipos de datos.

- pasatiempo es un arreglo dentro del objeto.

- contacto es otro objeto dentro de jon.

- saludar es una función como propiedad, la cual se puede invocar usando jon.saludar().

Los atributos no son más que variables dentro de un objeto. Así, nombre, apellido, edad, pasatiempo, soltero y contacto son atributos de mi objeto. Ojo: saludar no es un atributo, ya que, al ser una función, se considera un método y no una propiedad o atributo del objeto.

Veamos el ejemplo en código para ilustrar esto:

```js
// Ejemplo de uso
console.log(jon.nombre); // "Jon" - atributo
console.log(jon.apellido); // "Mircha" - atributo
console.log(jon.edad); // 35 - atributo
console.log(jon - pasatiempo); // ["correr", "hacer ejercicio"] -
console.log(jon.contacto); // ( email: "jonmirchaßgmail.com",
jon.saludar(); // "Hola" - método
```

En este código:

- nombre, apellido, edad, pasatiempo, soltero, y contacto son atributos del objeto jon.

- saludar es un método del objeto, ya que es una función y se invoca con jon.saludar().

Por ejemplo, en la clase anterior vimos el método forEach. Por eso se llama método, porque forEach es una función interna del objeto Array, que es el objeto que define un arreglo en JavaScript. Mientras que length, recuerden, es una propiedad de los arreglos. ¿Por qué? Porque es una variable que nos da el número de elementos que tiene el arreglo.

Quiero que noten la diferencia: mientras que un atributo o propiedad es como una variable dentro del objeto al que pertenece (como length, que devuelve el número de elementos en un arreglo), los métodos son funciones internas del objeto. Por ejemplo, el método fill() y el método of() de los arreglos son funciones que pertenecen al objeto Array. Todos los métodos llevan paréntesis porque, al ser funciones, requieren paréntesis para ser invocados, y, dependiendo de la función, pueden o no necesitar parámetros.

Es importante recordar que dentro de un objeto:

Las variables se llaman atributos o propiedades.

Las funciones se llaman métodos.

Imaginemos que vamos a crear otra función llamada decirMiNombre. Si se dan cuenta, nombre y apellido son llaves de nuestro objeto, y decirMiNombre es una función que también forma parte de este objeto. Cuando necesitemos hacer uso de una propiedad dentro del objeto, podemos utilizar la palabra this.

Quiero que entiendan que this, en inglés, significa "este" y se usa para referirse a una cosa específica en un contexto dado. En este caso, this hace referencia al contexto en el que nos encontramos, que es el objeto en sí. La palabra this se utiliza para hacer referencia al mismo objeto en el que estamos trabajando.

Por lo tanto, si quiero imprimir el nombre del objeto, usaré this.nombre, lo cual significa "desde este objeto, obtén la propiedad nombre".

```js
const jon = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
  pasatiempo: ["correr", "hacer ejercicio"],
  soltero: false,
  contacto: {
    email: "jonmircha@gmail.com",
    twitter: "@jonmircha",
  },
  saludar: function () {
    console.log("Hola");
  },
  decirMiNombre: function () {
    console.log(`Mi nombre es ${this.nombre} ${this.apellido}`);
  },
};

// Llamada a los métodos del objeto
jon.saludar(); // Imprime: Hola
jon.decirMiNombre(); // Imprime: Hola, ne llano Jon Mircha y tengo 35 año
```

En este ejemplo:

- this.nombre, this.apellido, y this.edad hacen referencia a las propiedades del mismo objeto jon.

- La función decirMiNombre utiliza this para acceder a las propiedades internas del objeto y mostrarlas en la consola.

Voy a mostrarles algunos métodos. Por ejemplo, recuerden que Object es el prototipo, o el objeto base en JavaScript, y tiene algunos métodos importantes y útiles.

Uno de estos métodos es keys(), que espera recibir un objeto. El método Object.keys() devuelve todas las llaves (o propiedades) del objeto en forma de un arreglo. En cada posición de este arreglo, se alista una de las llaves del objeto, como nombre, apellido, edad, pasatiempo, etc.

Aquí tienes el ejemplo en código:

```js
const jon = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
  pasatiempo: ["correr", "hacer ejercicio"],
  soltero: false,
  contacto: {
    email: "jonmircha@gmail.com",
    twitter: "@jonmircha",
  },
};
// Utilizando el método Object.keys para obtener las llaves del objeto
console.log(Object.keys(jon));
```

Este código imprimirá en la consola el siguiente arreglo:

```
["nombre", "apellido", "edad", "pasatiempo", "soltero", "contacto"]

```

En este caso, Object.keys(jon) devuelve un arreglo con todas las llaves del objeto jon, lo que puede ser muy útil para conocer las propiedades que contiene un objeto.

De igual manera, existe un método muy similar llamado values(), que, como pueden inferir, devuelve un arreglo, pero en lugar de contener las llaves, contiene los valores correspondientes de cada propiedad del objeto.

Aquí está el ejemplo en código:

```js
const jon = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
  pasatiempo: ["correr", "hacer ejercicio"],
  soltero: false,
  contacto: {
    email: "jonmircha@gmail.com",
    twitter: "@jonmircha",
  },
};
// Utilizando el método Object.values para obtener los valores del objeto
console.log(Object.values(jon));
```

Este código imprimirá en la consola el siguiente arreglo:

```
["Jon", "Mircha", 35, ["correr","hacer ejercicio"], false,
{ email: "jonmircha@gmail.com", twitter: "@jonmircha" }]
```

En este caso, Object.values(jon) devuelve un arreglo con todos los valores de las propiedades del objeto jon.

Otra propiedad interesante es, por ejemplo, hasOwnProperty(). Esta propiedad me permite saber si un objeto tiene una propiedad específica. Por ejemplo:

```js
console.log(jon.hasOwnProperty("nombre"));
```

Este código nos arroja un valor booleano. Lo que hace la propiedad hasOwnProperty es evaluar si el nombre de la propiedad que le he pasado se encuentra dentro de alguna de las llaves de este objeto.

hasOwnProperty("nombre"): Este método verifica si el objeto tiene la propiedad "nombre". En el ejemplo anterior, si el objeto jon tiene la propiedad nombre, devolverá true, de lo contrario, false.

De igual manera, como lo mencioné con los arreglos, los objetos tienen un montón de propiedades. Pero, creo que para una clase introductoria sobre los objetos, lo importante es que entiendan cómo se forma un objeto, qué tipos de datos podemos almacenar en él, la diferencia entre las variables dentro de un objeto (que se llaman atributos o propiedades) y las funciones (que se llaman métodos).

Algunos métodos comunes de los objetos incluyen keys(), values(), y hasOwnProperty(). Pero, recuerden que el objeto Object tiene muchas más propiedades y métodos. Pueden ir a la Mozilla Developer Network (MDN) y revisar todos los métodos y atributos que ofrece este objeto con mayor detalle.

Creo que para una introducción a lo que son los objetos, esta clase ha sido suficiente.
