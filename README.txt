1) GIT es uno de los sistemas de control de versiones mas usados actualmente
gracias a que es muy sencillo e intuitivo de usar (aun asi hace falta practica)
podremos trabajar de forma paralela en versiones que aun no sabemos si se uniran al 
proyecto principal.
Un Sistema de Control de Versiones es una herramienta para almacenar versiones.
Basicaamente estas se pueden usar para trabajar en paralelo, que nos permitiria depurar
errores mas facilmente.

2) Instale una version para windows de gitBash espero no tener inconvenientes al
utilizar esta aplicacion y tener que trabajas sobre unn repositorio en gitHub.

3) Inicie el proyecto siguiendo los pasos del tutorial, cree una carpeta llamada 
Proyectos, dentro de ella una llamada PaginaCliente y en ella aplique el comando init
lo cual significa que inicie mi repositorio local.

4) Al seguir los mismos pasos aprendi mas subcomandos como add, restore y commit.
Los cuales me ayudan a modificar mi archivo antes de actualizar mi repositorio local.
Tambien vimos como dar un paso hacia atras en una situacion de comentar erroneamente 
un commit, esto es con el parametro --amend.

5) Pudimos actualizar la pagina con el uso de una plantilla. La cual nos ayudo
muchisimo, reduciendo el tiempo invertido de codigo, aportando buena estetica y
experiencias adquiridas, espero a ustedes tambien les sirva. Aprendimos tambien a
corregir errores o aplicar cambios regresando los archivos puestos en el Stage
o inclusive commits hechos, esto gracias a los subcomandos retore, reset y revert
reset es un subcomando destructivo ya que es capaz de eliminar los commits
que le indiquemos, sin poder recuperar los archivos conntenidos luego, revert en
cambio nos permite regresar los archivos de nuestro commit al Stage aplicarles
las modificaciones que nos parecen necesartias y luego proceder a aplicar commit
sobre el archivo modificado.

6) Usamos ramas para poder trabajar en paralelo, es decir desde un punto del proyecto
principal (raiz), desarrollar un proyecto paralelo (rama) sin afectar al primero. Esto
nos permite, por ejemplo, que a partir de un commit que este fallando podamos desarrollar
la solucion y luego integrar esa solucion al proyecto, otros ejemplos podrian ser hacer
un cambio que nos hayan informado, realizar mejoras, etc . El subcomando 'branch' nos permitira
ver la lista de ramas, crear ramas nuevas, examinar las que hay, borrar ramas y
renombrarlas. Las ramas tienen repositorios incdividuales y de forma paralela, los
archivos que no esten preparados para el commit no se almacenan durante el desarrollo
de esta ramaa. Tambien note que si modifico mis archivos sin usar la consola, no habria
problemas, ya que git lo tomaria como un cambio que se le hizo al archivo almacenado en
el espacio de trabajo , comento esto porque cuadno quiero trabajar con ramas en mi
caso quise cambiarle de logo a mi pagina, entonces probe mover una imagen desde el 
espacio de trabajo hacia la carpeta style, para ello inserte el comando :

git mv logo.jpg style/logo.jpg

y por mas que intentaba variar el nombre o intercambiarlos siempre tenia la siguiente salida:

fatal : 

7) Uso de merge y conflictos: es necesario el uso de merge ya que si se ramifica
nuestro proyecto, podriamos desear volverlos a alojar dentro de la rama principal
para esto es que usamos merge. En nuestro caso hemos creado 2 ramas llamadas auxiliar
y auxiliar2, en una actualizamos los archivos README.txt e index.html, en la otra modifique
tambien el README.txt pero de otra manera, asi cuando vayamos a mezclar o fusionar
las ramas podamos ver si surgen conflictos y ver tambien como solucionarlo. Existen 3
formas de mezclar: La primera llamada fast-foward la cual surge a partir de 2 ramas
que no tienen archivos comunes editados. La segunda, estrategia recfursiva, surge cuando
debemos mezclar los cambios efectuados, sabiendo que los mismos no son con respecto a un
mismo archivo sobre la misma linea, este metodo agreaga y quita en uno lo que se agrego y
se quito en el otro, todo esto se guarda en un nuevo commit. La 3era manera, mezcla con
conflicto, nos intentara fusionar por medio del 2do metodo nuestras ramas, pero encontrara
un mismo archivo modificado sobre una misma linea y nos permitira editar ese archivo para
asi poder resolver dicho conflicto. Hare un merge sin conflicto y otro con uno. primero 
mezclo master con auxiliar y vemos que no genera conflicto, luego master con auxiliar 2 y 
vemos que nos genera un conflicto en el archivo README.txt 

salida al primer merge: 
	cristian@PCArGNtO MINGW32 ~/Proyectos/PaginaCliente (master)
	$ git merge auxiliar
	Updating 347ccaa..1e2f898
	Fast-forward
 	README.txt | 50 +++++++++++++++++++++++++++++++++++++++++++++++++-
 	index.html | 22 +++++++++++-----------
 	2 files changed, 60 insertions(+), 12 deletions(-)

salida del segundo merge:
	cristian@PCArGNtO MINGW32 ~/Proyectos/PaginaCliente (master)
	$ git merge auxiliar2
	Auto-merging README.txt
	CONFLICT (content): Merge conflict in README.txt
	Automatic merge failed; fix conflicts and then commit the result.

Haremos otras 2 ramas y las fusiones correspondientes siguiendo asi el tutorial y adquiriendo
experiencia sobre el tema.





GLOSARIO de subcomandos del comando git:



