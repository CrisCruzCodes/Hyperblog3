Terminal & shortcuts:
Si el nombre de una carpeta esmpieza con . significa que es una carpeta oculta
pwd -> Te indica en que carpeta te encuentras
En linux no existe C:. En linux el root donde arranca el sistema de archivos es /
cd -> Permite dirigirse a una carpeta (change directory). Si se teclea solo te lleva al home user ~
/ -> Raíz del disco
 ~ -> Hogar del usuario
 ls -> Muestra los archivos del directorio
 ls -al -> Muestra todos los archivos del directorio incluyendo los ocultos en una lista
 ls -l -> Muestra los archivos pero no los ocultos en una lista
 ls -a -> Mueestra los archivos del directorio incluyendo ocultos sin lista
 clear y command+k-> Limpian pantalla
 cd .. -> Regresa al directorio anterior
cd + primera letra de la carpeta a la que quiero navegar + tab -> Indica las carpetas que inician con la letra indicada
command + up or down -> Te lleva al inicio o final del texto
control + down -> Navega entre distintas ventanas de la misma aplicación
option + tab -> Navega entre distintas ventanas de la misma aplicación
control + tab -> Navega entre las distintas pestañas de vs code (como en opera)
mkdir nombreDeCarpeta-> Crea carpetas (Se pueden crear distintas carpetas separando los nombres por espacios)
touch nombreDelArchivo.txt-> Crea documentos
. -> Carpeta actual
.. -> carpeta anterior
cat nombreDelArchivo.txt -> Muestra el contenido del archivo
history -> Muestra historia de comandos escritos
rm nombreDelArchivo.txt -> Borra el archivo
ctrl + w -> Borra una palabra de la línea actual
ctrl + U -> Borra toda la línea
F11 -> Muestra el escritorio
command + shift + . -> Muestran archivos ocultos en finder
code . -> Abre vsCode desde la terminal
code -> Abre el archivo en code
code nombreDelArchivo.txt -> Abre el archivo en code

Crear un repositorio de Git y primer commit:
git init(dentro del directorio del proyecto) -> Inicializa git en el proyecto
git add nombreDelArchivo.txt -> Agrega archivos
git add . -> Agrega todos los archivos
git rm --cached nombreDelArchivo.txt -> Borra el archivo
git coonfig -> Muestra opciones de configuración de git
git config --list -> Muestra la configuración actual de git
- -> Un guión + la apreviación de la palabra (-g) 
-- -> Dos guioones + la palabra completa (--global)
git config --global -> Cambia configuración de git de manera global
git config --local y git config -> Cambia la configuración de git de manera local (Solo para el repo en el que se está trabajando)
git config --global user.name "Nombre" -> Cambia nombre

Analizar cambios en los archivos del proyecto:
git log nombreDelArchivo.txt -> Muestra los commits del archivo
git log -> Muestra los commits del repo
git show nombreDelArchivo.txt -> Muestra los cambios del archivo
git  commit -> Crea el commit sin mensaje y abre vim para guardar el mensaje. Se ingresa el mensaje sin comillas y se presiona esc + shift + zz -> para guardar y salir
git diff commitabcxyz1 commitabcxyz2 -> Indica la diferencia entre los 2 commits indicados

¿Qué es el staging y los repositorios? Ciclo de trabajo en git:
1.Directorio 2.Staging 3.Repo local
git init -> Se crea un área en memoria ram llamada staging, se crea el repositirio (.git)
git add -> Manda el archivo a staging (tracked). Antes de git add (untracked)
git commit -> Manda el archivo al repositorio

Volver en el tiempo en nuestro repositorio utilizando reset y checkout
git reset commitabcxyz -> Vuelve al commit anterior indicado
git reset --hard -> Vuelve todo al commit anterior
git reset --soft -> Vuelve al commit anterior en el directorio, pero sigue en staging
git log --stat -> Muestra los cambios específicos que se hicieron en los archivos a partir del commit
git checkout -> Te lleva a la ramma o al commit indicado
git checkout commitabcxyz nombreDelArchivo.txt -> Lleva a la versión del commit indicado de ese archivo
git checkout master -> Lleva de vuelta a la última versión de ese archivo

Git reset vs. Git rm:
git rm --cached: Elimina los archivos del área de Staging y del próximo commit pero los mantiene en nuestro disco duro.
git rm --force: Elimina los archivos de Git y del disco duro. Git siempre guarda todo, por lo que podemos acceder al registro de la existencia de los archivos, de modo que podremos recuperarlos si es necesario (pero debemos usar comandos más avanzados).
git reset --soft: Borramos todo el historial y los registros de Git pero guardamos los cambios que tengamos en Staging, así podemos aplicar las últimas actualizaciones a un nuevo commit.
git reset --hard: Borra todo. Todo todito, absolutamente todo. Toda la información de los commits y del área de staging se borra del historial.

Flujo de trabajo básico con un repositorio remoto:
git clone -> Clona el archivo de master al directorio local y crea la base de datos de todos los cambios historicos en el repositorio local
git push -> Se envían los cambios del repo local al repo remoto
git fetch -> Trae la última versión del rep remoto al repo local, pero no lo cambia en el directorio
git pull -> Crea un fetch y hace un merge con el directorio

Introducción a las ramas o branches de Git:
git checkout nombreDeRama -> Lleva al head de la rama (Su último commit)

Fusión de ramas con Git merge:
(master)git merge -> Une 2 ramas. Si estando en cabecera hago merge con master manda la rama master a cabecera. Une los últimos commits de  cada rama

Resolución de conflictos al hacer un merge:
git merge master -> Fusiona la rama en la que se esta con master

Uso de GitHub
git remote add origin https://github.com/CrisCruzCodes2/Hyperblog2.git (Liga https para clonar) -> Agrega un origen remoto de nuestros archivos
git remote -> Administra el conjunto de repositorios ("remotos") cuyas ramas rastrea.
git remote -v -> Muestra la url remota 
git push origin master(main) -> Envía al origen la rama master (https://github.com/CrisCruzCodes2/Hyperblog2.git)
git merge origin/main -> Hace un merge con la rama indicada en  el repositorio remoto (Es lo que hace git pull después del git fetch)

Tags y versiones en Git y Github
git log --all -> Muestra toda la historia del repo
git log --all --graph -> Muestra una versión gráfica de la historia del repo
git log --all --graph --decorate  --oneline ->  Muestra una versión gráfica comprimida  de la historia del repo
Como crear un alias:
alias tree="git log --all --graph --decorate --oneline"
Alias con git: $ git config --global alias.last 'log -1 HEAD' -> git last (Muestra el último commit)
git tag -a v0.1 -m "Nombre del tag" -> Crea una versión del repo por medio de un tag
git tag -d (nombre del tag)  -> Borra  el tag  en local
git push origin :refs/tags/(nombre del tag) ->  Borra el tag en remoto

Manejo de ramas en github
git show-branch -> Muestra cuales son las ramas que existen y su historia
git show-branch --all -> Muestra cuales son las ramas que existen y su historia pero con mas detalles
