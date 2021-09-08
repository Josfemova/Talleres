# Sistemas numéricos

## Introducción 

Estamos acostumbrados a utilizar únicamente base 10 para realizar operaciones diariamente, sin embargo, en diferentes contextos, es posible que sea útil trabajar con sistemas numéricos distintos. Un ejemplo es la programación de bajo nivel, en la cual se suele utilizar hexadecimal para distintas tareas, tal como referencias espacios en memoria.

El propósito de esta unidad es generalizar algunos conceptos matemáticos de forma que los mismos sean independientes a la base en la que se trabaja. 

El nombre de una base indica la cantidad de símbolos que componen a un sistema numérico:

- Base 2: {0,1}

- Base 4: {0,1,2,3}

- Base "10": {0,1,2,3,4,5,6,7,8,9}

- Base 16 : {0,1,2,3,4,5,6,7,8,9,A,B,C,D,E,F}

Decir base "diez" es correcto, sin embargo, escribirlo como "Base 10" es técnicamente un abuso del lenguaje, pero igual es la notación más utilizada. Se dice que es un abuso de lenguaje porque toda base es técnicamente Base "10", pues el 10 representa al número que corresponde al número de símbolos en cada base, por ejemplo, para contar en varias bases del \\(1\\) a \\((6)_{10}\\)

Base 2: 1-10-11-100-0101-0111

Base 4: 01-02-03-10-11-12

Base 6: 01-02-03-04-05-10

## Notación sigma

Para cuando estén llevando este curso, el plan contempla que estén llevando matemática discreta o cálculo. En dichas asignaturas se cubre el significado de la notación sigma y declaración de sumatorias, pero de forma simple 

\\[\sum_{i=k}^{n} f(i, n)\\] 

* Representa una suma consecutiva de términos de una función que depende de \\(i\\) y \\(n\\). 

* El término \\(i\\) es un contador, el cual inicia en un valor \\(k\\), usualmente 1 o 0, aunque puede ser otro valor. 

* Cada iteración se suma 1 a i

* Se detiene la suma una vez que i alcanza el valor n

Por ejemplo:

\\[\sum_{i=1}^{5} i  = 1 + 2 + 3 + 4 + 5\\] 
\\[\sum_{i=1}^{6} n = n+n+n+n+n+n = 6n \\] 
\\[\sum_{j=1}^{4} \frac{xn}{j} = 4x/1 + 4x/2 + 4x/3 + 4x/4 \\] 

Muy probablemente se encuentren variedades entre letras usadas en notación, por ejemplo, es posible encontrar una \\(j\\) en vez de la \\(i\\), pero lo que es importante notar es que el significado no cambia. El contador siempre va a ser la variable en la parte inferior de la letra sigma, y el valor tope siempre se va a encontrar sobre la letra.




