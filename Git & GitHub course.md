Terminal & shortcuts:
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

Crear un repositorio de Git y primer commit:
git init(dentro del directorio del proyecto) -> Inicializa git en el proyecto
git add nombreDelArchivo.txt -> Agrega archivos
git add . -> Agrega todos los archivos
git rm --cached nombreDelArchivo.txt -> Borra el archivo

