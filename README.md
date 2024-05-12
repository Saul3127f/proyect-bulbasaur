# CURSO GIT
## CLASE 1  
**CONCEPTOS BASICOS**

**Control de versiones** 

El control de versiones es un sistema que registra cambios en un codigo fuente es importante por:

-Rendimiento.

-Seguridad.

-Flexibilidad.

**Repositorios**

Un respositorio puede verse como una carpeta que almacena las diferentes versiones de los ficheros de un proyecto.

**States**

Los archivos en git pasan por tres estados principales

* Modified:Los archivos de un repositorio fueron modificados 

* Staged: Los archivos estan en el area de staged cuando los cambios fueron confirmados

* Commited: Los archivos fueron actualizados en el repositorio y se creo un commit de los cambios realizados.

**Commits**

Sirven para registrar cambios de los archivos.

>Un commit es como guardar una partida en un videojuego si se equivoca se puede volver ahi
 

**PRIMEROS COMANDOS**

**git init**

Inicializa o crea un nuevo repositorio en git.

`git init`

**git status**

Muestra el estado de los archivos del repositorio.

`git status`

**git add**

Mueve los cambios del directorio de trabajo al área del entorno de ensayo.

`git add "Nombre del archivo"`

De esta manera se suben los archivos de uno en uno al area de staged pero existe un 

comando que nos permite realizar los cambios de manera mas rapida

`git add .`

Este comando subira todos los archivos que estan en el area de modified al area de staged

**git commit**

Este comando guadara todos los cambios hechos en los archivos del area de staged.

`git commit`

**git commit -m**

El comando nos permite escribir el mensaje del commit desde la terminal.

`git commit -m "mensaje"`

**git log**

Comando que muestra todos los commits realizados hasta el momento.

`git log`

**git --help**

El comando que nos permite acceder a la documentacion  de determinado comando de modo de una pagina web

y poder ver todas las opciones que nos permite el comando.

`git <comando> --help`

Existe otro comando que nos permite ver una descripcion mas pequeña de un comando solo en la terminal

`git <comando> -h`

Este comando nos mostrara una pequeña descripcion del comando en la terminal.

**git restore**

El comando nos ayuda a restaurar cambios anteriores al ultimo commit.

`git restore <archivo>`

**git commit --amend -m "mensaje"**

Nos ayudara a reescribir el ultimo commit que hicimos si es que nos equivocamos en la redaccion.

**Punteros**

Los punteros en git son como unos faros nos indicaran en que rama estamos trabajando en la 

terminal se encuentran a lado del directorio donde estamos trabajando

## CLASE 2

**RAMAS**

Una rama es una version de la coleccion de directorios y archivos del repositorio 
con cada rama. 

se crea una copia de la coleccion de archivos actual.

Se podria decir que se crean diferentes copias donde el grupo de programadores

trabajan en diferentes partes del proyecto.

Las ramas nos permitiran a trabajar para resolver problemas especificos 

en el proyecto.

**COMANDOS CON RAMAS**

**git branch <nombre_rama>**

Ese comando nos permite crear,listar y renombrar ramas 

`git branch`

Ejecutando el comando sin ningun nombre de rama se puede

acceder a ver todas las ramas en el repositorio y ver en

cual nos encontramos ubicados.

**git switch <nombre-rama>**

El comando nos permite cambiar de rama y poder movernos entre 

las existentes.

`git switch`

Para realizar ambos pasos al mismo tiempo(crear rama y moverse a ese rama).

`git switch -c <nombre-rama>`

**git checkout**

El comando nos ayuda a cambiar entre ramas y restablecer cambios hechos en algunos archivos.

`git checkout`

**FUSIONAR RAMAS**

La accion de fusionar ramas nos permite fusionar los cambios 

que realizamos en cada rama, de forma que los cambios que hicimos en una rama 

tambien estaran presentes en otra rama.

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

Para realizar ese trabajo se usa el comando git branch -d nombre-rama.

`git branch -d <nombre_rama>`

pero antes de eliminar una rama es mejor revisar si las ramas fueron 

