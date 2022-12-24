# Pesquisa de Alinhamentos e Semelhança Sequencial
> Material baseado no tutorial [Sequence Alignment](https://github.com/AJVelezRueda/Introduccion_a_la_Bioinformatica/blob/master/Teorico_Practicos/Bioinform%C3%A1tica_Primeros_pasos/Alineamientos_secuenciales.md) de la Dra. Ana Julia Velez Rueda) da Dra. Ana Julia Velez Rueda
>
> LICENÇA : Este trabalho está licenciado sob uma Licença Creative Commons Atribuição-CompartilhaIgual 4.0 Internacional .
>
> **LICENSE**: This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg

### Índice
   * [Uma palavra não diz nada e ao mesmo tempo diz tudo](#Intro)
   * [Juntas pares](#juntas_a_la_mesmo)
   * [Semelhante não é igual](#Enter_alignments)
   * [Tipo de alinhamentos](#Alinhamentos)
   * [Pesquisa de similaridade sequencial](#Blast)


## [Uma palavra não diz nada e ao mesmo tempo diz tudo](#Intro)
Desde o trabalho realizado por Kossel em 1898 (Kossel, 1898)​ em que ele descreve que a função das proteínas poderia estar relacionada ao tipo de aminoácidos que a compõem e seu arranjo espacial, uma possível relação entre a função da proteína, sua composição de aminoácidos. Após décadas de experimentos, Anfinsen finalmente confirmou que a sequência de aminoácidos continha a informação necessária para o enovelamento de uma proteína em uma conformação biologicamente ativa (Anfinsen et al., 1961). Neste estudo, Anfinsen e outros postularam que a conformação biologicamente ativa ou estrutura terciária poderia ser prevista a partir da estrutura primária de uma proteína. Também recentemente na história, mais precisamente em 1953, Watson e Crick propõem um arranjo que estabiliza a estrutura primária do DNA e que, a posteriori, permitiria explicar os diferentes mecanismos celulares envolvidos na expressão gênica (Watson e Crick 1953). Hoje sabemos que tanto a estrutura primária da proteína quanto a dos ácidos nucléicos fornecem informações não apenas sobre sua estrutura e função, mas também informações sobre as características de um determinado organismo e sua relação evolutiva com outros organismos.

Existem diferentes mecanismos que explicam a biodiversidade, como mutações, duplicação de genes, reorganização de genomas e trocas genéticas, como recombinação, rearranjo e transferência lateral de genes. Variações aleatórias ocorrem em populações entre organismos individuais, variações não causadas pelo ambiente, que em alguns casos podem ser hereditárias. A interação de variações aleatórias e o ambiente determina o grau significativo em que os organismos se reproduzem e sobrevivem (seleção natural) e, portanto, as características da população. Dado tempo suficiente, a seleção natural leva ao acúmulo de mudanças que diferenciam grupos de organismos.

## [Juntas pares](#juntas_pares)

Duas sequências que compartilham um ancestral comum são chamadas de sequências homólogas (Reeck et al., 1987). Embora muitas vezes seja usado incorretamente, a homologia é qualitativa. Moléculas homólogas, ou homólogas, podem ser divididas em duas classes: parálogas, que são homólogas presentes em uma espécie e muitas vezes diferem em suas funções bioquímicas detalhadas; e ortólogos são homólogos que estão presentes em diferentes espécies e têm funções muito semelhantes ou idênticas. Compreender a homologia entre moléculas pode revelar sua história evolutiva, bem como informações sobre sua função; Se uma proteína recém-sequenciada for homóloga a uma proteína já caracterizada, temos uma forte indicação da função bioquímica da nova proteína.

> PARA PENSAR 🤔: Que tipo de informação pode ser extraída da comparação de sequências? Como você espera que pareça em uma comparação?pensamento

No entanto, é importante observar que dois genes podem acumular um grande número de alterações ao longo do tempo, portanto, os próprios dados da sequência podem não conter informações suficientes sobre a relação entre eles. Portanto, o termo homologia é usado apenas quando o ancestral comum é recente o suficiente para que a informação da sequência retenha semelhança suficiente para fazer inferências evolutivas (Park et al. 1998). Para avaliar relacionamentos evolutivos distantes, geralmente é melhor compará-los no nível de sequências de proteínas, enquanto para relacionamentos mais próximos, as sequências de ácidos nucléicos que os codificam são geralmente usadas, uma vez que estas tendem a ser menos informativas do que as sequências de proteínas (Pearson, mil novecentos e noventa e seis). É importante notar que a conclusão de que dois (ou mais) genes ou proteínas são homólogos é uma conjectura ou inferência, derivada de múltiplos cálculos, não um fato experimental. Mas como não há registro fóssil de formas extintas, a relação evolutiva entre dois genes é definida com base na semelhança entre eles.

> PARA PENSAR 🤔: Por que você acha que é melhor avaliar relações evolutivas distantes comparando proteínas?pensamento

Semelhante não é o mesmo
Conforme explicado acima, a maneira de encontrar relações evolutivas entre duas sequências e avaliar a similaridade entre elas envolve a comparação posição por posição entre elas. Embora as sequências de proteínas e ácidos nucleicos possam ser pensadas como textos ou sequências de caracteres, o processo de alinhar duas sequências não é tão simples quanto colocar uma sequência sobre a outra e comparar coluna por coluna se houver correspondência entre os resíduos ( ou personagens). Porque? Bem, porque como dissemos antes, com o passar do tempo as sequências podem sofrer mutações, inserções e deleções, e a consideração dessas mudanças não é trivial.

>
>🧗🏻‍♀️ DESAFIO I: Vamos tentar, então, alinhar essas duas palavras, para entender melhor o problema. Alinhe as palavras "BANANA" e "APPLE" na tabela interativa .
>
>Tome nota de suas observações e das conclusões que emergem dessas observações!ballot_box_with_checkPERGUNTAS DESENCADEADORAS: Existe apenas uma maneira de alinhá-los? Um dos possíveis alinhamentos é melhor que outro? Em caso afirmativo, por quê?
>

Agora, como dissemos, o objetivo do alinhamento de sequências é poder inferir relações evolutivas entre elas e avaliar sua similaridade. Porém, conseguir avaliar a similaridade entre duas sequências pode trazer algumas dificuldades, como você viu no exemplo, pois não existe uma forma única de alinhar duas sequências e, portanto, será necessário definir critérios que permitam identificar a melhor alinhamento.

A pontuação mais direta para avaliar a proximidade entre duas sequências pode ser baseada no número de caracteres idênticos em posições equivalentes em duas sequências alinhadas. Assim, podemos avaliar a porcentagem de resíduos idênticos, ou porcentaje de identidadsequência. Quanto maior esse percentual, mais próximas as sequências comparadas estão em termos de sua origem evolutiva.

>🧗🏻‍♀️DESAFIO II: Na tabela interativa a seguir, diferentes alinhamentos para as palavras "ANA" e "ANANA". Você verá um valor de identidade calculado aparecer no canto superior esquerdo para cada alinhamento que tentar.
>
> Tome nota dos valores de identidade observados e das conclusões tiradas dessas observações!
>
>Perguntas para começar a pensar: Todos os valores são iguais? Que considerações devem ser levadas em conta ao fazer o cálculo? Você consegue pensar em diferentes maneiras de calculá-lo? Serão todos igualmente válidos em Biologia?

Definimos identidade começamos a entender as implicações da introdução desses scripts, que chamaremos de agora em diante gaps. A presença de gaps representam as inserções e deleções nas sequências, e embora nos ajudem a encontrar um maior número de coincidências entre as sequências, eles introduzem gaps no alinhamento. Com que certeza eles podem adivinhar, a abertura de uma lacuna em uma posição ou outra ou a presença de mais de uma lacuna no alinhamento, tem suas implicações e requer nosso cuidado. Vamos analisar as questões que surgem a partir deste novo conceito:

> 🧗🏻‍♀️DESAFIO III: Experimente diferentes alinhamentos para as palavras "ANA" e "ANANA" em uma mesa interativa . Você verá que no canto superior esquerdo há um valor de identidade calculado para cada alinhamento que você tentar e um botão para alterar a penalidade que é dada para o cálculo de identidade.
>
> Experimente várias combinações, observe os valores de identidade observados e as conclusões tiradas dessas observações.
>
> Perguntas para começar a pensar: Quantas lacunas podemos introduzir? É razoável dar como equivalente uma lacuna com outro caractere ou letra? Como os valores de identidade obtidos estão relacionados às penalidades impostas ao gap? Que implicações você acha que uma penalidade de gap mais alta tem? Você consegue pensar em alguma outra forma de penalidade que não tenha sido considerada neste exemplo?
>

Como você bem viu no simulador, existe a possibilidade de dar um gap equivalente a qualquer outro personagem, porém isso não necessariamente representa melhor a realidade. No entanto, ao considerá-los como uma espécie de mismatch, introduzindo uma penalidade, também não é totalmente fácil encontrar o melhor alinhamento possível. É por isso que devemos nos colocar novamente no contexto biológico especificamente.

Como bem sabemos, em 1958 Crick levantou o dogma central da genética, onde estabeleceu que o fluxo de informação vai do DNA para o RNA, e deste para as proteínas. A expressão gênica, com suas etapas de transcrição e tradução, possibilita a obtenção de proteínas a partir das informações codificadas no DNA. Sabemos também que o código genético é composto por 64 combinações de tripletos de nucleotídeos (códons), que correspondem aos diferentes aminoácidos, e que orientam a decodificação da “mensagem” ou “informação” fornecida pelos genes para a síntese de proteínas. Embora uma estratégia possível seja apenas introduzir lacunas se elas aumentarem substancialmente a pontuação total de alinhamento, é importante ficar de olho na Biologia ao avaliar quando e quanto custa introduzir uma lacuna.

> PARA PENSAR🤔: Então, pensando em um alinhamento de ácidos nucléicos, quais são as implicações de abrir uma lacuna no alinhamento? O que implicaria a inserção ou deleção de uma região com mais de um resíduo?
>
>🧗🏻‍♀️DESAFIO IV: Experimente diferentes alinhamentos para as sequências de nucleotídeos na tabela interativa . Você poderá ver as traduções para cada sequência. Experimente várias combinações, tome nota das observações e das conclusões que delas surgem.
>
>PARA PENSAR 🤔: Importa se a lacuna que você introduz cai na primeira, segunda ou terceira posição do códon? Como você ponderaria as observações neste exercício para avaliar a similaridade entre duas sequências?

Outra forma de estimar a similaridade entre duas sequências pondera essas implicações na presença de inserções e deleções que estávamos avaliando, bem como pontuações que ponderam as mudanças de um caractere por outro de forma diferencial.

Por que deveria ser assim? Porque se falamos de nucleotídeos ou aminoácidos, você concordará que não é indistinto trocar um pelo outro. Uma mutação em um aminoácido pode, por exemplo, gerar uma mudança drástica na polaridade de uma região da proteína ou envolver uma alteração em sua estrutura secundária. Assim, poderíamos estimar a similaridade existente entre duas sequências, como a soma dos escores correspondentes aos resíduos em posições equivalentes em duas sequências alinhadas. Tabelas de pontuações de substituição de um resíduo por outro são chamadas de matrizes de substituição e são construídas levando em consideração as mudanças observadas em sequências conhecidas.

**Margaret Dayhoff** ele desenvolveu as matrizes PAM para aminoácidos, que são baseadas nas sequências de proteínas que ele compilou ao longo de uma década, publicadas como Atlas of Protein Sequence and Structure (Dayhoff, 1978). Nas matrizes PAM, cada elemento da matriz Mij quantifica a probabilidade de um aminoácido i ser substituído por outro aminoácido j no intervalo evolutivo de 1 PAM (1 PAM é definido como o intervalo evolutivo em que 1% dos aminoácidos alteração no alinhamento de 2 sequências). Essas mutações foram identificadas comparando sequências altamente semelhantes com pelo menos 85% de identidade, e assume-se que quaisquer substituições observadas foram o resultado de uma única mutação entre a sequência ancestral e uma das sequências atuais. As matrizes de substituição são utilizadas como parâmetros dos algoritmos de alinhamento de sequências de proteínas, de forma a poder atribuir uma pontuação a cada alinhamento possível, e assim poder escolher o melhor. No caso de alinhamentos de nucleotídeos, um sistema de pontuação muito mais simples é freqüentemente usado.

<img src="Dayhoff_matrix.png" alt="nw" height="300" width="300">

Figura retirada da obra: A Model of Evolutionary Change in Proteins. Dayhoff, MO, RM Schwartz e BC Orcutt. 1978. Atlas of Protein Sequence and Structure Vol. 5, suppl. 3. Fundação Nacional de Pesquisa Biomédica, Washington, DC

Agora, mesmo quando conseguimos encontrar a melhor pontuação para o nosso alinhamento, como saber se esse alinhamento tem relevância biológica, ou seja, se essas duas sequências são homólogas, ou o alinhamento é fruto do acaso? Para cada alinhamento pode ser estimada uma probabilidade ou significância estatística que nos permite estimar a imprecisão das medidas de similaridade e identidade, comparando o resultado obtido com o esperado se as sequências fossem alinhadas aleatoriamente.

É importante notar que a significância estatística não garante certeza!

## [Tipo de alinhamentos](#Alinhamentos)
Então que? Em resumo, podemos dizer que um alinhamento de sequência consiste em uma comparação de sequências biológicas (ácidos nucleicos ou proteínas), de forma a observar suas semelhanças e diferenças, buscando maximizar as semelhanças entre elas, e da forma mais razoável a partir de um ponto de vista, do ponto de vista biológico. Devemos lembrar que um alinhamento gerado por software representará apenas um dos muitos alinhamentos possíveis.

Este procedimento consiste em buscar séries de caracteres individuais que se encontrem na mesma ordem nas sequências a serem comparadas. Caracteres idênticos estão localizados na mesma coluna (match), enquanto caracteres não idênticos podem estar localizados na mesma coluna ( mismatch ) ou alinhado com o que chamamos de “gap” (indel).

Quando há troca de um resíduo por outro dizemos que há substituição. Quando falta uma base, dizemos que há uma lacuna (pode corresponder tanto a uma exclusão quanto a uma inserção).

Os alinhamentos servem, entre outras coisas, para: quantificar similaridades, encontrar domínios funcionais, buscar posições homólogas nas sequências.

Existem diferentes ferramentas para alinhar sequências, que podemos classificar em dois tipos:

- **Global** : alinhamento de toda a sequência, usando o máximo de caracteres possível. É útil ao comparar sequências muito semelhantes em tamanho e composição, por exemplo, de dois genes altamente conservados .

- **Local** : quando estamos interessados ​​apenas em alinhar regiões semelhantes entre sequências. É usado quando as sequências a serem comparadas são diferentes em tamanho ou possuem regiões não conservadas .

Um dos algoritmos mais usados ​​para encontrar alinhamentos globais é o algoritmo Needleman-Wunsch. Este é um exemplo de algoritmo de programação dinâmica, que subdivide problemas de cálculo, garantindo encontrar a solução ótima para 2 sequências dadas. Isso usa uma matriz quadrada para atribuir pontuações para os diferentes alinhamentos possíveis, dada uma pontuação para correspondências, incompatibilidades e lacunas; e, em seguida, retrocedendo ao longo da melhor escalação possível (com maior pontuação).

>
>🧗🏻‍♀️ DESAFIO V: Temos visto que o alinhamento de sequências não é trivial e requer contemplar os múltiplos caminhos possíveis, levando em consideração as informações biológicas que restringem esse universo de possibilidades.
>

É hora de levar esses conceitos ao concreto!

Propomos-lhe que pense nos passos a seguir num alinhamento de duas sequências curtas, tendo em conta uma matriz de pontuação genérica que contemple as complexidades que íamos vendo, ou seja, que penalize uma inserção ou eliminação de forma diferente de um desencontro (incompatibilidade) ou uma correspondência. Escreva-os ou descreva-os em um fluxograma.

> PARA PENSAR 🤔: O que é programação dinâmica? Por que você acha que é útil neste caso?

Vamos dar uma olhada em como funciona o algoritmo Needleman-Wunsch . Como dissemos anteriormente, trata-se de um procedimento que consiste em buscar séries de caracteres individuais que estejam na mesma ordem nas sequências a serem comparadas, colocando-os de forma a maximizar sua similaridade. Isso funciona com base em um sistema de pontuação de quão semelhantes são duas sequências. Este algoritmo calcula sequencialmente para cada posição na matriz uma pontuação que deriva de encontrar a maior pontuação entre as possíveis pontuações calculadas como a soma de uma célula adjacente, mais a correspondência/incompatibilidade (MM) da célula atual, valor que é obtido usando as matrizes de substituição que introduzimos anteriormente. Os seguintes valores são então derivados:

MM + Pontuação da célula superior
MM + Pontuação da célula esquerda
MM + Pontuação da célula superior esquerda

<img src="NW_matrix.png" alt="nw" height="300" width="300">

Dentre esses três valores, a pontuação da nossa célula em questão será a mais alta. Por fim, o algoritmo propõe o melhor alinhamento possível, que retorna a maior pontuação geral. Este alinhamento proposto é construído, seguindo o caminho com maior pontuação, percorrendo a matriz no sentido contrário; alinhar os dois caracteres ao mover diagonalmente alinha os dois caracteres, introduzindo um intervalo na sequência horizontal ao mover para baixo e um intervalo na sequência vertical ao mover para a direita.

>
>🧗🏻‍♀️DESAFIO VI: Usando a ferramenta interativa desenvolvida pelo Freiburg Bioinformatics Group, experimente diferentes penalidades de Gap para o exemplo proposto e veja o que acontece.
>
>Interpretando a recursão, explique com suas palavras de onde vêm os valores da matriz que é construída. Exponha suas conclusões!
>

Existem também ferramentas que permitem comparações de sequências pareadas e/ou alinhamentos múltiplos:

- A pares de sequências: mede a semelhança entre duas sequências.

- Alinhamento múltiplo: compara mais de duas sequências ao mesmo tempo.

Em ambos os casos o alinhamento pode ser local ou global, o que implicará algumas limitações de utilização para cada caso.

> PARA PENSAR 🤔: Em que casos um ou outro tipo de alinhamento será útil? Que limitações cada um terá?

## [Pesquisa de similaridade sequencial](#Blast)

BLAST (Basic Local Alignment Search Tool) (S. Henikoff e JG Henikoff, 1992) é a ferramenta mais amplamente utilizada na ciência para pesquisar similaridades sequenciais. Isso baseia sua operação na construção de alinhamentos locais. Este algoritmo heurístico compara uma sequência de consulta com sequências de diferentes bancos de dados, buscando alinhar subsequências (k-mers) de menor comprimento (3 aminoácidos ou 28 nucleotídeos por padrão) com as sequências do banco de dados.

Supondo que uma sequência semelhante conterá qualquer uma dessas palavras ou k-mers, estende-se o alinhamento para ambos os lados usando o algoritmo de programação dinâmica de Smith–Waterman (D. States, W. Gish e S. Altschul, 1991), buscando finalizar a coincidência global de ambas as sequências.

Existe uma grande família de programas derivados deste algoritmo, que levam diferentes tipos de sequência como sequência de busca. Vamos explorá-los!

> PARA PENSAR 🤔: Entre no servidor NCBI e veja os diferentes programas derivados do BLAST que são oferecidos. Para que serve cada um? Em quais casos você usaria cada um?
Vamos explorar esta ferramenta!
>
>🧗🏻‍♀️DESAFIO VII: Usando o programa BlastP, calcule o valor E e a % de identidade da sequência como entrada usando 20.000 acertos, um valor e de 100 e tomando os acertos com um mínimo de 70% de cobertura. Observe e discuta o comportamento de: valor E vs. % id, Pontuação vs % id, Pontuação vs valor E
>
>VVGGLGGYMLGSAMSRPIIHFGSDYEDRYYRENMHRYPNQVYYRPMDEYSNQNNFVHDCVNITIKQHTVTTTTKGENFTETDVKMMERVVEQMCITQYERESQAYYQRGSSMVLFSSSPPVILLISFLIFLIVG
>
>Agora vamos ver o que acontece quando usamos apenas fragmentos da nossa sequência de problemas:
>
>🧗🏻‍♀️ DESAFIO VIII: Realize novas buscas usando metade da sequência do problema e um quarto da sequência original. Compare os gráficos obtidos. Que conclusões você pode tirar?
>

Relações funcionais ou estruturais entre sequências homólogas podem ser inferidas a partir dos resultados de uma pesquisa BLAST. Uma vez que esta procura assume uma relação evolutiva, é assim possível identificar novos membros de um gene ou família de proteínas ou encontrar sequências idênticas, com significância estatística. Da mesma forma, é uma ferramenta amplamente utilizada para inferir a identificação de sequências não identificadas.

Mas como você pode ver, as pesquisas retornam muitos possíveis hits, que podem até ter as mesmas pontuações, por isso é necessário entender os diferentes níveis de confiança que descrevem cada parâmetro para escolher os melhores hitsou sequências para análise posterior:

`Maximum Score`: é a maior pontuação de alinhamento (bit-score) entre a sequência de consulta e os segmentos do banco de dados. É uma espécie de inversamente proporcional a valor-eou e-value. Quanto maior, menos provável que essa coincidência ou semelhança seja aleatória.

`Total score`: é a soma das pontuações de alinhamento de todas as sequências do mesmo banco de dados

`Percent Query Coverage`: é a porcentagem do comprimento da consulta incluída nos segmentos alinhados. Quanto menor, maior a probabilidade de as correspondências serem aleatórias.

`E-value`: representa a probabilidade de que a similaridade da sequência não seja aleatória. Quanto menor o valor de E, maior a probabilidade. Valores menores que 1e-3 representam correspondências de alta qualidade.

`Porcentaje de identidad`: como dissemos anteriormente, descreve como a consulta é semelhante às sequências alinhadas.

>
>🧗🏻‍♀️DESAFIO IX: Usando o BLAST, use pesquisas de similaridade sequencial para identificar a seguinte proteína:
>
>MIDKSAFVHPTAIVEEGASIGANAHIGPFCIVGPHVEIGEGTVLKSHVVVNGHTKIGRDNEIYQFASIGEVNQDLKYAGEPTRVEIGDRNRIRESVTIHRGTVQGGGLTKVGSDNLLMINAHIAHDCTVGNRCILANNATLAGHVSVDDFAIIGGMTAVHQFCIIGAHVMVGGCSGVAQDVPPYVIAQGNHATPFGVNIEGLKRRGFSREAITAIRNAYKLIYRSGKTLDEVKPEIAELAETYPEVKAFTDFFARSTRGLIR
>
>PARA PENSAR 🤔: Qual é a função da proteína? A que grupo taxonómico pertence? Em um nível apropriado de significância estatística, quantas sequências semelhantes são encontradas?
>
>🧗🏻‍♀️X DESAFIO: Realize uma nova execução do BLASTp, usando a mesma sequência, mas agora contra o banco de dados PDB. Você obtém os mesmos resultados? Que tipo de resultados (hits) são recuperados? Quando esse modo de correr pode ser útil para nós?
>