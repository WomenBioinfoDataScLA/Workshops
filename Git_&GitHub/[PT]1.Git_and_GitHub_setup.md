### CONTROLE DE VERSÕES

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## Contenido

1. [Instalação do Git](#instalação-do-git)
2. [Instalação em macOS](#instalação-em-macos)
3. [Instalação em Linux](#instalação-em-linux)
4. [Configure seus datos](#configure-seus-datos)
5. [Initializando Projetos](#initializando-projetos)
6. [Autenticação da conta](#autenticação-da-conta-do-github-via-ssh)

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

### Instalação em macOS
O `Git` para macOS pode ser baixado [aqui](https://sourceforge.net/projects/git-osx-installer/files/).

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/git_for_mac.png)

Após baixá-lo, você deve clicar duas vezes no arquivo para iniciar o instalador. Você só precisa seguir as etapas de instalação até que seja concluída com sucesso e Voilà! Agora você pode abrir o programa para usá-lo.

✅ [DICA] Confirme se a instalação funcionou executando `git --version` no terminal, desta vez você deve obter as informações sobre a versão instalada recentemente.

### Instalação em Linux

Com o terminal aberto, execute os seguintes comandos:

```bash
sudo apt-get update 

sudo apt-get install git
```

Para ter certeza de que a instalação funcionou, execute `git --version` novamente e veja se há informações sobre a versão instalada desta vez.

### Configure seus datos
Com o `Git` instalado em seu computador, tudo o que precisamos fazer é configurá-lo para que possamos usá-lo. Para isso, usaremos os seguintes comandos:


```bash
git config --global user.name <seu login>

git config --global user.email <seu email>
```

✅ [DICA] Lembre-se de substituir `<seu login>` pelo seu nome e `<seu e-mail>` pelo seu e-mail, o mesmo que você usou para criar a sua conta no `GitHub`.


<details>
  <summary> 🤓 LEIA MAIS AQUI </summary>
 Você pode ler mais sobre como configurar seu Git [aqui](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

</details>


## `Init`ializando projetos

Como mencionamos [anteriormente](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BES%5D0.Intro.md), `Git` funciona com um repositório local que está no seu computador. Assim, precisamos mostrar onde queremos armazenar nossos repositórios em nossa máquina.

Vamos começar criando uma pasta onde serão armazenados nossos repositórios que vamos criar para o `WBDS LA Camp`. Para isso, usaremos alguns comandos aprendidos no tutorial de [Bash/Linux]():

```bash
cd ~/Desktop

mkdir WBDSLA_Camp

cd WBDSLA_Camp
```

Agora que estamos dentro da pasta `WBDSLA_Camp`, vamos inicializar um repositório git na raiz da pasta, executando o seguinte comando:

```bash
git init
````

😍 Agora temos tudo pronto para começar a parte [prática](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D2.Pratica.md) deste tutorial.

## Autenticação da conta do GitHub via SSH

Agora vamos autenticar a sua conta e criar uma conexão entre o `Git` da sua máquina e a sua conta no `Github`.

Primeiro vamos checar se você já tem chaves SSH em sua máquina:

```bash
ls -al ~/.ssh
```
Se você receber um erro informando que ~/.ssh não existe, quer dizer que você não tem chaves `SSH`, então precisamos criar uma nova com o comando abaixo. Note que o seu endereço de email deve estar entre aspas.

```bash
ssh-keygen -t rsa -C "<seu email>"
```

Quando for solicitado "Enter file in which to save the key" (Inserir um arquivo no qual deseja salvar a chave), pressione Enter para aceitar o local padrão para salvar o arquivo com a chave. Em seguida, será solicitado "Enter passphrase", e no terminal, digite uma senha segura.

Dentre as mensagens que serão mostradas na tela, uma indicará onde a chave foi salva. Busque algo parecido com:

```
Your public key has been saved in <caminho para arquivo .pub>
```

Agora abra o arquivo contendo a chave, **selecione** todo o seu conteúdo e **copie** para o seu **clipboard**.

```bash
cat <caminho para arquivo onde está a chave> 
```

Pronto! Agora só precisamos adicionar essa chave na sua conta do Github. Para isso, vá nas [configurações da sua conta do github](https://github.com/settings/profile), clique em "SSH and GPG keys" à esquerda e depois em "New SSH key" à direita. Adicione um label à chave (você pode usar algo como "Meu Computador Pessoal") e depois cole a chave no local indicado.

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/paste_ssh.png)

Vamos testar a conexão, só pra ver se deu tudo certo? No terminal, corra:

```bash
ssh -T git@github.com
```

Você deve ver um aviso como este:

```
> The authenticity of host 'github.com (IP ADDRESS)' can't be established.
> RSA key fingerprint is SHA256:nThbg6kXUpJWGl7E1IGOCspRomTxdCARLviKw6E5SY8.
> Are you sure you want to continue connecting (yes/no)?
```

Digite `yes`. Se disser algo como o seguinte, funcionou:

```
Hi <seu login>! You've successfully authenticated, but Github does not provide shell access.
```

😍 Agora temos tudo pronto para começar a parte [prática](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D2.Pratica.md) deste tutorial.
