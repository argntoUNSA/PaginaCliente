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
lo cual significa que inicie mi repositorio local

4) Al seguir los mismos pasos aprendi mas subcomandos como add, restore y commit.
Los cuales me ayudan a modificar mi archivo antes de actualizar mi repositorio local.
TAmbien vimos como dar un paso hacia atras en una situacion de comentar erroneamente 
un commit esto con el parametro --amend.






GLOSARIO de subcomandos:
init: Sirve para poder iniciar un repositorio local vacio
	parametros:

add: Agrega archivos desde nuestro escenario de trabajo al stage preparandolos asi para
ser enviados al repositorio actual.
	parametros: 
		. : Agrega todos los archivos.
		<nombre del archivo> : A'grega solo el archivo 'nombrado

restore: Restaura el estado de un archivo
	parametros: 
		<nombre del archivo> : elimina el archivo nombrado.
		--staged <nombre del archivo> : Elimina del Stage el archivo nombrado
						pero lo aloja en el espacio de trabajo.

ommit : Nos sirve para actualizar nuestro repositor local, con los datos alojados en
el Stage por defecto sube todos los archivos.
	parametros:
		--amend : da un paso atras y nos permite editar la etiqueta del commit.

