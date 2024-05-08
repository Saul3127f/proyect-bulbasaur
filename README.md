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

**git log**

Comando que muestra todos los commits realizados hasta el momento

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

Para realizar ese trabajo se usa el comando git branch -d nombre-rama

`git branch -d <nombre_rama>`

pero antes de eliminar una rama es mejor revisar si las ramas fueron 

fusionadas correctamente porque suele pasar que puedes eliminar

horas de trabajo, por suerte git te notificara en ese caso.

>El comando git branch -D elimina la rama directamente

>El comando git branch -d te notificara si eliminar la rama tiene riesgos

## CLASE 3

**GITHUB**

Github es un servicio en la nube especializado en el control de versiones

de git, son completamente diferentes.

**Repositorios remotos**

Un repositorio remoto es simplemente una version de tu repositorio que se 

encuentran en internet.

**git push**

El comando nos permite subir todos los cambios que hicimos al repositorio local

al repositorio remoto asi tener ambos repositorios conectados y actualizados

`git push <origin><main>`

**git push -f**

Este comando forsa la actualizacion de una rama remota evitando todas las 

advertencias.

**git push --all**

El comando actualiza todas las ramas que trabajamos en el repositorio local

al repositorio remoto.

**git push -u**

El comando ayuda a simplificar el trabajo de maner que en el siguiente push 

solo ponemos git push y ya reconocera a que rama nos referimos.

**git push --delete**

El comando git push -delete ayuda a eliminar ramas remotas

`git push origin --delete main`

**Crear ramas remotas**

Para crear un rama remota es primordial primero crear una rama local luego

con la ayuda del siguiente comando se podra crear la rama remota

`git push <origin> <nombre_rama>`

>si la rama no existe de manera local existira un error 

## CLASE 4

**git pull**

El git pull es un comando que nos permite descargar el contenido de un

repositorio remoto lo cual nos permite extraer todo el contenido 

de ese repositorio remoto y actualizar nuestro repositorio local.

>Un git merge se puede ver como dos comandos juntos un git fetch el cual descargara 

>el contenido de la rama principal y con un git merge las fusionara

**pull request**

El git request es una funcionalidad de github la cual permite revisar los cambios realizados

en alguna rama del repositorio antes de realizar un git merge o fusionar las ramas

**Consejos antes de realizar un pull request**

 * Lee el archivo contributing.md el cual te dara un pantallazo de como trabajar en el repositorio
 * Procura que tu aporte sea lo mas parecido al trabajo original 
 * Enfoca tu ayuda en una parte en concreto
 * Redacta en tu pull request muy especifico de que es los cambios que realizaste