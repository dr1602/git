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