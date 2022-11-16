### CONTROLE DE VERSÕES

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## Mãos no terminal 💻

🥳 Agora que sabemos como compartilhar nossas contribuições com o mundo, vamos criar nosso primeiro commit!

Vamos precisar de um repositório local e um repositório remoto, um dos quais será a "réplica" do outro (`clones`). A partir do repositório local, faremos alterações que serão adicionadas ao repositório remoto.

>
> 🏅 Desafio III: Crie um repositório no GitHub com o nome `WBDS_LA_Camp`
>

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/%5BES%5DCONTROL_DE_VERSIONES_create_a_repo.png)

A primeira vez que baixamos um repositório localmente, diz-se que ele está `clonado` no nosso computador. Ou seja, é feita uma cópia local de tudo que está na pasta remota (no computador de Don GitHub): arquivos e metadados.

>
> 🏅 Desafio IV: Clone seu repositório `WBDS_LA_Camp` no seu computador
>

Para isso, copie o link que o GitHub gera para clonar o repositório:

![](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/%5BES%5DCONTROL_DE_VERSIONES_clone.png)

E digite no seu terminal:
```bash
#git clone <link do seu repositório>

git clone git@github.com:<seu login>/WBDS_LA_Camp.git
```

Agora que temos o clone do nosso repositório remoto, vamos começar a trabalhar no projeto! Crie um arquivo dentro da pasta `WBDS_LA_Camp` em seu computador:

```bash 
## Primeiro entramos na pasta que clonamos
## Lembre-se de passar o caminho da sua pasta para o comando cd
cd WBDS_LA_Camp

## Criamos um arquivo README.md
touch README.md
```

Vamos adicionar essas alterações ao índice e enviar as alterações para seu repositório remoto!

[Lembre-se](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D0.Intro.md) que para registrar as alterações, devemos primeiro adicioná-las. Quando quisermos adicionar todas as alterações que fizemos até agora podemos usar o argumento `.` para o comando `git add`, desta forma, quando fizermos `git add .` adicionaremos todos os arquivos gerados até agora e todas as outras alterações que fizemos até agora no repositório.

```bash
git add .
```

Uma vez que as alterações foram adicionadas, devemos usar o comando `git commit` para gravar permanentemente as alterações feitas no repositório. Este `commit` deve ser acompanhado de uma mensagem que descreva as características da alteração realizada, que podemos definir usando o parâmetro `-m` seguido da mensagem entre aspas:

```bash
git commit -m "README foi criado"
```

Agora podemos sincronizar o repositório remoto (origem) com o local, fazendo `git push`. Como vimos na [teoria](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D0.Intro.md), este comando envia todos os commits gerados localmente e que não foram enviados anteriormente.

Se tudo correr bem, você verá a seguinte mensagem no seu terminal:

```
Enumerating objects: 3, done.
Counting objects: 100% (3/3), done.
Writing objects: 100% (3/3), 218 bytes | 218.00 KiB/s, done.
Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
To https://github.com/<seu login>/WBDS_LA_Camp.git
 * [new branch]      main -> main
```

💡 Para pensar: De que forma você verificaria se as alterações foram carregadas no repositório remoto?

Agora vamos fazer algumas alterações no arquivo `README.md`. Adicione o seguinte texto ao arquivo e salve:

```
### Repositório de teste do WBDS LA Camp

**Autor/a/e: <seu nome>
```


Vamos então adicionar as alterações ao espaço `index`, mas desta vez, verificando cada uma das alterações, para ter certeza de que não cometemos nenhum erro nas alterações que adicionamos:

```bash
git add -p
```

✅ [NOTA] Pode ser que após o comando acima você receba uma mensagem de erro se no seu computador não tiver o Perl instalado. Para instalar, siga o comando que o terminal recomendar. Após instalar o Perl, teste rodar o comando acima novamente.

Vamos ver o que o Git nos diz:
   
```bash
diff --git a/README.md b/README.md
index e69de29..092eda1 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,3 @@
+### Repositório de teste do WBDS LA Camp
+
+**Autora: Ana Julia Velez Rueda
\ No newline at end of file
Stage this hunk [y,n,q,a,d,e,?]? 
```

