# 4.Concepto Inferir

En programación, inferir significa que el compilador (en el caso de TypeScript) o el intérprete (en otros lenguajes) deduce o adivina automáticamente el tipo de una variable o expresión basándose en su valor inicial o en cómo se utiliza, sin que tú tengas que especificarlo explícitamente.

**Concepto de Inferencia en TypeScript**

Piensa en la inferencia como el "sentido común" de TypeScript. Si declaras una variable y le asignas un valor directamente, TypeScript es lo suficientemente inteligente como para saber qué tipo de dato es ese valor y, por lo tanto, qué tipo debería tener la variable.

```ts
let nombre = "Alice"; // TypeScript infiere que 'nombre' es de tipo 'string'.
let edad = 30; // TypeScript infiere que 'edad' es de tipo 'number'.
let isActive = true; // TypeScript infiere que 'isActive' es de tipo 'boolean'.

//En los ejemplos anteriores, no tuvimos que escribir
let nombre: string = "Alice"; //TypeScript lo descubrió por sí mismo.
```