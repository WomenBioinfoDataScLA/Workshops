### CONTROLE DE VERSÕES


🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

#  Introdução

Para fazer o próximo tutorial de `Git e Github`, você precisará ter o Git instalado em seu computador e o GitHub configurado corretamente. 

## *Instalar o Git*

No material de [Primeiros Passos](https://github.com/WomenBioinfoDataScLA/WBDSLA_PreCamp_PT/blob/main/%5BPT%5DPrimeiros_Passos.md), explicamos como baixar e instalar o `Git Bash`, no caso de você ter o Sistema Operacional Windows em seu computador. Esse programa já vem com o Git instalado.

Se você têm o Sistema Operacional Linux ou macOS em seu computador, abra um `terminal`.

Com o GitBash ou um terminal aberto, vamos primeiro checar se você já têm o Git instalado. Para isso, cole o comando abaixo no terminal e aperte enter. Uma das formas de colar um texto no terminal é apertando o botão direito do mouse e depois clicar em `Paste` ou `Colar`. 

```bash
git --version
```

<img src="./assets/git_version.gif" style="width: 500px">


Se apareceu uma mensagem como: `git version 2.38.1`, você já têm o Git instalado, então pule essa etapa de instalação e vá para a etapa de configuração neste tutorial.

Se não apareceu uma mensagem com a versão de seu git após correr `git --version`, siga os próximos passos para realizar a instalação.

### macOS
O Git para macOS pode ser baixado [aqui](https://sourceforge.net/projects/git-osx-installer/files/).

<img src="./assets/git_for_mac.png" style="width: 500px">

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
Com o git instalado em seu computador, agora vamos configurar seu e-mail e nome de usuário utilizando os comandos a seguir. Mas lembre-se de substituir `<seu usuário>` com seu nome e `<seu email>` com o seu email pessoal.

```bash
git config --global user.name <seu usuário>

git config --global user.email <seu email>
```

## Configurar 

Agora vamos inicializar um repositório Git nesta pasta que estamos.

```bash
git init
````
