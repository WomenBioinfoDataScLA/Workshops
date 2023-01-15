# *Scripting e IDEs*

🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda y Franco Leonardo Bulgarelli. El mismo se encuentra bajo licencia
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa]. Toma elementos de [Recursos Python](https://flbulgarelli.github.io/recursos-python/), bajo la misma licencia.

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## ¿Qué es un script?

Un _script_ (en español: guion) es básicamente un conjunto de instrucciones ordenadas, que buscan resolver una tarea específica. ⛔ Momento, se parece mucho a la definición de un _programa_, ¿no?

Muy bien, ¡nos descubriste! Es que los scripts **son** programas, pero que tienen algunas características particulares:

 1) Suelen interactuar con bibliotecas del sistema operativo, ya sea directamente o por medio de comandos de bash;
 2) Se suelen ejecutar en una terminal (_shell_) y en general contra un intérprete;
 3) No suelen contar con una interfaz gráfica, sino que todas las interacciones ocurren a través entradas y salidas textuales;
 4) Reciben sus argumentos desde la terminal;
 5) Retornan un código numérico y entero de salida (`0` por defecto y en caso de éxito);
 6) Suelen operar principalmente contra archivos y _flujos de datos_, como la entrada estándar (`stdin`), la salida estándar (`stdout`) y el error estándar (`stderr`).

Yendo un poco más a concreto, los scripts suelen estar escritos en texto plano, usando un lenguaje de programación _interpretado_, como Python, Perl, Ruby o Bash, y su extensión variará justamente según su lenguaje. Por ejemplo los  scripts de Python usan la extensión `.py`, y los escritos en Bash, `.sh` (o directamente sin extensión).

## ¿Para qué queremos scripts?

Los scripts son particularmente útiles para automatizar tareas que se ejecutan periódicamente (también conocidas como tareas programadas o calendarizadas) o automatizar situaciones tediosas como:

 * Ejecutar un conjunto de programas y combinar sus resultados;
 * Descargar, subir, mover y/o descomprimir archivos;
 * Realizar conversiones de formatos;
 * Realizar tareas de construcción de proyectos de software, como compilación, prueba y publicación;
 * Realizar tareas de mantenimiento del sistema operativo, como instalar y configurar software, liberar espacio, etc.

## ¿Qué lenguajes se utilizan para scripting?

Como ya contamos, los lenguajes usados para scripting suelen ser interpretados, es decir, se ejecutan directamente contra un programa intérprete que lee y ejecuta las instrucciones, en lugar de requerir un compilación previa (como sería por ejemplo el caso de Java, C o Go).

Esto es así porque cuando programamos scripts nos importará que la escritura de dichos programas sea rápida y sencilla, pero no así que su ejecución sea rápida (los lenguajes compilados suelen optimizar nuestro código para reducir el tiempo de ejecución y recursos en general). Además los lenguajes de _scripting_ suelen ofrecer fácil integración para ejecutar programas externos, gestionar archivos e interactuar con el sistema operativo en general.

## Estructura de los scripts en Python

Los scripts tienen siempre un único punto de entrada, o _main_, que es aquello que se ejecutará cuando se invoque al mismo desde la terminal.

En Python podemos hacerlo de dos formas. Una es la más "básica", que consiste en contar con un archivo `.py` común y corriente, que importe los paquetes necesarios y ejecute ejecute las operaciones. Por ejemplo, supongamos que haremos un script que simplemente dice `hola mundo` y termina. Para ello deberemos escribir un archivo `hello.py` que contenga exactamente ésto:

```python
print("hola mundo")
```

Alternativamente, podemos escribirlo de una forma un poco más compleja, pero más "clásica" y conceptualmente correcta:

```python
def main():
    print("hola mundo")

if __name__ == "__main__":
  main()
```

¡Y eso es todo! Este es probablemente uno de los scripts más simples que podemos realizar.


## ¿Como ejecutamos un script?

Ahora bien, ¿cómo hacemos para ejecutarlo? La forma más obvia es ejecutar el archivo desde la terminal, usando la ruta absoluta o relativa al archivo invocando directamente el intérprete adecuado. Por ejemplo haciendo:


```
python3 hello.py
```

