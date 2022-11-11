# CONTROL DE VERSIONES

🚨 Este material fue creado por la Dra. Ana Julia Velez Rueda y Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## Contenido

1. [Instalación de Git](#instalación-de-git)
2. [Instalación para macOS](#instalación-para-linux)
3. [Instalación para Linux](#instalación-para-linux)
4. [Configura tus datos](#configura-tus-datos)
4. [Instalación para macOS](#instalación-para-linux)

## *Instalación de Git*

Para continuar con este tutorial, deberás tener Git instalado en tu computadora y GitHub configurado correctamente.

En el material de [Primeros Pasos](https://github.com/WomenBioinfoDataScLA/WBDSLA_PreCamp_setup/blob/main/%5BES%5DPrimeros_Pasos.md), te explicamos cómo descargar e instalar el `Git Bash`en caso de que tenga Sistema Operativo **Windows** en su computadora. Este programa ya viene con `Git` instalado.

Si estás usando una computadora con **Linux** o **macOS** tendrás que corroborar que `Git` se encuentra isntalado, vamos a por ello! 

Abrí una `terminal` y verificá si ya está `Git` instalado en la computadora... ¡Quien sabe, talvez tenemos suerte! Para ello, usaremos el siguiente comando:

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

### Configura tus datos
Con `Git` instalado en tu computadora, solo nos queda configurarlo para poder usarlo. Para ello usaremos los siguientes comandos:


```bash
git config --global user.name <tu login>

git config --global user.email <tu email>
```

✅ [TIP] Recordá reemplazar `<tu login>` con tu nombre y `<tu email>` con tu correo electrónico, el mismo que usaste para crear `GitHub`.


<details>
  <summary> 🤓 LEE MÁS AQUÍ </summary>
 Podés leer más sobre cómo configurar tu Git [aquí](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

</details>


## `Init`ializando proyectos

Como mencionamos [anteriormente](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BES%5D0.Intro.md), `Git` funciona con un repositorio local que está en su computadora. Luego, debemos mostrarle dónde queremos almacenar nuestros repositorios en nuestra máquina.

Comencemos por crear una carpeta donde se almacenarán nuestros los repositorios que crearemos para el `WBDS LA Camp`. Para esto, usaremos algunos comandos aprendidos en el tutorial de [Bash/Linux]():

```bash
cd ~/Desktop

mkdir WBDSLA_Camp

cd WBDSLA_Camp
```

Ahora que estamos dentro de la carpeta `WBDSLA_Camp`, inicializaremos un repositorio git en la raíz de la carpeta, ejecutando el siguiente comando:

```bash
git init
````

😍 Ahora tenemos todo listo para comenzar la parte [práctica](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BES%5D2.Practica.md) de este tutorial.
