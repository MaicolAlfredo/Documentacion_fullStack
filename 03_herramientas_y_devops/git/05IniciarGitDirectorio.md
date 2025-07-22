## 5.🚀 Inicializar Git en un Directorio

Esta guía te explica el proceso para configurar un nuevo repositorio de Git en un directorio local, cubriendo los comandos y archivos esenciales involucrados.

---

### Pasos para la Inicialización de Git

1.  **Navegar a tu directorio deseado**:

    - Escribe `cd`(change directory) en tu terminal.
    - Luego, arrastra la carpeta que quieras usar (por ejemplo, tu "Escritorio") y suéltala en la terminal. Esto generará la ruta de la carpeta.
    - Presiona `Enter`.

2.  **Crear una nueva carpeta (opcional)**:

    - Escribe `mkdir "nombre-de-tu-carpeta"` (por ejemplo, `mkdir youtube-git`) en la terminal.
    - Presiona `Enter`.

3.  **Cambiar a esa nueva carpeta**:

    - Usa `cd youtube-git` (o el nombre que le hayas dado a tu carpeta) para moverte dentro de ella.
    - Presiona `Enter`.

4.  **Crear archivos esenciales**:

    - Crea el archivo `README.md` con `touch README.md`. Este archivo es fundamental para documentar y explicar tu proyecto.
    - Crea el archivo `.gitignore` con `touch .gitignore`. Git utiliza este archivo para saber qué carpetas o archivos debe ignorar del control de versiones.

5.  **Verificar archivos (opcional)**:

    - Si ejecutas `ls`, no verás el archivo `.gitignore` porque es un archivo oculto. Para ver todos los archivos, incluyendo los ocultos, usa `ls -a`.

6.  **Inicializar Git en el directorio**:

    - Para que esta carpeta empiece a ser rastreada por Git, debes ejecutar el comando `git init`. Este comando solo se ejecuta **una sola vez** para inicializar un repositorio.

7.  **Abrir el editor de código**:
    - Usa `code .` para abrir el directorio actual en tu editor de código (como Visual Studio Code).

---
