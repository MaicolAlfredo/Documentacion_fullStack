# 5. Uso de TypeScript

¿Porque usarlo?, ¿no es lo suficientemente elástico Javascript para hacer estas cosas ? la realidad es que una de las razones Más exactas por las que se utiliza es también por los cambios de tipos de datos que suele hacer javascript y cómo los trata ya no solo porque sea un tipado débil y Dinámico por ejemplo imagínate una función tan sencilla como:

```ts
function sumar(a, b) {
  return a + b;
}

//Fíjate que aquí tipscript ya se queja de (a y b)
```

si esto lo ponemos en javascript no va a haber ningún problema, tú viendo seguramente esto no sabrías decirme qué es lo que va a ocurrir aquí por qué seguramente dices: "Ah sí me va a sumar dos números" Pero tú eso no lo sabes hasta que no lo uses hasta que tú no le pases aquí los dos números y lo peor es que podrías pasarle por ejemplo esto:

```js
function sumar(a, b) {
  return a + b;
}

sumar("Hola", 3); //->"hola3"
```

O sea podrías pasarle un hola y tres y lo está devolviendo es una cadena de texto porque ya no hace una suma hace una concatenación de dos cadenas de texto y lo mismo igual podríamos ponerle dos strings y lo que tú creías que hacía esto que era sumar dos operandos en realidad no es lo que está haciendo así que sobre todo por un tema de legibilidad vas a ver que las anotaciones de tipos nos van a ayudar un montón.

```js
//que por lo tanto esto no debería funcionar.
// porque no es lo mismo ver esto así sin saber cuáles son los tipos de datos que tenemos aquí.
function sumar(a, b) {
  return a + b;
}

console.log("hola", "mundo");

//  y que vamos a poder saber qué es exactamente lo que está haciendo esta función.
//a indicar que aquí lo que tiene que aceptar son dos números
function sumar(a: number, b: number) {
  return a + b;
}
```

Las anotaciones de tipos son una característica que, durante mucho tiempo, parecía que a lo mejor llegaría a JavaScript. Ahora, se está proponiendo añadirla. Esto se refiere a cómo funcionan los tipos, cómo le indicamos las características a nuestras variables, funciones y sus parámetros; básicamente, les indicamos los tipos que esperamos.