fusionadas correctamente porque suele pasar que puedes eliminar

horas de trabajo, por suerte git te notificara en ese caso.

>El comando git branch -D elimina la rama directamente

>El comando git branch -d te notificara si eliminar la rama tiene riesgos

## CLASE 3

**GITHUB**

Github es un servicio en la nube especializado en el control de versiones

de git, son completamente diferentes con git.

**Repositorios remotos**

Un repositorio remoto es simplemente una version de tu repositorio que se 

encuentran en internet.

**git clone**

Clona un repositorio remoto y se hace una copia local del repositorio remoto.

`git clone <url del repositorio remoto>`

**git push**

El comando nos permite subir todos los cambios que hicimos al repositorio local

al repositorio remoto asi tener ambos repositorios conectados y actualizados.

`git push <origin><nombredelarama>`

**git branch -a**

El comando nos permite listar todas las ramas remotas que tenemos en un repositorio.

**git push -f**

Este comando forsa la actualizacion de una rama remota evitando todas las 

advertencias. Actualmente no es recomendado por el riesgo que conlleva su uso.

`git push -f`

**git push --all**

El comando actualiza todas las ramas que trabajamos en el repositorio local

al repositorio remoto.

**git push -u**

El comando ayuda a simplificar el trabajo de escribir todo el nombre de la rama ya en el siguiente push 

solo ponemos git push y ya reconocera a que rama nos referimos.

**git push --delete**

El comando git push -delete ayuda a eliminar ramas remotas.

`git push origin --delete main`

**Crear ramas remotas**

Para crear un rama remota es primordial primero crear una rama local luego

con la ayuda del siguiente comando se podra crear la rama remota.

`git push <origin> <nombre_rama>`

>si la rama no existe de manera local existira un error

## CLASE 4

**git pull**

El git pull es un comando que nos permite descargar el contenido de un

repositorio remoto lo cual nos permite extraer todo el contenido 

de ese repositorio remoto y actualizar nuestro repositorio local.

>Un git merge se puede ver como dos comandos juntos un git fetch el cual descargara 

>el contenido de la rama principal y con un git merge las fusionara.

Los comandos con git pull son similares a git push ya que trabajan de manera identica ambos

**git pull --all**

El comando actualiza el repositorio local siendo similar al repositorio remoto.

`git pull --all`

**git pull -f**

Como git push -f el comando forsara todos los cambios para que el repositorio local sea identico al repositorio remoto
al igual que git push el comando no es recomendado por el riesgo que conlleva.

`git pull -f`

**pull request**

El git request es una funcionalidad de github la cual permite revisar los cambios realizados

en alguna rama del repositorio antes de realizar un git merge o fusionar las ramas.

**Consejos antes de realizar un pull request**

 * Lee el archivo contributing.md el cual te dara un pantallazo de como trabajar en el repositorio.
 * Procura que tu aporte sea lo mas parecido al trabajo original.
 * Enfoca tu ayuda en una parte en concreto.
 * Redacta en tu pull request muy especifico de que es los cambios que realizaste.
  
## CLASE 5

**FLujo de trabajo**

Un flujo de trabajo se puede entender como una recomendacion sobre como llevar un proyecto o

dicho de otra forma la manera que se trabajara.

**Formas de flujo de trabajo**

* gitflow.-Gitflow es un flujo de trabajo enfocado principalmente en el desarrollo bien organizado en ramas especializadas.
* github flow.- Se centra en el uso de pull request para un mejor desarrollo y se permite trabajar en cuantas ramas se pueda.
* Trunk Based Development.- Se trata de un flujo de trabajo que trabaja principalmente en la rama main siendo pocas las veces que opta .por crear ramas auxiliares.
* Ship / Show / Ask.- Esta compuesta por tres partes las cuales estan en el nombre:
    * Ship.- Sube los cambios a la rama main sin consultarlo.
    * Show.- Se crea una pull request y se revisa antes de fusionar los cambios con el main.
    * Ask .- Se consulta con el equipo antes de subir toda la informacion al grupo se usa mas con temas mas delicados o que dudamos de nuestras soluciones.
  
