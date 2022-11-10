### CONTROLE DE VERSÕES

🚨 Este material foi criado pela Dra. Ana Julia Velez Rueda e Dra. Liliane Conteville
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].

[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

##  Introdução

[O que é um sistema de controle de versões?](#version-control)
Um sistema de controle de versões é uma ferramenta que acompanha automaticamente as alterações em um documento ou diretório, criando efetivamente diferentes versões de nossos arquivos. Os sistemas de controle de versões começam com uma versão básica do documento e, em seguida, registram as alterações feitas em cada etapa do processo. Existem vários programas que nos permitem realizar o controle de versões de nossos projetos, mas neste tutorial veremos como usar o [Git](https://git-scm.com/downloads), um dos mais populares atualmente.

Para entender melhor o que o Git faz, você pode pensar nele como um artista tentando criar um filme [`stop motion`](https://pt.wikipedia.org/wiki/Stop_motion). Como você sabe, a construção desses filmes exige muitas fotos que registram detalhadamente os movimentos dos personagens. Vamos pensar então que o Git tira fotos instantâneos das mudanças durante a vida de um projeto para construir seu filme. Você poderia então pensar no projeto como um vídeo: um que você pode voltar no documento inicial e repetir cada estado ou mudança que você fez, até finalmente chegar à sua versão mais recente.

Cada registro dessas mudanças é chamado de `commit` e mantém metadados úteis (tempo e referências de autor, etc) sobre elas. O histórico completo de `commits` para um projeto específico e seus metadados formam um `repositório`.

![Git commits img](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/%5BPT%5DCONTROL_DE_VERSIONES_schema1.png)

Continuando com a analogia do vídeo, podemos pensar em cada `commit` como um quadro em nosso vídeo, sendo este todo o histórico de alterações de um arquivo ou diretório. Mas antes de tirar a foto, não seria uma má ideia preparar nossos personagens e apontar a câmera corretamente para que ela seja capaz de capturar essas mudanças, né? Então, quando fazemos `git add` o que fazemos é especificar quais movimentos de caracteres serão gravados na próxima foto (colocando as coisas na área `index` do Git), como gritar `cheeese` para que ninguém saia mal na foto. E então quando fazemos `git commit` dizemos ao Git que é hora de tirar uma foto e registrar de forma permanentemente os movimentos ou mudanças de nossos personagens.

![Git areas](https://raw.githubusercontent.com/WomenBioinfoDataScLA/Workshops/master/Git_%26GitHub/assets/%5BES%5DCONTROL_DE_VERSIONES_git_areas.png)

Resumindo, o Git tem uma área de teste `index` à qual podemos adicionar itens com `git add`. As alterações não são documentadas permanentemente até que as confirmemos com `git commit`. As mudanças são gerenciadas como uma unidade, gerando um `commit`, e são registradas fazendo `git commit`. Isso nos permite enviar grupos específicos de arquivos ao mesmo tempo ou separadamente, dependendo do que queremos.

📑 [**NOTA**]: É muito importante especificar as alterações feitas em cada `commit`, isso nos ajudará a rastrear as alterações quando quisermos voltar atrás.

Agora, o que acontece se alguma das alterações que fizemos não funcionar para nós? Bem, como acontece na vida real, as coisas podem "dar errado" e precisaremos recomeçar. Mas é claro que não vamos começar do zero se já estamos trabalhando no projeto há muito tempo... quer dizer, no filme! É por isso que pode ser bom para nós salvar as fotos que podem ser úteis no futuro em uma caixinha que chamaremos de `stash`, fazendo `git stash`. Você sempre pode reutilizar o que deixou `stashed` fazendo `git stash apply`.

## Git ao infinito e além...

O Git funciona com um repositório local que está no seu computador, onde você vai adicionar seus commits e um repositório remoto (na nuvem) no qual você pode fazer upload de seus commits, compartilhá-los com outra pessoa ou baixar os commits que alguém carregou.

Existem vários serviços para armazenar repositórios remotamente:

- [Github](https://github.com) 
- [Bitbucket](https://bitbucket.com)
- [Gitlab](https://gitlab.com/)

Para usá-los você deve se registrar e criar uma conta.

>
>🏅 Desafio I: Crie sua conta no [GitHub](https://github.com/). Tenha seu login e senha à mão, você vai precisar!
>
>🏅 Desafio II: Configure e instale seu [Git](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D1.Git_and_GitHub_setup.md) em seu computador!
>

Uma vez que um repositório é criado localmente, ele pode ser continuamente sincronizado com um repositório remoto análogo ao criado localmente. Essa sincronização geralmente é feita a partir do repositório local usando os comandos:
- `git clone`: para clonar ou baixar um repositório remoto para o nosso computador. Este comando é usado apenas uma vez, uma vez baixado pode ser atualizado usando os comandos detalhados abaixo.

- `git push`: para enviar os `commits` feitos localmente até agora

- `git pull`: para baixar as alterações que possam existir no repositório remoto (`origin`).

Mas já que `melhor que falar é fazer`, vamos ao que interessa com alguns exercícios [práticos](https://github.com/WomenBioinfoDataScLA/Workshops/blob/master/Git_%26GitHub/%5BPT%5D2.Pratica.md)!