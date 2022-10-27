# CONTROL DE VERSIONES


🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda y la Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

> Para realizar este recorrido necesitarás tener Git instalado en tu computadora y [GitHub adecuadamente](https://docs.github.com/es/get-started/quickstart/set-up-git) configurado. Podés encontrar un resumen de lo que necesitas en el [tutorial de configuración]().

##  Introducción

[¿Qué es un sistema de control de versiones?](#control-de-versiones)
Los sistemas de control de versiones comienzan con una versión base del documento y luego registran los cambios que realiza en cada paso del camino. 

Se podría pensar como un video: puede retroceder para comenzar en el documento inicial y reproducir cada estado o cambio que realizó, llegando finalmente a su versión más reciente.

Un sistema de control de versiones es una herramienta que realiza un seguimiento de los cambios de un documento o directorio de forma automática, creando efectivamente diferentes versiones de nuestros archivos. 

Cada registro de estos cambios se denomina `commit` y mantiene metadatos útiles sobre ellos. El historial completo de `commits` para un proyecto en particular y sus metadatos forman un `repositorio`. 

![Git commits img](#)

Siguiendo con la analogía del video, podemos pensar cada `commit` como un fotograma en nuestro video, siendo este el historial completo de cambios de un archivo o directorio. 

Cada `commit` funciona como un “paquete” de cambios realizados, que se pueden ir agregando al `stage` (estado intermedio con cambios) mediante el comando git add. 

Estos cambios se gestionan como una unidad, al generar un `commit`, y quedan registrados en una “foto” al hacer `git commit`.

Es muy importante especificar los cambios realizados en cada `commit`, esto nos ayudará a rastrear cualquier cambio al querer volver atrás.

![Git schema](./assets/%5BES%5DCONTROL_DE_VERSIONES_schema.jpg)

## Git al infinito y más allá...

Git trabaja con un repositorio local que está en tu computadora, donde vas a ir agregando tus commits y uno remoto (en la nube) en el cual podes subir tus commits, compartirlos con alguien más o bajarte los commits que haya subido alguien.

Existen varios varios servicios para almacenar repositorios remotamente:

- [Github](https://github.com) 
- [Bitbucket](https://bitbucket.com)
- [Gitlab](https://gitlab.com/)

Para usarlos deberás registrarte y crear una cuenta. 

>
>🏅 Desafío I: Creá tu cuenta en [GitHub](https://github.com/) ¡Tené a mano tu nombre de usuarie y contraseña, lo vas a necesitar!
>

Podemos hacer una sincronización saliente del repo local al remoto (origin), haciendo `git push`. Este comando envía los commits generados localmente que no se hayan enviado anteriormente.

Podemos también descargar los cambios del repositorio remoto utilizando el comando `git pull`.

![Git complete schema](./assets/%5BES%5DCONTROL_DE_VERSIONES_esquema_completo.png)

¡Ahora que sabemos compartir nuestros aportes con el mundo, vamos a crear nuestro primer commit!:

1) Necesitaremos un repositorio local y uno remoto. Desde el local haremos cambios, que luego vamos a agregar al repositorio remoto.

> 

2) La primera vez que usas GIT vas a tener que configurar tu nombre completo y tu email con los siguientes comandos:
git config --global user.name "TU NOMBRE"
git config --global user.email "TU DIRECCION DE EMAIL"

3) Una vez creada la cuenta y un repositorio en alguno de estos servicios, tenés que bajarte la información del repositorio remoto a tu computadora
