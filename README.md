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

Ejecutando el comando sin ningun nombre de rama se puede

acceder a ver todas las ramas en el repositorio y ver en

cual nos encontramos ubicados.

**git switch <nombre-rama>.-**
El comando nos permite cambiar de rama y poder movernos entre 

las existentes

`git switch`

Para realizar ambos pasos al mismo tiempo(crear rama y moverse a ese rama)

`git switch -c <nombre-rama>`

**git checkout**

El comando nos ayuda a cambiar entre ramas y restablecer cambios hechos en algunos archivos

`git checkout`

**FUSIONAR RAMAS**

La accion de fusionar ramas nos permite fusionar los cambios 

que realizamos en cada rama, de forma que los cambios que hicimos en una rama 

tambien estaran presentes en otra rama

**git merge**

Se emplea el comando git marge para fusionar una rama con la rama 

en la que nos encontramos.

`git merge <nombre de la rama>`

Ademas fusiona los commits presentes en la rama asi tener una nueva 

version del repositorio.

**Conflictos**

Un conflicto se puede entender como una situacion donde se fusionan

dos ramas y una rama hiso cambios en una parte del codigo y otra 

tiene una parte diferente de ese codigo por lo cual git no sabra cual

permanecera o cual es la correcta.

**Resolver Conflictos**

El problema de conflictos se presenta cuando usamos el comando 

git merge en git(al intentar fusionar dos ramas), soltara un mensaje

como el siguiente:

>1 Auto-merging file.txt

>2 CONFLICT (content): Merge conflict in file.txt

>3 Automatic merge failed; fix conflicts and then commit the result.

Las lineas 1 y 2 muestran el archivo exacto en donde es presente

el conflicto, la linea 3 explica que resolvamos el conflicto y 

realizemos un commit.

Una vez ingresando al archivo en cuestion si revisamos encontraremos

una seccion del codigo que sera similar a:

```java
public class Example {
    public void metodoRandom() {
//<<<<<<< HEAD
        System.out.println("Hola a todos");
//=======
        System.out.println("Hola a solo Juan");
//>>>>>>> otra rama
    }
}
```
A primeras se puede observar tres lineas en especial HEAD, ======

y otra rama, eso nos indica el conflicto se encuentra en ese bloque de codigo

el codigo debajo del HEAD pertenece a esa rama y la que esta debajo de 

====== es perteneciente a la otra rama para resolver el conflicto solo

debemos elegir que parte del codigo de cual rama usaremos y la mantenemos y el resto

debe ser eliminada, ya finalmente hacemos un commit y el codigo quedaria:

```java
public class Example {
    public void metodoRandom() {

        System.out.println("Hola a todos");
    }
}
```

Al finalizar la fusion de las ramas lo mejor es eliminar la rama que 

fusionamos con la main para asi no tener ramas libres.

Para realizar ese trabajo se usa el comando git branch -D nombre-rama

`git branch -d <nombre_rama>`

pero antes de eliminar una rama es mejor tener cuidado p