## **16. Manejo de Errores 19:26**

16. Manejo de Errores 19:26

En la sesión anterior estuvimos viendo y terminamos de revisar todo lo necesario para empezar a concretar ejercicios de programación con JavaScript. En los últimos dos vídeos vimos los condicionales y los loops. Hoy aprenderás cómo manejar errores en JavaScript.

JavaScript tiene un mecanismo para el manejo y la detección de errores que, si lo comparamos, puede parecerse a un if-else. Este mecanismo se llama try-catch-finally. Es una estructura que permite evaluar fragmentos de código, y cuando se genera un error (o el código lanza un error explícitamente), este es capturado en el bloque catch. Es una manera organizada y eficiente de gestionar errores.

Estructura básica: try-catch

La estructura básica tiene tres partes principales:

1. try: Aquí colocamos el código que queremos evaluar.
2. catch: Este bloque captura cualquier error que ocurra en el bloque try.
3. finally (opcional): Este bloque se ejecuta siempre, haya ocurrido un error o no.

Ejemplo:

```js
trt{
  console.log("En el bloque 'try' se agrega el código a evaluar.");
}catch (error){
  console.log("El bloque 'catch' captura cualquier error ocurrido en el 'try'");
}finally{
console.log("El bloque 'finally' es ejecuta siempre, al final del bloque");
}
```

Detalle del flujo de ejecución

**Bloque try**

Es donde colocamos el código que queremos evaluar. Si no hay errores, el bloque catch se omite.

```js
try{
  console.log("Este es código dentro del bloque 'try'")
}
```

Bloque catch

Si ocurre un error dentro del bloque try, este será capturado por el bloque catch.

```js
try{
  //Intenta ejecutar este código.
  console.log(variableNoDefinida); Esto generará un errors porque la variable no esta definida
}catch (error){
  console.log("Se produjo un error: ", error.message); //captura el error
}
```

Bloque finally

Este bloque se ejecuta siempre, sin importar si hubo o no un error en el bloque try.

```js
try {
  console.log("Ejecutando código en 'try'.");
} catch (error) {
  console.log("Se produjo un error.");
} finally {
  console.log("El bloque 'finally' se ejecuta siempre.");
}
```

Observación importante

Si hay un error en el bloque try, pero este es manejado por el bloque catch, el flujo del programa continúa sin problemas. Si no hay errores, el bloque catch se ignora, y el programa pasa directamente al bloque finally.

Personalización de mensajes de error en JavaScript

Podemos personalizar nuestros propios mensajes de error evaluando condiciones específicas con un bloque if. Por ejemplo, para comprobar si un valor es un número, usamos la función isNaN(). Esta función evalúa si el valor no es un número:

- Si no es un número, devuelve true.
- Si es un número, devuelve false.

Dentro del bloque if, utilizamos la palabra reservada throw para lanzar un error personalizado. Este error puede ser manejado más adelante con un bloque try-catch.

Recuerda que la documentación de MDN Web Docs describe varios tipos de errores predefinidos en JavaScript (como SyntaxError, TypeError, ReferenceError, entre otros). Sin embargo, el tipo de error más común y genérico es Error, que crea una instancia básica para personalizar mensajes.

Ejemplo:

```js
try {
  let numero = "text";

  if (isNaN(numero)) {
    //Lanza un error si el valor no es un número.
    throw new error("El carácter introducido no es un número.");
  }
  console.log(`El cuadrado del número es: ${numero * numero} `);
} catch (error) {
  //captura y maneja el error
  console.log(`Se produjo el siguiente error: ${error.message}`);
}
```

Ventajas de manejar errores con try-catch

Esta estructura no solo es útil para manejar errores de sintaxis, sino que también permite detectar errores lógicos. Por ejemplo, si esperamos recibir un número y, en su lugar, obtenemos una cadena de texto, podemos capturar ese error para evitar fallos en el programa.

Ejemplo práctico de validación:

Imagina que estás desarrollando una aplicación web donde los datos ingresados por el usuario podrían no coincidir con el formato esperado (por ejemplo, números enviados como texto). En este caso, encapsulamos el código dentro de un bloque try-catch para manejar estos errores de manera eficiente.

```js
function procesarDatos(entrada) {
  try {
    let numero = Number(entrada);

    //Validar si la conversión fue exitosa.
    if (isNaN(numero)) {
      throw new error("El carácter introducido no es un número válido.");
    }
    console.log(`El número ingresado es válido: ${numero} `);
  } catch (error) {
    //Manejar el error y mostrar un mensaje claro.
    console.log(`Error: ${error.message}`);
  }
}

// Probar la funcion con diferentes valores.
procesarDatos("texto"); // Error: El dato ingresado no es un número válido.
procesarDatos(42); // El número ingresado es válido: 42.
```

Conclusión

El manejo de errores en JavaScript con try-catch nos permite anticipar y gestionar problemas en nuestro código. Esto es especialmente útil para evitar errores inesperados que puedan interrumpir la ejecución de una aplicación. Implementar mensajes personalizados con throw no solo mejora la claridad de nuestros programas, sino que también facilita su depuración y mantenimiento.

Espero que esta explicación sobre el manejo y la personalización de errores en JavaScript te sea útil. ¡Practica estos conceptos para fortalecer tus habilidades en el desarrollo web!
