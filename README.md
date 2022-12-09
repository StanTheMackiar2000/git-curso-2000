# Curso _Git_ y _GitHub_

## Configuracion global

```js

git --version
git config --global user.name "Jonathan MirCha"
git config --global user.email jonmircha@gmail.com
git config --global user.ui true
git config --global init.defaultBranch main
git config --list
// asignando visual studio code como editor de configuración de git
git config --global core.editor "code --wait"
git config --global -e
// para estandarizar los saltos de línea en windows
git config --global core.autocrlf true
// para estandarizar los saltos de línea en linux/mac
git config --global core.autocrlf input
// ver todas las opciones de la configuración en la terminal
git config -h
// ver todas las opciones de la configuración en el navegador
git help config

```

## Flujo basico

```js

// agregar los cambios de un archivo al staged
git add archivo/directorio
# agregar todos los cambios de todos los archivos al staged
git add .


// los cambios son comprometidos en el repositorio
// debes escribir el mensaje del cambio
// cuando se abra el archivo de configuración
// al terminar guarda y cierra el archivo
// para que los cambios tengan efecto
git commit
// es un shortcut del comando anterior
// escribes y confirmas el mensaje del cambio en un sólo paso
git commit -m "mensaje descriptivo del cambio"


// se agrega el origen remoto de tu repositorio de GitHub
git remote add origin https://github.com/usuario/repositorio.git
// la primera vez que vinculamos el repositorio remoto con el local
git push -u origin main
// para las subsecuentes actualizaciones, sino cambias de rama
git push


//para descargar los cambios del repositorio remoto al local
git pull

```

# Clonar archivos

```
git clone https://github.com/StanTheMackiar/git-curso/tree/main
```

# Ramas

```js
// crear rama
git branch nombre-rama

// cambiar de rama
git checkout nombre-rama

// crear una rama y cambiarte a ella
git checkout -b rama

// eliminar rama
git branch -d nombre-rama

// eliminar ramas remotas
git push origin --delete nombre-rama

//eliminar rama (forzado)
git branch -D nombre-rama

// listar todas las ramas del repositorio
git branch

// lista ramas no fusionadas a la rama actual
git branch --no-merged

// lista ramas fusionadas a la rama actual
git branch --merged

// rebasar ramas
git checkout rama-secundaria
git rebase rama-principal
```
