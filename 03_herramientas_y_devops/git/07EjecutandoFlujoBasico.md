## 7. Ejecutando el flujo básico local 0:53:19

Vamos a ejecutar esto comando.
El 1º comando que tenemos que ejecutar (por que recuerda que en VSC ha detectado 2 cambios. contexto aqui en el 5º capitulo.

RECUERDA que en la medida de lo posible evita utilizar interfaces visuales mejor vete acostumbrando al trabajo con los comandos.). Entonces para pasar del directorio de trabajo al staging para que indece git los archivos que tenemos en el repositorio si ser traqueado o sea sin ser revisado recuerda que tenemos el comando `git add` para pasar del modified al stage, ahora puede ejecutar `git add archivo/directorio` y el nombre del archivo o directorio que quieras ir traqueando es decir uno por uno o si quieres agregar todos los cambios de un jalón con `git add .` ahi ya hemos ejecutado del working directory al staging, ahora si decidiera decir "aqui irá el primer registro oficial de mi repositorio" que generalmente siempre es "first commit" o "primer commit" para comprometer ya los cambios en el historial de repositorio tu puedes ejecutar el comando `git commit` cuando ejecutas el comando se te abrirá en la terminal el editor de codigo entonce escribes el mensaje descriptivo para tu cambio. Hay una version mas rapida si le agrega al comando git commit la bandera de -m y entre comillas describe el mensaje entonces ahi se estará guardando el cambio.

---

## 🚀 Ejecutando el Flujo Básico Local de Git

Vamos a ejecutar los comandos esenciales para mover nuestros cambios a través de los estados locales de Git. (Recuerda que en VS Code ya habrás notado algunos cambios, esto se relaciona con el quinto capítulo del curso).

---

### De `modified` a `staged`: Agregando Archivos

Para pasar los archivos de tu **directorio de trabajo** (estado `modified`) al **área de preparación** o `staging` (donde Git los indexa y comienza a rastrearlos), usamos el comando `git add`.

Tienes dos opciones:

- **Agregar archivos o directorios específicos**: Usa `git add archivo/directorio` seguido del nombre del archivo o directorio que quieres rastrear. Esto te permite agregarlos uno por uno.

- **Agregar todos los cambios de una vez**: Si quieres incluir todas las modificaciones de golpe, usa `git add .` (el punto `.` significa "todos los archivos y directorios en el directorio actual").

Con `git add`, tus cambios ya han pasado del `working directory` al `staging`.

---

### De `staged` a `commited`: Confirmando Cambios

Una vez que tus cambios están en el `staging`, puedes decidir que es momento de hacer el "primer registro oficial" de tu repositorio. Generalmente, este primer compromiso se etiqueta como "first commit" o "primer commit". Para **comprometer** (o confirmar) esos cambios en el historial de tu repositorio, usas el comando `git commit`.

Tienes dos maneras de hacerlo:

- **Con editor de texto en la terminal**: Si ejecutas solo `git commit`, se abrirá tu editor de texto predeterminado en la terminal. Allí podrás escribir un **mensaje descriptivo** para tu cambio, explicando qué modificaciones incluye. Guarda y cierra el editor para completar el commit.

- **De forma más rápida con mensaje directo**: Si quieres una versión más rápida, puedes agregar la bandera `-m` al comando `git commit` y, entre comillas, escribir tu mensaje descriptivo. Por ejemplo: `git commit -m "Mensaje descriptivo de mi cambio"`. De esta forma, el cambio se guardará directamente con el mensaje proporcionado.

Con `git commit`, tus cambios quedan registrados en la "cabeza" de tu repositorio local, formando parte del historial del proyecto. ¡Felicidades, has completado tus primeros pasos en el flujo local de Git!