## Clase 6

### Buenas practicas de git

**Commits**

Un commit debe ser redactado muy a menudo esto permite tener varios puntos de guardado 

lo que nos ayudara a saber mejor en que punto hubo un error y asi arreglarlo

**Redactar un buen commit**

* Procurar escribir con verbos en imperativo
* No usar punto final ni puntos suspencivos
* Usar menos de 50 caracteres(ser lo mas breves posibles)
* Usa una semantica especial para commits:
  * fix:(tipo del cambio) se arreglo un bug(Descripcion del cambio) 

**Nombres de ramas**

Las ramas al igual que los commits deben ser claros para los que las usen procura usar 

nombres que describan que hace la rama

Para mejor entendimiento usa un nombre que explique que se arregla en la rama:
* feature: Ramas donde se desarrolla una nueva caracteristica 
* hotfix: Rama donde se arreglas errores criticos
* bug: Rama donde se cambia el codigo fuente para arreglar bugs.
Al igual que esas existen algunas mas que ayudaran a un trabajo mas organizado.

## Clase 7

### Deshacer cambios

Deshacer cambios es una parte muy importante de un proyecto en git ya que suele pasar que 

realizamos algunos cambios incorrectos en el repositorio remoto por lo que es necesario 

volver a un punto donde todo funcionaba.

Existen dos formas de deshacer cambios una son las contructivasy otras las constructivas.

**git reset**

El comando git reset tiene dos versiones las cuales son:

**git reset soft:** El comando nos permite regresar a un commit pasado sin deshacer los 

cambios actuales, los cambios posteriores al commit que nos movimos pasaran al estado staged.

 Ya de ahi se elige que cambios se mantienen.

**git reset hard:** El comando git reset hard a diferencia del soft deshace todos los cambios

 hasta el commit que no moveremos. Sin posibilidad de recobrarlos.

`git reset hard/soft <id del commit>`

o

`git reset hard/soft HEAD~<numero de commits que retrosederemos>`

**git revert:** El comando git revert realiza un proceso realizado parecido a un merge lo que

 hara al ejeutarlo es unir el ultimo commit con un commit que elijamos, por esa razon es muy
 
  comun tener conflictos al ejecutarlo.

`git revert <id commit>`

Al aparecer un conflicto con git revert tenemos dos opciones abort y continue.

**git revert abort**

Cancela el revert actual

**git revert continue**

Este comando se debe ejecutar despues de resolver un conflicto para continuar con el revert

**git checkout:** 

Aparte de que permite movernos entre ramas el comando git checkout nos ayudara a deshacer cambios

en gitLa estructura del comando es distinta `git checkout <id del commit>` lo que hara el comando
 
es dirigirnos al estado de los archivos hasta ese commit ya de ahi podemos elegir que cambios 

queriamos que se mantengan como estaban.Despues se debe regresar a la rama donde estaba el commit,

para aplicar los cambios.

## Clase 8

### Hocks, alias y trucos de git

**Hooks**

Un hook es realizar un sript cuando sucede una situacion en git, por ejemplo el post-commit resulta 

siendo un hook

**Alias**

Alias es una manera de simplificar comandos largos, ya que generaremos un "alias"para ese comando en
 
especial asi ya no escribiremos tantos mas al contrario nos ahorraremos un monton de tiempo

**Manera de crear un alias**

La manera de crear un alias es ejecutando un comando en la terminal

`git config --global alias.<alias> <comando que remplazara>`

De esa manera la siguiente ves que ejecutemos el alias realizara su trabajo.

**Trucos de git**

Algunos comandos pueden romar otra forma y facilitarnos las cosas en nuestro trabajo con git por ejemplo:

* Recuperar un archivo de otra rama: `git checkout <SHA><archivo>`
* Cambiar el nombre a un commit existente: `git commit --amend -m <descripcion commit>`
* Guardar cambios temporales: `git stach`
* Aplicar cambios a un commit: `git cherry-pick <SHA>`
--
Fin del curso de git
--