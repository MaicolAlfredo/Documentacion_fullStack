## 9. undefined, null & NaN

Bueno, vamos a continuar. En la clase anterior vimos los tipos de dato boolean y en esta clase vamos a hablar de los valores primitivos que les he puesto en esta lista. undefined y NaN son casos muy particulares de JavaScript, y a veces hay cierta confusión, sobre todo entre null y undefined. Pero bueno, en esta clase voy a tratar de desmitificar todos esos conceptos que a veces se pueden malentender.

Primero, ¿qué es undefined? undefined va a indicar un valor ausente. Fíjense que tanto null como undefined representan un valor ausente, es decir, una variable que no tiene valor. La gran diferencia es que, mientras undefined es una variable que no ha sido inicializada, null es un valor que el programador asigna intencionalmente.

Por ejemplo, recuerden que en clases anteriores, cuando les explicaba las cadenas de texto y empezaba a concatenar cierto contenido a una variable, en algún momento hice una variable sin asignarle valor. Entonces, cuando nosotros como programadores hacemos ese tipo de prácticas, JavaScript detecta el valor de dicha variable como undefined.

Para ilustrarlo:

```js
let indefinida;
console.log(indefinida);
```

Si quiero que JavaScript le detecte el valor undefined, simplemente no le asigno valor.

Por otro lado, si asignamos el valor null, estamos diciendo intencionalmente que esa variable está vacía. Aquí un ejemplo:

```js
let vacia = null;
console.log(vacia);
```

Diferencia clave:

- undefined es cuando JavaScript detecta que la variable no tiene valor.
- null es cuando el programador le asigna explícitamente ese valor especial.

Recuerda que ambos significan que la variable está vacía, pero la diferencia es que undefined no ha sido inicializada, mientras que con null el programador le asigna ese valor.

Finalmente, hay otro tipo de valor que a veces nos ocurre cuando, por ejemplo, hacemos operaciones aritméticas entre diferentes tipos de datos que no son numéricos. Esto puede generar un valor especial llamado NaN (Not a Number).

Ejemplo de código para generar NaN:

```js
let noEsUnNumero = "texto" * 3.5;
console.log(noEsUnNumero);
```

En este caso, JavaScript nos está diciendo que no puede realizar una operación matemática entre una cadena de texto y un número, por lo que devuelve NaN.

En resumen:
NaN significa "No es un número".

Se genera cuando intentamos hacer operaciones con valores que no son numéricos.

Básicamente, con esto cerramos la parte de los tipos primitivos. En el siguiente vídeo comenzaremos con los tipos compuestos o complejos, empezando con las funciones, y más adelante veremos objetos, arreglos, clases, etc. Habrá un apartado especial en este curso sobre programación orientada a objetos donde explicaremos conceptos como prototipos, clases, etc.
