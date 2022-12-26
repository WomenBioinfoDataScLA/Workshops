# La vida en tres dimensiones: introducción a la Bioinformática Estrutural

##### Autora: Dra. Ana Julia Velez Rueda
>
> Material baseado no material de [Introducción a la Bioinformática de AJVeleRueda](https://github.com/AJVelezRueda/Introduccion_a_la_Bioinformatica)
>
> **LICENÇA**: Este trabalho está licenciado sob uma
[Licença Internacional Creative Commons Attribution-ShareAlike 4.0][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

## origami molecular

A Bioinformática Estrutural se concentra principalmente em explorar a relação entre a estrutura e a função de macromoléculas biológicas e promove o desenvolvimento de ferramentas computacionais para elucidar as bases estruturais da função biológica. Como entidades dinâmicas, a relação estrutura-função em macromoléculas biológicas, como proteínas ou ácidos nucléicos, mais especificamente, é formulada como uma relação estrutura-dinâmica-função. É por isso que esta disciplina é fundamental para a compreensão de vários tópicos que vão desde o design racional de medicamentos até a regulação da expressão gênica. Esta área da bioinformática só pode contribuir do ponto de vista conceitual, aumentando nosso conhecimento sobre as bases mecanicistas de um determinado sistema, mas a Bioinformática Estrutural também está intimamente ligada aos desenvolvimentos Biotecnológicos, Farmacêuticos e Medicinais.

Uma aproximação a esse grande mundo da bioinformática estrutural pode ser feita a partir do estudo particular, mas muito amplo, das proteínas.

## Uma solução no seu bolso

As proteínas são as unidades funcionais, estruturais e evolutivas das células. Sabemos pelos primeiros trabalhos realizados por Anfinsen que **existe uma forte relação entre estrutura e função**, ou seja, que a atividade biológica de uma proteína depende do arranjo espacial de sua cadeia polipeptídica. Um grande número de proteínas requer uma certa estrutura terciária (como chamamos sua estrutura tridimensional) para cumprir suas funções biológicas. Quatro níveis diferentes são definidos, conhecidos como estrutura primária, secundária, terciária e quaternária, e cada um deles é constituído a partir do anterior.

Hoje sabemos que, embora as proteínas possam adotar uma estrutura definida, elas não o são e que existem muitos enovelamentos possíveis que explicam sua funcionalidade. Em um dos primeiros trabalhos que estudaram a relação entre estrutura e função das proteínas, Pauling e Mirsky definiram o estado nativo das proteínas como um dobramento ou conformação característica, que confere às proteínas sua função, e cuja perda chamou de desnaturação (Mirsky e Pauling, 1936). .

Em sua superfície, as proteínas são moldadas em numerosas cavidades e protuberâncias que criam microambientes exclusivos para ligação de ligantes ou catálise. E como as proteínas se movem, as cavidades também têm topologias dinâmicas, com características que também podem mudar de uma conformação para outra. A dinâmica dessas cavidades é crítica para entender a função da proteína.


Hoje sabemos que existem muitos enovelamentos possíveis que explicam a funcionalidade da proteína, ou seja, que o estado nativo não é único, mas que atualmente é descrito como um conjunto de conformações em equilíbrio dinâmico. A distribuição relativa dos diferentes confôrmeros pode variar devido a mudanças no ambiente da proteína (presença de ligantes, flutuações de pH, modificações pós-traducionais, etc.) (Kumar et al., 2000; Rueda et al., 2018). A magnitude da diversidade conformacional observada nas proteínas pode variar desde flutuações nas cadeias laterais até rearranjos globais da estrutura terciária (Böttcher et al., 2000; Koshland, 1998;Plapp, 2010). Mesmo pequenas mudanças conformacionais geram diferenças nas estruturas das proteínas (cavidades e túneis) que são descritas na estrutura tridimensional, tendo efeitos em sua função.

Mas é claro que saber em que consiste a estrutura de uma proteína de maneira computacional apresenta certas complexidades. Eles existem em formas de representar a informação tridimensional de uma molécula no computador. Existe uma infinidade de aplicativos gratuitos que nos permitem visualizar desde a estrutura de uma pequena molécula até uma proteína, e que também nos permitem explorar com mais profundidade as subestruturas das proteínas. Vamos começar com uma exploração de uma estrutura tridimensional de uma molécula simples:

>
> 🧗🏻‍♀️ Desafio I: Vamos explorar como passamos de um plano, uma sequência ou um desenho para uma estrutura tridimensional. Abra a ferramenta [MolView](https://molview.org/) em seu navegador e mova a molécula visualizada na ferramenta
>
> 🧗🏻‍♀️Desafio II: agora digite `N-Butan` no buscador para ver o que a ferramenta te atrai, depois tente `1-butene` e `1-Butyne`, que diferenças você vê entre essas moléculas em sua disposição no espaço? Como você imagina que a informação deve ser armazenada em um computador para poder ir do plano para algo tridimensional?
>

Como você deve se lembrar na geometria, um sistema de coordenadas é um sistema de referência que usa números para determinar a posição de um objeto ou ponto no espaço. Para armazenar informações estruturais sobre uma molécula de maneira computacional, devemos recorrer a esse conhecimento básico de geometria para fornecer ao computador uma maneira fácil de interpretar os dados espacialmente.

Como você deve ter notado, ao utilizarmos o plano, na tela à esquerda da ferramenta, obtemos duas coordenadas para descrever a posição de cada espaço. Porém, quando passamos para uma figura tridimensional, apenas duas coordenadas dificultam a determinação da localização do ponto (ou neste caso, átomo) no espaço; e torna-se necessário mover para um eixo de 3 coordenadas. Existe um tipo de arquivo muito comum em bioinformática, que é comumente usado para armazenar esse tipo de informação geométrica, que é conhecido como arquivo `PDB` e no qual muitas ferramentas começam a realizar as diferentes análises estruturais que podemos vai ver abaixo. .


Existem muitas maneiras de estudar a relação entre estrutura e função da proteína e as implicações dessa relação, portanto, nesta nota, tentaremos resumir alguns aspectos básicos da análise.

## Um problema estrutural

Mas como melhor que decir es hacer, vamos nos enforcar agora em um sistema concreto para estudar suas características estruturais. A ubiquitina (ubiquitina em inglês) é uma proteína pequeña que foi encontrada em todas as células eucariotas (de allí viene seu nome: ubiquo significa onipresente). Esta proteína é a encargada da marcación química das proteínas que não são necessárias, para que sejam reconhecidas e destruídas por outras proteínas.

>**PARA PENSAR** 🤔:Por que uma célula quer destruir suas próprias proteínas?

Descubra um pouco mais sobre a estrutura terciária da ubiquitina. Para isso, entraremos no site do Banco de Dados de Proteínas (Protein Data Bank, o PDB) (https://www.rcsb.org/). Esta página web corresponde a uma das bases de dados mais utilizadas na bioinformática, onde se encontram armazenadas todas as estruturas de macromoléculas biológicas obtidas até o momento. As estruturas são armazenadas em forma de arquivos que contêm as coordenadas no espaço, em ejes imaginários X, Z e Y, de todos os átomos de uma molécula dada. Estas coordenadas podem ser interpretadas por alguns programas gráficos para mostrar de forma tridimensional como se vería, por exemplo, uma proteína em uma célula ou em uma membrana.

No quadro de busca do PDB, inserimos o código identificador da ubiquitina humana: 1UBQ.

![PBD_database](pdb_home_page.png)


A página correspondente ao 1UBQ contém todas as informações disponíveis sobre o experimento que determina a estrutura terciária da ubiquitina humana. Inclui informações adicionais sobre a proteína extraída de outras bases de dados, que permite saber mais sobre sua sequência, outras proteínas semelhantes, etc. A primeira tela que vemos é um resumo da informação estrutural (Structure Summary).

>**PARA PENSAR** 🤔:¿Qué información nos provee esta página?
>
>**PARA PENSAR** 🤔:Como se determina a estrutura desta proteína?
>A la izquierda vemos uma representação da estrutura de ubiquitina. O que significa las cintas, las flechas y las regiones angostas?
>
>**PARA PENSAR** 🤔:¿Representa esa imagen a la realidad del sistema biológico?
>
>**PARA PENSAR** 🤔:La estructura 1UBQ fue “refinada a una resolución de 1.8 Angstroms”. Este é o erro associado ao experimento: enquanto maior é a resolução, menor é a certeza de determinar a posição de cada átomo.
>


Exploramos a guia de visualização tridimensional (3D View). Com o mouse podemos girar, aproximar e deslocar a molécula. O menu da direita nos permite alterar o modo de representação.
Na tela principal, vemos uma representação da estrutura ubiquitina.

![PBD_database](pdb_protein_page.png)


>**PARA PENSAR** 🤔: O que significan las cintas, las flechas y las regiones angostas?
>**PARA PENSAR** 🤔:¿Qué diferenças y similitudes notamos respeito à representação inicial?
>**PARA PENSAR** 🤔: No menu da izquierda há opções de diferentes tipos de representação e formas de colorir a estrutura tridimensional. O que poderia ser útil para visualizar o mesmo de maneiras distintas?


Voltando à página principal da estrutura, podemos usar o menu direito para baixar um arquivo (Download de arquivos) com as coordenadas espaciais de cada átomo desta proteína. No pequeno menu que se abre, elegiremos baixar a estrutura da proteína no formato PDB (formato PDB), o padrão para estruturas de biomoléculas.

![PBD_database](pdb_protein_page.png)

>**PARA PENSAR** 🤔:¿Qué información esperaría encontrar como resultado un experimento destinado a determinar a estrutura terciaria de uma molécula biológica?

Podemos explorar o conteúdo do arquivo que acabou de baixar se o observarmos com um editor de texto. Fazendo clique com o botão direito do mouse sobre o arquivo baixado, usamos a opção Abrir e selecionamos o Bloco de Notas ou outro editor de texto.

>**PARA PENSAR** 🤔: ¿En qué consiste un archivo PDB?
>
>**PARA PENSAR** 🤔:Desplacémonos por el archivo hasta find las líneas que comienzan con la palabra ATOM. Que tipo de informação traz esta seção?
>
>**PARA PENSAR** 🤔:¿Podíamos extrair deste arquivo informações sobre a estrutura primária da proteína em questão? Como se apresenta esta informação e o que significa a representação? Desde o ponto de vista computacional: de que tipo de dados se trata esta informação?
>
>**PARA PENSAR** 🤔: Você acha que o formato PDB é útil para apresentar os resultados do experimento?
>
>**PARA PENSAR** 🤔: Observamos que la información respeta cierta estructura interna. Quais são os benefícios e as limitações de impor uma estrutura para comunicar os resultados de um experimento?
>
>Hemos visto que las proteínas tienen estructura tridimensional y hemos podido observar algumas características de las mismas. Será igual com a ingestão de nucléicos?
Rosalind Franklin é uma ciência muito relevante, que fez menos reconhecimento do merecido. Contamos sobre os procedimentos que puso Rosalind.
>



## Uma solução no bolso

Por suposto, é difícil entender o que consiste a estrutura de uma molécula simplesmente olhando o conteúdo de um arquivo PDB. Você sabe que existem formas de representar a informação tridimensional no computador. Existe uma multiplicidade de aplicativos gratuitos que nos permitem visualizar a estrutura de uma proteína e que nos permitem também explorar as subestruturas proteicas mais profundamente.

Como dijimos interiormente, as proteínas são as unidades funcionais, estruturais e evolutivas das células. Sabemos desde os primeiros trabalhos realizados por Anfinsen, que **existem uma forte relação entre estrutura e função**, es decir que a atividade biológica de uma proteína depende da disposição espacial de sua cadeia polipeptídica.

Las proteínas no son un ovillo, sino que la mayoría adopta una estrutura dada en el espacio. Se definem quatro níveis distintos, conhecidos como estrutura primária, secundária, terciária e cuaternária, e cada um deles se constitui a partir do anterior. Hoje em dia sabemos que ainda adotamos uma estrutura definida, as proteínas não estão quietas e que existem muitas possibilidades que explicam sua funcionalidade.

Em sua superfície, as proteínas têm forma de cavidades e protuberâncias numerosas que criam microambientes únicos para a união de ligandos ou a catálise. E como as proteínas se mudam, as cavidades também têm topologias dinâmicas, com características que também podem mudar de uma conformação para outra.

A dinâmica destas cavidades é fundamental para compreender a função das proteínas.
Existe uma grande variedade de softwares capazes de prever a localização dessas subestruturas proteicas e suas propriedades. E esta informação combinada com a informação evolutiva y sequencial, pode ser de grande utilidade nos campos de aplicação dos mais diversos, desde o design de fármacos, até o desenvolvimento de alimentos.

¡Vamos adentrarnos na anatomia das proteínas!


## O futuro chegou 📍

O estudo estrutural de proteínas nos proporciona múltiplos campos de aplicação, por exemplo um dos mais explorados atualmente é o desenho racional de fármacos. Conhecendo-se a base biológica de uma doença, ou seja, conhecendo-se as moléculas envolvidas, é possível projetar drogas que interajam com a molécula responsável, de forma que esta a modifique e modifique o quadro patológico. Em outras palavras, o design racional de medicamentos consiste na aplicação do conhecimento biológico e estrutural dos receptores (proteínas envolvidas em uma determinada doença) para projetar moléculas que interajam apenas com eles... tanto quanto possível!

Um estudo de caso interessante é que [EGFR](https://www.uniprot.org/uniprotkb/P00533/entry) é um dos principais marcadores de câncer de pulmão. Que apresenta características diferenciais entre as conformações ativas e inativas que tentaremos explorar computacionalmente.

Existe uma grande variedade de softwares capazes de prever a localização dessas subestruturas proteicas e suas propriedades. E esta informação, combinada com informação evolutiva e sequencial, pode ser muito útil para entender a natureza da função da proteína. Todas essas informações são combinadas de forma simples de visualizar e processar no [CaviDB](https://cavidb.org). [CaviDB](https://cavidb.org), um banco de dados on-line gratuito que fornece informações sobre cavidades de proteínas e suas propriedades, o que também permite estudar a diversidade conformacional de cavidades de proteínas.

Vamos começar estudando essa proteína, analisando as diferenças e semelhanças de duas conformações ativas e inativas da proteína:

         - A estrutura 1M14 corresponde a um conformador ativo: ou seja, uma estrutura com atividade

         - A estrutura 3W32 corresponde a uma conformação inativa.

>
>🧗🏻‍♀️DESAFIO II: Compare o sítio ativo de ambos os confôrmeros (posição 837), bem como os tamanhos das bolsas. O que você observa?
>
>🧗🏻‍♀️DESAFIO III: Pesquise mais sobre a proteína usando o banco de dados [Uniprot](https://www.uniprot.org/) e anote os sites biologicamente relevantes
>
> 🧗🏻‍♀️DESAFIO IV: Algum sítio de relevância biológica coincide com outras cavidades previstas nas conformações ativa e inativa?
>
> 💡 Investigar: Investigar em que consiste o docking, em que ideias se baseia o seu funcionamento Como poderia este método ser utilizado para tratar o cancro?
>


## Sobre as cascas da evolução

As albúminas são as proteínas químicas mais abundantes nos mamíferos e têm a principal propriedade de unir e transportar muitos compostos endógenos e exógenos, em sua maioria hidrofóbicos. A proteína é globular e é composta por três domínios homólogos (I, II e III), cada um dos cuales contém dois subdomínios semelhantes (A e B). As albúminas se conservam ao longo dos vertebrados e os membros desta família mostram uma grande diversidade estrutural, apesar da conservação da sequência global. Es decir que, embora sua função biológica não seja enzimática, se provou sua capacidade catalítica para várias reações. Curiosamente, embora todas as albúminas de mamíferos compartilhem a função principal de transporte de ligandos através do sangue, diferem no tipo de reações que podem catalisar. Além disso, a capacidade catalítica das albúminas em solventes orgânicos las convierte em candidatos para econômicos para manipulação biotecnológica para seu aproveitamento em processos industriais.

Em particular, a albumina do sangue humano (HSA) é a proteína principal no plasma, é um dos múltiplos ligantes e recentemente foi descrita como um transportador de fármacos muito importante. Esta proteína monocatenaria tem vários locais de união de fármacos e injeções graciosas, sem embargo, a maioria dos fse unen a los llamados Sitios I (Met 1 a Asn 111) e II (de Gln 196 a Pro 303). Em particular, os resíduos Lys 199, Arg 410, Tyr 411, Cys 34 e Lys 195 de HSA são descritos como alguns dos mais importantes, não só para a união de ligandos sino também para as atividades catalíticas descritas para esta proteína.


Se sabe que a capacidade catalítica de uma cavidade suele se associa a algumas características estruturais das mesmas, como a presença de aminoácidos ativados (com pKas anormais) em ambientes majoritariamente hidrofóbicos

>
> 🧗🏻‍♀️DESAFIO IV: Investigar no [CaviDB](https://cavidb.org) as características estruturais da Albumina Humana na estrutura `1AO6A`:
>
> - Quantas cavidades foram previstas para essa estrutura? Quais são as principais cavidades em termos de tamanho de proteína? Existem cavidades que se sobrepõem aos resíduos descritos como relevantes para a atividade enzimática da albumina?
>
> - Alguma das cavidades cataliticamente ativas está ativada? Quais faixas de pKa são observadas em tais cavidades?
>
> 🧗🏻‍♀️ DESAFIO V: Sabe-se que na albumina bovina o sítio ativo é deslocado do humano, embora também envolva um aminoácido carregado (Lys 221). Investigar em [CaviDB](https://cavidb.org) as características estruturais da estrutura da albumina bovina `4JK4A` e comparar as características do seu sítio ativo com as características do sítio ativo da albumina humana (Lys 199)
>
> 💡 Para investigar: Leia mais sobre as [descobertas](https://www.sciencedirect.com/science/article/abs/pii/S0300908422000426) feitas por pesquisadores da Universidade Nacional de Quilmes sobre a evolução das albuminas e compare-as com o que você pode observar.
>