🙈 Opa! Precisávamos fechar os asteriscos para que nosso texto `**Autora` ficasse em negrito. Vamos dizer ao git que não queremos adicionar as alterações usando a flag `n` e apertando enter.

```bash
diff --git a/README.md b/README.md
index e69de29..092eda1 100644
--- a/README.md
+++ b/README.md
@@ -0,0 +1,3 @@
+### Repositório de teste do WBDS LA Camp
+
+**Autora: Ana Julia Velez Rueda
\ No newline at end of file
Stage this hunk [y,n,q,a,d,e,?]? n

```

>
> 🏅 Desafio V: Adicione os asteriscos de fechamento antes dos dois pontos `:` e adicione novamente as alterações com `git add -p`, mas desta vez usando a flag `y`
>

🤔 Hmmm... Não, não obtive resultados no meu terminal, e você? Será que nada aconteceu?

>
> 🏅 Desafio VI: Digite o comando `git status` e descubra se o Git se distraiu ou realmente adicionou as alterações ao `index`. Em seguida, faça um `commit` e um `push`.
>

Agora vamos adicionar alguns detalhes à nossa documentação:

>
> 🏅 Desafio VII: Adicione o seguinte texto `Lorem ipsum é o texto que é comumente usado em design gráfico em demonstrações de tipografia ou rascunhos para testar o design visual antes de inserir o texto fino.` e depois de salvar digite o comando `git diff` no terminal.
>

💡 Para pensar: Para que serve este comando?

Desculpe, acho que me arrependi 🙈! Talvez não tenha sido uma boa ideia documentar nosso repositório usando um texto genérico... vamos tentar salvar as alterações para mais tarde:

>
> 🏅 Desafio VIII: Digite o comando `git stash`
>

💡 Para pensar: Para que serve este comando? Como ficou o arquivo `README.md` agora?

👀 Descubra o que os comandos `git stash show` e `git stash list` fazem

Agora adicione o seguinte texto no README: `O WBDS LA Camp é um curso de treinamento intensivo gratuito para estudantes de graduação e pós-graduação que têm interesse em aprender bioinformática e ciência de dados do zero.`

>
> 🏅 Desafio IX: Digite o comando `git diff`. O quê os símbolos `+` e `-` marcam? Onde estão as mudanças que descartamos?
> 

Adicione as alterações ao `index`, faça um novo `commit` e corra `git stash apply`. Veja como está o arquivo `README.md` agora.

>
> 🏅 Desafio X: Use os comandos apropriados para fazer com que seu repositório remoto fique assim (mas com o seu nome):
>

```
### Repositório de teste do WBDS LA Camp

**Autora**: Ana Julia Velez Rueda

## Sobre o WBDS LA Camp
O WBDS LA Camp é um curso de treinamento intensivo gratuito para estudantes de graduação e pós-graduação que têm interesse em aprender bioinformática e ciência de dados do zero.
```

>
> Descarte as alterações com `git restore --staged README.md` e `git checkout README.md`
>

>
> 🏅 Desafio XI: Adicione mais uma seção à nossa documentação que contenha informações sobre nosso trabalho, adicione essa alteração ao `index`, faça um novo `commit` e `push`.
>

```
## Sobre mim
Meu nome é Ana Julia Velez Rueda, sou doutora em bioinformática, formada pela Universidade Nacional de Quilmes na Argentina.
```

💡 Para pensar: Como ficou o arquivo `README.md` agora? As alterações podem ser recuperadas?

👀 Descubra o que os comandos `git stash show` e `git stash list` retornam

Tem mais um detalhe! 🙈

Haverão situações em que você vai preferir ignorar arquivos ou diretórios após o `commit`. Para isso, um arquivo chamado `.gitignore` deve ser criado e dentro dele devem ser adicionados os nomes ou padrões dos arquivos/diretórios a serem ignorados.

>
> 🏅 Desafio X: Gere um arquivo `lixo.txt` e ignore-o usando um arquivo `.gitignore`
>
