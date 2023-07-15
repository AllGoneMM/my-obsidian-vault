# RAMAS
## RAMIFICACION
La ramificación o *branching* es una de las principales características que ofrecce Git. Se trata de crear ramas o *branches* que son líneas de desarrollo independientes que permiten trabajar de forma simultánea en el desarrollo de diferentes funcionalidades del proyecto.

### VISUALIZAR RAMAS
Para poder visualizar todas las ramas existentes en nuestro repositorio usaremos el siguiente comando, este nos devolverá un listado de las ramas indicando con un **\*** la rama que se encuentra activa actualmente:
````bash
git branch
````
#cmd 

#### FLAGS
Para visualizar todas las ramas existentes junto a información adicinal como el último commit de cada rama junto con su *hash* usaremos el *flag* `-v`:
````bash
git branch -v
````
#cmd 


### CREAR RAMAS
Para poder crear una nueva rama podemos usar el siguiente comando:
>Debemos tener en cuenta que la rama se creará a partir del commit al que estaremos apuntando en ese momento con **HEAD** y que **HEAD** no se cambiará a dicha rama automáticamente.

````bash
git branch <nombre-rama>
````
#cmd 

### NAVEGAR ENTRE RAMAS
#### GIT SWITCH
Una vez tengamos más de una rama, podemos navegar entre estas mediante el siguiente comando:
````bash
git switch <nombre-rama>
````
#cmd 
##### CAMBIANDO DE RAMA SIN GUARDAR LOS CAMBIOS
Hay que tener en cuenta el comportamiento que tiene Git si tratamos de cambiar de rama sin haber realizado un commit de los cambios:
- Si el cambio realizado es una modificación de un archivo, Git nos advertirá de esto y nos pedirá que realicemos un **commit** o **stash**
- Si el cambio realizado es un archivo nuevo que hemos añadido al proyecto, al no entrar en conflicto con ningún archivo existente, Git nos dejará cambiar de rama sin problema
##### FLAGS
###### CREAR Y CAMBIAR DE RAMA
Podemos utilizar `git switch` para crear y cambiar de rama de manera simultánea mediante el flag `-c` (*create*):
````bash
git switch -c <nombre-rama> 
````
#cmd 

#### GIT CHECKOUT
`git checkout` es el único comando que existía antes para cambiar de rama, sin embargo, además de poder utilizarse para poder cambiar de rama tenía otros usos que podían llevar a confusión, es por esto que se introdujo `git switch`. El comando es el siguiente:
````bash
git checkout <nombre-rama>
````
#cmd 
> Algunos otros usos que tiene `git checkout` son:
> - Crear una nueva rama y cambiar a ella
> - Cambiar a un commit específico
> - Si existen cambios sin confirmar y usamoss `git checkout` para cambiar de rama, estos cambios se trasladarán a la rama que cambiemos
##### FLAGS
###### CREAR Y CAMBIAR DE RAMA
Es el equivalente a utilizar `git switch -c` para crear una nueva rama y cambiar a ella:
````bash
git checkout -b <nombre-rama>
````
#cmd 
### BORRAR Y RENOMBRAR RAMAS
#### BORRAR RAMA
Para poder borrar una rama que se encuentra *totalmente fusionada* emplearemos el comando `git branch` con el *flag* `-d`/`--delete`:
> No podemos borrar una rama si nuestro *HEAD* está apuntando a dicha rama, primero tendremos que posicionarnos en otra rama diferente.
````bash
git branch -d <nombre-rama>
````
#cmd 

Para forzar el borrado de una rama podemos usar `--force` o `-D`:
````bash
git branch -D <nombre-rama>
````
#cmd 


#### RENOMBRAR RAMA
Al igual que para el borrado, para renombrar una rama se utiliza el comando `git branch`, esta vez en combinación con el *flag* `-m`/`--move`:
> Al contrario de lo que sucede con el borrado, para renombrar una rama debemos estar posicionados dentro de la rama
````bash
git branch -m <nuevo-nombre>
````
#cmd 

Para forzar el renombrado de una rama podemos utilizar `--force` o `-M`:
````bash
git branch -M <nuevo-nombre>
````
#cmd 

## HEAD
**Head** es un concepto que veremos a menudo si trabajamos con Git. **Head** es un **puntero** que referencia el contexto actual en el que nos encontramos trabajando (*branch*) que a su vez estará referenciando a un commit.

>Por defecto, **Head** siempre apuntará a nuestro commit más reciente.

## FUSION DE RAMAS
Cuando terminamos de realizar un cambio en una rama que estamos trabajando, normalmente nos interesará combinar estos cambios con otra rama que suele ser nuestra rama principal u otra rama diferente, esto se llama **merging**.

El comando para fusionar ramas es el siguiente:
````bash
git merge <nombre-rama>
````
#cmd 

> Cuando realizamos un *merging* estamos fusionando ramas, no commits específicos.


> El merge siempre se realiza posicionándose a la rama a la que se quiere fusionar, por ejemplo:
> Si tenemos una rama principal llamada *main* que queremos fusionar con una rama llamada *feature* en la que hemos terminado de desarrollar una funcionalidad, entonces deberemos posicionar nuestro *HEAD* en main y a continuación ejecutar `git merge`.

- recursive strategy
- fast forward
- conflicting merge