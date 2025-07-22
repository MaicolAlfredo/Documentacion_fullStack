# 09. Cuando No sabe Inferir un tipo 23:25

Ejemplos donde SÍ necesitas escribir tipos explícitamente (la inferencia no es suficiente o es ambigua):

Estos son los casos donde la inferencia no puede ayudarte, o te daría un tipo any (lo cual casi siempre debes evitar), o donde especificar el tipo añade claridad intencional.

1. **Variables declaradas sin inicialización inmediata: Si no asignas un valor al declarar, TypeScript no tiene información para inferir**.

```ts
let datos; // TypeScript infiere "any" (esto es malo)
datos = "informacion";
datos = 123; // permite esto porque es "any"

// Mejor
let datosString: string; //Explicas que será un string
datosString = "informacion";
//datosString = 123; Error: Type 'number' is not assignable to type 'string'
```

**¿Por qué es necesario?** Evita el tipo any, que desactiva las ventajas de TypeScript.

---

## El Tipo unknown:

Seguridad sobre la Incertidumbre 🧐
En TypeScript, existe un tipo llamado `unknown` (desconocido) que es muy útil para manejar valores cuyo tipo exacto no conoces en el momento de escribir el código. A diferencia de `any` (que desactiva todas las verificaciones de tipo), `unknown` es la opción segura y consciente de tipos para cuando te enfrentas a una incertidumbre.

Cuando declaramos una variable con `unknown`, le estamos diciendo a TypeScript: "No tengo ni idea de qué tipo de dato hay aquí dentro". Por ejemplo:

```ts
let myValue: unknown = "Hola, mundo"; // myValue es de tipo unknown
```

**¿Por qué unknown es estricto?**

La clave de unknown es que _TypeScript no te permitirá usar propiedades o métodos_ directamente sobre una variable de este tipo, a menos que primero "demuestres" cuál es su tipo real. Es decir, unknown te obliga a ser explícito y cauteloso.

Si intentaras hacer esto:

```ts
let myValue: unknown = "Hola, mundo";
// myValue.toUpperCase(); // ¡Error de TypeScript en compilación! ❌
// Error: 'Object is of type 'unknown'.'
```

TypeScript se queja porque, aunque myValue pueda contener una cadena en ese momento, el compilador no puede tener la certeza de que `toUpperCase()` exista en el tipo subyacente de myValue sin una verificación explícita. Este comportamiento te **protege de errores en tiempo de ejecución** al forzarte a manejar la incertidumbre en tiempo de desarrollo.
