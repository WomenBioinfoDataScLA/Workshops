### CONTROLE DE VERSÕES

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## Contenido

1. [Instalação do Git](#instalação-do-git)
2. [Instalação para macOS](#instalação-para-linux)
3. [Instalação para Linux](#instalação-para-linux)
4. [Configure seus datos](#configure-seus-datos)
4. [Instalação para macOS](#instalação-para-linux)

## *Instalação do Git*

Para seguir acompanhando este tutorial, você precisará ter o Git instalado em seu computador e o GitHub configurado corretamente. 

No material de [Primeiros Passos](https://github.com/WomenBioinfoDataScLA/WBDSLA_PreCamp_PT/blob/main/%5BPT%5DPrimeiros_Passos.md), explicamos como baixar e instalar o `Git Bash`, no caso de você ter o Sistema Operacional **Windows** em seu computador. Esse programa já vem com o Git instalado.

Se você estiver usando um computador com **Linux** ou **macOS**, você precisará ter certeza de que o `Git` está instalado, vamos ver isso.

Abra um `terminal` e verifique se o `Git` já está instalado no computador... Quem sabe estamos com sorte! Para isso, usaremos o seguinte comando:

```bash
git --version
```

✅ [DICA] Uma das maneiras de colar um texto no terminal é pressionando o botão direito do mouse e clicando em `Paste` ou `Colar`. Você também pode usar as teclas `Ctrl` + `Shift` + `c` para copiar e `Ctrl` + `Shift` + `v` para colar. E depois não se esqueça de pressionar `Enter`


![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/git_version.gif)

🚨 Se você receber uma mensagem como: `git version 2.38.1`, após executar o comando é porque você já tem o `Git` instalado, e não precisará seguir as instruções de instalação, você pode ir direto para a etapa de configuração.

Se você não recebeu nenhuma mensagem a mostrada acima, precisará instalar o `Git` no seu computador 🥺. Não se desespere, aqui vamos nós!

### Instalação para macOS
`Git` para macOS pode ser baixado [aqui](https://sourceforge.net/projects/git-osx-installer/files/).

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/git_for_mac.png)

Após baixá-lo, você deve clicar duas vezes no arquivo para iniciar o instalador. Você só precisa seguir as etapas de instalação até que seja concluída com sucesso e Voilà! Agora você pode abrir o programa para usá-lo.

✅ [TIP] Confirmá que la instalação funcionó ejecutando `git --version` en la terminal, esta vez deberías obtener la informação sobre lala versión recientemente instalada.

### Instalação para Linux

Con la terminal abierta, ejecuta los siguientes comandos:

```bash
sudo apt-get update 

sudo apt-get install git
```

Para asegurarse de que la instalação funcionó, ejecute `git --version` nuevamente y vea si esta vez hay informação sobre la versión instalada.

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


#######################





Abra o arquivo baixado para iniciar o instalador. Siga os passos de instalação até concluir com êxito. Em seguida, abra o programa.

Confirme que a instalação funcionou correndo `git --version` novamente e veja se dessa vez aparece uma informação sobre a versão instalada.

### Linux

Com o terminal aberto, corra os seguintes comandos:

```bash
sudo apt-get update 

sudo apt-get install git
```

Para ter certeza que a instalação funcionou, corra `git --version` novamente e veja se dessa vez aparece uma informação sobre a versão instalada.

## *Configurar seus dados*
Com o git instalado em seu computador, agora vamos configurar seu e-mail e nome de usuário utilizando os comandos a seguir. Mas lembre-se de substituir `<seu login>` com seu nome e `<seu email>` com o seu email pessoal.

```bash
git config --global user.name <seu login>

git config --global user.email <seu email>
```

📑 [**NOTA**]: Se você precisar de mais informações, cheque a documentação no site do [github](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

## *Onde armazenar meus repositórios?*

Como foi dito anteriormente, o Git funciona com um repositório local que está no seu computador. Então precisamos mostrar para ele aonde queremos armazenar os nossos repositórios em nossa máquina.

Vamos começar criando uma pasta em que os repositórios serão armazeados. Para isso, vamos utilizar alguns comandos aprendidos no tutorial de Bash/Linux: 

```bash
cd ~/Desktop

mkdir Projetos

cd Projetos
```

Agora que estamos dentro da pasta `Projetos`, vamos inicializar um repositório git na raiz da pasta, execute o comando a seguir:

```bash

git init

````

😍 Já estamos com tudo pronto para começar de fato a parte prática deste tutorial, que se encontra em [1.Pratica.md](%5BPT%5D1.Pratica.md)