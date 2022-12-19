# Alinhamento de sequências

## O que é?
O alinhamento de sequências consiste na comparação de sequências biológicas (DNA ou proteínas), de forma a se observar suas semelhanças e diferenças, buscando maximizar as similaridades entre elas. Abaixo estão representadas duas sequências de DNA no formato FASTA e o alinhamento entre elas.

🤔 Lembre-se: Um arquivo FASTA contém um cabeçalho para cada sequência biológica, que é definido por uma linha que se inicia com o caractere `>`, seguido do nome da sequência e na linha seguinte encontra-se a sequência biológica.

Temos abaixo duas sequências no formato fasta:

```
>Sequência_1
ATGATCCTGTC
>Sequência_2
ATGCTCCTTC
```

Alinhamento entre essas duas sequências:

```
ATGATCCTGTC
|||:|||| ||
ATGCTCCT-TC
```

Sequências alinhadas são tipicamente representadas como linhas de uma matriz, na qual as letras que formam as sequências são alinhadas em colunas sucessivas. É possível que seja necessário um pareamento de letras distintas (mismatch, aqui representado por `:`) ou a inserção de espaçamentos (gaps, aqui representado por `-`) entre os resíduos para que se consiga um melhor alinhamento entre as sequências.

