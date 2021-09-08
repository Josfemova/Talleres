# Conversiones de base


# Fórmula general

Todo número, de cualquier base, se puede expresar utilizando la fórmula general:

\\[N = \sum_{i=1}^{m-1} r^{i-1}d_{i-1} + \sum_{j=-1}^{-n}r^{j}d_{j}\\]

\\[\begin{pmatrix} r: \text{base} \\\\ m: \text{cantidad de dig. enteros} \\\\ n: \text{cantidad de dig. fraccionales}\end{pmatrix}\\]

La notación usada en el curso se abusa un poco de la notación, pues se puede notar que el contador j no aumenta, sino que disminuye, la forma "correcta" sería:

\\[N = \sum_{i=1}^{m-1} r^{i-1}d_{i-1} + \sum_{j=1}^{n}r^{-j}d_{j}\\]

Ambas notaciones son intercambiables, pero se favorece la primera sobre la segunda!!!

Nótese algo importante, la fórmula, al igual que toda otra operación matemática, aplica independientemente de la base en la que se trabaje. Lo que puede cambiar es que tan fácil es acostumbrarse a la operación. 

Ejemplo:

\\[ 101.1101_{2} = N_{10} =\sum_{i=1}^{3-1} 2^{i-1}d_{i-1} + \sum_{j=-1}^{-4}2^{j}d_{j}\\]
\\[=[2^2 * 1 + 2^1 * 0 + 2^0 * 1] + [2^{-1}*1 + 2^{-2}*1 +2^{-3}*0+ 2^{-4}*1] \\]
\\[ 5 + 1/2 + 1/4 + 1/16  = 5.8125\\]

Usualmente, la fórmula general resulta más útil cuando se trata de convertir a base decimal. No significa que la fórmula no aplique para otras bases, pero resulta algo impráctica para cálculos rápidos, a menos de que se tenga una familiaridad considerable con la base en la que se trabaja. Por ejemplo, la opearción anterior en sentido inverso se denotaría como:

\\[5.8125_{2} = N_{10} =\sum_{i=1}^{1-1} r^{i-1}d_{i-1} + \sum_{j=1}^{100}r^{-j}d_{j}\\]


# División consecutiva


# Atajo: Conversion de bases que son potencia de otra


