# *Introdução ao Linux e Bash*

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda, baseado no tutorial [Linux and Bash] (https://github.com/AJVelezRueda/Fundamentos_de_informatica/blob/master/Intro_Linux_Bash/Intro_linux.md) dos autores Ana Julia Velez Rueda e Guillermo Benitez. está sob licença
[Licença Internacional Creative Commons Attribution-ShareAlike 4.0][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## [Linux](#linux)

Como você já deve saber, o Linux é um sistema operacional de código aberto licenciado sob a GNU GPL (General Public License), que nos permite pegar o código, modificá-lo e distribuí-lo livremente. Graças a esse recurso, muitas distribuições foram geradas, entre as quais as mais recomendadas para começar no mundo do Linux são **Ubuntu** ou **Linux Mint**. Neste curso, recomendamos fortemente o uso de uma dessas duas distribuições, pois com outro sistema operacional não poderemos suportá-los.

Uma das principais características do Linux é a organização hierárquica das pastas do sistema, que pode ser pensada como uma árvore, sendo a raiz a base do sistema e a partir daí as pastas se ramificam.
![alt text](https://www.linuxadictos.com/wp-content/uploads/linux-tree-directories.jpg)

A outra característica que distingue o Linux é a existência de dois tipos de usuários, que poderíamos simplesmente dividir em usuários e administradores (ou usuário root ou superusuário). Esses usuários são gerados automaticamente quando configuramos nossa conta e podemos utilizá-los conforme nossa necessidade. Para a maioria das coisas, precisaremos apenas de permissões de usuário, mas para certas tarefas precisaremos de permissões de root. Dito isto, recomendamos fortemente que apenas para tarefas específicas você use o usuário root, para todo o resto você deve usar o usuário comum.

## [Interface de linha de comando (CLI)](#CLI")

* [1. shell](#1_shell)
* [2. Comandos básicos](#2_commands)


### [1. shell](#1_shell)

O shell é a camada mais externa do sistema operacional, é a interface entre o usuário e o sistema operacional. Shells incorporam uma linguagem de programação para controlar processos e arquivos, bem como iniciar e controlar outros programas. O shell gerencia a interação entre o usuário e o sistema operacional solicitando entrada do usuário, interpretando essa entrada para o sistema operacional e manipulando qualquer saída do sistema operacional. O shell é um programa que executamos na forma de um repl(read printable loop), ele interpreta os comandos que o usuário digita e posteriormente os transmite ao sistema e retorna o resultado.

Podemos dizer em geral que os comandos que:
- seguir a seguinte estrutura:

```bash
$ comando [opções] [argumentos]
```

- consiste na própria palavra (comando) e opcionalmente nas opções e/ou argumentos

- determinar o código ou biblioteca a ser usado

- Podem ser modificados em seu comportamento padrão através de opções ou argumentos: embora o comando contenha a instrução que queremos realizar, o argumento indica onde o comando deve operar e a opção solicita a modificação da saída.

Existem argumentos passados ​​para o comando que permitem que ele opere em um objeto/dado, etc., embora possam não existir.

Depois de digitar um comando, a saída obtida é uma informação de texto ou uma ação específica executada pelo computador. Portanto, a chave é escrever o comando correto, um ponto que geralmente é considerado uma desvantagem nesse design de interface do usuário e para o qual geralmente são usadas formas de interface mais atraentes, como GUI (Graphical User Interaction).


### [2. Comandos básicos](#2_commands)

Existem vários shells, sendo o mais comum o bash (chamado de "Bourne Again SHell"). Após a execução, o shell exibe um prompt de comando, que no caso do Bourne shell geralmente é um $ (cifrão), momento em que o shell está pronto para receber um comando. Embora existam muitos comandos que você pode usar com a CLI, eles geralmente se enquadram em duas categorias:

+ Os comandos que tratam dos processos
+ Os comandos que manipulam os arquivos

### **Comandos que manipulam arquivos**

Alguns exemplos desse tipo de comando são:

**_`ls`_**:

Este comando lista todos os arquivos em uma pasta e aceita como parâmetro. O comando padrão excluirá arquivos ocultos. Para mostrar todos os arquivos, você pode adicionar `-a`.

```bash
$ ls -a
```

**_`cd`_**:

mudança de diretório

```bash
$ cd directory_that_I_want_to_go
```

**_`mv`_**:

Renomeie ou mova um arquivo para os arquivos e diretórios no sistema de arquivos do sistema operacional. É importante lembrar que o nome do arquivo e a extensão devem ser escritos.

Se quisermos, por exemplo, renomear um arquivo:


```bash
$ mv resource.extension renomeado_resource.extension
```

Se quisermos mudar o caminho desse arquivo para um novo, devemos inserir o nome do arquivo seguido do caminho:


```bash
$ mv resource.extension home/Directory
```
Já vimos a estrutura dos comandos, mas como saber quais são as opções de um comando? Ou ainda, como sabemos o que um determinado comando faz?
Para esses casos, o Linux nos oferece duas maneiras de obter essas respostas. Uma dessas opções é utilizar outro comando, chamado `man` que mostra, precisamente, o manual do comando em questão:

```bash
homem ls
```

A outra opção para responder a essas perguntas é a opção `--help`.

```bash
ls --help
```

Vamos dar uma olhada rápida em alguns comandos básicos muito úteis, com algumas opções apropriadas.

- Algumas opções úteis do comando `ls` são:

- `-l` para ver os arquivos em forma de listas, com mais alguns detalhes, alguns dos quais são as permissões que o arquivo ou pasta possui, a quem pertence, o peso, a data de modificação, etc.
- `-a` para ver todos os arquivos, mesmo os ocultos
- `-d` apenas para listar os diretórios
- `-h` para ver a saída "legível por humanos". Esta opção só pode ser usada se a opção `-l` for usada. Desta forma poderemos ver o peso em Bytes, Kilobytes, etc.

Essas opções podem ser combinadas. Por exemplo, para ver os arquivos e pastas em um formato de lista, para que todos sejam exibidos e estejam em um formato legível por humanos, você pode escrever:

```bash
ls-lah
```

- Já vimos como mover um arquivo ou pasta, mas você também pode copiá-los, com o comando `cp`, onde você deve usar a opção `-r` se trabalhar com pastas

```bash
cp file destination_folder
cp -r pasta pasta_destino
```

- `toque` para criar um arquivo

```bash
$touch Nome_do_arquivo
```

- Se o que queremos criar é uma pasta, devemos usar o comando `mkdir`

```bash
mkdir nome_da_pasta
```

- Podemos usar um editor de texto embutido chamado `vim` para modificar o arquivo. Você também pode usar um editor gráfico de texto chamado `gedit`.

```bash
vim nome_do_arquivo
gedit Nome_do_arquivo
```

- `rm` para deletar arquivos. Pode ser usado com a opção `-r` para remover uma pasta

```bash
arquivo rm
diretório rm -r
```

- Para ver o que está dentro de um arquivo temos algumas opções.

- Uma delas é usar o mesmo editor de texto que usamos para modificá-lo.
- Outra maneira de exibir um arquivo é usar o comando `cat`:

```bash
arquivo de gato
```
Este comando também é usado para poder ver vários arquivos ao mesmo tempo, concatenando-os um abaixo do outro.

- Outra opção é visualizar o arquivo de forma que não seja exibido por completo na tela, mas leia aos poucos. Para isso, o comando `less` é usado

```bash
menos arquivo
```
Nesse caso, para interromper a leitura, você deve pressionar a tecla **q**.

- Existem comandos que nos mostram o início ou o fim do arquivo, que são `head` e `tail`. Por padrão, eles mostram as primeiras ou últimas 10 linhas, respectivamente, mas com a opção `-n` você pode solicitar o número de linhas que desejar.

```bash
arquivo principal
head -n 5 arquivo
arquivo final
cauda -n 5 arquivo
```

- Uma forma de imprimir texto na tela é utilizando o comando `echo`, onde o argumento, caso não seja uma variável, sempre vem entre aspas.

```bash
echo "Olá mundo!"
```

- Dado um arquivo de texto podemos querer contar quantas palavras, caracteres ou linhas ele possui, para as quais pode ser utilizado o comando `wc`, onde algumas de suas opções são:

- `-l` para saber o número de linhas
- `-m` para saber o número de caracteres
- `-w` para saber o número de palavras

```bash
wc -l arquivo
arquivo wc-m
wc -w arquivo
```

- Para concatenar as ações de diferentes comandos, você pode usar o pipe `|`, que pega a saída ou o resultado das ações do lado esquerdo e o usa como entrada do lado direito.

```bash
gato arquivo1 arquivo2 | banheiro -l
```

Aqui ao invés de mostrar a concatenação de _arquivo1_ e _arquivo2_ na tela isso se torna a entrada do comando `wc` e com a opção `-l` obtém o número de linhas, que é o que acaba sendo mostrado na tela.

- `grep` é um comando muito útil que procura um padrão que passamos para ele em um determinado arquivo:

uma. Basicamente pode ser usado para pesquisar a ocorrência de palavras em um arquivo de texto.

```bash
grep arquivo "palavra"
```
b. Outra opção útil pode ser `-v` que nos permite excluir as linhas que incluem essa palavra que passamos como parâmetro

```bash
grep -v arquivo "palavra"
```


- Já vimos um comando para concatenar arquivos um abaixo do outro, mas também existe a possibilidade de colá-los um ao lado do outro, o que é muito útil quando trabalhamos com arquivos que contêm colunas e queremos concatená-los ao lado de cada um de outros. O comando usado para isso é `colar`, onde uma opção muito útil é `-d` com a qual podemos definir o delimitador entre os arquivos (por padrão é uma tabulação).

```bash
colar arquivo1 arquivo2
cole -d " " arquivo1 arquivo2
```

- Algo que aparece ao usar `ls -a` é uma pasta cujo nome é um ponto `.` e outra que é dois pontos `..`. Esses pontos são úteis, pois representam o diretório atual (no qual estamos) e o superior, respectivamente. Desta forma, se passássemos para uma pasta com o comando `cd`, para voltar para onde estávamos, teríamos que escrever:

```bash
cd ..
```

- Outro comando muito útil é o `find`, com o qual podemos encontrar arquivos de uma determinada pasta pelo nome. A estrutura básica é `find [from_where] -name [file_name]`. Como já vimos, as pastas do Linux são organizadas como ramos de uma árvore, portanto, quando definimos a pasta onde a pesquisa será realizada, ela pesquisará essa pasta e todas as subpastas.

```bash
encontre /home -name "nome"
```

- Muitas vezes nos acontecerá ter que trabalhar com muitos arquivos que compartilham alguma característica, como a extensão, e seria complicado ter que usar o mesmo comando para cada arquivo. Ou também pode acontecer que queiramos ver todos os arquivos de uma determinada extensão ao mesmo tempo, mas, novamente, seria complicado usar `cat` e escrever o nome de cada arquivo. Para esses casos, utiliza-se um caractere que representa um curinga ou curinga, entendido como "qualquer caractere". Por exemplo, se temos 20 arquivos com extensão .txt e queremos concatená-los, podemos fazer:

```bash
gato *.txt
```
- Outro comando útil na manipulação de texto é `sort`, que é usado para classificar um arquivo, organizando os registros em uma ordem específica. A menos que especificado de outra forma, o comando `sort` classifica o arquivo assumindo que o conteúdo é ASCII.
```bash
classificar arquivo.txt
```

uma. Uma opção útil é `-o` que nos permite redirecionar a saída para um arquivo:

```bash
sort -o saída.txt arquivo.txt
```

b. Outra opção útil é `-k`, que nos permite classificar com base em uma coluna específica.
```bash
sort -k 4 arquivo.txt
```

c. Com a opção `-r` também podemos ordenar o arquivo ao contrário (decrescente por padrão):
```bash
classificar -r arquivo.txt
```

## [Script](#script)

Como você pode ver, todos esses comandos são muito úteis, mas até agora só vimos como executá-los em um terminal, um comando por vez. O verdadeiro potencial desses comandos é visto quando eles estão contidos em um script, ou seja, em um arquivo de texto. A questão aqui é, como o sistema reconhece que este arquivo deve ser executado? No linux, todos os arquivos de texto simples são exatamente isso, então a extensão que colocamos neles não influencia, pois é mais para o uso da pessoa, para o qual você tem que indicar de alguma forma que determinado arquivo é um script contendo comandos para ser executado. Para isso precisamos de duas coisas:

- Antes de mais nada, na primeira linha devemos escrever `#!`, que é conhecido como _shebang_, seguido do caminho do shell (neste caso, bash). Em sistemas Linux é: `#!/bin/bash`
- Em segundo lugar, o arquivo deve ter permissões de execução

Como vimos hoje, usando `ls -l` uma das descrições que aparecem são as permissões, que são:

- ler (`r`)
- escreva (`w`)
- execute(`x`)

Para modificar as permissões de um arquivo, use o comando `chmod` cujas opções são:

- +r, +w ou +x para dar permissões de leitura, gravação ou execução para um arquivo, respectivamente
- -r, -w ou -x para removê-los.

Essas opções, como com `ls`, podem ser combinadas, então se eu quiser dar permissões completas para um arquivo eu poderia fazer:

```bash
arquivo chmod +rwx
```

Finalmente, se quisermos executar um arquivo que tenha permissões de execução, temos duas opções:

- Escreva o caminho completo (absoluto) do arquivo
- Se estivermos na pasta onde o arquivo está localizado, podemos usar o `.`

```bash
/home/ana/scripts/script_name.sh #caminho absoluto
./script_name.sh #caminho relativo
```