# *Introducción a Linux y Bash*

🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda, basado en el tutorial de [Linux y Bash](https://github.com/AJVelezRueda/Fundamentos_de_informatica/blob/master/Intro_Linux_Bash/Intro_linux.md) de los autores Ana Julia Velez Rueda y Guillermo Benítez. El mismo se encuentra bajo licencia 
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## [Linux](#linux)

Como ustedes ya sabrán, Linux es un sistema operativo de código abierto con licencia GNU GPL (General Public License), la cual nos permite poder tomar el código, modificarlo y distribuirlo libremente. Gracias a esta característica se generaron muchas distribuciones, entre las cuales las más recomendadas para iniciar en el mundo de Linux son **Ubuntu** o **Linux Mint**. En este curso recomendamos fuertemente utilizar alguna de estas dos distribuciones, ya que con otro sistema operativo no vamos a poder darles soporte.

Una de las características principales de Linux es la organización jerárquica de las carpetas del sistema, la cual se puede pensar como un árbol, siendo la raíz la base del sistema y a partir de allí las carpetas se ramifican.
![alt text](https://www.linuxadictos.com/wp-content/uploads/linux-arbol-directorios.jpg)

La otra característica que distigue a Linux es la existencia de dos tipos de usuarios, que podríamos dividir en simplemente usuarios y administradores (o usuario root o superusuario). Estos usarios se generan automáticamente cuando configuramos nuestra cuenta y los podemos usar dependiendo de nuestra necesidad. Para la mayoría de las cosas solo vamos a necesitar permisos de usuario, pero para ciertas tareas vamos a necesitar los permisos de superusuario. Dicho esto, recomendamos fuertemente que solo para las tareas específicas se utilice el superusuario, para todo lo demás hay que usar el usuario común.  

## [Interfaz de línea de comandos(CLI)](#CLI")

* [1. Caparazón](#1_shell)
* [2. Comandos básicos](#2_comandos)


### [1. Caparazón](#1_shell)

El shell es la capa más externa del sistema operativo, esta es la interfaz entre el usuario y el sistema operativo. Los shells incorporan un lenguaje de programación para controlar procesos y archivos, además de iniciar y controlar otros programas. El shell gestiona la interacción entre el usuario y el sistema operativo solicitándole la entrada, interpretando dicha entrada para el sistema operativo y gestionando cualquier resultado de salida procedente del sistema operativo. La shell es un programa que ejecutamos en la forma de un repl(read printable loop), este interpreta los comandos que ingresa el usuario y posteriormente los transmite al sistema y arroja el resultado. 

Podemos decir en general que los comandos que:
- siguen la siguiente estructura:

	```bash
	$ comando [opciones] [argumentos]
	```

- consisten en la palabra (comando) en sí y opcionalmente las opciones y/o argumentos

- determinan el código o librería que se va a usar

- pueden ser modificados en su comportamiento por defecto mediante opciones o argumentos: si bien el comando contiene la instrucción que queremos realizar, el argumento indica dónde debe operar el comando y la opción solicita la modificación de la salida.

Existen argumentos que se le pasan al comando que le permiten operar sobre un objeto/dato, etc., aunque pueden no existir.

Después de escribir un comando, el resultado que se obtiene es información de texto o una acción específica realizada por la computadora. Por ello, la clave es escribir el comando correcto, un punto que suele considerarse como una desventaja en este diseño de interfaz de usuario y por lo que se suelen utilizar formas más atractivas de interfaz como GUI (Graphical User Interaction).


### [2. Comandos básicos](#2_comandos)

Existen varios shells, la más común es bash (llamada "Bourne Again SHell"). Después de ejecutarse, el shell visualiza un indicador de mandatos o prompt, que en el caso del Bourne shell suele ser un $ (signo de dólar), momento en que el shell está preparado para recibir un comando. Si bien hay muchos comandos que podés usar con CLI, en general se dividen en dos categorías:

+ Los comandos que manejan los procesos
+ Los comandos que manejan los archivos

###  **Comandos que manejan archivos**

Algunos ejemplos de este tipo de comandos son:

**_`ls`_**: 

Este comando lista todos los archivos en una carpeta y acepta como parámetro. El comando predeterminado excluirá los archivos ocultos. Para mostrar todos los archivos, puedes agregar `-a`.


```bash
$ ls -a
```

**_`cd`_**: 

Cambio de directorio 

```bash
$ cd directorio_al_que_quiero_ir
```

**_`mv`_**: 

Renombrar o mover un archivo los archivos y directorios en su sistema de archivos del sistema operativo. Es importante recordar que se debe escribir el nombre del archivo y la extensión. 

Si queremos por ejemplo deseamos renombrar un archivo:


```bash
$ mv recurso.extension recurso_renombrado.extension
```

Si deseamos cambiar la ruta de ese archivo a una nueva debemos ingresar el nombre del archivo seguida la ruta:


```bash
$ mv recurso.extension home/Directorio
```
Ya vimos la estructura de los comandos, pero, ¿cómo sabemos cuales son las opciones de un comando? O más aún, ¿cómo sabemos qué es lo que hace un comando dado?
Para estos casos Linux nos ofrece dos maneras de poder obtener estas respuestas. Una de estas opciones es usar otro comando, llamado `man` el cual muestra, justamente, el manual del comando en cuestión:

```bash
man ls
```

La otra opción para contestar estas preguntas es la opción `--help`

```bash
ls --help
```

Veamos rápidamente algunos comandos básicos muy útiles, con algunas opciones según corresponde.

- Algunas opciones útiles del comando `ls` son:

	- `-l` para ver los archivos en forma de listas, con algunos detalles más, alguno de los cuales son los permisos que tiene el archivo o carpeta, a quien pertenece, el peso, la fecha de modificación, etc.
	- `-a` para ver todos los archivos, inluso los ocultos
	- `-d` solo para listar los directorios
	- `-h` para ver el resultado "legible" para el humano. Esta opción solo se puede usar si se utiliza la opción `-l`. De esta forma vamos a poder ver el peso en Bytes, Kilobytes, etc.

	Estas opciones se pueden combinar. Por ejemplo para ver los archivos y carpetas en formato de lista, que se muestren todos y estén en formato legible para el humano se puede escribir:

	```bash
	ls -lah
	```

- Ya vimos como mover un archivo o carpeta, pero también se pueden copiar, con el comando `cp`, donde hay que utilizar la opción `-r` si se trabaja con carpetas

	```bash
	cp archivo carpeta_destino
	cp -r carpeta carpeta_destino
	```

- `touch` para crear un archivo

	```bash
	$touch Nombre_del_archivo
	```

- Si lo que queremos crear es una carpeta hay que usar el comando `mkdir`

	```bash
	mkdir nombre_carpeta
	```

- Podemos usar un editor de textos integrado, llamado `vim` para modificar el archivo. También se puede usar un editor de texto con interfaz grafica llamado `gedit`.

	```bash
	vim Nombre_del_archivo
	gedit Nombre_del_archivo
	```

- `rm` para eliminar archivos. Se puede usar con la opción `-r` para eliminar una carpeta

	```bash
	rm archivo
	rm -r directorio
	```

- Para poder ver lo que hay dentro de un archivo tenemos algunas opciones.

	- Una de estas es usar el mismo editor de texto que usamos para modificarlo.
	- Otra forma de mostrar un archivo es usar el comando `cat`:

		```bash
		cat archivo
		```
		Este comando también sirve para poder ver varios archivos a la vez concatenándolos uno por debajo del otro.
	
	- Otra opción es ver el archivo de manera que no se muestre por completo en la pantalla, sino que lo leamos a poco. Para esto se usa el comando `less`

		```bash
		less archivo
		```
		En este caso, para dejar de leer hay que apretar la tecla **q**.

- Existen comandos que nos muestran el inicio o el final del archivo, los cuales son `head` y `tail`. Por defecto muestran las primeras o las últimas 10 líneas, respectivamente, pero con la opción `-n` se puede pedir la cantidad de líneas que queramos.

	```bash
	head archivo
	head -n 5 archivo
	tail archivo
	tail -n 5 archivo
	```

- Una forma de poder imprimir texto en la pantalla es usar el comando `echo`, donde el argumento, si no es una variable, va siempre entre comillas

	```bash
	echo "Hola Mundo!"
	```

- Dado un archivo de texto podemos querer contar cuantas palabras, caracteres o líneas tiene, para lo cual se puede usar el comando `wc`, donde, algunas de sus opciones son:

	- `-l` para saber el número de líneas
	- `-m` para saber el número de caracteres
	- `-w` para saber el número de palabras

	```bash
	wc -l archivo
	wc -m archivo
	wc -w archivo
	```

- Para concatenar las acciones de distintos comandos se puede usar el pipe, `|`, el cual toma la salida o el resultado de las acciones que hay en el lado izquierdo y lo usa de entrada para el lado derecho.

	```bash
	cat archivo1 archivo2 | wc -l
	```

	Aquí en lugar de mostrarse la concatenación de _archivo1_ y _archivo2_ en la pantalla esto pasa a ser la entrada del comando `wc` y con la opción `-l` obtiene la cantidad de líneas, lo cual es lo que se termina mostrando en la pantalla.

- `grep` es un comando muy útil que busca un patrón que le pasemos en un archivo dado:

	a. De forma básica se puede usar para buscar la ocurrencia de palabras en un archivo de texto. 

	```bash
	grep "palabra" archivo
	```	
	b. Una opción útil para este caso es `-o` con la cual aparece la cantidad de ocurrencias en forma de lista.

	```bash
	grep -o "palabra" archivo
	```
	b. Otra opción útil puede `-v` que nos permite excluir las líneas que incluyen dicha palabra que pasando como parámetro

	```bash
	grep -v "palabra" archivo
	```


- Ya vimos un comando para concatenar archivos uno debajo del otro, pero también existe la posibilidad de pegarlos uno al costado del otro, cosa que resulta muy útil cuando trabajamos con archivos que contengan columnas y las queramos concatenar una al lado de la otra. El comando que se usa para esto es `paste`, donde una opción muy útil es `-d` con el cual podemos definir el delimitador entre los archivos (por defecto es una tabulación)

	```bash
	paste archivo1 archivo2
	paste -d " " archivo1 archivo2
	```

- Algo que aparece al usar `ls -a` es una carpeta cuyo nombre es un punto `.` y otra que son dos puntos `..`. Estos puntos son útiles ya que representan el directorio actual (en el cual estamos) y el superior, respectivamente. De esta manera, si con el comando `cd` nos movimos a una carpeta, para volver a donde estábamos habría que escribir:

	```bash
	cd ..
	```

- Otro comando muy útil es `find`, con el cual podemos encontrar archivos a partir de cierta carpeta por su nombre. La estructura básica es `find [desde_donde] -name [nombre_del_archivo]`. Como ya vimos las carpetas de Linux se organizas como ramificaciones de un árbol, por lo que cuando definimos la carpeta donde se tiene que realizar la búsqueda va a buscar en esa carpeta y todas las subcarpetas.

	```bash
	find /home -name "nombre"
	```

- Muchas veces nos va a ocurrir que hay que trabajar con muchos archivos que comparten alguna característica, como lo puede ser la extensión, y sería engorroso tener que usar el mismo comando para cada archivo. O también puede pasar que queremos ver al mismo tiempo todos los archivos de cierta extensión, pero de nuevo, seria engorroso usar `cat` y escribir el nombre de cada archivo. Para estos caso se utiliza un caracter que reprenta un comodín o wild card, el cual se entiende como "cualquier caracter". Por ejemplo si tenemos 20 archivos con extensión .txt y queremos concatenarlos podríamos hacer:

	```bash
	cat *.txt
	```
- Otro comando útil cuando manipulamos texto es `sort`, que se usa para ordenar un archivo, organizando los registros en un orden particular. Si no especificamos otra cosa, el comando `sort` ordena el archivo asumiendo que el contenido es ASCII
	```bash
	sort archivo.txt
	```
	
	a. Una opción útil es `-o` que nos permite redireccionar la salida a un archivo:
	
	```bash
	sort -o salida.txt archivo.txt
	```

	b. Otra opción útil es `-k` que nos permite ordenar teniendo en cuenta una columna en partiular
	```bash
	sort -k 4 archivo.txt
	```

	c. Con la opción `-r` podemos además ordenar el archivo de forma inversa (descendiente por defecto):
	```bash
	sort -r archivo.txt
	```

## [Scripting](#scripting)

Como ven todos estos comandos son muy útiles, pero hasta ahora solo vimos la forma de ejecutarlos en una terminal, de a un comando por vez. El verdadero potencial de estos comandos se ve cuando están contenidos en un script, es decir, en un archivo de texto. La pregunta aquí es, ¿cómo reconoce el sistema que este archivo se tiene que ejecutar? En linux todos los archivos de texto plano son justamente eso, por lo que no influye la extensión que le pongamos, ya que esto es más para uso de la persona, por lo cual hay que de alguna manera indicarle que un archivo en particular es un script que contiene comandos que deben ejecutarse. Para esto necesitamos dos cosas:

- En primer lugar, en la primera línea debemos escribir `#!`, el cual se conoce como _shebang_, seguido de la ruta del interprete (bash en este caso). En los sistemas Linux es: `#!/bin/bash`
- En segundo lugar el archivo tiene que tener permisos de ejecución

Como vimos hoy, usando `ls -l` una de las descripciones que aparece son los permisos, los cuales son:

- de lectura (`r`)
- de escritura (`w`)
- de ejecución (`x`)

Para modificar los permisos de un archivo se utiliza el comando `chmod` cuyas opciones son:

- +r, +w o +x para darle permisos de lectura, escritura o ejecución a un archivo respectivamente
- -r, -w o -x para quitárselos.

Estas opciones, al igual que con `ls`, se pueden combinar, por lo que si quiero darle todos los permisos a un archivo podría hacer:

```bash
chmod +rwx archivo
```

Por último, si queremos ejecutar un archivo que tenga permisos de ejecución tenemos dos opciones:

- Escribir la ruta completa (absoluta) del archivo
- Si estamos en la carpeta donde se encuentra el archivo podemos usar el `.`

	```bash
	/home/ana/scripts/nombre_script.sh #ruta absoluta
	./nombre_script.sh #ruta relativa
	```
