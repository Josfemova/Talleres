# Crear repositorio

Primero vamos a crear un repo para el proyecto

* Crear repo llamado RooksVsAvatars
* Crear carpeta local para proyecto
* git init
* agregamos los archivos iniciales
* agregamos archivos y ensamblamos el primer commit
* git remote add origin "url repo"
* git push --set-upstream origin master
* ponemos las credenciales y listo

Ahora, creemos las ramas. Supongamos que este proyecto tiene solo una rama experimental. Vamos a crearla

* git branch experimental
* git push -u origin experimental

con esto ambas ramas, remota y local, quedan coordinadas.

También está el caso posible de que un miembro del equipo ya haya creado una rama. entonces creemos la rama en github directamente para que puedan ver como se replica una rama que ya existe en el remoto

* crea rama en remoto llamada preprod
* git config pull.rebase false
* chequeamos los cambios en el remoto con git fetch
* git checkout --track origin preprod

Si ejecutamos git branch -a podemos ver que ahora salen listadas las ramas en el repo remoto y las ramas locales correspondientes

Ahora, digamos que son otro miembro del grupo, el repo ya está hecho, y ustedes lo que quieren es empezar a colaborar. Para esto, deben crear una carpeta donde quieran almacenar el proyecto 
* abrimos la consola
* git clone "url repositorio"
* cd  "nombredelproyecto" para colocarnos en la subcarpeta

ahora, tenemos que crear las ramas locales que queremos coordinar, esto, igual que en el paso anterior, lo podemos hacer con checkout --track 

recordar siempre configurar el tipo de operación que quieren utilizar para administrar un pull. 
