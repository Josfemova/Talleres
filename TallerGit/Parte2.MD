
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