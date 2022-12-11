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

## Fusiones

```js
// nos cambiamos a la rama principal que quedará de la fusión
git checkout rama-principal
// ejecutamos el comando merge con la rama secundaria a fusionar
git merge rama-secundaria
```

## Agregar modificaciones al ultimo cambio

```js
// sin editar el mensaje del último commit
git commit --amend --no-edit

// editando el mensaje del último commit
git commit --amend -m "nuevo mensaje para el último commit"

// eliminar el último commit
git reset --hard HEAD~1

```

## Desplazarse en el historial del respositorio

```js
// cambiar a una rama
git checkout nombre-rama

// cambiar a un commit en particular
git checkout id-commit

```

## Registro del historial

```js
git log

// muestra en una sola línea por cambio
git log --oneline

// guarda el log en la ruta y archivo que especifiquemos
git log > commits.txt

// muestra el historial con el formato que indicamos
git log --pretty=format:"%h - %an, %ar : %s"

// cambiamos la n por cualquier número entero y mostrará los n cambios recientes
git log -n

// muestra los cambios realizados después de la fecha especificada
git log --after="2019-07-07 00:00:00"

// muestra los cambios realizados antes de la fecha especificada
git log --before="2019-07-08 00:00:00"

// muestra los cambios realizados en el rango de fecha especificado
git log --after="2019-07-07 00:00:00" --before="2019-07-08 00:00:00"

// muestra una gráfica del historial de cambios, rama y fusiones
git log --oneline --graph --all

// muestra todo el registro de acciones del log
// incluyendo inserciones, cambios, eliminaciones, fusiones, etc.
git reflog

// diferencias entre el Working Directory y el Staging Area
git diff

```


## Reseteo del historial

```js
//nos muestra el listado de archivos nuevos (untracked), borrados o editados
git status

// borra HEAD
git reset --soft

// borra HEAD y Staging
git reset --mixed

// borra todo: HEAD, Staging y Working Directory
git reset --hard

// deshace todos los cambios después del commit indicado, preservando los cambios localmente
git reset id-commit

// desecha todo el historial y regresa al commit especificado
git reset --hard id-commit


```

