# Git de JonMircha

Indice
- [1. Introducción](#1-introduccíon)
- [2. Requisitos para tomar este curso](#2-requisitos-para-tomar-este-curso-00139)
- [3. Introducción a Git](#3-introducción-a-git-00747)
- [4. Configuracíon inicial](#4-configuracíon-inicial-01815)
- [5. Inicializar Git en un directorio](#5-inicializar-git-en-un-directorio-03404)
- [6. Explicando el flujo básico de Git](#6-explicando-el-flujo-básico-de-git-04043)
- [7. Ejecutando el flujo básico local](#7-ejecutando-el-flujo-básico-local-05319)

## 1. Introduccíon
No importa cual sea tu perfil en este maravilloso mundo del diseño y desarrollo y la programación, no importa si eres frontend o backend, o te dediques a las bases de datos a la infrestructura es indispensable que aprendas esta herramientas.

`Git` es un software que permite gestionar el versionado de nuestro código, lo que facilita el seguimiento y control de los cambios en nuestros proyectos.

`GitHub` es una plataforma en la nube que permite compartir ese código con otros. Es una herramienta indispensable, sobre todo si trabajas en equipos remotos y multidisciplinarios. Si tus compañeros de trabajo están en diferentes partes del mundo, GitHub facilita la colaboración y el avance conjunto en los proyectos.

Existen otras plataformas, como Bitbucket y GitLab, pero Git y GitHub son los líderes en sus respectivas categorías. Git es el rey de los sistemas de control de versiones, y GitHub se ha consolidado como la principal plataforma para compartir y colaborar en proyectos de código.

[Indice](#git-de-jonmircha)
## 2. Requisitos para tomar este curso 0:01:39
- Instalar Git
  Cuando descargar git te viene instalado una terminal llamada gitbash, es en esta herramienta que se trabajara todo el curso.
- Manejo de la terminal.
- Manejar algun editor de codigo.
- Conocer la sintaxis markdown.
- Crear una cuenta en GitHub.
- Te sugiero que desde el primer momento te lanzes a el manejo de git a traves de la terminal de comando pues tendras mayor control que si utilizas algun interfaz visual donde ejecuta los comandos por ti.

[Indice](#git-de-jonmircha)

## 3. Introducción a Git 0:07:47

¿Qué es Git?
Git es un software de control de versiones distribuido y descentralizado, ideal para que equipos de desarrolladores trabajen en el mismo código de manera colaborativa. Es decir, permite a cada miembro hacer cambios en su copia local y luego sincronizar esos cambios en un origen común (generalmente en una plataforma como GitHub).

¿Por qué es importante el control de versiones?
La versión es un concepto común en software. Los sistemas operativos y muchas aplicaciones actualizan sus versiones para mejorar o corregir fallos. Git permite aplicar esta filosofía al desarrollo, de manera que puedas gestionar diferentes versiones de un proyecto. Esto incluye:

- Mantener un historial de cambios.
- Recuperar versiones anteriores (rollback) si surge algún error.

¿Qué significa "distribuido y descentralizado"?
Cada desarrollador tiene su propia copia del proyecto. Así, todos pueden trabajar en paralelo sin interferir. Los cambios se sincronizan en un origen común (repositorio), y cualquier integrante puede actualizar su copia local con los cambios de los demás. Esto facilita el trabajo en equipo y permite el trabajo remoto.

¿Git y GitHub son lo mismo?
No. Git es el software de control de versiones que instalas y usas en tu computadora. GitHub es una plataforma web que facilita compartir y colaborar en proyectos de Git, aunque GitHub no es el único. También existen otras como GitLab y Bitbucket.

_Ventajas de usar Git_
1. Estándar en la industria: Git es ampliamente utilizado.
2. Código colaborativo y versionado: Ayuda a mantener el control de los cambios en equipo.
3. Productividad y control: Permite manejar errores rápidamente y volver a versiones estables si es necesario.
4. Soporte extenso: Hay herramientas visuales como GitKraken, GitHub Desktop y opciones en editores como Visual Studio Code que integran Git y facilitan su uso.

[Indice](#git-de-jonmircha)

## 4. Configuracíon inicial 0:18:15
1. Verificación de la instalación:
Muestra la versión instalada de Git para confirmar la instalación.
```bash
git --version
```
2. Configuración global:

Establece valores que aplican a todos los proyectos en tu sistema:
```bash 
git config --global user.name "Nombre de usuario"
git config --global user.email "correo@ejemplo.com"
git config --global color.ui true
git config --global core.editor "code --wait"
```
`--global` hace que estas configuraciones apliquen de manera general en tu sistema.

3. configuración local:

Si necesitas una configuración específica en un solo repositorio (ej. diferentes cuentas), puedes omitir --global y ejecutar los mismos comandos dentro del repositorio.

4. Otros comandos útiles:
- Ver la configuración actual
```bash
git config --list
```
Presiona "q" para salir del listado.
- Configurar saltos de línea:
```bash
git config --global core.autocrlf true
```
- Ayuda de comandos:
```bash
git config -h
git help <comando>
```
Muestra una ventana del navegador con la documentación detallada del comando.

[Indice](#git-de-jonmircha)

## 5. Inicializar Git en un directorio 0:34:04
Primero, abrimos la terminal y escribimos `cd`, seguido de la ruta a la carpeta donde queremos trabajar. En este caso, seleccionaremos el Escritorio. Podemos arrastrar la carpeta deseada a la terminal para que se genere automáticamente la ruta y luego presionamos Enter.

A continuación, creamos una nueva carpeta con el comando mkdir "nombre_de_la_carpeta", por ejemplo:
```bash
mkdir youtube-git
```
Después, nos cambiamos a esa carpeta utilizando:
```bash
cd youtube-git
```
Dentro de esta carpeta, creamos un archivo llamado README.md con el siguiente comando:
```bash
touch README.md
```
El archivo `README.md` es fundamental, ya que contiene la explicación y la documentación de cada proyecto, librería, framework, etc.

También podemos crear un archivo llamado .gitignore con el comando:
```bash
touch .gitignore
```
Este archivo es importante porque, al ser detectado por Git, le indica qué carpetas o archivos debe ignorar según la ruta que definamos en su interior.

Si ejecutamos el comando `ls`, se mostrarán todos los archivos de la carpeta, pero el archivo .gitignore no aparecerá en la lista, ya que es un archivo oculto. Para ver todos los archivos, incluidos los ocultos, podemos usar:
```bash
ls -a
```
Para que esta carpeta empiece a ser rastreada por Git, debemos ejecutar el siguiente comando:
```bash
git init
```
Este comando inicializa un nuevo repositorio en Git y solo se debe ejecutar una vez por repositorio.

Finalmente, para abrir el editor de código, escribimos:
```bash
code .
```
[Indice](#git-de-jonmircha)

## 6. Explicando el flujo básico de Git 0:40:43
El flujo básico de Git consta de 4 estados. Cada estado representa un paso en el proceso de versionado de nuestro código. Tres de estos estados son locales (suceden en tu computadora) y el cuarto es el estado remoto, que ocurre en la plataforma donde tu código está alojado, como GitHub.

Estos son los cuatro estados:
1. **Modified** (modificado): El primer estado. Ocurre cuando realizamos cambios en los archivos en nuestro directorio de trabajo. Este es el estado en el que cualquier modificación al código aún no ha sido rastreada oficialmente por Git.
2. **Staged** (preparado): El segundo estado, al cual el archivo pasa cuando lo añadimos al área de preparación, o "staging". Este es el índice (index) donde Git empieza a rastrear los cambios. Para mover un archivo al estado `staged`, usamos el comando `git add`.
3. **Committed** (confirmado): El tercer estado. Aquí, el cambio se registra en el historial de Git, quedando almacenado en el repositorio local. Para esto, utilizamos el comando `git commit`, que lleva el cambio desde el "staging" hasta la "cabeza" (HEAD) del repositorio local. Es un registro permanente en el historial que, mientras el repositorio exista, quedará allí.
4. **Remote** (remoto): El cuarto estado. Este sucede en el servidor remoto (como GitHub) donde se aloja nuestro código. Para enviar los cambios desde el repositorio local al remoto, utilizamos el comando `git push`.

Veamos el flujo en detalle:
1. **Working Directory (Directorio de Trabajo)**: Aquí es donde realizas modificaciones en los archivos. Este es el estado `modified`. Todo cambio, creación o eliminación de archivos ocurre en este directorio.
2. **Staging Area (Área de Preparación)**: Con el comando `git add`, movemos los cambios al área de preparación, donde Git comienza a rastrear los archivos que serán incluidos en el próximo commit. Esta área permite decidir qué cambios incluir o excluir.
3. **HEAD (Cabeza del Repositorio Local)**: Con el comando git commit, movemos los cambios desde la "staging area" al historial del repositorio local. Aquí, Git confirma los cambios y los almacena de forma permanente en el historial de versiones.
4. **Remote Repository (Repositorio Remoto)**: Una vez que tenemos los cambios confirmados (commits) en el repositorio local, podemos subirlos al servidor remoto (como GitHub) utilizando git push. Este comando envía los cambios del repositorio local al repositorio remoto, integrándolos con el código ya existente allí.

**Recuerda**: En un entorno de equipo, antes de comenzar a trabajar, asegúrate de tener la última versión del código. Para obtener las actualizaciones más recientes desde el repositorio remoto a tu directorio de trabajo, utiliza el comando git pull, que descarga los cambios y los integra en tu copia local.

**Resumen del flujo básico**:

1. **Modified** → **Staged**: Usa `git add` para mover archivos al área de preparación.
2. **Staged** → **Committed**: Usa `git commit` para registrar los cambios en el historial local.
3. **Committed** → **Remote**: Usa `git push` para enviar los cambios al repositorio remoto.
4. **Remote** → **Working Directory**: Usa `git pull` para obtener los cambios realizados por otros en el equipo.
Este flujo básico es fundamental para cualquier persona que trabaje con código, y es esencial dominarlo para manejar Git con fluidez.

[Indice](#git-de-jonmircha)

## 7. Ejecutando el flujo básico local 0:53:19
Vamos a ejecutar estos comandos.

El primer comando que debemos ejecutar es `git add`, ya que, en Visual Studio Code, detectamos dos cambios pendientes (recuerda evitar el uso de interfaces visuales y acostumbrarte a trabajar con comandos para ganar fluidez en la terminal).

El comando `git add` nos permite mover archivos del estado _modified_ (modificado) al estado _staged_ (preparado). Para ello, puedes ejecutar `git add archivo/directorio`, especificando el nombre del archivo o directorio que deseas preparar. Este enfoque permite agregar archivos uno por uno. Si deseas agregar todos los cambios de una vez, puedes usar `git add .`, lo cual moverá todos los archivos modificados al área de staging.

Una vez que tus archivos están en staging, puedes decidir hacer tu primer registro oficial en el historial del repositorio (por ejemplo, con un mensaje como “first commit” o “primer commit”). Para confirmar estos cambios y comprometerlos en el historial, ejecuta el comando `git commit`. Al hacerlo, se abrirá el editor de código en la terminal, donde podrás escribir un mensaje descriptivo sobre el cambio realizado.

Para una versión más rápida del comando, puedes agregar la bandera `-m`, seguida de tu mensaje entre comillas. Por ejemplo, `git commit -m "primer commit"`. Esto permite registrar el cambio y añadir un mensaje de una sola vez, sin necesidad de abrir el editor.