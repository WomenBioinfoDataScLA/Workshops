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
Un sistema de control de versiones es una herramienta que realiza un seguimiento de los cambios de un documento o directorio de forma automática, creando efectivamente diferentes versiones de nuestros archivos. Los sistemas de control de versiones comienzan con una versión base del documento y luego registran los cambios que realiza en cada paso del camino. Existen múltiples programas que nos permiten realizar un control de versiones de nuetsros prosyectos, pero en este tutorial veremos cómo utilizar [Git](https://git-scm.com/downloads), uno de los más populares en la actualidad.

Para comprender mejor qué hace Git se podría pensar que es un artista que intenta crear una película de [`stop motion`](https://es.wikipedia.org/wiki/Animaci%C3%B3n_en_volumen). Como bien sabrán, la construcción de estas películas requiere de muchas fotos que resgistren los movimientos de los personajes al detalle. Pensemos entonces que Git toma fotos instantáneas de los cambios durante la vida de un proyecto, para construir su película. Se podría pensar al proyecto entonces como un video: sobre el que se puede retroceder para comenzar en el documento inicial y reproducir cada estado o cambio que realizó, hasta llegar finalmente a su versión más reciente.

Cada registro de estos cambios se denomina `commit` y mantiene metadatos (referencias temporales y de autorías, etc) útiles sobre ellos. El historial completo de `commits` para un proyecto en particular y sus metadatos forman un `repositorio`. 

![Git commits img](./assets/%5BES%5DCONTROL_DE_VERSIONES_schema1.png)

Siguiendo con la analogía del video, podemos pensar cada `commit` como un fotograma en nuestro video, siendo este el historial completo de cambios de un archivo o directorio. Pero antes de tomar la foto, no sería mala idea preparar a nuestros personajes y apuntar la cámara adecuadamente para que sea capaz de capturar estos cambios adecuadamente. Entonces, al hacer `git add` lo que hacemos es especificar qué movimientos de los personajes quedarán registrados en la próxima foto (colocando las cosas en el área `index` de Git), algo así como gritar `cheeese` para que nadie salga con mala cara. Y luego, cuando hacemos `git commit` le indicamos a Git que es momensto de tomar la foto y registrar de forma permanente los movimientos o cambios en el estado de nuestros personajes.

![Git areas](./assets/%5BES%5DCONTROL_DE_VERSIONES_git_areas.png)

En resumen, Git tiene un área de preparación `index` a la que podemos agregar elementos con `git add`. Los cambios no se documentan de forma permanentehasta que los confirmamos con `git commit`. Los cambios se gestionan como una unidad, al generar un `commit`, y quedan registrados al hacer `git commit`. Esto nos permite enviar grupos específicos de archivos al mismo tiempo o separados, según lo que deseemos.


📑 [**NOTA**]: Es muy importante especificar los cambios realizados en cada `commit`, esto nos ayudará a rastrear cualquier cambio al querer volver atrás.

Ahora bien ¿Qué pasa si alguno de los cambios que hicimos no nos sirve? Bueno, como en pasa en la vida real, las cosas pueden "malir sal" y vamos a necesitar volver a empezar. Pero por su puesto que no vamos a comenzar desde cero si llevamos buen rato trabajando en el proyecto.. ehem! ¡mejor dicho, en la película! Es por eso que quizás nos venga bien guardar las fotos que nos pueden servir en un futuro en una cajita que llamaremos `stash`, haciendo `git stash`. Pero ojo, que siempre se puede reutilizar aquello que dejamos `stasheado` haciendo `git stash apply`. 


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



## Manos a la terminal 💻

🥳 ¡Ahora que sabemos compartir nuestros aportes con el mundo, vamos a crear nuestro primer commit!

Necesitaremos un repositorio local y uno remoto, que van a ser uno la "replica" del otro (`clones`). Desde el repositorio local haremos cambios, que luego vamos a agregar al repositorio remoto.

>
> 🏅 Desafío II: Creá un repositorio en GitHub con el nombre `WBDS_LA_Camp`
>
> ![](./assets/%5BES%5DCONTROL_DE_VERSIONES_create_a_repo.png)
>

La primera vez que nos descargamos localmente un repositorio, se dice que se `clona` en nuestra computadora. Es decir, se hace una copia local de todo lo que contiene la carpeta remota (en la computadora de Don GitHub): archivos y metadatos.


>
> 🏅 Desafío III: Cloná tu repositorio `WBDS_LA_Camp` en tu computadora
>
> Para eso copiá el enlace que te genera GitHub para clonar el repositorio:
>
> ![clone](./assets/%5BES%5DCONTROL_DE_VERSIONES_clone.png)
>
> Y escribí en tu terminal:
> ```bash
> #git clone <enlace a tu repo>
>
> git clone git@github.com:AJVelezRueda/WBDSLA_Camp.git
> ```
>

📑 [**NOTA**]: La primera vez que usas GIT vas a tener que [configurar](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls) Stu nombre completo y tu email con los siguientes comandos:

```bash
git config --global user.name <TU NOMBRE>
git config --global user.email <TU DIRECCION DE EMAIL>
```

Una vez creada la cuenta y un repositorio en alguno de estos servicios, tenés que bajarte la información del repositorio remoto a tu computadora
