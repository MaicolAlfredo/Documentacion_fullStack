## **20 Parámetros REST Operador Spread**

En sesiones anteriores hemos estado revisando nuevas características que llegaron desde el año 2015, o desde la versión 6 de ECMAScript, a nuestro lenguaje favorito: JavaScript.

En esta ocasión, te voy a hablar de dos características muy particulares y útiles, sobre todo si estás interesado en el mundo de los frameworks o librerías reactivas como Angular, Vue y React.

Los parámetros rest y el operador de propagación (o spread operator) son herramientas que utilizamos en el día a día como programadores de JavaScript.

Parámetros Rest

Los parámetros rest son una forma de agregar virtualmente una cantidad infinita de parámetros a una función o incluso almacenarlos en una variable.

Imagina que tienes un arreglo, pero no sabes exactamente cuántos valores vas a recibir. Posteriormente, con esos valores, podrías realizar ciertas operaciones o procesos.

Para definir los parámetros rest, solo necesitas anteponer tres puntos suspensivos (...) al nombre donde se almacenarán los valores adicionales.

Por ejemplo, vamos a crear una función que nos permita sumar valores. ¿Qué pasa si no solo recibes dos valores, sino tres, cuatro o incluso más? Aquí es donde los parámetros rest resultan útiles.

En el siguiente ejemplo, los primeros dos valores (a y b) se suman directamente, y los demás valores (almacenados en c) se procesan como un arreglo. Usaremos el método forEach para recorrer los valores en c, sumar cada elemento al resultado y, al final, retornarlo.

vamos a crear una función, que nos permita sumar.¿que pasa si no recibo 2 valores, voy a recibir 3 o 4 o 5?entonces es ahi donde nos puede servir un tercer parametro, que sea una parametro rest( pongo los 3 puntos suspensivo y luego la palabra c). Vamos a guardar el resultado en una variable de 'a+b' que son los valores seguro que pasaran, y luego todo lo que llegue despues de 'c' lo voy a tratar como si fuera un arreglo, como 'c' es un arreglo entonces voy a utilizar el metodo 'forEach'. Recuerden que forEach recibe Una funcion que se va a ejecutar por cada uno de los elementos que venga dentro de 'c', entonce al numero en cuestion (n) pues le sume al lo que valga resultado para que haga una sumatoria de los numero que valla recibiendo. y pues simplemente voy a retornar la variable de 'resultado' después de haber hecho el forEach de los resultados en 'c'.

```js
function sumar(a, b, ...c) {
  let resultado = a + b; // Sumar los dos primeros valores

  // Recorrer los valores adicionales y sumarlos al resultado

  c.forEach(function (n) {
    resultado += n;
  });

  return resultado; // Retornar el resultado final
}

// Ejemplo de uso

console.log(sumar(1, 2)); // 3

console.log(sumar(1, 2, 3)); // 6

console.log(sumar(1, 2, 3, 4)); // 10

console.log(sumar(1, 2, 3, 4, 5)); // 15
```

Operador de Propagación (Spread Operator)

El spread operator nos permite expandir los elementos de un arreglo o de un objeto en situaciones donde se necesita desglosarlos para trabajar con múltiples valores.

Imagina que ya tienes un arreglo con ciertos elementos y recibes nuevos valores que quieres combinar en un solo arreglo. En lugar de usar métodos como concat o push, puedes emplear el spread operator (...) para lograrlo de manera más simple y limpia.

Ejemplo inicial: Concatenar arreglos sin el spread operator

Supongamos que tienes dos arreglos:

```js
const arr1 = [1, 2, 3, 4, 5];
const arr2 = [6, 7, 8, 9];
```

Si intentas crear un nuevo arreglo que combine arr1 y arr2 sin usar el spread operator, podrías escribir algo como:

```js
const arr3 = [arr1, arr2];
console.log(arr3);
// Resultado: [[1, 2, 3, 4, 5], [6, 7, 8, 9]]
```

Esto crea un arreglo de dos elementos, donde cada elemento es un arreglo interno. Pero lo que queremos es combinar todos los valores en un solo arreglo con 10 posiciones.

Solución: Usar el spread operator

Con el spread operator, puedes desglosar los elementos de arr1 y arr2 directamente en el nuevo arreglo:

```js
const arr3 = [...arr1, ...arr2];
console.log(arr3);
// Resultado: [1, 2, 3, 4, 5, 6, 7, 8, 9]
```

Ahora arr3 es un solo arreglo que contiene todos los valores de arr1 y arr2.

En React y otros frameworks, el spread operator se usa comúnmente para trabajar con el estado de un componente. El estado es un objeto que centraliza los datos de un componente. Si necesitas modificar solo una propiedad sin alterar las demás, puedes utilizar el spread operator para crear una copia del objeto original y luego sobrescribir únicamente el valor que deseas cambiar.

Diferencia entre Rest y Spread

Aunque tanto los parámetros rest como el spread operator utilizan los tres puntos suspensivos (...), tienen propósitos diferentes:

Parámetros Rest:

- Agrupan múltiples argumentos en una función en un único arreglo.
- Se usan principalmente en la definición de funciones para manejar parámetros variables.

Spread Operator:

- Desglosa los elementos de un arreglo u objeto en elementos individuales.
- Se usa para expandir valores en llamadas a funciones, arreglos u objetos.
