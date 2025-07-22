## 11. Arreglos

En la clase anterior, vimos los conceptos básicos de las funciones. Hoy, veremos el segundo tipo de datos complejos, que son los arreglos.

Si abro el navegador y escribo un par de corchetes [], el navegador reconocerá esto como un arreglo vacío. Existen diferentes maneras de declarar arreglos. Por ejemplo, es importante recordar lo que vimos en la sesión 4 sobre las constantes: podemos declarar arreglos usando const. Aunque internamente cambien los elementos de un arreglo, mientras siga siendo un arreglo, puede ser tratado como una constante.

Algunos programadores prefieren declarar arreglos con la palabra clave let, mientras que otros optan por const. Esto depende de la preferencia del programador. Aquí usaré const para definir mis arreglos.

Ejemplos de Declaración de Arreglos

Para declarar un arreglo vacío, podemos escribir:

```js
const a = [];
```

Pero, si queremos crear un arreglo b con algunos elementos desde el inicio, podemos hacer lo siguiente:

```js
const b = [1, true, "hola", ["A", "B", "C"]];
```

Este arreglo b contiene cuatro elementos:

1. El número 1

2. Un valor booleano true

3. La cadena "hola"

4. Un arreglo de letras ["A", "B", "C"]

Si ejecutamos el siguiente código en la consola:

```js
console.log(b);
```

La consola nos mostrará el contenido de b, indicando que es un arreglo con cuatro elementos. Además, dentro del cuarto elemento (el subarreglo), podremos ver tres elementos: "A", "B", y "C".

Longitud de un Arreglo

Los arreglos en JavaScript siempre empiezan con el índice 0. Esto significa que el primer elemento está en la posición 0, el segundo en 1, y así sucesivamente. Para obtener la longitud de un arreglo (el número total de elementos que contiene), usamos la propiedad length:

```js
console.log(b.length);
```

Así como en las cadenas de texto length nos devuelve el número de caracteres, en arreglos nos devuelve el número de elementos.

Accediendo a Elementos en un Arreglo

Imaginemos que queremos acceder solo al elemento "hola" en el arreglo b. Como es el tercer elemento, se encuentra en la posición 2 (recordando que el índice empieza en 0). Usamos la notación de corchetes [] para acceder a este elemento:

```js
console.log(b[2]); // salida: hola
```

Si en cambio accedemos al primer elemento:

```js
console.log(b[0]);
```

Esto nos imprimirá el número 1, ya que es el primer elemento del arreglo b.

Ejemplo Adicional: Acceder a un Subarreglo

Supongamos que queremos acceder al subarreglo ["A", "B", "C"] dentro de b. Como este es el cuarto elemento, está en la posición 3:

```js
console.log(b[3]); // salida:["A", "B", "C"]
```

Y, si deseamos obtener solo la letra "B" del subarreglo, especificamos dos índices:

```js
console.log(b[3][1]); // salida: B
```

Ejemplo de Ajedrez: Coordenadas en el Tablero

Para comprender mejor la estructura de posiciones en arreglos, imagina un tablero de ajedrez. Supongamos que necesitamos referirnos a una pieza, como un caballo en la casilla h2. Para localizarlo, deberíamos ubicar la columna h y luego el número 2. De manera similar, en un arreglo podemos acceder a posiciones específicas mediante índices.

Por ejemplo, si queremos ver todas las piezas, usamos el nombre del arreglo. Si queremos ver solo una pieza en particular, usamos la coordenada o posición del índice de esa pieza.

Ahora, hay nuevas formas de crear arreglos, como usando Array.of(). Este método permite crear un arreglo con los elementos que le especifiquemos. Por ejemplo:

```js
const c = Array.of("x", "y", "z", 9, 8, 7);
console.log(c);
```

Al ejecutar console.log(c), el resultado será:

```
["x", "y", "z", 9, 8, 7]
```

La consola nos dirá que c es un arreglo de seis posiciones, y mostrará los valores que contiene.

Este es un nuevo método que se introdujo en el estándar ECMAScript en 2015 (conocido como ECMAScript 6 o ES6), y Array.of() nos permite crear arreglos llenando directamente los elementos en su declaración.

Otra manera muy útil de crear arreglos es inicializarlos con valores predeterminados en todas sus posiciones. Imagina que tienes una aplicación de ecommerce con mil productos, y mientras se cargan sus valores reales, necesitas asignarles temporalmente un descuento de 0% en un arreglo. Para este tipo de situaciones, existe un método que permite inicializar un arreglo y asignarle el mismo valor a todas sus posiciones.

Por ejemplo, voy a crear un arreglo llamado d usando el método Array().fill(). Este método pertenece al objeto Array en JavaScript y permite asignar un valor a todas las posiciones de un arreglo.

