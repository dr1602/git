# Curso de Git

## Lista de comados

Para revisar la version:
```sh
> - git --version
```

Para iniciar git:
```sh
> - git init
```

Para cambiar la rama default:
```sh
> - git config init.defaultBranch main
```

Para cambiar de rama:
```sh
> - git branch -m main
```

Para recibir ayudade las diferentes ramas de git:
```sh
> - git --help
```

Para configurar git con nombre de usuario:
```sh
> - git config global user.name "Drs1602"
```

Para configurar git con correo:
```sh
> - git config global user.email "ejemplo@mail.com"
```

Para ver la configuracion:
```sh
> - git config --list
```

Para ver la carpeta con todos los cambios de git puedes usar el siguiente comando desde el root:
```sh
> ls -a
```

Para crear un archivo de texto desde terminal editable en terminal:
```sh
> nano testing.txt
```

Para guardar, confirmar guardar y salir:
```sh
CTRL X
y
ENTER
```

Comandos adicionales de terminal y de GIT:
```sh
# Directorio de Trabajo
cp
mv
touch
create
ramadelete

# Area de Staging
git add <file>
git rm --cached <file> # para sacarlo de staging
git rm --force <file>

# Repositorio Git
git commit
git commit -ammend
git reset --soft
git reset --mixed
git reset --hard
```

(https://education.github.com/git-cheat-sheet-education.pdf)[CheatSheet]

Para ver los cambios que has hecho:
```sh
> git log
```

## Ramas

Para ver las ramas y en que rama te encuentras
```sh
> git branch
```

Para crear una nueva rama y cambiarte hacia dicha rama
```sh
> git branch
```

Para crear una archivo y poderlo editar desde Nano
```sh
> nano testingdave.txt
```

### Archivo con Nano

Para guardar un archivo con arbol
```sh
> ctr + o
> enter
```

Para cerrar el archivo
```sh
> ctr + x
```

### De vuelta a las ramas

Un nuevo metodo para cambiar de rama es:
```sh
> git switch ***
```

Ejemplo:
```sh
> git switch main
```

Para hacer merge de las ramas o fucionarlas:
```sh
> git marge daves
```

para ver el historial de los archivos creados, modificados, etc.
```sh
> git log
```

para cerrar un git log, usar:
```sh
> q
```

ya que se unifico la rama individual con la secundaria, ya no se necesita tener la rama secundaria por lo que se requiere eliminar. asi evitamos tener ramas duplicados o evitar problemas

Para eliminar:
```sh
> git branch -D dave
```

## Git Reset y Git Revert

**git reset**: te devuelve a un commit anterior, eliminando los cambios en el historial como si nunca hubieran ocurrido. Explorar el historial de commits, también sirve para recordar que se estuvo haciendo en cada uno de los commits. Ver los punteros y regresar al útlimo commit

**git revert**: crea un nuevo commit que "revierte" los cambios realizados por un commit específico.

1. Para este ejercicio se realiza:

```sh
> nono error.txt
> git add .
> git commit -m 'nuevo archivo especial creado'
> git log
```
y nos fijamos en el identificador:

```sh
0d2c018c3c65e26e4a19f3dfbc6ff6ccd9db0036


commit 0d2c018c3c65e26e4a19f3dfbc6ff6ccd9db0036 (HEAD -> main)
Author: dr1602 <david.arangelg@gmail.com>
Date:   Tue Feb 4 21:42:08 2025 -0600
```

```sh
git reset 0d2c018c3c65e26e4a19f3dfbc6ff6ccd9db0036 --no-edit
```

Para git reset existen para volver atrás entre versiones..., y te puede convenir trabajando con tu equipo..

```sh
git reset --hard
git reset --mix
git reset --soft
```