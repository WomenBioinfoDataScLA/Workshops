### CONTROL DE VERSIONES

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## Mãos no terminal 💻

Podemos fazer uma sincronização de saída do repositório local para o remoto (origem), fazendo `git push`. Este comando envia todos os commits gerados localmente que não foram confirmados anteriormente.

Também podemos extrair alterações do repositório remoto usando o comando `git pull`.

🥳 Agora que sabemos como compartilhar nossas contribuições com o mundo, vamos criar nosso primeiro commit!

Vamos precisar de um repositório local e um repositório remoto, um dos quais será a "réplica" do outro (`clones`). A partir do repositório local, faremos alterações, que serão adicionadas ao repositório remoto.

>
> 🏅 Desafio II: Crie um repositório no GitHub com o nome `WBDS_LA_Camp`
>

<img src="./assets/%5BES%5DCONTROL_DE_VERSIONES_create_a_repo.png" style="width: 500px">

A primeira vez que baixamos um repositório localmente, diz-se que ele está `clonado` no nosso computador. Ou seja, é feita uma cópia local de tudo que está na pasta remota (no computador de Don GitHub): arquivos e metadados.

>
> 🏅 Desafío III: Clone seu repositório `WBDS_LA_Camp` no seu computador
>

Para isso, copie o link que o GitHub gera para clonar o repositório:

<img src="./assets/%5BES%5DCONTROL_DE_VERSIONES_clone.png" style="width: 500px">

E digite no seu terminal:
```bash
#git clone <enlace a tu repo>

git clone git@github.com:AJVelezRueda/WBDSLA_Camp.git
```

📑 [**NOTA**]: Se precisar de mais informações, consulte a documentação no site do [github](https://docs.github.com/en/get-started/getting-started-with-git/about-remote-repositories#cloning-with-ssh-urls).

Agora que temos o clone do nosso repositório remoto, vamos começar a trabalhar no projeto! Crie um arquivo dentro da pasta `WBDS_LA_Camp` do seu computador:

```bash 
## Primeiro entramos na pasta que clonamos
## Lembre-se de passar o caminho da sua pasta para o comando cd
cd WBDSLA_Camp

## Criamos um arquivo README.md
touch README.md
```

>
> 🏅 Desafio IV: Adicione essa alteração ao índice e envie as alterações para seu repositório remoto
>

📑 [**NOTA**]: Quando queremos empurrar tudo o que temos até agora, adicionamos o argumento `.` ao comando `git add`, desta forma, ao correr `git add .` adicionaremos todas as alterações que fizemos até agora ao repositório. Quando queremos documentar permanentemente as alterações no repositório, fazemos um `git commit`. É importante que esse `commit` acompanhe uma mensagem descrevendo a alteração realizada e para isso utilizamos o parâmetro `-m` seguido da mensagem entre aspas. 

Para enviar todas os `commits` locais para o repositório remoto:

```
git push origin main

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
> 🏅 Desafio VI: Digite o comando `git status` e descubra se o Git se distraiu ou realmente adicionou as alterações ao `index`
>

💡 Para pensar: Que passo precisaríamos para confirmar as mudanças? Exatamente, você pode confirmá-los agora!

Antes de confirmar nossas alterações, vamos adicionar alguns detalhes à nossa documentação:

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

Agora adicione o seguinte texto: `O WBDS LA Camp é um curso de treinamento intensivo gratuito para estudantes de graduação e pós-graduação que têm interesse em aprender bioinformática e ciência de dados do zero.`

>
> 🏅 Desafio IX: Digite o comando `git diff`. O quê os símbolos `+` e `-` marcam? Onde estão as mudanças que descartamos? Corra `git stash apply` e observe como ficou o arquivo `README.md` agora.
>
>
> 🏅 Desafío X: Use os comandos apropriados para fazer com que seu repositório remoto fique assim (mas com o seu nome):

```
### Repositório de teste do WBDS LA Camp

**Autora**: Ana Julia Velez Rueda

## Sobre o WBDS LA Camp
O WBDS LA Camp é um curso de treinamento intensivo gratuito para estudantes de graduação e pós-graduação que têm interesse em aprender bioinformática e ciência de dados do zero.

```
Vamos adicionar mais uma seção à nossa documentação que contenha informações sobre nosso trabalho:

```
## Sobre mim
Meu nome é Ana Julia Velez Rueda, sou doutora em bioinformática, formada pela Universidade Nacional de Quilmes na Argentina.
```

Que vocês acham disso? Nossa documentação está melhor agora? Hmmm... bem, talvez não e talvez seja melhor parar por aqui, certo?

>
> 🏅 Desafio XI: Para dizer adeus, descarte as alterações com `git checkout README.md` 
>

💡 Para pensar: Como ficou o arquivo `README.md` agora? As alterações podem ser recuperadas?

👀 Descubra o que os comandos `git stash show` e `git stash list` retornam
