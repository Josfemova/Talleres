# Video 1: Introducción general

Esta serie de videos forman parte del taller de uso de Git.

Mi nombre es José Morales, y soy el asistente del profesor Milton Villegas Lemus para el curso de taller de programación.

Recuerden que en caso de que les surja alguna duda durante el proceso de seguir los videos del taller, me pueden contactar por los canales de comunicación habilitados, entre ellos, el grupo de telegram, el grupo de classroom o el correo electrónico.

En este primer video les daré una breve introducción sobre qué es git, y por qué lo vamos a usar.

En los videos posteriores, cubriremos los comandos básicos que es necesario que aprendan a utilizar para poder hacer uso de la herramienta y algunos otros detalles respecto a situaciones que se pueden presentar durante el uso de la herramienta.

---

La primera pregunta es entonces ¿qué es git?

Git es un programa de control de versiones. Existen alternativas, pero git es el líder de facto en la industria.

De forma algo reduccionista, se prodría decir que la funcionalidad de git es la misma que la de los controladores de versión de archivo usados en google drive y en onedrive, con los que probablemente ya estén familiarizados. La diferencia es que git está diseñado principalmente como una herramienta para el proceso de desarrollo de software.

La funcionalidad principal del programa es la administración de cambios a una base de código fuente, aunque además de eso, también almacena metadata relacionada a los cambios realizados. Esto hace de git una herramienta escencial en proyectos de desarrollo que involucran varios colaboradores. 

---

A grandes rasgos, git es una forma de coordinar un mismo espacio de trabajo entre varios colaboradores. Similar a la forma en la que trabaja onedrive con las aplicaciones de escritorio de office, Git permite a cada colaborador tener una copia del espacio de trabajo, la cual puede modificar incluso estando desconectado de internet. La profundidad de git radica en como controla las operaciones de coordinación del espacio de trabajo, y como rastrea los cambios realizados al código fuente.

---

El propósito de esta serie de videos es que al finalizar, sean capaces de utilizar git al menos en un nivel básico para el uso en los proyectos programados del curso, aunque se les recomienda que profundicen un poco más en los comandos disponibles y funcionamiento del programa en general, puesto que es una herramienta que se utiliza en casi todos los cursos de programación de la carrera.

## Sección 1: Estructura de datos

Para usar git es esencial comprender primero como organiza los datos.

### Árboles

En primer lugar, esta el concepto del árbol, o tree, que es básicamente una captura del estado del directorio del proyecto. Un árbol contiene referencias a subárboles y los archivos del proyecto. En estas capturas, los archivos se guardan como "blobs", las cuales solo contienen información de los cambios realizados respecto a capturas anteriores. 

### Commit

El commit es el bloque fundametal de git. Funcionalmente, es el enlace entre dos árboles, y contiene la información de como se dió la transición de un árbol a otro. Esto incluye:

1. Responsable de los cambios realizados que llevaron al nuevo estado del directorio
2. Momento en que se dió la transición
3. Un mensaje respecto a dicha transición

Cabe notar que un árbol puede ser la base para más de un commit, es decir, el estado "actual" es relativo a cuál camino de commits se esté siguiendo. Estos caminos se pueden unir de nuevo en un solo árbol mediante una operación llamada merge

### Historia

Al grafo conformado por árboles y commits se le llama historia, ya que funcionalmente es un registro de los cambios que se han hecho a través del tiempo. En sí, muestra los caminos que han llevado de un estado del proyecto a otro estado. Este camino puede recorrerse de manera regresiva, es decir, la estructura de datos funciona como un respaldo de diferentes estados del proyecto en diferentes momentos

### Cabeceras y ramas

Una cabecera es un puntero a un commit. Las cabeceras funcionan para señalar respecto a qué arbol se realizaron una serie de cambios. 
Existen dos tipos de cabeceras.

La cabecera principal o HEAD indica el estado más reciente sobre el cual se están realizando cambios, el denominado "working tree", y es contra este árbol que se compara el estado actual del proyecto para decidir que información debe ir en el nuevo commit a realizar. 

Las cabeceras rama o branch apuntan a commits específicos, que pueden estar relacionados o no. Se utilizan como herramientas para aislar flujos de trabajo, de forma en que por ejemplo, se puede administrar el desarrollo de funcionalidades experimentales, manteniendo de manera paralela una versión del proyecto estable sin estas funcionalidades. 

Varias cabeceras pueden apuntar a un mismo commit, por ejemplo, las cabeceras rama son utilizadas para comunicarle a git cual debe ser el valor de la cabecera HEAD a usar para el próximo commit. 

## Conceptos: repositorio, origin y remote

Un repositorio se refiere al directorio en el que se almacena tanto la estructura de datos que maneja git, como los archivos del proyecto, 

El programa de git puede funcionar como cliente y como servidor. Usualmente, se usan servidores como Github o Gitlab para almacenar el repositorio de un proyecto. 

Dentro del contexto de git, remote se refiere a un repositorio que no es el local, esto puede ser incluso el repositorio de un compañero de trabajo en la misma red. 

El nombre de "origin" se le da al repositorio original o principal de un proyecto. Para nuestro caso, funcionalmente se refiere al repositorio que crean en github u otra plataforma, y es respecto a este repositorio que se coordinan el resto de repositorios.


# Video 2: Uso local

En este video cubriremos diferentes comandos de git.
Para esto es necesario que tengan git en su computadora instalado.
En Linux y en Mac, Git puede ser utilizado directamente en la consola.
En Windows, cuando instalan git pueden seleccionar si desean poder ejecutar desde consola del sistema, o si prefieren tener solamente la consola de git bash.

