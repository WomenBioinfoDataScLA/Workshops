# CONTROL DE VERSIONES


🚨 Este material foi criadp pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

> Para fazer este tutorial você precisará ter o Git instalado em seu computador e o [GitHub](https://docs.github.com/es/get-started/quickstart/set-up-git) configurado corretamente. Você pode encontrar um resumo do que precisa no [tutorial de configuração](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

##  Introdução

[O que é um sistema de controle de versões?](#version-control)
Um sistema de controle de versões é uma ferramenta que acompanha automaticamente as alterações em um documento ou diretório, criando efetivamente diferentes versões de nossos arquivos. Os sistemas de controle de versões começam com uma versão básica do documento e, em seguida, registram as alterações feitas em cada etapa do processo. Existem vários programas que nos permitem realizar o controle de versões de nossos projetos, mas neste tutorial veremos como usar o [Git](https://git-scm.com/downloads), um dos mais populares atualmente.

Para entender melhor o que o Git faz, você pode pensar nele como um artista tentando criar um filme [`stop motion`](https://pt.wikipedia.org/wiki/Stop_motion). Como você sabe, a construção desses filmes exige muitas fotos que registram detalhadamente os movimentos dos personagens. Vamos pensar então que o Git tira fotos instantâneos das mudanças durante a vida de um projeto para construir seu filme. Você poderia então pensar no projeto como um vídeo: um que você pode voltar a começar no documento inicial e repetir cada estado ou mudança que você fez, até finalmente chegar à sua versão mais recente.

Cada registro dessas mudanças é chamado de `commit` e mantém metadados úteis (tempo e referências de autor, etc) sobre elas. O histórico completo de `commits` para um projeto específico e seus metadados formam um `repositório`.

![Git commits img](./assets/%5BPT%5DCONTROL_DE_VERSIONES_schema1.png)

Continuando com a analogia do vídeo, podemos pensar em cada `commit` como um quadro em nosso vídeo, sendo este todo o histórico de alterações de um arquivo ou diretório. Mas antes de tirar a foto, não seria uma má ideia preparar nossos personagens e apontar a câmera corretamente para que ela seja capaz de capturar essas mudanças. Então, quando fazemos `git add` o que fazemos é especificar quais movimentos de caracteres serão gravados na próxima foto (colocando as coisas na área `index` do Git), como gritar `cheeese` para que ninguém saia mal na foto. E então quando fazemos `git commit` dizemos ao Git que é hora de tirar uma foto e registrar de forma permanentemente os movimentos ou mudanças de nossos personagens.

![Git areas](./assets/%5BES%5DCONTROL_DE_VERSIONES_git_areas.png)

Resumindo, o Git tem uma área de teste `index` à qual podemos adicionar itens com `git add`. As alterações não são documentadas permanentemente até que as confirmemos com `git commit`. As mudanças são gerenciadas como uma unidade, gerando um `commit`, e são registradas fazendo `git commit`. Isso nos permite enviar grupos específicos de arquivos ao mesmo tempo ou separadamente, dependendo do que queremos.

📑 [**NOTA**]: É muito importante especificar as alterações feitas em cada `commit`, isso nos ajudará a rastrear as alterações quando quisermos voltar atrás.

Agora, o que acontece se alguma das alterações que fizemos não funcionar para nós? Bem, como acontece na vida real, as coisas podem "dar errado" e precisaremos recomeçar. Mas é claro que não vamos começar do zero se já estamos trabalhando no projeto há muito tempo... quer dizer, no filme! É por isso que pode ser bom para nós salvar as fotos que podem ser úteis no futuro em uma caixinha que chamaremos de `stash`, fazendo `git stash`. Você sempre pode reutilizar o que deixou `stashed` fazendo `git stash apply`.

## Git ao infinito e além...

O Git funciona com um repositório local que está no seu computador, onde você vai adicionar seus commits e um repositório remoto (na nuvem) no qual você pode fazer upload de seus commits, compartilhá-los com outra pessoa ou baixar os commits que alguém carregou .

Existem vários serviços para armazenar repositórios remotamente:

- [Github](https://github.com) 
- [Bitbucket](https://bitbucket.com)
- [Gitlab](https://gitlab.com/)

Para usá-los você deve se registrar e criar uma conta.

>
>🏅 Desafio I: Crie sua conta no [GitHub](https://github.com/). Tenha seu login e senha à mão, você vai precisar!
>

Podemos fazer uma sincronização de saída do repositório local para o remoto (origem), fazendo `git push`. Este comando envia todos os commits gerados localmente que não foram confirmados anteriormente.

Também podemos extrair alterações do repositório remoto usando o comando `git pull`.

## Manos a la terminal 💻

🥳 ¡Ahora que sabemos compartir nuestros aportes con el mundo, vamos a crear nuestro primer commit!

Necesitaremos un repositorio local y uno remoto, que van a ser uno la "replica" del otro (`clones`). Desde el repositorio local haremos cambios, que luego vamos a agregar al repositorio remoto.

>
> 🏅 Desafío II: Creá un repositorio en GitHub con el nombre `WBDS_LA_Camp`
>

<img src="./assets/%5BES%5DCONTROL_DE_VERSIONES_create_a_repo.png" style="width: 500px">

La primera vez que nos descargamos localmente un repositorio, se dice que se `clona` en nuestra computadora. Es decir, se hace una copia local de todo lo que contiene la carpeta remota (en la computadora de Don GitHub): archivos y metadatos.


>
> 🏅 Desafío III: Cloná tu repositorio `WBDS_LA_Camp` en tu computadora
>
> Para eso copiá el enlace que te genera GitHub para clonar el repositorio:
>

<img src="./assets/%5BES%5DCONTROL_DE_VERSIONES_clone.png" style="width: 500px">

> Y escribí en tu terminal:
> ```bash
> #git clone <enlace a tu repo>
>
> git clone git@github.com:AJVelezRueda/WBDSLA_Camp.git
> ```
>

📑 [**NOTA**]: La primera vez que usas GIT vas a tener que [configurar](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls)  tu nombre completo y tu email con los siguientes comandos:

```bash
git config --global user.name <TU NOMBRE>
git config --global user.email <TU DIRECCION DE EMAIL>
```
¡Ahora que tenemos el clon de nuestro repositorio remoto, vamos a comenzar a trabajar en el proyecto! Creá un archivo dentro de la carpeta `WBDS_LA_Camp` de tu computadora:

```bash 
## Ingresamos primero a la carpeta que nos clonamos
## recordá pasarle al comando cd el path tu carpeta
cd WBDSLA_Camp

## creamos un archivo README.md
touch README.md
```

>
> 🏅 Desafío IV: agregá estos cambios al index y empujá los cambios a tu repositorio remoto
>

📑 [**NOTA**]: Cuando queremos empujar todo lo que tenemos hasta ahora resulta agregar el argumento `.` al comando `git add`, de esta forma, al hacer `git add .` agregaremos todos los cambios que hicimos hasta aquí en el repositorio.

Si todo sale bien vas a ver en tu terminal el siguiente mensaje:

```bash
Counting objects: 8, done.
Delta compression using up to 4 threads.
Compressing objects: 100% (8/8), done.
Writing objects: 100% (8/8), 246.61 KiB | 1.88 MiB/s, done.
Total 8 (delta 4), reused 0 (delta 0)
remote: Resolving deltas: 100% (4/4), completed with 4 local objects.
To github.com:WomenBioinfoDataScLA/Workshops.git
   d2ba9b7..af541bb  master -> master
```

💡 Para pensar: ¿De qué otro modo comprobarías que efectivamente los cambios fueron subidos al repositorio remoto?


Ahora hagamos algunos cambios sobre el archivo `README.md`. Agregá al archivo el siguiente texto y guardá:

```
### Repositorio de práctica del WBDS LA Camp

**Autor/a/e: <tu nombre>
```

Vamos entonces a agregar los cambios al espacio `index`, pero esta vez de a poco, verificando cada uno de los cambios, para asegurarnos que no cometimos ningún error en los cambios que agregamos:

```bash
# agregamos de a partes
git add -p
```

Veamos qué nos dice Git:

```bash
diff --git a/README.md b/README.md
index e69de29..092eda1 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,3 @@
+### Repositorio de práctica del WBDS LA Camp
+
+**Autora: Ana Julia Velez Rueda
\ No newline at end of file
Stage this hunk [y,n,q,a,d,e,?]? 
```

🙈 ¡Ups! Nos faltó cerrar los asteriscos para que se pinte nuestro texto `**Autora` en negrita. Vamos a decirle a git que no queremos agregar los cambios usando el flag `n` e ingresando enter.

```bash
diff --git a/README.md b/README.md
index e69de29..092eda1 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,3 @@
+### Repositorio de práctica del WBDS LA Camp
+
+**Autora: Ana Julia Velez Rueda
\ No newline at end of file
Stage this hunk [y,n,q,a,d,e,?]? n

```

>
> 🏅 Desafío V: Agregá los asteriscos de cierre antes de los dos puntos `:` y volvé a agregar los cambios con `git add -p`, pero esta vez usando el flag `y`
>

🤔 Hmmm...No, obtuve ningún resultado en mi terminal ¿Vos sí? ¿Será que no pasó nada? 

>
> 🏅 Desafío VI: Escribí el comando `git status` y averiguá si Git se distrajo o efectivamente agregó los cambios al `index`
>

💡 Para pensar: ¿Qué paso nos faltaría para confirmar los cambios? ¡Exácto, ya podés confirmarlos!

Antes de confirmar nuestros cambios vamos a agregar algunos detalles a nuesta documentación:

>
> 🏅 Desafío VII: Agregá el siguiente texto `Lorem ipsum es el texto que se usa habitualmente en diseño gráfico en demostraciones de tipografías o de borradores de diseño para probar el diseño visual antes de insertar el texto fina.` y luego de guardar escribí el comando `git diff` en la terminal.
>

💡 Para pensar: ¿Para qué nos sirve este comando?

¡Lo siento, creo que me arrepentí 🙈! Quizás no era tan buena idea para documentar nuestro repo usar un texto genérico... probemos guardar los cambios para después:

>
> 🏅 Desafío VIII: Escribí el comando `git stash`
>

💡 Para pensar: ¿Para qué nos sirve este comando?¿Cómo se ve el archivo `README.md` ahora? 

👀 Investigá qué hacen los comandos `git stash show` y `git stash list`

Ahora agregá el siguiente  texto:`El WBDS LA Camp es un curso de formación intensivo gratuito para estudiantes de grado y posgrado que tengan interés ​​en aprender bioinformática y ciencia de datos desde cero.`

>
> 🏅 Desafío IX: Escribí el comando `git diff` ¿Qué marcan los símbolos `+` y `-`? ¿Dónde están los cambios que descartamos?  hacé `git stash apply` y observá como se ve el archivo `README.md` ahora.
>
>
> 🏅 Desafío X: Usá los comandos que correspondan para que tu repositorio remoto se vea del siguiente modo:

```
### Repositorio de práctica del WBDS LA Camp

**Autora**: Ana Julia Velez Rueda

## Sobre el WBDS LA Camp
El WBDS LA Camp es un curso de formación intensivo gratuito para estudiantes de grado y posgrado que tengan interés ​​en aprender bioinformática y ciencia de datos desde cero.

```

Vamos a agregar una secición más a nuetsra documentación que tenga información sobre nuestro trabajo:

```
## Sobre mí
Mi nombre es Ana Julia Velez Rueda, soy doctora en bioinformática, gradudada en la Universidad Nacional de Quilmes de Argentina.
```

¿Qué les parece? ¿Quedó mejor ahora nuestra documentación? Hmmm...bueno tal vez no y quizás sea mejor frenar acá ¿no? 

>
> 🏅 Desafío XI: Para despedirnos, descartá los cambios con `git checkout README.md` 
>

💡 Para pensar: ¿Cómo se ve el archivo `README.md` ahora? ¿Se podrán recuperar los cambios?

👀 Investigá qué devuelven los comandos `git stash show` y `git stash list`
