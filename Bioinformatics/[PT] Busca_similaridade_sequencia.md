# Busca por similaridade entre sequências
> Material baseado no tutorial [Sequence Alignment](https://github.com/AJVelezRueda/Introduccion_a_la_Bioinformatica/blob/master/Teorico_Practicos/Bioinform%C3%A1tica_Primeros_pasos/Alineamientos_secuenciales.md) da Dra. Ana Julia Velez Rueda
>
>
> **LICENSE**: This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## [Busca por similaridade entre sequências](#Blast)

BLAST (Basic Local Alignment Search Tool) (S. Henikoff e JG Henikoff, 1992) é a ferramenta mais amplamente utilizada na ciência para pesquisar similaridades entre sequências, baseando sua operação na construção de alinhamentos locais. Este algoritmo heurístico compara uma sequência de interesse com sequências de diferentes bancos de dados, buscando alinhar subsequências (k-mers) de menor comprimento (3 aminoácidos ou 28 nucleotídeos por padrão) com as sequências do banco de dados.

Supondo que uma sequência semelhante tenha qualquer uma dessas palavras ou k-mers, estende-se o alinhamento para ambos os lados usando o algoritmo de programação dinâmica de Smith–Waterman (D. States, W. Gish e S. Altschul, 1991), buscando finalizar a similitude global de ambas as sequências.

Existe uma grande família de programas derivados deste algoritmo, que recebem diferentes tipos de sequência como sequência de busca. Vamos explorá-los!

> PARA PENSAR 🤔: Entre no servidor NCBI e veja os diferentes programas derivados do BLAST que são oferecidos. Para que serve cada um? Em quais casos você usaria cada um?
Vamos explorar esta ferramenta!
>
>🧗🏻‍♀️DESAFIO VII: Usando o programa BlastP, calcule o E-value e a % de identidade da sequência abaixo como input usando 20.000 hits, um e-value de 100 e hits com um mínimo de 70% de cobertura. Observe e discuta os comportamentos: E-value vs. % id, Score vs % id, Score vs E-value
>
>VVGGLGGYMLGSAMSRPIIHFGSDYEDRYYRENMHRYPNQVYYRPMDEYSNQNNFVHDCVNITIKQHTVTTTTKGENFTETDVKMMERVVEQMCITQYERESQAYYQRGSSMVLFSSSPPVILLISFLIFLIVG
>
>Agora vamos ver o que acontece quando usamos apenas fragmentos da nossa sequência de interesse:
>
>🧗🏻‍♀️ DESAFIO VIII: Realize novas buscas usando metade da sequência de interesse e um quarto da mesma. Compare os gráficos obtidos. Que conclusões você pode tirar?
>

Relações funcionais ou estruturais entre sequências homólogas podem ser inferidas a partir dos resultados de uma busca por BLAST. Já que esta busca assume uma relação evolutiva, é possível identificar novos membros de uma família de genes ou de proteínas ou encontrar sequências idênticas, com significância estatística. Da mesma forma, é uma ferramenta amplamente utilizada para inferir a identificação de sequências não identificadas.

Mas como você pode ver, as pesquisas retornam muitos possíveis hits, que podem até ter as mesmas pontuações, por isso, é necessário entender os diferentes níveis de confiança que descrevem cada parâmetro para escolher os melhores `hits` ou sequências para análises posteriores:

`Maximum Score`: é a maior pontuação de alinhamento (bit-score) entre a sequência de interesse e os segmentos do banco de dados. É uma espécie de inversamente proporcional ao e-value. Quanto maior, menos provável que essa coincidência ou semelhança seja aleatória.

`Total score`: é a soma das pontuações de alinhamento de todas as sequências do mesmo banco de dados.

`Percent Query Coverage`: é a porcentagem do comprimento da sequência de interesse inclusa nos segmentos alinhados. Quanto menor, maior a probabilidade das correspondências serem aleatórias.

`E-value`: representa a probabilidade de que a similaridade entre as sequências não sejam aleatórias. Quanto menor o e-value, maior a probabilidade. Valores menores que 1e-3 representam correspondências de alta qualidade.

`Porcentagem de identidade`: como dissemos anteriormente, descreve como a sequência de interesse é semelhante às sequências alinhadas.

>
>🧗🏻‍♀️DESAFIO IX: Usando o BLAST, realize buscas de similaridade entre sequências para identificar a seguinte proteína:
>
>MIDKSAFVHPTAIVEEGASIGANAHIGPFCIVGPHVEIGEGTVLKSHVVVNGHTKIGRDNEIYQFASIGEVNQDLKYAGEPTRVEIGDRNRIRESVTIHRGTVQGGGLTKVGSDNLLMINAHIAHDCTVGNRCILANNATLAGHVSVDDFAIIGGMTAVHQFCIIGAHVMVGGCSGVAQDVPPYVIAQGNHATPFGVNIEGLKRRGFSREAITAIRNAYKLIYRSGKTLDEVKPEIAELAETYPEVKAFTDFFARSTRGLIR
>
>PARA PENSAR 🤔: Qual é a função da proteína? A que grupo taxonômico ela pertence? Em um nível apropriado de significância estatística, quantas sequências semelhantes são encontradas?
>
>🧗🏻‍♀️DESAFIO X: Realize uma nova busca por BLASTp, usando a mesma sequência, mas agora contra o banco de dados PDB. Você obtém os mesmos resultados? Que tipo de resultados (hits) são recuperados? Quando essa opção pode nos ser útil?
>

