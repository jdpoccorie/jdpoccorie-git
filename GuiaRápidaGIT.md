# Curso de Git
### Introducción
> Es un Sistema de control de versiones para el mantenimiento eficiente y confiable de nuestros trabajos o proyectos... c:

## Parte I
### ¿Qué es?
* Es un sistema de control de versiones 
* Es el mas usado en la actualidad 
* El creador es Linus Torvalds
* Git es gratuito y opensource
* git es usado en trabajos colaborativos
> Un sistema de control de versiones nos permite hacer un seguimiento de los cambios que apliquemos a nuestros proyectos, entonces a medida que vayamos haciendo cambios estas quedaran grabadas en nuestro repositorio. Asi, si cometimos algun error en un cambio podremos regresar al cambio anterior...

### Soluciones

> Normalmente cuando nosotros tenemos un proyecto en desarrollo tenemos varias carpetas que funcionan o almacenan nuestros backup, esto resulta muy confuso a la hora de manejar nombres de carpetas... con Git solucionamos esto.

### Estructura
En git reconocemos tres partes fundamentales que son:

1. Working Directory | Directorio de Trabajo 
   * Contiene todos nuestros archivos de trabajo para añadir a staging area se usa el comando " git add "

2. Staging Area | Area de Preparación
   * Observamos algunos archivos de nuestro trabajo que estan en cambios. 
   * Esta es la seccion de actualizaciones para añadir archivos al repositorio se usa el comando " git commit "

3. Repository | Repositorio
   * Applicando un " commit " tenemos nuestro repositorio actualizado


> ** Git permite la creacion de ramas **
> * Esto ayuda a que algunas ramas esten en evolución, otras en desarrollo otras en finalización.
> * En estos aspectos las ramas ayudan a trabajar modularmente.

