# TUTO_GIT
MI PRIMER PROYECTO GIT CREADO


Configuración Básica
Configurar Nombre que salen en los commits

	git config --global user.name "dasdo"
Configurar Email

	git config --global user.email dasdo1@gmail.com
Marco de colores para los comando

	git config --global color.ui true
Iniciando repositorio
Iniciamos GIT en la carpeta donde esta el proyecto

	git init
Clonamos el repositorio de github o bitbucket

	git clone <url>
Añadimos todos los archivos para el commit

	git add .
Hacemos el primer commit

	git commit -m "Texto que identifique por que se hizo el commit"
subimos al repositorio

	git push origin master
GIT CLONE
Clonamos el repositorio de github o bitbucket

	git clone <url>
Clonamos el repositorio de github o bitbucket ?????

	git clone <url> git-demo
GIT ADD
Añadimos todos los archivos para el commit

	git add .
Añadimos el archivo para el commit

	git add <archivo>
Añadimos todos los archivos para el commit omitiendo los nuevos

	git add --all 
Añadimos todos los archivos con la extensión especificada

	git add *.txt
Añadimos todos los archivos dentro de un directorio y de una extensión especifica

	git add docs/*.txt
Añadimos todos los archivos dentro de un directorios

	git add docs/
GIT COMMIT
Cargar en el HEAD los cambios realizados

	git commit -m "Texto que identifique por que se hizo el commit"
Agregar y Cargar en el HEAD los cambios realizados

	git commit -a -m "Texto que identifique por que se hizo el commit"
De haber conflictos los muestra

	git commit -a 
Agregar al ultimo commit, este no se muestra como un nuevo commit en los logs. Se puede especificar un nuevo mensaje

	git commit --amend -m "Texto que identifique por que se hizo el commit"
GIT PUSH
Subimos al repositorio

	git push <origien> <branch>
Subimos un tag

	git push --tags
GIT LOG
Muestra los logs de los commits

	git log
Muestras los cambios en los commits

	git log --oneline --stat
Muestra graficos de los commits

	git log --oneline --graph
GIT DIFF
Muestra los cambios realizados a un archivo

	git diff
	git diff --staged
GIT HEAD
Saca un archivo del commit

	git reset HEAD <archivo>
Devuelve el ultimo commit que se hizo y pone los cambios en staging

	git reset --soft HEAD^
Devuelve el ultimo commit y todos los cambios

	git reset --hard HEAD^
Devuelve los 2 ultimo commit y todos los cambios

	git reset --hard HEAD^^
Rollback merge/commit

	git log
	git reset --hard <commit_sha>
GIT REMOTE
Agregar repositorio remoto

	git remote add origin <url>
Cambiar de remote

	git remote set-url origin <url>
Remover repositorio

	git remote rm <name/origin>
Muestra lista repositorios

	git remote -v
Muestra los branches remotos

	git remote show origin
Limpiar todos los branches eliminados

	git remote prune origin 
GIT BRANCH
Crea un branch

	git branch <nameBranch>
Lista los branches

	git branch
Comando -d elimina el branch y lo une al master

	git branch -d <nameBranch>
Elimina sin preguntar

	git branch -D <nameBranch>
GIT TAG
Muestra una lista de todos los tags

	git tag
Crea un nuevo tags

	git tag -a <verison> - m "esta es la versión x"
GIT REBASE
Los rebase se usan cuando trabajamos con branches esto hace que los branches se pongan al día con el master sin afectar al mismo

Une el branch actual con el mastar, esto no se puede ver como un merge

	git rebase
Cuando se produce un conflicto no das las siguientes opciones:

cuando resolvemos los conflictos --continue continua la secuencia del rebase donde se pauso

	git rebase --continue 
Omite el conflicto y sigue su camino

	git rebase --skip
Devuelve todo al principio del rebase

	git reabse --abort
Para hacer un rebase a un branch en especifico

	git rebase <nameBranch>
OTROS COMANDOS
Lista un estado actual del repositorio con lista de archivos modificados o agregados

	git status
Quita del HEAD un archivo y le pone el estado de no trabajado

	git checkout -- <file>
Crea un branch en base a uno online

	git checkout -b newlocalbranchname origin/branch-name
Busca los cambios nuevos y actualiza el repositorio

	git pull origin <nameBranch>
Cambiar de branch

	git checkout <nameBranch/tagname>
Une el branch actual con el especificado

	git merge <nameBranch>
Verifica cambios en el repositorio online con el local

	git fetch
Borrar un archivo del repositorio

	git rm <archivo> 
Fork
Descargar remote de un fork

	git remote add upstream <url>
Merge con master de un fork

	git fetch upstream
	git merge upstream/master
  
  
  …or create a new repository on the command line
echo "# Curso-styde" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/gjcarrillo/Curso-styde.git
git push -u origin master


…or push an existing repository from the command line
git remote add origin https://github.com/gjcarrillo/Curso-styde.git
git push -u origin master

  
  
  
  
  ##Lista de comandos útiles para Git

###Para clonar el repositorio de GitHub (sólo una vez):

git clone https://github.com/susannalles/MinimalEditions.git
###Para subir nuevos materiales a GitHub:

git init: inicia git al interno de la carpeta
git add nombre_archivo.txt: añade el documento (o carpeta) en el area de espera ("stage")
git commit -m "mi primer mensaje de cambios": describe los cambios realizados
git remote add origin https://github.com/susannalles/MinimalEditions.git: apunta a la dirección donde deseáis subir el nuevo material
git push -u origin master": subís los cambios al repositorio remote en GitHub por primera vez
###Push & Pull

git add *: añade el documento (o carpeta) en el area de espera ("stage")
git commit -m "mensaje con los detalles del cambio": describe los cambios realizados
git push origin master: subís los cambios a GitHub *git push origin [branch]: subís los cambios al repositorio remote en GitHub. Asegurar de escribir el nombre del branch que quieres subir sus cambios y nunca subes al master sin que todos revisamos sus cambios.
###Sincronizar nuestra copia con el original:

git pull: baja los cambios del repositorio remoteo a nuestra copia en local
###La Brújula: git status: señala lo que se ha modificado en la carpeta de trabajo

###Branches

git branch: Para ver en que branch estas trabajando.
git branch [name]: Para crear un branch nuevo. Asegurar de usar git checkout para camibar al branch.
git checkout [branch]: Para cambiar de un branch a otro. Así por ejemplo, si estamos en "master" y queremos cambiarnos a un branch llamado "classwork", haremos 'git checkout classwork'.
git branch -d [name]: Para quitar un branch. Es posible que git te da un error. Git no te permite quitar un branch que tiene commits no escritos al origin con esta orden. Si estas completamente seguro de que quieres quitar el branch, puedes usar la orden git branch -D [name].
git checkout -b nombre_branch: para bajar el contenido de un branch
git pull origin nombre_branch: para actualizar el contenido de un branch (y empezar a trabajar en ese branch).
git checkout -b nombre_branch: para descargar el contenido de un branch
git checkout -- file.html: para ignorar los cambios hechos en local (cuando queremos hacer un push)







Guía de comandos de Git
How to update github forked repository?

Trabajos con ramas
####Crear una rama git branch <nombre rama>

####Cambiar de rama git checkout <nombre rama>

####Eliminar una rama git branch -d <nombre rama>

####Crear una rama y directamente hacer checkout en ella git checkout -b <nombre rama>

####Merge especial git merge --no-ff myfeature

####Renombrar una rama

git branch -m <vieja rama> <nueva rama>

####Crear tag

git tag -a 1.2.1

###Acciones con archivos

####Deshacer cambios locales (reset) Con este comando descartamos los cambios locales y volvemos al estado que teníamos guardado en el respositorio

git reset --hard

####Deshacer cambios locales (checkout) Deshace los cabios realizados en el archivo indicado evitando utilizar git reset --hard

git checkout nombreDeArchivo

Si quieres desahacer los cambios realizados en todos los archivos puedes utilizar

git checkout -- .

####Elimina el último commit

git reset --hard HEAD~1

####La recuperación hace un nuevo commit en la rama actual sin ir "hacia atrás" en la historia

git revert <COMMIT>

####Add y commit de todos los archivos a la vez

git commit -a -m 'Este es mi mensaje'

####Cuando queremos quitar un archivo que ya esta añadido. Comando opuesto a git add

git reset nombre_del_archivo

####Deshaciendo el merge

git reset --merge (git version 1.6.1) git merge --abort (git version 1.7.4)

####Ignorar temporalmente un archivo

git update-index --assume-unchanged <archivo>

Volver a trackearlo:

git update-index --no-assume-unchanged <archivo>

Listado de archivos temporalmente ignorados:

git ls-files -v | grep ^[a-z]

####Ignorar un archivo local modificado y no añadido para actualizarse

Primero se añade con git add nombre_del_archivo a continuación se borra del stage git reset --hard HEAD y por último se git pull para actualizarse.
