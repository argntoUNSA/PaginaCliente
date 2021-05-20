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

5) Pudimos actualizar la pagina el uso de una plantilla. Esta planilla nos ha ayudado
muchisimo, reduciendo el tiempo invertido de codigo, aportando buena estetica y 
experiencias adquiridas. espero a ustedes tambien les sirva. Saludos . Aprendimos 
tambien a que para corregir errores o aplicar cambios podemos regresar los archivos puestos
en el Stage inclusive commits hechos, estogracias a los subcomandos retore, reset
y revert. reset es un subcomando destructivo ya que es capaz de eliminar los commits
que le indiquemos, sin poder recuperarlos luego, revert en cambio nos permite regresar
nuestro commit aplicarle las modificaciones que nos parecen necesartias y luego 
proceder a aplicar commit sobre el archivo modificado.

6) Usamos ramas para poder trabajar en paralelo, es decir desde un punto del proyecto
principal (raiz), desarrollar un proyecto paralelo (rama) sin afectar al primero. Esto
nos permite, por ejemplo, que a partir de un commit que este fallando podamos desarrollar
la solucion y luego integrar esa solucion al proyecto. el subcomando branch nos permitira 
ver la lista de ramas crear ramas nuevas, examinar las que hay, borrar ramas y 
renombrarlas. Las ramas tienen repositorios incdividuales y de forma paralela, los 
archivos que no esten preparados para el commit son reemplazados. Tambien note que si
modifico mis archivos sin usar la consola, no habria problemas, ya que git lo tomaria
como un cambio que se le hizo al archivo, comento esto porque cuadno quiero trabajar 
con ramas en mi caso quise cambiarle de logo a mi pagina, entonces inserte el comando 
git mv logo.jpg style/logo.jpg y por mas que intentaba variar el nombre o intercambiarlos
pero siempre tenia la siguiente salida: 






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

ommit : Nos sirve para actualizar nuestro repositor local, con los datos alojados en
el Stage por defecto sube todos los archivos.
	parametros:
		--amend : da un paso atras y nos permite editar la etiqueta del commit.

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
		<nombre1> <nombre2> : compara ambos commits nombrados
		<nombre> : compara lo que hay en HEAD con lo que hay en el commit nombrado.
		HEAD-num : num = 1...n con n natural, podra comparar HEAD con alguno anterior.
		HEAD : compara los archivos que estan apuntados por HEAD y los que estan en 
			el Stage.

branch : Nos permite crear, modificar y borrar ramas. com las cuales podremos trabajar de 
forma paralela para luego poder mezclarlas.
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
				
checkout : Nos permite viajar entre ramas ya creadas.
	parametros: 
		<nombre de la rama> : cambia el puntero HEAD y ahora apunta a la rama del nombre 
					indicado.