Aunque es claramente más sencilla, esta forma abreviada de ejecución puede tener algunas desventajas respecto de usar todos los pasos anteriores, entre ellas y la más importante es que obliga a quienes utilizan nuestro script a conocer el intérprete contra el que debe ejecutar el script.

Sería mejor que la persona que usa nuestro script no tuviera que saber con qué interprete ejecutar el archivo, ¿no? En otras palabras, poder hacer simplemente `./hello.py`. Pero, ¿cómo reconocería el sistema que este archivo que a simple vista parece un archivo de texto común se tiene que ejecutar como un script?

En **linux** todos los archivos de texto plano son justamente eso textos planos, por lo que no influye la extensión que le pongamos, por lo cual hay que de alguna manera indicarle que un archivo en particular es un script que contiene comandos que deben ejecutarse. Para esto necesitamos:

    1) En primer lugar, en la primera se suele escribir `#!`, que se conoce como shebang, seguido de la ruta del interprete contra el que se debe ejecutar el programa (python en este caso). En los sistemas Linux es: `#!/bin/python3`

    2) En segundo lugar el archivo tiene que tener permisos de ejecución. Como ya vimos, esto último se puede hacer usando el comando `chmod` cuyas opciones son:

     `+r`, `+w` o `+x` para darle permisos de lectura, escritura o ejecución a un archivo respectivamente

     `-r`, `-w` o `-x` para quitárselos.


     Estas opciones, se pueden combinar, por lo que si quiero darle todos los permisos a un archivo podría hacer:

    ```bash
    chmod +rwx archivo
    ```

    3) Por último, debemos ejecutar el archivo usando la ruta completa (absoluta) al archivo o estando en la carpeta donde se encuentra el archivo podemos usar el `./nombre_script.py`

Por ejemplo, en nuestro `hello.py` nos quedará así:

```python
#!/bin/python3

def main():
    print("hola mundo")

if __name__ == "__main__":
  main()
```

## IDEs o Entornos de Desarrollo

Para escribir cómodamente nuestros scripts vamos a necesitar una herramienta llamada editor de código, que se parece bastante a un editor de texto, pero no sirve para escribir poemas, currículums, o trabajos prácticos de la escuela (donde nos va a importar que nos corrija la ortografía, subrayar, poner negritas o cambiar colores), sino para crear programas complejos. :star_struck:

Muchos de estos editores de código (o editores a secas, de ahora en más) se pueden instalar en tu propia computadora. Algunos de ellos son:

