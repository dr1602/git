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

## Git tag y git checkout

**git tag**: un tag es como una etiqueta que peudes aplicar a un commit para indetificarlo fácilmente en el futuro.

**git checkout**: cambiar de una rama a un commit específico a otro, también puede servir para comparar ramas, sin que se afecte a la rama principal

### Git tag
Para asignar un tag mas un mensaje al ultimo commit
```sh
> git tag -a v1.0 -m 'Mi primer version'
```

para buscar o generar una lista de tags
```sh
> git tag
```

para profundizar que dice la version segun el tag
```sh
> git show <tag>
> git show v1.0
```
*Ese comando te muestra información como:*
1. Persona que hace el commit
2. $$
3. dato del commit
4. cambios
5. mensaje
6. otros

para borrar un tag sin afectar un commit
```sh
> git tag -d <tag>
> git tag -d v1.0
```
**No modifica que el historial de los commits, sólo agrega un nuevo separador**

para revisar un punto en particular sin modificar el trabajo que actualmente estoy haciendo
```sh
> git checkout <hash_del_commit>
```
### Notas desde la consola sobre este comando

You are in 'detached HEAD' state. You can look around, make experimental
changes and commit them, and you can discard any commits you make in this
state without impacting any branches by switching back to a branch.

If you want to create a new branch to retain commits you create, you may
do so (now or later) by using -c with the switch command. Example:

  git switch -c <new-branch-name>

Or undo this operation with:

  git switch -

*para volver a la rama principal*
```sh
> git checkout main
```

*para confirmar que nada sucedió:*
```sh
> git log
> git branch
```

y verás que no hay nuevas ramas, ni cambios, es una ram dummy

## [Como resolver conflictos de rama en git](Como resolver conflictos de rama en git)

1. creas un archivo en nano
2. haces una nueva branch
3. modificas los cambios en la nueva branch
4. haces commit de los cambios
5. regresas a la rama main
6. haces cambios al mismo archivo de nano desde la rama main
7. haces commit de esos cambios
8. procedes a hacer merge con:

```sh
> git merge developer
```
*arroja:*

Auto-merging conflict.txt
CONFLICT (content): Merge conflict in conflict.txt
Automatic merge failed; fix conflicts and then commit the result.

*reedito los cambios en nano, de este caso específico con:*
```sh
> git merge developer
```

*reviso los cambios con*
```sh
> git status
```