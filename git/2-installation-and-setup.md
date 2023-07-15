# INSTALACION Y CONFIGURACION
## GIT CLI VS GUI
Existen dos maneras de interactuar con **Git**. La primera y la más importante es mediante la consola de comandos y la otra es mediante un software con interfaz gráfica.

La consola de comandos es la manera tradicional de interactuar con Git. Con el aumento de su popularidad comenzaron a aparecer cada vez más programas que permitían interactuar con Git mediante una interfaz gráfica, como por ejemplo:
- GitHub Desktop
- SourceTree
- Tower
- GitKraken
- Ungit

### GUI

#### PROS
- Es más atractivo para usuarios nuevos de Git
- Es más intuitivo de utilizar, sobretodo para usuarios nuevos
- Algunas personas prefieren una interfaz gráfica a una consola de comandos
#### CONTRAS
- Utilizando una interfaz gráfica, ignoras las instrucciones y funcionamiento que hay detrás de las acciones realizadas
- Puede provocar dependencia a un software en particular
- Es más dificil solucionar un problema cuando algo sale mal
- La manera de trabajar cambia entre diferente software de Git con GUI
### CLI
#### PROS
- Git es una herramienta que fue diseñada para ser utilizada por la consola de comandos, por lo que la documentación y recursos oficiales se refieren todos a la consola de comandos
- Una vez dominada, la consola de comandos puede ser mucho más rápida que la interfaz gráfica
- Algunas de las funcionalidades más avanzadas solo se encuentran disponibles en CLI
- Los comandos son siempre los mismos, independientemente del sistema o equipo que estemos utilizando
#### CONTRAS
- Puede resultar intimidante para usuarios nuevos
- A pesar de todo, algunos usuarios pueden preferir la interfaz gráfica
-


## INSTALACION WINDOWS
Originalmente, Git fue diseñado para trabajar en Linux y Mac, por lo que para poder trabajar con Git en Windows, necesitaremos un emulador de consola de Linux en nuestro equipo Windows.

El instalador oficial de Git para Windows nos incluye el emulador de **Bash** llamado **Git Bash**. La descarga e instalación es relativamente sencilla, debemos dirigirnos a la [página oficial de descarga de Git](https://git-scm.com/download/win), descargar el ejecutable de instalación e instalar el programa.

## CONFIGURACION
### MODIFICAR NOMBRE Y CORREO
Una vez instalado Git, debemos configurar alguna información básica como proporcionar un nombre de usuario y un correo electrónico con los que se registrarán los cambios realizados.

El nombre de usuario debe ser uno con el que queramos ser identificado y no es recomendable cambiarlo. En cuanto al correo, se recomienda usar el mismo con el que crearemos una cuenta en **GitHub**.

Comando para establecer el nombre de usuario con el que asociaremos nuestro trabajo:
````bash
git config --global user.name "Mykyta Metelytsya"
````
#cmd

Comando para ver nuestro nombre de usuario:
````bash
git config user.name
````
#cmd 

Comando para establecer un correo electrónico con el que asociaremos nuestro trabajo:
````bash
git config --global user.email "shadyrnb@gmail.com"
````
#cmd 

Comando para ver nuestro correo electrónico:
````bash
git config user.email
````
#cmd 

> El flag `--global` permite que estos cambios se apliquen a todos los repositorios con los que trabajaremos dentro del equipo
### MODIFICAR EDITOR POR DEFECTO
Para modificar el editor de texto que usaremos conjuntamente con Git a la hora de ejecutar cierto comandos usaremos el siguiente comando: 
````bash
git config --global core.editor "path" #Path indica la ruta absoluta de nuestro editor de texto
````