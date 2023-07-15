# CONCEPTOS BASICOS DE GIT: ADD Y COMMIT
## ¿QUE ES UN REPOSITORIO?
Un repositorio es un espacio de trabajo en el que desarrollaremos un proyecto en concreto. Cada repositorio es independiente de otros dentro de nuestro equipo, con su propio propósito e historial de modificaciones.
## GIT STATUS Y GIT INIT
### GIT STATUS
Este comando nos proporciona información del estado en el que se encuentra nuestro repositorio y todos sus contenidos:
````bash
git status
````
#cmd 
### GIT INIT
Este comando crea un repositorio de Git en el directorio actual, debe emplearse al menos una vez por proyecto en el que queramos utilizar Git:
````bash
git init
````
#cmd

Este comando crea un directorio llamado `.git` donde se almacenará toda la información del historial de nuestro repositorio.
> Si eliminamos `.git` perderemos todo nuestro historial de cambios.

> Debemos tener cuidado de no crear un repositorio dentro de otro. Para ello, antes de utilizar `git init`, podemos comprobar si nos encontramos en un repositorio con `git status`.

## GIT ADD Y GIT COMMIT
Uno de los principales propósitos de Git o de cualquier CVS, es poder crear diferentes puntos de restauración en nuestros proyectos tras realizar algunos cambios. Estos puntos de restauración se conocen como *commits*.
### FLUJO DE TRABAJO DE LOS COMMITS
1. Trabajamos en nuestro proyecto realizando cambios
2. Agrupamos los cambios realizados en diferentes grupos clasificados según el proposito final de ese conjunto de cambios
3. Realizamos el *commit*

![commit-workflow](../img/commit-workflow.png)
> **Working directory** es nuestro directorio de trabajo en el que se encuentra inicializado nuestro repositorio Git, **staging area** es el paso previo al commit y **repository** se refiere a la carpeta `.git` donde se guardará todo nuestro historial de cambios.
### GIT ADD
Este comando permite añadir archivos que han sido modificados al **staging area** antes de registrarlos con un `commit`:
````bash
git add file1 file2 file3
git add . # Añade todos los archivos modificados dentro del directorio al staging area
````
#cmd 

### GIT COMMIT
El comando `commit` registra los cambios realizados de los archivos que se encuentran en el **staging area**. Cuando realizamos un **commit** debemos proporcionar un mensaje que resume los cambios realizados.

Hay dos maneras de ejecutar el comando `commit`:

Al ejecutar este comando se nos abrirá el editor de texto establecido por defecto para introducir un mensaje para dicho commit y a continuación se registrarán los cambios:
````bash
git commit
````
#cmd 

De esta otra forma podremos realizar el **commit** especificando el mensaje directamente:
````bash
git commit -m "mensaje"
````
#cmd 
#### COMMIT FLAGS
Mediante el flag `-a`, podremos ejecutar commit directamente sin pasar por el comando `add`:
> `-a` añadirá todos los cambios, sería lo mismo que ejecutar `git add .`
> Este flag no funcionará si añadimos un archivo nuevo

````bash
git commit -a -m "nombre-commit"
````
#cmd

### GIT LOG
Conforme vayan aumentando el número de commits realizados en nuestro repositorio, es posible que deseamos poder **ver todos los commits** de alguna manera, para ello utilizamos el siguiente comando, que nos mostrará una lista con todos los **commits** realizados con sus respectivos datos, como la fecha en la que se realizó, el autor y el mensaje del commit:
````bash
git log
````
#cmd 

Si queremos visualizar los commits de una manera más abreviada, podemos usar el siguiente comando:
````bash
git log --oneline
````
#cmd