init: Sirve para poder iniciar un repositorio local vacio.
	parametros:

rm : Nos ayuda en la eliminacion de archivos
	parametros : 
		<nombre/s de archivo/s> : elimina el/los archivo/s nombrado/s

mv : Mueve y renombra archivos
	parametros :
		<nombre viejo>...<nombre nuevo>	: cambia el nombre del archivo
		<nombre viejo>...<lugar nuevo/nombre nuevo> : mueve el archivo
add: Agrega archivos desde nuestro escenario de trabajo al stage preparandolos asi para
ser enviados al repositorio actual.
	parametros: 
		. : Agrega todos los archivos.
		<nombre del archivo> : Agrega solo el archivo nombrado.

restore: Restaura el estado de un archivo.
	parametros: 
		<nombre del archivo> : elimina el archivo nombrado.
		--staged <nombre del archivo> : Elimina del Stage el archivo nombrado
						pero lo aloja en el espacio de trabajo.

commit : Nos sirve para actualizar nuestro repositor local, con los datos alojados en
el Stage por defecto sube todos los archivos.
	parametros:
		--amend : da un paso atras y nos permite editar la etiqueta del commit.

log : Nos permite visualizar todos los commits que se hicieron, quienes lo hicien¡ron 
cuando lo hicieron, que cambios aportaron y demas detalles.
	parametros:
		<> : enlista con detalles todos los commits que se realizaron hasta el 
			momento de parte de la rama actual.
		--oneline : Nos muestra la lista mas simplificada, dandonos el prefijo 
			del hash perteneciente al commit y el titulo de la descipcion 
			del commit.
		--all : Nos muestra la lista completa de todos los commits realizados
			desde todas las ramas.
		--decorate : Decora la lista señalando a que rama apunta HEAD.
		--graph : Nos muestra la lista como un grafo, el cual se crea a partir 
			del uso de commit desde distintas ramas.
reset : Nos es util para eliminar commits hechos, tiene 3 opciones de uso, el primero
es por defecto y nos deja los archivos incluidos en esos commits en el espacio de 
trabajo, el segundo con el parametro --soft nos deja los archivos en el Stage y por
ultimo --hard que nos elimina el commit y su contenido.
	parrametros:
		por defecto : Elimina el ultimo commit poniendo los archivos en nustro
				espacio	de trabajo.
		<nombre del comit> : elimina todos los commits hasta antes que el nombrado.
		--soft <nombre del archivo> : Elimina el commit nombrado y coloca los
						cambios en el Stage. Aun no se que pasa si 
						el 'commit nombrado no es el ultimo.
		--hard <nombre del archivo: Elimina no solo el commit si no tambien los 
						archivos que contenia.

revert : nos revierte a un estado anterior al commit mas actual o dependiendo el nombre del
commit que le indiquemos.
	parametros:
		<nombre del commit> : nos crrea un commit nuevo donde agrega lo que se le 
					quito y le quita lo que se le agrego y de ese modo 
					hace el commit.
		--no-commit : nos permite almacenar los archivos reestaurados en el Stage
				asi podremos agregarle o modificarlo para lluego con el
				parametro --continue poderlos  enviar al repositorio local.

diff : compara dos archivos y por defecto esos archivos son aquellos que estan en el espacio 
de trabajo y en el Stage.
	parametros:
		<> : Compara y muestra las diferencias entre los archivos del Stage y los
                        que estan siendo modificados en el espacio de trabajo.
                <nombre1> <nombre2> : Compara ambos commits nombrados y nos muestra las
                                        diferencias.
                <nombre> : Compara lo que hay en Stage con lo que hay en el commit nombrado y
                                nos muestra las diferencias.
                HEAD-num , num = 1...n con n natural : Podra comparar HEAD con alguno anterior
                                                        y mostrarnos las diferencias.
                HEAD : Compara los archivos que estan apuntados por HEAD y los que estan en
                        el Stage luego nos muestra las diferencias.

		
branch : nos permite enlistar, crear, renombrar y borrar ramas
	parametros:
		<> : nos enlista las ramas que tenemos creadas.
		<> -v : la lista tiene mas detalles

		<nombre de la rama> : Crea una nueva rama con el nombre indicado.
		-b <nombre de la rama> : crea una nueva rama con el nombre indicado y mueve 
					el control a ella,
		-m <nombre antiguo> <nombre nuevo> : Nos permite renombrar la rama de nombre
							antiguo indicado, por el nombre nuevo
							indicado.
		-W <nombre antiguo> <nombre nuevo> : Renombra aunque presente conflictos.
		-d <nombre de la rama> : Borra una rama ya creada, con el nombre indicado.
		-D <nombre de la rama> : Fuersa la eliminacion de una rama con el nombre 
					indicado.

checkout : una de las ultilidades de este comando es poder cambiar entre ramas creadas o que 
aun no lo este, en algunas versiones funciona como el comando 'restore'
	parametros:
		<nombre de la rama> : Se mueve HEAD a la rama indicada si es que esta creada.
		-b <nombre de la rama> : Crea una nueva rama, con el nombre indicado y se
					mueve hacia ella.

merge: Es una operacion de fusion de ramas, puede generar conflictos en determinados casos.
Esta fusion tiene 3 metodods posibles: fast-foward, estrategia recursiva y mezcla con conflicto.
        parametros:
                <nombre de una rama> : Mezclara la rama actual con aquella indicada.

                --continue : Nos permite resolver los conflictos para luego seguir con
                        la mezcla y el commit correspondiente <conflicto> --> <resuelve> --> --continue
