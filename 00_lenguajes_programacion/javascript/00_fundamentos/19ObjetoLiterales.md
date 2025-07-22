## **19. Objetos literales 7:19**

En el video anterior estuvimos viendo características nuevas de ECMAScript y hablamos de la desestructuración. Hoy quiero mostrarte lo que se conoce como objetos literales. Los objetos literales no son más que una nueva forma de escribir atributos y métodos, e incluso de asignarlos.

Por ejemplo, anteriormente, imagina que tengo un par de variables: nombre y edad. Voy a crear un objeto llamado perro, al cual le asigno como atributo nombre el valor de la variable nombre, y como atributo edad el valor de la variable edad. Esto es sin usar las características nuevas de los objetos literales.

```js
let nombre = "danGer";

let edad = 1;

const perro = {
  nombre: nombre,
  edad: edad,
  ladrar: function () {
    console.log("guauu guauu");
  },
};

console.log(perro);
perro.ladrar();
```

Con las nuevas características de ECMAScript, podemos simplificar el proceso de asignar variables a las propiedades de un objeto. Por ejemplo, voy a reutilizar las variables nombre y edad. El equipo encargado del estándar de JavaScript observó que, frecuentemente, asignamos variables a propiedades del objeto usando el mismo nombre, como en nombre: nombre. Esto puede simplificarse.

Si la variable que estás asignando como valor a una propiedad del objeto tiene el mismo nombre que la propiedad, entonces JavaScript permite que lo escribas de forma abreviada. Aquí tienes cómo hacerlo:

```js
let nombre = "danGer";

let edad = 1;

const dog = {
  nombre,
  edad,
  ladrar: function () {
    console.log("guauu guauu");
  },
};
```

**Métodos en Objetos Literales**

Ahora, ¿qué pasa con los métodos en los objetos literales? Con ECMAScript 6, se introdujo una nueva forma de simplificarlos. Anteriormente, la forma de declarar un método dentro de un objeto era la siguiente:

```js
const dog = {
  nombre: "optimus",
  edad: 2,
  raza: "callejero",
  ladrar: function () {
    console.log("guauu tres vesces");
  },
};

console.log(dog);
dog.ladrar();
```

**Nueva Sintaxis para Métodos**

Con las características introducidas en ECMAScript 6, ya no es necesario usar la palabra reservada function ni los dos puntos (:) al definir un método dentro de un objeto. La nueva sintaxis es más limpia y directa:

```js
const dog = {
  nombre: "optimus",
  edad: 2,
  raza: "callejero",
  ladrar() {
    console.log("guauu tres vesces");
  },
};

console.log(dog);
dog.ladrar();
```