* [Sublime](https://www.sublimetext.com/);
* [Visual Studio Code](https://code.visualstudio.com/);
* [Atom](https://atom.io/);
* [Vim](https://www.vim.org/).

Además, para desarrollar aplicaciones y sistemas más complejos, existen herramientas aún más completas (¡y complejas! :sweat:) que se conocen como Entornos Integrados de Desarrollo (_IDEs_ por sus siglas en inglés). Uno de los más populares es [PyCharm](https://www.jetbrains.com/es-es/pycharm/). También existen IDEs en línea como [Colaboratory](https://colab.research.google.com/) y [Jupyter](https://jupyter.org/) que no requieren que los descarguemos en nuestra computadora. :muscle:

Con la excepción de Colab, para usar cualquiera de estos editores y entornos de desarrollo, vamos a tener que instalarlos en nuestras computadoras. Y con eso ya estaremos en condiciones de programar y ejecutar nuestros scripts, ¿no?

¡No! Porque los editores sólo son herramientas para escribir código, y no vienen con Python 😒. Veamos entonces antes de continuar como instalar todas estas cosas.

## Instalación del entorno local

> Nota: esta guía está orientada a una instalación local en Linux. Si tenés Windows, [acá](https://code.visualstudio.com/docs/python/python-tutorial) encontrarás más información.

Para utilizar Python localmente (es decir, en tu computadora en lugar de en una plataforma online como [Replit](https://replit.com/) o [Mumuki](https://mumuki.io)) vamos a tener que instalar algunos programas. Abrí una terminal. Notarás que aparece algo similar a lo siguiente:

```shell
mi_nombre@mi_computadora:~$
```

Esto lo que está indicando es que iniciaste sesión en la computadora `mi_computadora` con un usuario llamado `mi_nombre`. Además, el signo `$` (también llamado prompt) indica que la terminal está lista para aceptar comandos. Por último, el símbolo `~` indica que estás en el directorio principal de `mi_nombre`, también denominado _home_.

¿Y qué comandos podés ejecutar? Estos son algunos de los (tantísimos) disponibles:

  * `cd`: cambia de directorio
  * `ls`: muestra los contenidos del directorio
  * `pwd`: muestra el directorio actual

La forma más sencilla para instalar Python en Ubuntu (20.04 o superior) es con el siguiente comando:

```bash
$ sudo apt install python3 python-is-python3 python3-pip
```

Visual Code es uno de los editores de código más comunes y flexibles (en 2023). Por eso, en este tutorial vamos a elegirlo. Para instalarlo en Ubuntu ejecutaremos lo siguiente:

```bash
$ sudo snap install code
```

O, si este comando genera una advertencia, podremos hacer lo siguiente:

```bash
$ sudo snap install code --classic
```

¡Llegó la hora de probar todo! Para editar un archivo, podés abrir Visual Code desde el menú de aplicaciones, o ejecutando en una terminal el comando `code`. Ejemplo:

```bash
$ code mi_script.py
```

> Nota: el soporte que Visual Code ofrece para Python por defecto es limitado. Si querés mejorar el soporte podés instalar la extensión oficial para Python, desde el menú de Extensiones (_Extensions_, en la barra lateral izquierda). Allí deberás buscar "Python" y elegir la extensión provista por Microsoft:
>
> ![captura de pantalla de visual code](./vs_python_extension.png)

Luego, para ejecutar los contenidos del archivo, podés hacer:

```bash
$ python3 mi_script.py
```


## Un script más complejo

Como mencionamos anteriormente, los scripts suelen interactuar con el el sistema de archivos (_file system_ o _FS_) y el sistema operativo en general (_Operative System_ u _OS_). Justamente por ello es que [el módulo `os`](https://docs.python.org/es/3.10/library/os.html) de Python nos será de particular ayuda cuando escribamos nuestros scripts. Allí encontraremos operaciones como las siguientes:

  * `os.stat`: nos permite obtener estadísticas de un archivo (como por ejemplo su tamaño)
  * `os.rename`: nos permite renombrar archivos
  * `os.rmdir`: nos permite eliminar directorios

De igual forma, [el submódulo `os.path`](https://docs.python.org/3/library/os.path.html) nos dará más funcionalidades para interactuar con archivos y sus rutas:

 * `os.path.dirname`: nos permite obtener el directorio donde un archivo está contenido
 * `os.path.exists`: nos permite saber si un archivo existe
 * `os.path.join`: nos permite concatenar rutas (por ejemplo, combinar `/una` y `ruta` para obtener `/una/ruta`)

Por último, [el módulo `sys`](https://docs.python.org/es/3/library/sys.html) nos dará acceso a `sys.argv`: una lista que contiene el nombre del script y los argumentos con los que se ejecutó un programa.

¡Veamos un pequeño ejemplo! Creá el siguiente script `stats.py`

```python
#!/bin/python3

import os
import sys
from datetime import datetime # para transformar fechas

archivo = sys.argv[1] # el primer parámetro se corresponde con la posición 1,
                      # dado que la posición 0 contiene al nombre del script

print("Obteniendo información del archivo", archivo)

estadisticas = os.stat(archivo)
print("Pesa:", estadisticas.st_size, "bytes")
print("Modificado por última vez:", datetime.utcfromtimestamp(estadisticas.st_atime).strftime('%Y-%m-%d %H:%M:%S'))
```

Para poder hacer ejecutable a nuestro script deberemos hacer lo siguiente:


```bash
chmod u+x stats.py
```

Y ahora lo podemos ejecutar así:

```bash
./stats.py '[ES]Scripting.md'
Obteniendo información del archivo [ES]Scripting.md
Pesa: 11730 bytes
Modificado por última vez: 2023-01-15 17:26:31
```

> 💪 ¡Desafío final! Creá un script `swap.py` que tome dos nombres de archivo y renombre al primero con el nombre del segundo, y al segundo lo renombre con el nombre del primero.
> Ejemplo:
>
> ```bash
> $ cat hola.txt
> hola
> $ cat chau.txt
> chau
> $ ./swap.py hola.txt chau.txt
> $ cat hola.txt
> chau
> $ cat chau.txt
> hola
> ```