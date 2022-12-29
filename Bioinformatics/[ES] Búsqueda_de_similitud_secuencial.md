# Búsqueda de similitud secuencial
> Material basado en el tutorial de [_Alineamiento de secuencias_](https://github.com/AJVelezRueda/Introduccion_a_la_Bioinformatica/blob/master/Teorico_Practicos/Bioinform%C3%A1tica_Primeros_pasos/Alineamientos_secuenciales.md) de la Dra. Ana Julia Velez Rueda
>
>
> **LICENSE**: This work is licensed under a
[Creative Commons Attribution-ShareAlike 4.0 International License][cc-by-sa].
>
>[![CC BY-SA 4.0][cc-by-sa-image]][cc-by-sa]

[cc-by-sa]: http://creativecommons.org/licenses/by-sa/4.0/
[cc-by-sa-image]: https://licensebuttons.net/l/by-sa/4.0/88x31.png
[cc-by-sa-shield]: https://img.shields.io/badge/License-CC%20BY--SA%204.0-lightgrey.svg


## [Búsqueda de similitud secuencial](#Blast)


BLAST (Basic Local Alignment Search Tool) (S. Henikoff and J. G. Henikoff, 1992) es la herramienta más utilizada en ciencia para realizar búsquedas por similitud secuencial.  Esta basa su funcionamiento en la construcción de alineamientos locales. Este algoritmo heurı́stico compara una secuencia problema contra secuencias de distintas bases de datos, buscando alinear subsecuencias (k-meros) de longitud más corta (3 amino ácidos o 28 nucleótidos por defecto) con las secuencias de la base de datos. 

Asumiendo que una secuencia similar contendrá alguna de estas palabras o k-meros, extiende el alineamiento hacia ambos lados mediante el algoritmo de programación dinámica de Smith–Waterman (D. States, W. Gish, and S. Altschul, 1991), buscando nalaizar la coincidencia global de ambas secuecias. 


Existe una gran familia de programas derivados de este algoritmo, que toman distintos tipos de secuencia como secuencia de búsqueda. ¡Vamos a exploráarlos! 

>**PARA PENSAR** 🤔: Ingresá al servidor del NCBI y mirá los distintos programas derivados del BLAST que se ofrecen ¿Para qué sirve cada uno? ¿En qué casos usarías cada uno?   
Vamos a explorar esta herramienta!
>
>🧗🏻‍♀️DESAFIO VII: Utilizando el programa BlastP calculá el E-value y % identidad de la secuencia como input usando 20000 hits, un e-value de 100 y tomando aquellos hits con un mínimo de 70% cobertura. Observe y discuta el comportamiento de: E-value vs % id, Score vs % id,  Score vs E-value
>
>VVGGLGGYMLGSAMSRPIIHFGSDYEDRYYRENMHRYPNQVYYRPMDEYSNQNNFVHDCVNITIKQHTVTTTTKGENFTETDVKMMERVVEQMCITQYERESQAYYQRGSSMVLFSSPPVILLISFLIFLIVG
>
>Veamos ahora qué pasa cuando usamos sólo fragmentos de nuestra secuencia problema: 
>
>🧗🏻‍♀️DESAFIO VIII: Realizá nuevas búsquedas usando la mitad de la secuencia problema y para un cuarto de la secuencia original. Compará los gráficos obtenidos. ¿Qué conclusiones puede sacas?
>

A partir de los resultados de una búsqueda con BLAST se pueden inferir relaciones funcionales o estructurales entre secuencias homólogas. Ya que esta búsqueda asume una relación evolutiva, es posible de este modo identificar nuevos miembros de una familia de genes o de proteínas o encontrar secuencias idénticas, con una significancia estadística. Así mismo, es una herramienta muy utilizada para inferir la identificación de secuencias sin identificación. 

Pero como pudieron observar, las búsquedas arrojan muchos posibles `hits`, que inclusipueden tener las mismas puntuaciones, por lo que es necesario diferenciar comprender los diferentes niveles de confianza que describen cada parámetro para elegir los mejores `hits` o secuencias para los análisis posteriores:

- `Maximum Score`: es la puntuación de alineación más alta (bit-score) entre la secuencia de consulta y los segmentos de la base de datos. Es una especie de inversamente proporcional al `valor-e` o `e-value`. Cuanto más grande, menos probable de que esta coincidencia o similitud sea al azar.

- `Total score`: es la suma de las puntuaciones de alineación de todas las secuencias de la misma base de datos

- `Percent Query Coverage`: es el porcentaje de la longitud de la consulta que se incluye en los segmentos alineados. Cuanto más pequeño, más probable que las coincidencias sean al azar.

- `E-value` representa la probabilidad de que la similitud de la secuencia no sea aleatoria. Cuanto menor sea el valor E, mayor la probabilidad. Valores inferiores a 1e-3 representa coincidencias de muy alta calidad.

- `Porcentaje de identidad`: como dijimos anteriormente, describe qué tan similar es la consulta a las secuencias alineadas.


>🧗🏻‍♀️DESAFIO IX: Utilizando BLAST utilizá búsquedas de similitud secuencial para identificar a la siguiente proteína:
>
>MIDKSAFVHPTAIVEEGASIGANAHIGPFCIVGPHVEIGEGTVLKSHVVVNGHTKIGRDNEIYQFASIGEVNQDLKYAGEPTRVEIGDRNRIRESVTIHRGTVQGGGLTKVGSDNLLMINAHIAHDCTVGNRCILANNATLAGHVSVDDFAIIGGMTAVHQFCIIGAHVMVGGCSGVAQDVPPYVIAQGNHATPFGVNIEGLKRRGFSREAITAIRNAYKLIYRSGKTLDEVKPEIAELAETYPEVKAFTDFFARSTRGLIR
>
>**PARA PENSAR** 🤔: ¿Cuál es la función de la proteína? ¿A qué grupo taxonómico pertenece? A un nivel de significancia estadística adecuado ¿cuántas secuencias similares se encuentran? 
>
>🧗🏻‍♀️DESAFIO X:  Realizá una nueva corrida del BLASTp, utilizando la misma secuencia , pero ahora contra la base de datos PDB.  ¿Se obtienen los mismos resultados? ¿Qué tipo de resultados (hits) se recuperan? ¿Cuándo nos podría ser útil este modo de corrida?
