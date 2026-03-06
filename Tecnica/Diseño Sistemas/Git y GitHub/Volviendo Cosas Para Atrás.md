
Vamos a ver que pasa cuando algo no salió como queremos y queremos
volver a un commit viejo etc.

### **Eliminar el último commit (pero no cambiar archivos que ves ahora - tal como los ves).**

Supongamos que hice un commit pero no me gustó (le faltó agregar algo o lo que fuera).

Bueno, puedo eliminar el último commit (porque no me gustó) y mis archivos y carpetas van a seguir a como los veo ahora (después cuando esté listo tendré que commitear).

Como se hace?

	git reset --soft HEAD~1

Git **solo elimina el último commit**, pero **no toca tus archivos**.

Todo lo que habías **modificado antes de ejecutar** *git reset --soft* permanece exactamente 
igual en tu carpeta.

Los cambios siguen igual y ya están en "staging" (como si hubieras hecho un "git add ."),
listos para que hagas un commiteo.

Y si hacés cambios en los archivos, recordar....

	git add .

Y después el commiteo.


### **Eliminar el último commit y también borrar todos los cambios que hiciste en ese commit.**


Si el último commit que hiciste no te gustó y tampoco te gustó todo lo que cambiaste en ese commit (archivos nuevos, modificados, eliminados), podés usar un comando que 

- Elimina el último commit
- Tira todos los cambios que hayas hecho en el último commit... para atrás.

El comando es este:

	git reset --hard HEAD~1


Este comando hace tres cosas al mismo tiempo:

1. **Elimina el último commit del historial.**
2. **Revierte los archivos al estado exacto del commit anterior.**
3. **Descarta todos los cambios** que estaban en ese commit (archivos nuevos, modificados o eliminados).

### **Listar Los Commits del Repositorio **

*Lo que vamos a ver va a servir mas tarde para **restaurar un commit específico**.*

Si quiero ver los commits de mi repositorio hago...

	git log --oneline

Esto me permite ver todos los commits del repositorio ordenadamente.
Para cada repositorio voy a poder ver también el código identificador del commit (al inicio.)

Ejemplo:

a3f5c21 agrego login  
b7a91cd primer commit



### **Restaurar un Commit en Particular.... Sin Eliminar todos los Commits que hice después de ese Commit  **

Supongamos que tengo estos commits

- Primer commit (ID: ar33334) 
- ==Primera versión del sitio (ID: blablabla)== 
- Segunda versión del sitio (ID: brrerere)
- Tercera versión del sitio. (ID: rororororo)

Si quiero volver a la "Primera Version" del sitio (sin eliminar los commits que hice después), hago lo siguiente...

	git restore --source=blablabla

Ejemplo:

	git restore --source=blablabla 

Esto hace lo siguiente:

- Toma **todos los archivos como estaban en el commit B**    
- Reemplaza los archivos actuales por esos    
- **NO borra los commits posteriores (C, D, etc.)**    

Tras restaurar un commit, Git notará diferencias con el último commit que habíamos hecho ("Tercera Versión del Sitio" siguiendo el ejemplo). En la práctica, después de restaurar un commit,
hacer uno nuevo. Ejemplo:

	git add .  
	git commit -m "volver a estado del commit B"

### **Restaurar un Commit en Particular.... Eliminando todos los Commits que hice después de ese commit (Danger) **


Supongamos que tengo estos commits:

- Primer commit (ID: ar33334) 
- ==Primera versión del sitio (ID: blablabla)== 
- Segunda versión del sitio (ID: brrerere)
- Tercera versión del sitio. (ID: rororororo)

Si quiero quedarme con la "Primera Version" del sitio y **eliminar los commits que le siguen** 
(no voy a poder restaurar esos commits), hago lo siguiente...

	git reset --hard <commit>

Donde en <commit> va el id del commit.

Siguiendo nuestro ejemplo, si quiero restaurar "blablabla" hago

	git reset --hard blablabla

