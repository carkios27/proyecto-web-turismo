# Explora Perú — proyecto de práctica con Git y GitHub

## 1. Abrir el proyecto en Visual Studio Code
1. Descarga y descomprime `proyecto_web_turismo.zip`.
2. Abre Visual Studio Code.
3. Ve a **Archivo > Abrir carpeta...** y selecciona `proyecto_web_turismo`.
4. Abre `index.html` en el navegador. Puedes usar la extensión **Live Server** si la tienes instalada.

## 2. Crear el repositorio local y publicarlo
En VS Code, abre **Terminal > Nueva terminal** dentro de esta carpeta. Ejecuta:

```bash
git init
git add .
git commit -m "Crear página inicial de Explora Perú"
git branch -M main
```

Crea un repositorio vacío en https://github.com/new llamado `proyecto-web-turismo`. No agregues README, licencia ni `.gitignore` en GitHub si ya vas a subir estos archivos locales. Después enlázalo (reemplaza TU-USUARIO):

```bash
git remote add origin https://github.com/TU-USUARIO/proyecto-web-turismo.git
git push -u origin main
```

## 3. Clonar una segunda copia
Vuelve a la carpeta anterior en la terminal y ejecuta el comando desde una ubicación donde no exista ya una carpeta con ese nombre:

```bash
cd ..
git clone https://github.com/TU-USUARIO/proyecto-web-turismo.git proyecto-web-turismo-copia
```

Abre la carpeta `proyecto-web-turismo-copia` en una segunda ventana de VS Code (**Archivo > Nueva ventana**, luego **Abrir carpeta**).

## 4. Hacer al menos dos cambios visibles en la segunda copia
En `proyecto-web-turismo-copia/index.html`, por ejemplo:
- Cambia el título principal a `Machu Picchu te espera`.
- Cambia el párrafo descriptivo para incluir una frase personal.

Guarda y comprueba en el navegador. Registra y sube los cambios:

```bash
git add .
git commit -m "Personalizar textos de la página"
git push
```

## 5. Actualizar la primera copia con git pull
Regresa a la terminal de la primera carpeta `proyecto_web_turismo` y ejecuta:

```bash
git pull origin main
```

Abre o actualiza `index.html` en el navegador y toma una captura donde se vean los cambios recibidos.

## 6. Crear una rama, añadir una mejora e integrarla a main
Haz esto en la segunda copia, después de que esté sincronizada:

```bash
git switch -c mejora-boton
```

Edita `index.html` y cambia el texto del botón principal, por ejemplo, de `Descubrir el destino` a `¡Quiero conocerlo!`. Guarda el archivo y verifica el cambio visual. Luego:

```bash
git add .
git commit -m "Mejorar texto del botón principal"
git push -u origin mejora-boton
```

En GitHub puedes abrir un **Pull request** de `mejora-boton` hacia `main` y pulsar **Merge pull request**. Alternativamente, para practicar la integración local:

```bash
git switch main
git pull origin main
git merge mejora-boton
git push origin main
```

Si haces el merge en GitHub, vuelve a la primera copia y ejecuta `git pull origin main`. Si haces el merge local desde la segunda copia, igualmente ejecuta `git pull origin main` en la primera copia.

## 7. Evidencias que debes entregar
Guarda capturas reales (no simuladas) en una carpeta llamada `evidencias`:
1. Página inicial abierta en el navegador.
2. Terminal mostrando `git init`, el primer `git commit` y `git push`.
3. Segunda copia abierta en VS Code y los dos cambios visibles en el navegador.
4. Terminal mostrando `git clone`.
5. Rama `mejora-boton` visible en VS Code o con `git branch`, y el botón mejorado en el navegador.
6. Pull request integrado en GitHub o terminal mostrando `git merge` y `git push`.
7. Primera copia actualizada después de `git pull`, con el resultado final en el navegador.
8. Repositorio de GitHub abierto y su URL visible.

No inventes ni edites las capturas para aparentar comandos que no ejecutaste: deben mostrar tu propio proceso.

## 8. Explicación breve de los comandos
- `git init`: inicia un repositorio Git en la carpeta del proyecto.
- `git add .`: prepara los archivos modificados para el siguiente commit.
- `git commit -m "mensaje"`: guarda una versión de los cambios en el historial local.
- `git push`: envía commits al repositorio remoto de GitHub.
- `git clone URL`: descarga una copia del repositorio remoto en otra carpeta.
- `git pull`: trae cambios del remoto y los integra en la rama local actual.
- **Rama (`git switch -c nombre`)**: crea y activa una línea de trabajo independiente para desarrollar una mejora sin modificar directamente `main`.
- `git merge nombre`: integra los cambios de otra rama en la rama actual.

## 9. Comprobación final
En ambas carpetas puedes ejecutar:

```bash
git status
git branch
git log --oneline --all --graph
git remote -v
```

Antes de entregar, confirma que el repositorio sea público (si así lo solicita el docente), que `main` tenga la versión final y que el enlace de GitHub abra correctamente.
