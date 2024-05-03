# CURSO GIT
## CLASE 1  
**CONCEPTOS BASICOS**

**Control de versiones.-** El control de versiones es un sistema que registra cambios en un codigo fuente es importante por:

-Rendimiento.

-Seguridad.

-Flexibilidad.

**Repositorios.-**
Un respositorio puede verse como una carpeta que almacena las diferentes versiones de los ficheros de un proyecto.

**States**

-Modified.

-Staged.

-commited.

**Commits.-**
Sirven para registrar cambios de los archivos

>Un commit es como guardar una partida en un videojuego si se equivoca se puede volver ahi
 

**PRIMEROS COMANDOS**

**git init.-**
Inicializa o crea un nuevo repositorio en git.

`git init`

**git status.-**
Muestra el estado de los archivos del repositorio.

`git status`

**git add.-**
Mueve los cambios del directorio de trabajo al área del entorno de ensayo.

`git add "Nombre del archivo"`

**git commit.-**
Este comando guadara todos los cambios hechos en los archivos del area de staged

`git commit`

**HEAD.-**
HEAD ( es com un faro ) este puntero sirve a GIT para saber 
en que rama estamos en cada momento.
## CLASE 2
**RAMAS.-**
Una rama es una version de la coleccion de directorios y archivos del repositorio 
con cada rama, 

se crea una copia de la coleccion de archivos actual.

Se podria decir que se crean diferentes copias donde el grupo de programadores

trabajan en diferentes partes del proyecto.

Las ramas nos permitiran a trabajar para resolver problemas especificos 
en el proyecto

**COMANDOS CON RAMAS**

**git branch <nombre_rama>.-**
Ese comando nos permite crear,listar y renombrar ramas 

`git branch`

**git switch <nombre-rama>.-**
El comando nos permite cambiar de rama y poder movernos entre 

las existentes

`git switch`

Para realizar ambos pasos al mismo tiempo(crear rama y moverse a ese rama)

`git switch -c <nombre-rama>`

**git checkout**

El comando nos ayuda a cambiar entre ramas y restaura directorio de trabajo

`git checkout`



