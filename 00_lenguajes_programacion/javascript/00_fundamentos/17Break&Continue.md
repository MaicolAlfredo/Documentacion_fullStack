## 17. **break & continue 8:42**

Vamos a continuar, y en clases anteriores ya habíamos visto el uso de estructuras de control como condicionales y ciclos. De hecho, cuando les mostraba el uso de la instrucción switch-case, en cada uno de los casos utilizábamos la palabra break para romper el flujo de ejecución de los casos del switch.

Les mencioné que lo que hace break es salir de la estructura, en este caso del switch, para evitar leer todos los casos. Entonces, el día de hoy, como ya se habrán dado cuenta en el título del video, vamos a ver precisamente para qué nos sirve break y otra palabra muy parecida llamada continue.

Estas palabras nos ayudan a controlar el flujo de nuestras estructuras de control, sobre todo cuando, por ejemplo, estamos en un bucle y queremos detenernos al alcanzar cierto número de repeticiones o romper la estructura. Por otro lado, a veces resulta útil solo saltarnos ciertas iteraciones de un bucle según un patrón.

Imagínense que, de una lista, queremos imprimir solo los números pares o solo los números impares. Para esto, break o continue nos pueden ser de gran ayuda.

Ahora vamos a ver un pequeño ejercicio:

```js
const numeros = [1, 2, 3, 4, 5, 6, 7, 8, 9, 0];
```

Vamos a recorrer este arreglo. ¿Por qué no utilizamos el método forEach de los arreglos? Bueno, las palabras reservadas break y continue no se pueden usar en métodos de los arreglos. Estas están destinadas para utilizarse en estructuras de control como for, while, do-while, if, switch-case, etcétera. Por eso, recorreremos el arreglo utilizando un for.

Ejemplo con for:

```js
for (let i = 0; i < numeros.length; i++) {
  console.log(numeros[i]);
}
```

Ahora imaginen:

Quiero que cuando i valga 5, el bucle termine. Para esto usamos break.

Ejemplo con break:

```js
for (let i = 0; i < numeros.length; i++) {
  if (i === 5) {
    break;
  }

  console.log(numeros[i]);
}
```

¿Qué pasa aquí?

La sentencia break, como ya lo habíamos visto en switch-case, termina la ejecución de la estructura en la que se encuentra, que en este caso es el for.

Si se dan cuenta, después del número 4, el bucle se interrumpe y ya no imprime del 6 al 0 porque se ha salido del ciclo al cumplirse la condición i === 5.

Ejemplo con continue:

¿Qué pasa si queremos omitir solo la iteración en la que i vale 5, pero queremos que el ciclo continúe? Utilizamos continue.

```js
for (let i = 0; i < numeros.length; i++) {
  if (i === 5) {
    continue;
  }

  console.log(numeros[i]);
}
```

¿Qué hace continue?

A diferencia de break, que termina todo el ciclo, continue solo omite la iteración actual y el bucle continúa con las siguientes iteraciones.

Resultado esperado con continue:

El código imprime:

```
1
2
3
4
5
6
7
8
9
0
```

Cuando la condición i === 5 se cumple, se omite la impresión de ese número (en este caso, el valor 6 en el arreglo) y el ciclo continúa con las siguientes iteraciones.

**Diferencias clave entre break y continue:**

break:

- Termina el ciclo en el momento en que se ejecuta.
- Útil cuando necesitamos salir completamente de un bucle o estructura de control.

continue:

- Solo omite la iteración actual del ciclo y continúa con las siguientes.
- Útil cuando queremos ignorar ciertas condiciones específicas pero seguir con el resto del bucle.

Conocer estas palabras reservadas es esencial para controlar el flujo de nuestras estructuras de control y desarrollar programas más robustos.

