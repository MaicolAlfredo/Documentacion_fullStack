# Escribir menos tipos posibles

La afirmación "en TypeScript tienes que intentar escribir los menos tipos posible" se refiere a una práctica recomendada que maximiza los beneficios de TypeScript, y se basa en el concepto de _inferencia de tipos_.

**¿Qué significa "escribir los menos tipos posible"?**
Significa que debes permitir que TypeScript _infiera los tipos automáticamente_ siempre que sea posible, en lugar de escribirlos explícitamente tú mismo. TypeScript es muy bueno deduciendo el tipo de una variable o expresión basándose en cómo la inicializas o la usas.

## Ejemplos donde NO necesitas escribir tipos explícitamente (TypeScript los infiere):

Estos son los escenarios donde TypeScript es lo suficientemente inteligente como para deducir el tipo por sí solo:

1. **Variables inicializadas inmediatamente**

```ts
let nombre = "Alicia"; // TypeScript infiere: "nombre" es de tipo "string"

let edad = 25; // typeScript infiere: "edad" es de tipo "number"

const isActivo = true; // typeScript infiere: "isActivo" es de tipo de "boolean".

// Si intentas hacer esto, TypeScript te dará un error:
// edad = "treinta";
// Error: Type 'string' is not assignable to type 'number'.
```

2. **Arreglos inicializados con elementos del mismo tipo:**

```ts
let numeros = [1, 2, 3]; // TypeScript infier:"numeros" es de tipo "number"

let ciudades = ["Madrid", "Barcelona"]; // TypeScript infiere: "ciudades" es de tipo "string[]"
// Si intentas añadir algo que no sea del tipo inferido,error: 'numberos.push("cuatro");
//Error:Argument of type 'string' is not assignable to parameter of type 'number'.
```
