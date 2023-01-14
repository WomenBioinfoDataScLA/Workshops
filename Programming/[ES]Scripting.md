# *Scripting e IDEs*

🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda y Franco Leonardo Bulgarelli. El mismo se encuentra bajo licencia
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

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

## ¿Como ejecutamos un script?

Ahora bien, la gran pregunta es ¿cómo reconoce el sistema que este archivo que a simple vista parece un archivo de texto común se tiene que ejecutar como un script?:

En **linux** todos los archivos de texto plano son justamente eso textos planos, por lo que no influye la extensión que le pongamos, por lo cual hay que de alguna manera indicarle que un archivo en particular es un script que contiene comandos que deben ejecutarse. Para esto necesitamos:

    1) En primer lugar, en la primera se suele escribir #!, que se conoce como shebang, seguido de la ruta del interprete contra el que se debe ejecutar el programa (python en este caso). En los sistemas Linux es: `#!/bin/python3`

    2) En segundo lugar el archivo tiene que tener permisos de ejecución. Como ya vimos, esto último se puede hacer usando el comando `chmod` cuyas opciones son:

     `+r`, `+w` o `+x` para darle permisos de lectura, escritura o ejecución a un archivo respectivamente

     `-r`, `-w` o `-x` para quitárselos.


     Estas opciones, se pueden combinar, por lo que si quiero darle todos los permisos a un archivo podría hacer:

    ```bash
    chmod +rwx archivo
    ```

    3) Por último, debemos ejecutar el archivo usando la ruta completa (absoluta) al archivo o estando en la carpeta donde se encuentra el archivo podemos usar el `./nombre_script.py`

La mayoría de estos pasos son equivalentes en todos los sistemas operativos y pueden ser resumidos quizás tomando algunos atajos:

    1) Ejecutar el archivo desde la terminal, usando la ruta absoluta o relativa al archivo invocando directamente el intérprete adecuado. Por ejemplo haciendo:

    ```python
    python3 nombre_script.py
    ```

Aunque es claramente más sencilla, esta forma abreviada de ejecución puede tener algunas desventajas respecto de usar todos los pasos anteriores, entre ellas y la más importante es que obliga a quienes utilizan nuestro script a conocer el intérprete contra el que debe ejecutar el script.


## IDEs o Entornos de Desarrollo