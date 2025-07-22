# Ventajas

TypeScript nació en Microsoft y fue lanzado al público en 2012. Su objetivo principal era abordar las limitaciones de JavaScript en la construcción de aplicaciones a gran escala, ofreciendo una capa de tipado estático que facilitara el desarrollo y mantenimiento de código complejo. Desde entonces, ha crecido enormemente en popularidad, siendo adoptado por grandes empresas y proyectos de código abierto.

Javascript es un lenguaje de programacion con tipado debil y dinamico.
¿que quiere decir esto?

Que sea debil, quiere decir:

```js
//que al crear una variable de tipo "string"
let a = "hola";
console.log(a); //-> hola
//luego podemos reasignar otro valor por ejemplo de tipo "number"
a = 2;
console.log(a); //-> 2

//Vemos aqui su naturaleza debil y dinamica. Dinamica porque podemos cambiar los tipos de una variable, como vemos en el ejemplo empezo siendo un "string" y luego paso a ser "number".

//Podemos comprobar con un typeof
console.log(typeof a); //-> number
```