## Parte II
### Instalación y Configuración de Git
#### Instalación
1. Para descargar git click [aquí](https://desktop.github.com/)
   * Recomendable: Tener cuenta en Git
2. Indicarle a Git cual sera nuestro nombre de usuario y nuestro email, esto porque los commit de nuestro Git deben de estar asociados a un autor.
   * Los commit son nuestras ediciones(actualizaciones)
   * Para la configuracion usaremos los comandos de la pagina de [Git](https://git-scm.com/book/tr/v2/Customizing-Git-Git-Configuration)
    > $ git config --global user.name "John Doe"
    
    > $ git config --global user.email johndoe@example.com

   * Para poner en el editor e sublime text2 !Recomendable
   >git config --global core.editor "'c:/program files/sublime text 2/sublime_text.exe' -w"
   
   * Para poner en el editor de sublime text 3
   >git config --global core.editor "'c:/program files/sublime text 3/subl.exe' -w"

   * Para Mac y Linux
   >git config --global core.editor "subl -n -w" 

#### Configuración

1. Entramos a la consola Preferida GitShell,** GitBash**, CMD de Windows, etc...
2. Configuramos el nombre de usuario
 > git config --global user.name "JDiegoP"
3. Configuramos el email del Usuario 
 > git config --global user.email "juandiego.poccori@gmail.com"
4. Verificamos si configuramos correctamente
 > git config --global --list
5. Listo!!!

### Creando nuestro primer Repositorio
Un **repositorio** es un lugar de almacenamiento del cual pueden ser recuperados e instalados los paquetes de software en un ordenador.

**En Git nuestros archivos presentas estados:**
> * Untracked (No Rastreados | Sin seguimiento)
> * Unmodified
> * Modified
> * Stanged

UNTRACKED | UNMODIFIED | MODIFIED | STAGED
------------ | ------------- | ------------- | -------------
Por defecto los archivos de nuestra carpeta no estaran marcados o rastreados por asi decirlo. | Una vez pasados por Untracked estos archivos estaran como no modificados, al estar asi nosotros no podremos enviarlos al staged area. | Nuestros archivos al ser editados pasan a modified. | Haciendo un stage the file pasan a staged area.

1. Al estar en el **staged area**.
   1. Hacemos un commit y estos archivos se registraran pasando al repositorio a estar como archivos unmodified(no modificados) de una nueva version 
   2. Finalmente si nosotros queremos dejar de ver algunos archivos podemos eliminarlos de nuestro repositorio y pasar nuevamente a estar no marcados untracked...
2. Tambien veremos un comando **status** que nos permitira saber el estado de nuestros archivos.

## Parte III
### Primer Ejemplo práctico >> Volver a una versión anterior
Para este primer ejemplo nos pondremos el caso de desarrollar un sitio web, los cambios que registraremos con commit son los siguientes...

1. Definir la estructura HTML de del sitio web
2. Añadir Información 
3. Añadir un poco de CSS

Para ello usaremos los comandos:
> * git init (Para crear e iniciar nuesto Repositorio)
> * git add
> * git commit
> * git status


**Pasos:**

1. Creamos nuestra carpeta en el disco local C:/ llamada Proyecto
2. Para iniciar nuestro repositorio entramos en el GitBash y nos ubicamos en la carpeta de nuestro proyecto usando comandos cd
3. Una vez estando en la carpeta escribir "git init" para crear un repositorio.
   * Nos aparecera algo asi :v Eso significara que se ha inicializado un repositorio...
   * C:\proyectoGit [master +1 ~0 -0 !]>
> **Nota:** Cuando iniciamos git se creara una carpeta invisible .git que contendra toda la info del proyecto; commit usados, etc.
   
4. Usamos "git status"
> git status

   * Nos avisara que estamos en la rama master
   * y que tenemos nuestro archivo index en estado untracked osea no marcado
5. Usaremos el "git add index.html" para llevarlo a unmodified
> git add index.html

6. Verificamos con git-status nuevamente
   * Nos aparecera changes to be committed
7. Para crear nuestro primer commit se escribe el siguiente codigo en el shell que aparte debe de ir aconpañado con una pequeña descripción o mensaje
> "git commit -m "Proyecto con los archivos base"

   * Nos aparecera >>> [master (root-commit) b3f3a7a] Proyectos con los archivos base
   * 1 file changed, 1 insertion(+)
   * create mode 100644 index.html
   * que significa que el commit se realizo correctamente
8. Listo registramos nuestro primer commit
> **Comandos que Usamos:**
> git add -A añadir a staged area todos los archivos de la carpeta
> git commit -m
> git log
> git checkout 
> * Nos permite volver a una version anterior para visualizar como era antes
> * Se le indicara a que version regresar...
> * Para saber que version escribir se escribira **"git log"**
> * Entonces para que nosotros veamos con el checkout copiamos el commit que sera parecido a este:b3f3a7a8ddefbd8048ba4360b328c6de1cf4d502
> * y escribir:
> * git checkout b3f3a7a8ddefbd8048ba4360b328c6de1cf4d502
> * y ya estaremos en la version anterior de nuestro index.html

9. Si editamos nuestro archivo index de la carpeta y volvemos a escribir git status nos aparecera un mensaje de que el archivo index fue modificado entonces lo que tenemos que hacer es nuevamente añadir con git add... etc pero en este caso usaremos:
> git add -A que significa afectar a todos los archivos modificados pasen al staged area.

10. Ahora podremos hacer nuevamente un commit acampañado de un mensaje
11. Verificar codigo git checkout de arriba
12. Si queremos ver la version actual ponemos igual el checkout con el commit actual o sino escribir:
> git checkout master

13. para usar el git log es recomendable usar un archivo de texto como en el ejemplo
> git log > commits-txt

14. Nos vamos a nuestra carpeta y veremos que se creo un archivo commits.txt
15. Por ultimo modificamos nuestro index.html y le enlazamos un archivo css y en el shell escribimos nuevamente "git status" y nos aparecera que se modificaron archivos en nuestra carpeta.
16. Entonces analizamos de que el archivo que creamos commits.txt no pertenece a nuestro proyecto pero estilos.css si, entonces podemos añadir dos veces git add o simplemente poner git add -A para agregar ambos a staged area.
17. Entonces escribimos nuevamente git status vemos que ya aparece ya estan en ahi porque estan en verde y ya podriamos hacerle un commit.
18. Veremos que nos aparece el commits.txt pero nosotros no queriamos a ese entonces que podriamos hacer... Continuará... :V

## Parte IV
### Remover archivos del staging area
1. El comando para eliminar del staging area es... pero antes para ver la lista de comandos usaremos el 
> git help

2. Vemos el rm que es para remover archivos.
3. Como queremos saber mas de este archivo escribimos git help rm.. y al presionar enter se nos cargara en nuestro navegador una ayuda o info de este commando
  * Leemos que los archivos seran removidos del staging area o del directorio de trabajo pero que es imposible eliminar el archivo ya que no tiene sentido y que tenemos dos opciones
  > git help rm
    ```
    -f : La eliminacion del archivo sera del staging area de la carpeta de trabajo osea desaparecera(borrado y eliminado) el archivo
    --cached : Solo eliminamos del staging area pero el archivo seguira apareciendo en la carpeta de trabajo
    Entonces la que necesitamos es --cached
    ```
    
4. Escribimos git rm --cached commits.txt
> git rm --cached commits.txt

5. Ahora si ponemos nuevamente git status nos apareceran de que commits.txt es untracked.
6. Pero si una vez mas quisieramos usar el git add -A veremos que nuevamente aparece el commits.txt en el stageg area entonces lo que queremos es que se ignore ese archivo.. lo que tenemos que usar es...  el ignore
25. para usar esto usaremos gitignore... entonces lo que hacemos es ir a nnuestra carpeta de trabajo y para testear creamos un archivo de texto y le ponemos .gitignore pero no funcionara al menos en windows lo que tenemos que hacer es .gitignore. con eso si funcionara.
26. Entramos a ese documento y en ahi escribimos commits.txt
27. Entonces nuevamente ejecutamos el git status y ya no nos aparecera el commits.txt sino el .gitignore que estara bien!!!

## Parte V
### Como agregar y eliminar commits
> git reset: Lo que hace es borrar un commit que ya se realizó
> Lo usamos en casos muy graves

> **Podemos aplicarlo en tres modalidades...**
> * --soft
> * --mixed
> * --hard

Caso 1

> Si por ejemplo nosotros tenemos los commits

> a b c d
> * Sea cual sea el metodo de modalidad que apliquemos el que se eliminara sera siempre d.
> * Si usamos el soft no tocamos el index ni el work tree simplemente eliminamos el commit
> * Si usamos **mixed** nosotros reseteamos el index pero no modificamos el work tree
> * Si usamos **hard** nosotros eliminamos el commit y reseteamos index y work tree
> * Si usamos dos veces al mismo archivo con el hard se volvera a tener nuevamente ese repositrio

> **Repaso**
> * git add
> * git add -A : pasar todos los archivos de la carpeta del trabajo
> * git commit -m "" : luego de tener en el stanged area usamos el commit seguido de una descripcion o mensaje  descripcion del commit. Finalmente se guardara en el repositorio
> * git checkkout : con este comando nosotros podremos ver una version anterior de nuestro proyecto
> * git rm : para remover del index y ponerlos en work tree

### Tener en cuenta los 3 estados
* Work Tree : Nuestra carpeta de Trabajo.. por medio de add
* Staged Area ó index : Area de estancia por medio de commit
* Repository: Constituye una nueva version de nuestro proyecto

## Parte VI
### Ramas y Fusiones
Anteriormente manejamos una rama que vendria a ser master sobre esta nosotros creamos **commit** eso esta bien si trabajamos **de manera particular** sin que otros compañeros trabajen con nosotros. Aprendimos a usar el **git commit** y el **git reset** aprendimos las 3 partes de Git que son el **work tree** carpeta de trabajo... el **index o staged area** y el **repository** o repositorio.

> Notas:
> * El git reset no es recomendable porque implica eliminar commits y por lo general se ve que los commit avanzan hacia adelante entonces para evitar eso es recomendable generar una rama independiente a la master para que sobre esa rama se trabaje esa particularidad y que cuando esta se haya implementado se fusione a la rama master entonces si hay error solo se elimina de la rama independiente y no afecta a la master


** COMANDOS **
> git branch : Se usa para listar las ramas existentes en nuestro proyecto

> git branch nombre : Se usa para crear una nueva rama con el nombre que le indiquemos

> git branch -d nombre : Se usa para eliminar ramas

> git merge : Nos permite fusionar ramas 

> git checkout: Tambien se usa para visualizar ramas distintas

**Pasos**

1. Usamos git branch y como observamos solo tenemos la master...
2. Creamos una nueva rama...
3. git branch veremos la nueva rama creada.
4. Usando el git checkout podremos elegir en que rama estaremos...
5. git checkout ejemplo
6. git branch -> Veremos que nos ubicamos en "ejemplo" ya no es master
7. agregamos un commit en ejemplo
8. Entramos nuevamente en la rama master y en el shell escribimos git log
9. Veremos que no nos aparece el commit agregado en ejemplo entonces nos queda fusionar las ramas..
10. Entonces estando ubicados en master escribimos "git merge ejemplo" y acabamos de hacer nuestra primera fusion Nos aparecera fast forward osea que no hubieron conflictos...
11. si ponemos git log veremos que en verdad se fusiono con la rama ejemplo.
12. Si ponemos nuevamente git branch veremos que se encuentra sigue la otra rama asi es que si queremos podemos eliminar la rama ejemplo ya que por lo general en git las ramas que ya fueron fusionadas se eliminan entonces usamos... 
13. git branch -d ejemplo 
14. ponemos git branch y listo estaran eliminados...

**Veremos un ejemplo con Conflicto**

1. creamos una nueva rama y nos ubicamos en ella
2. editamos el html
3. creamos el commit en la nueva rama
4. antes de hacer el commit entramos nuevamente en el master para hacer un conflicto.
5. Una vez estando en el master creamos un nuevo commit para ver que se hace en caso de conflicto...
6. Listo!! ;)

## Parte VII
### Tutorial de Git Repositorios Remotos

Tendremos que crearnos un repositorio en github
Despues tendremos que copiar la direccion https en el mio salio [GitHub jspoccorie](https://github.com/jdpoccorie/git.git)

1. Nos ubicamos en la carpeta donde estan los qrchivos que vamos a subir desde el shell de github..
2. inicializamos el git en esa carpeta
3. testeamos poniendo git status
4. Nos aparecera todos nuestros archivos en la carpeta
5. Creamos el commit con todos ellos
6. A vecer aparecera un warning que nos dira que el fin de linea de varios archivos van a ser remplazados por CRLF en vez de LF unicamente este warning mayormmente este error aparece en windows  pero se ignora nomas...
7. usamos el commit git commit -m "Pruebita remota"
8. Entonces ponemos git log y veremos nuestro commit
9. Estos cambios solo se realizaron localmente por lo que para subir a github usaremos el git remote -v que nos dira a los repositorios remotos a los que estamos conectados ademas nos aparecera las url's
10. para añadir un repositorio remoto usamos
	git remote add ejemplito https://maslaurl.com
11. verificamos si se crearon nuestros repositorios con git remote o con fit remote -v
12. Veremos que nos aparece fetch y push que son los valores con los que podremos trabajar...
13. El comando **fetch** nos va a permitir descargar cambios que sucedieron en el repositorio remoto para que veamos si hay cambios que no los tenemos sincronizados y el **push** nos va a permitir subir los archivos una vez que estemos perfectamente sincronizados... Entonces cada vez de que alguien quiera subir un archivo tendra que hacer primero un fetch para que este realmente sincronizado con los cambios anteriores y luego trecien podra subir sus cambios con push
    
14. Para subir los archivos tendremos que escribir en el shell:
> git push ejemplito master

15. Nos pedira nuestro usuario y contraseña del github y procedera a subir los archivos...
16. Luego actualizamos nuestro repositorio de github
17. Listo!!!


### Para cambiar el nombre de un commit
1. git commit --amend
2. Se nos abrira un archivo en el editor en el cual nos aparecera el nombre del ultimo commit c:
3. Editamos el nombre del commit
4. Listo!!!

### Renombrar Archivos
commando para renombrar archivos

* git mv
* git mv file_from file_to

1. ponemos en el shell git mv index.html pagina.html
2. entramos en git status
3. hacemos commit al al renamed c:
4. Listo se cambio los archivos...

### Regresar en el tiempo
* git log --decorate --graph --all
* git log --decorate --graph --all --oneline
* Los anteriores comandos nos ayudan a ver la relacion de los commit

1. Ponemos cualquiera de los anteriores para ver la lista de los commits
2. escribir en el shell git checkout 2365ee5
3. Nos damos cuenta de que nuestros archivos se actualizaron con los de esa vez en que creamos el commit, asi nosotros podemmos movernos a cualquier punto... Excelente!!
4. Volvemos a master que en si nos regresara al HEAD c:


### Trabajar con Etiquetas
¿Como crear etiquetas en git? Buscar!

> Notas:
> * No es necesario estar en master para crear ramas y no es asi!!! ;v
> * Para moverse entre ramas se usa el 
> * git log --decorate --oneline --all --graph para ver en una linea los commmit
> * git log --decorate --all --graph Commits en nuestras ramas

### Curso Git desde cero
Sistema de control de versiones para el mantenimmiento eficiente y confiable de archivos

### Zonas de git
1. Directorio de trabajo
2. Area de preparacion
3. Directorio Git

### Flujo de trabajo basico de git
1. Modificas una serie de archivos en tu directorio de trabajo
2. Preparas los archivos, añadiendolos a tu area de preparacion.
3. Confirmas los cambios, los que toma los archivos tal y como estan en el area de preparacion y almacena esa copia instantanea de manera permanente en tu directorio git.

### Configurando git por primera vez
git config --global user.name "Juan Diego"
git config --global user.email "juandiego.poccori@gmail.com"
git config --global core.editor ...
git config --list

### git branch
Una rama en git es simplemente un apuntador movil apuntando a una de los commits
Puedo crear todas las ramas que quiera y/o necesite.
Las ramas nuevas se crean apuntando al commits actual donde esta ubicado el HEAD.

### git commit --amend
Este comando utiliza el area de preparacion para la confirmacion.
Al final terminaras con una sola confirmación - la segunda confirmacion reemplaza el resultado de la primera.

Si no hemos hecho cambios desde la ultima confirmacion entonces la instantanea (commit) lucira exactamente igual y lo unico que cambiaremos sera el mensaje del commit

### git commit -a -m "mensaje del commit" || git commit -am "mensaje del commit"
Con este commando podemos saltar el area de preparacion osea que ya no ponemos el git add -A c:

### Fusionar ramas
### git branch
Una rama en Git es simplemente un apuntador movil apuntando a una de los commits

### git branch --no-merged
Nos muestra cuales ramas no han sido fusionadas a la rama actual

### git branch --merged
Nos muestra las ramas que han sido fusionadas a la rama actual

Un conflicto nos dice que dos ramas modificaron la misma linea 


