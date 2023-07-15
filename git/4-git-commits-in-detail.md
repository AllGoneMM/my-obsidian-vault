# GIT COMMIT EN DETALLE Y OTRAS CUESTIONES
## DOCUMENTACION DE GIT
Es importante conocer que existe una documentación oficial de Git en su [página oficial](https://git-scm.com/doc), esto puede resultar muy útil, sobretodo porque cada comando en Git tiene múltiples opciones y posibilidades.
## ATOMIC COMMITS
Este término se refiere a que cada commit debe encapsular una única nueva funcionalidad, cambio o resolución. Es decir, que dentro de lo posible, cada commit debe estar centrado en una única cosa. Realizar commits que incluye más de una funcionalidad es una mala práctica.
## CONVENCION DE MENSAJES DE COMMIT
Existen una serie de convenciones a la hora de nombrar commits. El uso de estas convenciones a la hora de realizar commits nos ofrece múltiples ventajas, como por ejemplo:
- Fácil identificación del propósito del commit y su descripción
- Mejor organización y comunicación si se trabaja en grandes equipos
- Generación automática de *changelogs*

Podemos encontrar la página oficial donde se indican las convenciones [aquí](https://www.conventionalcommits.org/en/v1.0.0/#summary).

### RESUMEN DE CONVENCIONES
Cada commit debe estar formado por: **una cabecera**, **un cuerpo** y un **pie de página**:
````text
<tipo de commit>(<módulo donde se realiza el cambio>): <breve descripción>

<cuerpo>

<pie de página>
````
Ejemplo:
`docs(changelog): update changelog to beta.5`
````
fix(release): need to depend on latest rxjs and zone.js

The version in our package.json gets copied to the one we publish, and users need the latest of these.
````
> Importante: si un commit revierte los cambios de otro, el encabezado debe comenzar por `revert:` seguido del encabezado del commit a revertir. En el cuerpo debemos especificar: `This reverts commit <hash>`
#### ENCABEZADO
- **Tipo de commit**: indica el propósito del commit, puede ser alguno de los siguientes:
	- **docs**: Cambios producidos en la documentación del proyecto
	- **feat**: Indican la introducción de una nueva funcionalidad
	- **fix**: Indica la solución de un error
	- **perf**: Indica el cambio de código para mejorar el rendimiento
	- **refactor**: Indica código que no introduce una nueva funcionalidad ni arregla un error
	- **style**: Indica cambios que mejoran la legibilidad del código 
	- **test**: Indica que se han incluido o corregido tests
- **Módulo donde se introduce el cambio**: bastante descriptivo. Esta parte es opcional y no siempre es obligatorio incluirlo
- **Breve descripción**: debemos utilizar el presente del imperativo, sin mayúsculas y sin punto al final

#### CUERPO 
El cuerpo del commit debe incluir las causas que han motivado a realizar el cambio o ampliar la descripción del encabezado. Debe estar escrito en el presente del imperativo.

#### PIE DE PAGINA
Se utiliza para indicar cambios dicho cambio ha roto alguna funcinalidad anterior o la haya cambiado drásticamente. Debemos comenzar el pie de página indicando `BREAKING CHANGE` seguido de un espacio y una descripción de la funcinalidad afectada.

> Un commit nunca debería de superar la longitud de 100 caracteres.

> Esta convención es específica de Angular, aunque está bastante extendida en otros frameworks.
## MODIFICAR UN COMMIT
### AMEND
Este *flag* del comando commit nos permite modificar el último commit realizado en caso de que, por ejemplo, hayamos olvidado incluir un fichero o queramos modificar el mensaje de nuestro commit.

Antes de utilizar el comando debemos modificar y/o agregar los ficheros que queramos incluir en el último commit. A continuación introducimos el comando, que nos abrirá nuestro editor por defecto donde podremos también cambiar el mensaje del commit:
````bash
git commit --amend
````
#cmd 

## GITIGNORE
`.gitignore` es un fichero oculto que usaremos dentro del directorio raiz de nuestro proyecto con un repositorio Git inicializado en el que indicaremos ficheros y directorios que queremos que Git no guarde en el repositorio, algunos de los archivos que puede ser util incluir en este fichero pueden ser:
- Ficheros que contienen credenciales o información sensible
- Ficheros de configuración de nuestro editor de texto
- Ficheros de log
- Dependencias

Cada línea dentro de nuestro fichero `.gitignore` indicará un fichero o directorio que queramos ignorar:
- Los directorios se indicarán con una barra al final: **nombre-directorio/**
- Los nombres de los ficheros se indicarán de manera literal sin ningún añadido
- Podemos utilizar expresiones regulares como, por ejemplo, **\*.log**. Esto ignorará todos los archivos que terminen en **.log**
- 
Existen diferentes [plantillas](https://www.toptal.com/developers/gitignore) de `.gitignore` para frameworks/lenguajes específicos.
