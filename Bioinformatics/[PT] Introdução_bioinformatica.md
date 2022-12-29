# Bioinformática: uma breve introdução

##### Autora: Dra. Ana Julia Velez Rueda
> Material baseado no material [_Introducción a la Bioinformática_ de AJVeleRueda](https://github.com/AJVelezRueda/Introduccion_a_la_Bioinformatica )
> 
> **LICENSE**: This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


### Índice
  * [1. Uma introdução à Introdução](#1_intro)
  * [2. Biomoléculas](#2_biomolec)
  * [3. Proteínas](#3_proteínas)
  * [4. Ácidos Nucleicos](#4_acnuc)
  * [5. Pipa cósmico de que planeta você veio?](#5_keg)
    [6. Uniprot](#6_uniprot)
  * [7. Bibliografia](#7_citations)


[1. Uma introdução à Introdução](#1_intro)

Bioinformática é uma disciplina científica que visa aplicar métodos computacionais à análise de dados biológicos, a fim de responder a inúmeras questões. Os primórdios da bioinformática estão intimamente relacionados aos avanços científicos. Entre outros projetos, o Projeto Genoma Humano foi um marco na ciência e mostrou a necessidade de recorrer a métodos automatizados para a análise do enorme fluxo de dados que é produzido com técnicas de sequenciamento. Mas nem tudo na Bioinformática é sobre processamento de dados, essa disciplina pode gerar, entre outras coisas, dados de relevância biológica derivados de simulações e cálculos que retomam conhecimentos já estabelecidos. 
Hoje, no campo da Bioinformática, por exemplo, estão sendo desenvolvidas ferramentas para prever a ligação de drogas à proteínas; ou a presença de cavidades e sítios de ligação em estruturas de proteínas, etc. É assim que, por meio da tecnologia, podemos perceber diferentes processos biológicos e colocar conceitos em imagens que de outra forma seriam muito abstratas para nós. Um passo importante para aplicar o pensamento computacional (binário) à Biologia é reconhecer quais dados ou informações nos fornecem conhecimento biológico. Em princípio, pode-se dizer que qualquer descrição de um sistema biológico pode ser um "dado biológico". Por exemplo, podemos considerar como dados biológicos  o número de morcegos em uma determinada região, o número de doentes com influenza em uma população, o número de glóbulos vermelhos por mililitro de sangue, entre outros. 
Agora, partindo do micro para o macro, poderíamos pensar em células. Dentro de cada uma das células do corpo há informações importantes armazenadas, também há muitas outras coisas, mas focando nas informações que tornam cada célula "quem elas são" poderíamos destacar algumas moléculas muito importantes.

>
> 🧗🏻‍♀️DESAFIO I: Você poderia encontrar um exemplo de macromoléculas que armazenam informações sobre a 'identidade' de um determinado organismo?
>

[2. Biomoléculas](#1_biomolec)

A química dos organismos vivos é organizada em torno do carbono (Sim! O elemento químico). Este elemento tem a capacidade de formar ligações simples com hidrogênio ou ligações duplas com átomos de oxigênio e/ou nitrogênio; dois átomos de carbono podem compartilhar duas ou até três ligações com outros átomos de carbono. Os átomos de carbono ligados covalentemente podem formar cadeias lineares, ramificadas ou circulares; formando os esqueletos aos quais se juntam grupos de outros átomos "grupos funcionais" que lhe conferem as características funcionais específicas.
O arranjo espacial dos grupos substituintes de uma molécula orgânica determina sua configuração, dois isômeros conformacionais só podem ser interconvertidos pela quebra de ligações. Ligações duplas, em torno das quais não há liberdade de rotação; e os centros quirais, em torno dos quais os substituintes são arranjados em uma sequência específica, definem a configuração de uma molécula. E como as interações moleculares entre as biomoléculas são estereoespecíficas, essa característica se torna relevante para sua função. A conformação molecular se refere, então, à disposição espacial dos grupos substituintes que possuem liberdade de movimento/de adotar diferentes disposições no espaço, e conforme essas conformações no espaço variam, variará a função e/ou funcionalidade de uma dada molécula.
Biomoléculas são todas as moléculas envolvidas na estrutura e funcionamento do organismo vivo, sejam elas grandes moléculas poliméricas (macromoléculas) como carboidratos, lipídios, proteínas e ácidos nucléicos ou seus monômeros: monossacarídeos, ácidos graxos, aminoácidos e nucleotídeos, bem como seus intermediários metabólicos. Sem ter que entrar no detalhe químico da estrutura dos monômeros: (monossacarídeos, ácidos graxos, aminoácidos e nucleotídeos) que veremos mais adiante, é conveniente ter uma ideia inicial do que são as grandes moléculas dos organismos vivos, os carboidratos, os lipídeos, as proteínas e os ácidos nucleicos. Cada uma dessas macromoléculas é formada pelo encadeamento de monômeros, unidos por ligações características. 

[3. Proteínas](#3_proteinas)

As proteínas são polímeros de desidratação de aminoácidos. As proteínas podem ser constituídas por uma ou mais cadeias peptídicas, que são chamadas de subunidades iguais ou diferentes. Elas também têm uma composição de aminoácidos característica e alguns podem ter grupos químicos adicionais, não aminoacídicos (grupos prostéticos). 
Os aminoácidos são anfólitos, com uma estrutura básica que possui um grupo amino (NH2, básico) e um grupo carboxílico (COOH, ácido). Há sempre pelo menos um átomo de carbono entre o grupo amino e o grupo carboxílico. A fórmula geral dos aminoácidos é representada da seguinte forma:

```
  COO-
     |
H3N+ -C-H
	  |
	 R1
```

Os aminoácidos diferem entre si pela natureza de seus grupos R, que podem variar desde um simples hidrogênio até uma cadeia de carbono com outros substituintes, formando assim uma lista de 22 aminoácidos que se combinam para formar todas as proteínas presentes nos seres vivos. A união dos aminoácidos por meio de uma ligação peptídica, que dá origem às cadeias peptídicas, ocorre entre o grupo COOH de um aminoácido e o grupo NH2 de outro. Nosso organismo utiliza apenas 20 e consegue sintetizar 10 destes, por isso são chamados de aminoácidos essenciais, tornando-se componentes essenciais da alimentação diária de um ser humano. 

Por possuírem um centro quiral, existem dois estereoisômeros D e L (levógiros ou dextrógiros), cujo nome vem de sua atividade óptica de deflexão da luz, embora nos organismos vivos encontremos principalmente os isômeros L. Estes também possuem propriedades ácido-base e em alguns casos apresentam grupos ionizáveis em suas cadeias laterais: ácido aspártico e glutâmico, arginina, lisina, histidina, etc. 

![Tabela Periódica de Aminoácidos](../assets/bioinformatics/tabla_aminoacidos.png  "nesta tabela você pode ver os aminoácidos com suas estruturas químicas e com o código de uma letra na margem superior esquerda. Os aminoácidos ácidos são mostrados em vermelhos (com grupos COOH em suas cadeias laterais), em rosa os aminoácidos polares, em azul os básicos (com grupos NH2 em suas cadeias laterais) e em azul claro os aminoácidos apolares.") 

A atividade de uma proteína depende em grande parte do arranjo espacial de sua cadeia polipeptídica. As proteínas não são uma bola, mas assumem uma determinada estrutura no espaço. Quatro níveis diferentes são definidos, conhecidos como estrutura primária, secundária, terciária e quaternária, e cada um deles é constituído a partir do anterior. A mesma cadeia polipeptídica pode adquirir diferentes estruturas secundárias em diferentes segmentos. A estrutura tridimensional de uma proteína normal em seu ambiente fisiológico normal é determinada pela totalidade das interações interatômicas e, portanto, pela sequência de aminoácidos, a composição dos aminoácidos que a compõem (estrutura primária) [(Anfinsen et al ., 1961)]( ). Como forma de “encurtar” o número de letras usadas para simbolizar um aminoácido, as nomenclaturas de 3 letras e 1 letra foram estabelecidas por convenção. Assim, por exemplo, a forma mais curta de simbolizar a Asparagina pode ser usando “Asn” ou, ainda mais simples, apenas “N”.

A **estrutura secundária** que uma proteína adota se deve à formação de pontes de hidrogênio entre os átomos que formam a ligação peptídica. Os tipos básicos de estrutura secundária são:

  - α-hélice: dobramento em espiral da cadeia polipeptídica sobre ela mesma.
  - Folha dobrada (folha beta dobrada): a dobra não cria uma estrutura helicoidal, mas uma folha dobrada em zigue-zague. 
  - Loops: sem forma definida.

A **estrutura terciária** de uma proteína corresponde ao enovelamento tridimensional das proteínas, devido às interações de suas cadeias laterais. As proteínas podem se dobrar e se desdobrar repetidamente, tendo a termodinâmica como “força motriz”, até atingirem um mínimo de energia, denominado estado nativo. Pauling e Mirsky, em seu trabalho publicado em 1936, dão uma primeira definição do estado nativo das proteínas como: um dobramento ou conformação característica, que confere às proteínas sua função, e cuja perda eles chamam de desnaturação [(Mirsky e Pauling, 1936)]( ). No entanto, a descrição atual do estado da proteína nativa propõe que as proteínas na água (que se aplica às células) apresentam mais de uma conformação possível, que podem se interconverter e explicar sua função [(Frauenfelder et al., 1991; Wei et al., 2016)](). A função de uma proteína e suas propriedades serão determinadas, então, pela distribuição de seus subestados conformacionais e pelas redistribuições das populações nos diferentes ambientes [(Zhuravlev et al., 2009)](). 
Do ponto de vista menos Bio e mais informático, as proteínas (e veremos mais adiante que também os ácidos nucléicos, tanto DNA quanto RNA) podem ser representadas "em uns e zeros" de múltiplas maneiras.

>🧗🏻‍♀️ DESAFIO II: Proponha uma forma de expressar as informações contidas na estrutura primária das proteínas usando tipos de dados da linguagem de programação que você conhece.
>
>🧗🏻‍♀️ DESAFIO III: Você consegue imaginar em que tipo de dados você poderia expressar as informações da estrutura terciária da proteína?
>
>🧗🏻‍♀️ DESAFIO IV: Rosalind Franklin é uma cientista muito relevante, que recebeu menos reconhecimento do que merecia. Quais foram suas contribuições neste campo? O que sua história nos diz sobre o mundo da ciência?
>
>👉 Veja o artigo "[O caso de Rosalind Franklin](https://mujeresconciencia.com/2014/05/09/el-caso-de-rosalind-franklin/)" da Mujeres con Ciencia..

Dissemos que o fato de uma proteína adquirir uma ou outra estrutura depende da composição dos aminoácidos que a compõem (estrutura primária). A frequência de aparecimento dos diferentes aminoácidos em uma determinada estrutura secundária foi estudada detalhadamente e observou-se que estes não se distribuem da mesma forma, mas que alguns aminoácidos predominam em determinadas estruturas. Em outras palavras, conhecendo a sequência de uma proteína e a preferência de cada um dos 20 aminoácidos para fazer parte de uma ou outra estrutura, poderíamos prever qual arranjo no espaço uma determinada proteína adotará. 

>
>🧗🏻‍♀️ DESAFIO V: Escreva um script em Python que calcule a porcentagem total de aminoácidos carregados do seguinte peptídeo, usando a tabela periódica de aminoácidos para clasificar-los: 
>


[4. Ácidos Nucleicos](#4_acnuc)


Os ácidos nucleicos constituem o material genético dos organismos e são necessários para o armazenamento e expressão da informação genética. Existem dois tipos de ácidos nucléicos, química e estruturalmente diferentes: ácido desoxirribonucléico (DNA) e ácido ribonucléico (RNA); ambos têm a mesma estrutura geral em todos os seres vivos. Do ponto de vista químico, os ácidos nucléicos são macromoléculas constituídas por polímeros lineales de nucleotídeos, unidos por ligações fosfodiésteres, sem periodicidade aparente. Um nucleotídeo é uma molécula orgânica formada por três componentes: uma base nitrogenada (purina ou pirimidina), um açúcar (pentose) e um grupo fosfato.

![Estrutura básica de um nucleotídeo](https://raw.githubusercontent.com/AJVelezRueda/Introduccion_a_la_Bioinformatica/master/Teorico_Practicos/Bioinform%C3%A1tica_Primeros_pasos/nucleotido.jpg "Composto genericamente por três componentes: uma base nitrogenada (purina ou pirimidina), um açúcar (pentose) e um grupo fosfato.")


Dentro da célula, o DNA armazena as informações necessárias para construir proteínas. O DNA é uma cadeia formada por muitas combinações de quatro nucleotídeos A, C, G e T, que diferem entre si na base nitrogenada que o compõe. As diferentes combinações conferem-lhe diferentes funcionalidades. Para que as informações passem do DNA para as proteínas, a mensagem genética é copiada do DNA para outra molécula, o RNA. O RNA é muito semelhante ao DNA, mas eles são diferenciados pelo açúcar (pentose) que carregam: ribose e desoxirribose, respectivamente. 

Os nucleotídeos são ligados entre si pelo grupo fosfato, que serve de ponte entre o primeiro nucleotídeo e o próximo. As moléculas de DNA e RNA também são capazes de assumir uma estrutura no espaço. Quatro níveis de estrutura são definidos, como no caso das proteínas: primário, secundário, terciário e quaternário, cada um dos quais é constituído a partir do anterior. A estrutura primária dos ácidos nucléicos corresponde à sequência ordenada de nucleotídeos da extremidade 5' à 3' de uma molécula. A informação genética está contida na ordem exata dos nucleotídeos. 
A estrutura secundária é o arranjo local da estrutura primária estabilizada por pontes de hidrogênio, que segundo o modelo de Watson e Crick corresponde a uma estrutura de dupla hélice [(Watson e Crick, 1953)]()... Bah! “de” Watson e Crick…


>PARA PENSAR: Quantas proteínas um organismo pode sintetizar? Do que depende a quantidade e as características das proteínas que um organismo pode sintetizar? 🤔
>

A estrutura terciária é uma dobra complicada na estrutura secundária adquirindo uma forma tridimensional. O DNA tem uma estrutura terciária, que consiste na fibra torcida sobre si mesma, formando uma espécie de super-hélice. Esse arranjo é chamado de DNA superenrolado e permite o empacotamento do DNA nas células. O DNA é uma molécula muito longa em algumas espécies, mas nas células eucarióticas ele está alojado dentro do núcleo, um pequeno compartimento. 


>🧗🏻‍♀️ DESAFIO VI: O que faz com que dois indivíduos de uma espécie sejam diferentes? Proponha uma maneira de verificar sua resposta fazendo um diagrama de um possível método computacional para esse fim.
>
>☑️ PERGUNTAS INICIANTES: Quais informações você deve ter? Como você deve expressar essas informações para a análise?
>

Existem diferenças nas estruturas do DNA e do RNA, o primeiro será uma fita dupla, enquanto o RNA geralmente é encontrado como uma fita simples (alguns vírus podem apresentar RNA de fita dupla... Droga!). Vários tipos de RNA são conhecidos e todos eles participam de uma forma ou de outra na síntese de proteínas. São eles: RNA mensageiro (mRNA); RNA ribossomal (rRNA), que forma a estrutura dos ribossomos; RNA de transferência (tRNA) e pequenos RNAs nucleares (snRNAs). Outros tipos incluem microRNAs (miRNAs), pequenos interferentes (siRNAs), etc. 

[5. Pipa cósmica, de que planeta você veio?](#5_kite)


Agora, obter informações biológicas para processamento computacional não é uma questão básica. De onde vem essa informação? Onde encontramos sequências de proteínas ou sua função na célula; ou mesmo informações relacionadas a pacientes infectados com COVID-19? 😱

Em linhas gerais, cientistas de todo o mundo desenvolvem diversos conhecimentos relacionados aos seres vivos. Este conhecimento é obtido com base em observações e experimentação. Os dados e conclusões obtidos são compartilhados entre os cientistas de forma organizada, seja por meio de publicações em revistas super-arqui-nerds ou, por exemplo, por meio de **Bancos de dados** disponíveis na internet. Um banco de dados biológico (DB) é uma coleção estruturada de dados; em particular, um banco de dados biológico é uma coleção de informações relacionadas aos seres vivos. Esses dados vêm de experimentos científicos, literatura publicada, análise computacional, etc. Na maioria dos casos será necessário realizar algum tipo de tratamento nos dados para sua interpretação. 

Em bioinformática, é essencial entender a diferença entre dados e informações. Embora as informações possam ser derivadas diretamente de conjuntos de dados, os dados são algo como massa de pão crua 🥖🍞 antes de ir para o forno, tem tudo para virar pão, mas falta cozimento. Tal como na cozinha🍴, o tipo de tratamento dos dados dependerá da pergunta a que queremos responder e do material de início, tal como a sua análise dependerá do contexto da informação que obtemos. Ou seja, não vamos processar uma imagem da mesma forma que uma sequência. E mesmo quando uma sequência de proteína pode ser pensada como uma string (ou palavra), a informação que derivamos de seu processamento não pode ser interpretada da mesma forma que uma história de [Mariana Enríquez](https://es.wikipedia.org / wiki/Mariana_Enr%C3%ADquez). Em suma, será necessário colocar a cabeça para ir de simples letras à entender os fenômenos que estão por trás da natureza que nos cerca.


[6. Uniprot](#6_uniprot)

Os dados contidos em bancos de dados biológicos podem incluir, por exemplo: funções, estrutura e localização de proteínas ou genes, efeitos clínicos de mutações, bem como semelhanças de sequências ou distâncias evolutivas, etc. Entre as bases de dados mais utilizadas por cientistas de todo o mundo, bioinformáticos ou não, estão [GenBank](https://www.ncbi.nlm.nih.gov/genbank/) (coleção de todas as sequências biológicas estudadas), [PDB]( https://www.rcsb.org/) (que armazena informações estruturais disponíveis sobre ácidos nucléicos e proteínas) e Uniprot (que armazena informações sobre proteínas).

Vamos dar uma olhada em como funciona e o que é [Uniprot](https://www.uniprot.org/). O banco de dados UniProt (UniProtKB) torna acessíveis, de forma estruturada e gratuita, dados de sequências de proteínas com anotações funcionais, precisas, consistentes e ricas em sequências. As bases de dados geralmente mudam sua fachada ou UI (interface do usuário), então aqui vamos enfatizar seu conteúdo.

**UniProt** está dividido em duas seções ou subconjuntos de dados: **Swiss-Prot**, que é a seção de registros anotados manualmente. Ele incorpora informações extraídas da literatura e análises computacionais avaliadas por curadores de todo o mundo. **TrEMBL**, por sua vez, é a seção com registros analisados computacionalmente aguardando anotação manual completa.

>
> 🧗🏻‍♀️ DESAFIO VII: Pesquisar a quantidade de entradas contidas em cada seção do **Uniprot**
>
> 🧗🏻‍♀️ DESAFIO VII: Utilizar o código LPXA_ECOLI como texto de pesquisa no banco de dados [Uniprot](https: //www.uniprot.org/): 
> a) Identifique o tipo de proteína: É uma enzima? Se sim, qual é a sua atividade?
> b) Identifique o organismo de origem da proteína.
> c) Analise os "termos GO": anote o processo biológico, a função e o local onde o LPXA_ECOLI desempenha o seu 
> papel biológico.
> d) A proteína está cristalizada? Que código de entrada ela tem no PDB? Para quê serviria a base de dados do PDB então?
>

[7. Bibliografia](#7_citations)

Anfinsen, CB, Haber, E., Sela, M. e White, FH (1961). A cinética de formação da ribonuclease nativa durante a oxidação da cadeia polipeptídica reduzida. Proc Natl Acad Sci USA 47, 1309–1314.

Frauenfelder, H., Sligar, SG e Wolynes, PG (1991). As paisagens energéticas e os movimentos das proteínas. Ciência 254, 1598-1603.

Mirsky, AE e Pauling, L. (1936). Sobre a estrutura de proteínas nativas, desnaturadas e coaguladas. Proc Natl Acad Sci USA 22, 439–447.

Watson, JD e Crick, FH (1953). Estrutura molecular dos ácidos nucleicos; uma estrutura para o ácido nucleico de desoxirribose. Natureza 171, 737–738.

Wei, G., Xi, W., Nussinov, R. e Ma, B. (2016). Conjuntos de proteínas: como a natureza aproveita as flutuações termodinâmicas para a vida? Os diversos papéis funcionais dos conjuntos conformacionais na célula. Chem. Rev. 116, 6516-6551.

Zhuravlev, PI, Materese, CK e Papoian, GA (2009). Desconstruindo o estado nativo: paisagens energéticas, função e dinâmica das proteínas globulares. J. Phys. Chem. B 113, 8800–8812.

