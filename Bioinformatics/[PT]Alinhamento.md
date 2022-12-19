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

## Alinhamento Global X Alinhamento Local

### Alinhamento Global
No alinhamento global, as sequências são comparadas em sua extensão total, utilizando tantos caracteres quanto possível.  

🎯 Esse tipo de alinhamento é apropriado quando se espera haver similaridade em toda ou na maior parte da extensão das sequências analisadas. Assim, ele maximiza as regiões de similaridade e minimiza os gaps. 

Como exemplo de alinhamento global, considere as sequências `GAAGGATTAG` e `GATCGGAAG`. O alinhamento global resultante destas sequências está apresentado abaixo 👇

```
GAA-GGATTAG
||: |||  ||
GATCGGA--AG
```

### Alinhamento Local
No alinhamento local há uma busca por regiões similares entre as sequências, não sendo necessário incluir toda a extensão das sequências comparadas.

🎯  Esse tipo de alinhamento é apropriado quando se espera que apenas algumas regiões específicas das sequências analisadas (ex: domínios) sejam similares entre si.

Como exemplo de alinhamento local, considere as sequências `CAGTTATGTCAGGGGACTGC` e `ATGTCTTTCAGCAGTTATGTCAG`. O alinhamento local resultante destas sequências está apresentado abaixo 👇

```
           CAGTTATGTCAGgggactgc
           ||||||||||||
atgtctttcagCAGTTATGTCAG
```
