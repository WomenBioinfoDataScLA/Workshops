# *Scripting e IDEs*

🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda y el Ing. Franco Leonardo Bulgarelli. El mismo se encuentra bajo licencia 
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## ¿Qué es un script?

Un script es básicamente un conjunto de instrucciones ordenadas, que buscan resolver una tarea específica. Títipcamente son archivos de texto que contienen todas las instrucciones que resuelven un problema dado en un lenguaje de programación espacífico. Según el lenguaje tendrán una extensión distinta. Por ejemplo los  scripts de Python usan la extensión `.py`.

Podríamos decir que los scripts cumplen una o todas las siguientes características:

 1) Puede interactuar con bibliotecas del sistema directamente o por medio de comandos de bash:
 
 2) Se ejecuta en una terminal y en general contra un intérprete:
 
 3) Son particulamente útiles para automatizar tareas de tipo cron o automatizar tareas tediosas:
 
 4) Permite el uso de argumentos desde la terminal o shell:

 5) Retornan un código numérico de salida:


## ¿Qué lenguajes se utilizan para scripting?

Existen algunos lenguajes que se denominan de `scripting`, que tienen como carácterística general su fácil interacción e integración con otros lenguajes de programación. Se utilizan principalmente en combinación con otros lenguajes, aunque  muchos de ellos pueden usarse como leguajes principales de un proyecto dado.


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