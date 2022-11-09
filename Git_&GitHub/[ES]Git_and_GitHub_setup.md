
## Contenido

1. [Instalación de Git](#instalación-de-git)
2. [Configura tus datos](#configura-tus-datos)

## *Instalación de Git*

Para continuar con este tutorial, deberás tener Git instalado en tu computadora y GitHub configurado correctamente.

En el material de [Primeros Pasos](https://github.com/WomenBioinfoDataScLA/WBDSLA_PreCamp_PT/blob/main/%5BES%5DPrimeros_Pasos.md), te explicamos cómo descargar e instalar el `Git Bash`en caso de que tenga Sistema Operativo **Windows** en su computadora. Este programa ya viene con `Git` instalado.

Si estás usando una computadora con **Linux** o **macOS** tendrás que corroborar que `Git` se encuentra isntalado, vamos a por ello! 

Abrí una `terminal` y verificá si ya está `Git` instalado en la computadora... ¡Quien sabe, atl vez tenemos suerte! Para ello, usaremos el siguiente comando:

```bash
git --version
```

✅ [TIP] Una de las formas de pegar un texto en la terminal es presionando el botón derecho del mouse y luego haciendo clic en `Paste` o `Pegar`. También podés usar las teclas `Ctr` + `Shift` + `c` para copiar y `Ctr` + `Shift` + `v` para pegar. Luego, no te olvides de presionar `Enter` 


![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/git_version.gif)

🚨 Si te aparece un mensaje como: `git version 2.38.1`, luego de haber ingresado el comando es porque ya tenés instalado `Git`, y no será necesario que sigas las intrucciones de instalación, podés ir directamente al paso de configuración.

Si no obtuviste ningún mensaje como el antes mencionado, será necesario instalar `Git`en tu computadora 🥺. ¡No desesperes que allá vamos!

### Instalación para macOS
`Git` para macOS se puede descargar [aquí](https://sourceforge.net/projects/git-osx-installer/files/).

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/git_for_mac.png)

Luego de descargarlo, deberás hacer doble click sobre el archivo para iniciar el instalador. Solo te queda seguir los pasos de instalación hasta que se complete con éxito y ¡Voilà! Ya podés abrir el programa para usarlo.

✅ [TIP] Confirmá que la instalación funcionó ejecutando `git --version` en la terminal, esta vez deberías obtener la información sobre lala versión recientemente instalada.

### Instalación para Linux

Con la terminal abierta, ejecuta los siguientes comandos:

```bash
sudo apt-get update 

sudo apt-get install git
```

Para asegurarse de que la instalación funcionó, ejecute `git --version` nuevamente y vea si esta vez hay información sobre la versión instalada.

## *Configura tus datos*
Con git instalado en su computadora, ahora configuremos su correo electrónico y nombre de usuario usando los siguientes comandos. Pero recuerda reemplazar `<tu login>` con tu nombre y `<tu email>` con tu correo electrónico personal.

```bash
git config --global user.name <tu login>

git config --global user.email <tu email>
```

📑 [**NOTA**]: Si necesita más información, consulte la documentación en el sitio web [github](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

## *¿Dónde guardar mis repositorios?*

Como se mencionó anteriormente, Git funciona con un repositorio local que está en su computadora. Luego, debemos mostrarle dónde queremos almacenar nuestros repositorios en nuestra máquina.

Comencemos por crear una carpeta donde se almacenarán los repositorios. Para esto, usaremos algunos comandos aprendidos en el tutorial de Bash/Linux:

```bash
cd ~/Desktop

mkdir Proyectos

cd Proyectos
```

Ahora que estamos dentro de la carpeta `Proyectos`, inicialicemos un repositorio git en la raíz de la carpeta, ejecute el siguiente comando:

```bash

git init

````

😍 Ahora estamos con todo listo para comenzar la parte práctica de este tutorial, que se puede encontrar en [1.Practica.md](%5BES%5D1.Practica.md)