Imaginemos que necesitamos un arreglo de 100 posiciones y queremos llenarlas todas con el valor false. Para hacer esto, podemos escribir:

```js
const d = Array(100).fill(false);
console.log(d);
```

Si ejecutamos console.log(d), veremos que la consola muestra un arreglo de 100 posiciones, todas inicializadas con el valor false.

Los arreglos, como vimos, tienen propiedades útiles, como la propiedad .length, que devuelve el número de elementos. Por ejemplo, imagina que tenemos un arreglo con los colores RGB (rojo, verde y azul):

```js
const colores = ["rojo", "verde", "azul"];
```

Si necesitamos agregar un nuevo elemento al final del arreglo, podemos usar el método .push(). Este método añade el nuevo elemento en la última posición. Por ejemplo, si queremos agregar el color "Negro":

```js
colores.push("negro");
console.log(colores);
```

Al imprimir colores, veremos que ahora tiene cuatro elementos, siendo "Negro" el último agregado. El método .push() siempre inserta el elemento al final del arreglo.

De igual manera, podemos utilizar el método .pop(). Este método elimina el último elemento del arreglo. Por ejemplo:

```js
colores.pop();
console.log(colores);
```

Después de ejecutar .pop(), veremos que el último elemento del arreglo ha sido eliminado. Así, el método .push() agrega un elemento al final del arreglo, mientras que .pop() quita el último elemento.

Los arreglos en JavaScript tienen una gran cantidad de métodos, especialmente útiles en el contexto del paradigma funcional y la programación orientada a componentes. Este estilo de programación ha introducido métodos como .map(), .reduce(), y .filter(), entre otros, que permiten escribir código de una manera más funcional.

Si quisiera mostrar todos los métodos que existen para los arreglos, esta clase sería demasiado extensa. Como vimos en la clase sobre cadenas, puedes consultar la documentación en MDN (Mozilla Developer Network) para ver todas las propiedades y métodos disponibles, junto con ejemplos.

A lo largo del curso, veremos estos métodos en profundidad. Más adelante, cuando abordemos los paradigmas de programación, retomaremos estos métodos orientados a la programación funcional.

Sin embargo, hay un método con el que cerraré esta clase, que nos permite ejecutar una función en cada elemento de un arreglo. Este es también un método funcional de los arreglos.

Por ejemplo, imaginen que quiero formar una lista en HTML usando una etiqueta `<ul>`, donde cada color esté dentro de un elemento <li>. Para esto, puedo usar el método forEach. Este método ejecuta una función en cada elemento del arreglo.

Aquí tienes un ejemplo para que lo veas en acción:

```js
const colores = ["rojo", "verde", "azul"];

//Usamos un forEach para recorer cada color y crear un elemento <li>
colores.forEach(function (el) {
  console.log(`<li>${el}</li>`);
});
```

Explicación del código:

- forEach recibe una función como callback (una función que se ejecuta en cada elemento del arreglo).

- En este caso, declaramos una función anónima que toma el elemento actual (el) como parámetro.

- Dentro de la función, utilizamos console.log para mostrar cada color dentro de un elemento `<li>`.

Cuando lleguemos a temas más avanzados, veremos cómo utilizar arrow functions en lugar de funciones anónimas. Por ahora, usamos una función anónima para que el ejemplo sea fácil de entender.

Este método forEach es muy útil para trabajar con cada elemento de un arreglo y ejecutar acciones específicas en ellos.

Ahora, imaginen que cada elemento `<li>` necesita tener una referencia única en el atributo id. Podemos lograr esto pasando un segundo parámetro al método forEach, el cual indica el índice que ocupa cada elemento dentro del arreglo. A este parámetro podemos llamarlo index, y luego interpolarlo para incluirlo en el atributo id de cada `<li>`.

Aquí tienes un ejemplo:

```js
const colores = ["rojo", "verde", "azul"];

// Recorremos el arreglo y generamos una lista con un id unico
colores.forEach(function (el, index) {
  console.log(`<li id="${index}">${el}</li>`);
});
```

Explicación del código:

- forEach recibe una función que tiene dos parámetros: el primer parámetro (el) representa el valor del elemento actual en el arreglo, mientras que el segundo parámetro (index) representa el índice de ese elemento.

- Dentro del console.log, usamos la interpolación de strings para crear un elemento `<li>` que tiene un id igual al índice del elemento. Esto generará como resultado elementos con id='0', id='1', id='2', etc.

Con el método forEach, podemos recorrer cada elemento del arreglo, acceder a su valor con el primer parámetro (el) y su índice con el segundo parámetro (index o i), lo cual resulta útil en muchos casos.
