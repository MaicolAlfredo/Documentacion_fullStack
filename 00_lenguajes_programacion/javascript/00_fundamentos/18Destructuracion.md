## **18. Destructuración 9:08**

En las clases anteriores creo que hemos terminado de abordar bastante bien los conceptos básicos para comenzar a programar en JavaScript. En los siguientes vídeos voy a continuar con algunas de las nuevas características que tenemos a nivel de escritura y de algunas de las nuevas capacidades que han llegado al lenguaje gracias al estándar de ECMAScript 6, introducido en el año 2015.

El día de hoy quiero comenzar con una práctica que es muy utilizada: la desestructuración o destructuring. La desestructuración es una nueva forma de asignar valores, sobre todo de arreglos y objetos. Si estás en el mundo de JavaScript utilizando librerías o frameworks como Angular, React o Vue, seguramente has usado este tipo de sintaxis, que permite asignar dinámicamente lo que viene en un arreglo o en un objeto a nuevas variables de una manera más ágil. Por ejemplo, cuando recibes en ReactJS las propiedades de un componente padre hacia un componente hijo.

Imagínense que tenemos un arreglo de números y tengo la necesidad de, a partir de este arreglo, guardar cada una de las posiciones, es decir, cada uno de los valores, en variables diferentes.

```js
const numeros = [1, 2, 3];
```

¿Cómo sería con desestructuración?

Creo un arreglo al cual le voy a asignar el contenido del arreglo de números que tengo guardado en la variable numeros. Entonces, dinámicamente, lo que estoy haciendo es lo siguiente: sé que numeros es un arreglo, y a cada una de las posiciones de ese arreglo las estoy guardando dinámicamente en estas variables: uno, dos y tres. Vean que en el momento que mando un console.log, obtengo los valores correspondientes a cada posición.

```js
const [uno, dos, tres] = numeros;
console.log(uno, dos, tres); // salida: 1 2 3
```

Ahora, imagínense que tengo una variable llamada persona, que es igual a un objeto. Es muy importante tener en cuenta que nombre, apellido y edad son propiedades del objeto persona. Si quisiera realizar una desestructuración similar, hago lo mismo que en el ejemplo anterior, solo que en este caso es un objeto, no un arreglo. Por lo tanto, le digo que dentro de ese objeto van a ir las variables, y les asigno las propiedades correspondientes del objeto persona.

Después, si me dirijo al console.log e imprimo las variables nombre, apellido y edad, vean que he logrado esa desestructuración. Es decir, he creado dinámicamente estas tres variables (nombre, apellido y edad) y les he asignado los valores de las propiedades del objeto persona.

```js
let persona = {
  nombre: "Jon",
  apellido: "Mircha",
  edad: 35,
};

let { nombre, apellido, edad } = persona;

console.log(nombre, apellido, edad);
```

Conclusión:

La desestructuración o destructuring permite asignar de forma dinámica valores de arreglos u objetos a variables específicas, haciéndolo de manera más eficiente y clara. Es una característica introducida con ES6 que es ampliamente utilizada en librerías y frameworks modernos como React, Vue o Angular.
