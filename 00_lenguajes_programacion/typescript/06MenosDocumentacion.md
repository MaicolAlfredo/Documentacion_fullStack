# 6. Menos documentación
Escribir menos documentación en TypeScript en comparación con JavaScript tradicional es una de sus grandes ventajas. No es que se escriba cero documentación, sino que TypeScript reduce drásticamente la necesidad de ciertos tipos de comentarios y documentación manual debido a su sistema de tipos estático.

Cuando defines variables, parámetros de función y retornos de funciones con tipos explícitos en TypeScript, esa información ya está documentando el código.

Lo esencial es esto:

- Autodocumentación: Cuando usas nombre: string o edad: number en tu código TypeScript, ya estás diciendo qué tipo de dato se espera. No necesitas un comentario adicional que lo explique.

- Interfaces y Tipos: Si defines una interface Usuario { nombre: string; edad: number; }, eso ya es documentación sobre la estructura de tus objetos.

- Menos comentarios redundantes: Al ser los tipos explícitos, no tienes que escribir comentarios explicando qué tipo de parámetros acepta una función o qué devuelve. Tu código se vuelve más legible por sí mismo.

---

Así, TypeScript te ahorra tiempo al no tener que documentar manualmente cosas que el propio sistema de tipos ya aclara. ¡Es su gran ventaja!