Para esta sección, deben crear una carpeta en la que probaremos diferentes comandos de git.
Una vez dentro de la carpeta, deben abrir una consola de comandos dentro de la misma.
Esto se logra abriendo el menú de contexto presionando el click derecho del ratón y escogiendo la opción de abrir la consola de su sistema operativo. En windows, es "git bash", en mac y en linux la opción que deben seleccionar es "abrir terminal aquí". Adicionalmente, si estan en windows y prefieren la consola de powershell, pueden presionar shift+click derecho y seleccionar la opción de ejecutar ventana de comandos de powershell


### Init

Git init se utiliza para inicializar un repositorio. Le indica a git que debe crear los archivos necesarios para controlar la carpeta actual como un repositorio local. 

### status, diff y add

git status nos da información sobre los cambios realizados hasta ahora. Para ver los cambios en sí, está el comando diff, el cuál nos indica líneas agregadas y líneas eliminadas

Add se utiliza para agregar los cambios realizados a una lista que posteriormente se usará cuando se realice un commit. Al comando se le puede especificar los archivos que queremos que analice para agregar a la lista, pero la mayoría de las veces es más conveniente solo colocar un "punto" o agregando la bandera "--all", los cuales le indican a git que debe chequear todos los archivos y agregar sus cambios al próximo commit

### Commit

git commit es un comando utilizado para ensamblar un nuevo commit con los cambios agregados anteriormente. 
siempre es necesario indicar un mensaje antes de ensamblar el nuevo commit, esto se hace por medio de la bandera "guión m", aunque hay otras formas.
Es preferible para los mensajes utilizar verbos en  infinitivo y hablar en tercera persona singular.

### Branch

Este comando es utilizado para crear una nueva cabecera rama bajo un nombre en específico. 
De esta manera creamos flujos de trabajo paralelos que no interatúan entre sí a menos de que hagamos una operación merge. 
Si al comando no se le da ningún nombre, solo lista las ramas del repositorio

### Checkout

Es un comando multifuncional en el sentido que su funcionamiento puede servir para diferentes propósitos. En sí, lo que hace es coordinar la carpeta actual con la captura a la que apunta una cabecera. Si le damos un nombre de archivo, retorna dicho archivo a su estado tal como está almacenado en la cabecera HEAD, osea, respecto al último commit.

Otro uso es moverse de rama. Al darle el nombre de una rama, git coordinará la carpeta con el commit al que apunta dicha cabecera. Si hay cambios que no se han agregado a un commit, pueden perderse, por lo cual es aconsejable hacer un commit antes de cambiar de rama si se realizaron cambios, o almacenar los cambios utilizando el comando stash


### Stash

Stash provee una pila para almacenar cambios sin hacer un commit. Se utiliza más que todo cuando se necesitan hacer cambios rápidos. con push o sin ningún comando extra, guarda los cambios actuales y ejecuta el equivalente a un checkout,es decir, restaura la carpeta actual al estado del último commit. Para recuperar los cambios guardados, se utiliza el subcomando pop, el cual aplica los últimos cambios guardados en la pila. 


### Merge

Merge lo que hace es coordinar los cambios de dos capturas distintas. La captura a la cual se le aplican los cambios es la que señala la cabecera rama actual. Como argumento, al comando se le da el nombre de la rama con la cual se quiere coordinar la rama actual. 
Por ejemplo, en el caso de querer actualizar la rama maestra, usamos checkout master, y luego aplicamos merge y el nombre de la rama cuyos cambios queremos aplicar a la rama actual. 

Durante una operación merge pueden encontrarse conflictos. 
Por ejemplo, puede que un archivo haya sido editado de manera simultánea en diferentes ramas, por lo cuál git no sabe decidir cuales líneas debe conservar y cuáles debe remover. 

En estos casos, git comunica que debemos revisar los archivos con conflictos, resolver por nuestra cuenta cuales líneas deben permanecer y cuáles deben removerse, y por último hacer un nuevo commit para poder finalizar la operación merge.
Cuando git entra en este estado, podemos utilizar el comando status para ver cuales archivos tienen que ser fusionados a mano. Si consideramos que es muy riesgoso continuar con el merge, podemos utilizar la bandera "--abort" para cancelar la operación y retornar la carpeta actual al estado antes de comenzar el merge

# Uso remoto

Ciertos comandos son específicos para la interacción con repositorios remotos.

### Fetch

Es un comando utilizado para chequear a que commit apunta una cabecera rama en un repositorio remoto. Si el repositorio remoto y el local están coordinados, este commit debe ser el mismo. De lo contrario, git señala que las cabeceras difieren, e indica por cuantos commits la rama actual está adelantada o atrasada respecto al repositorio remoto

### Pull

Cuando fetch retorna que el repositorio remoto está adelantado, Pull integra los commits del repositorio remoto en el repositorio local, efectivamente coordinando el estado de ambos repositorios

### Push

Cuando se realiza un commmit y el mismo no está presente en el remoto, push lo que hace es actualizar el repositorio remoto utilizando el local como referencia. Este comando se utilzia en los casos en los cuales el respositorio local está adelantado al remoto.


--- 

Esto será todo lo que veremos a nivel teórico. El siguiente video lo que presentará es un ejemplo de uso de git utilizando la plataforma de github, y algunas características específicas de dicho ambiente. 